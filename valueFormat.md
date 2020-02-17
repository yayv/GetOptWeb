
本文件描述的格式为 WEB API 接口中，对值的描述方式

格式语法 
```
  "[*|!]<格式名>[数值范围][:长度][#默认值]//说明"
```
示例
```
{
	"姓名":"*string:32//用户的真实姓名",
	"年龄":"*int[0,100]:3#",
	"手机号":"mobile:16//手机号",
	"性别":"string{男,女}//性别可以不填",
}
```

#### 语法解释
[*|!] 
```
选项符 ,或无,表示该参数项是否必须填写, * 为必填, !根据前后文条件确定是否必填, 具体条件需要在具体情境下具体描述, 本格式约定无法给出更多参考
```

格式名
```
基础数据格式包括: int, float, date, time, datetime, string, text
扩展数据格式包括: email, phone, mobile, idcard, plateNumber, text,base64, MD5等
```
数值范围
```
以{[(三个符号中的一个开始，由{开始则必须由}结束, 如{a,b,c}, 表示为枚举类型; [()] 的组合表示为 时间和数字可以用集合形式表示取值范围如 (1,100], 表示 大于1小于等于100的范围.
```

长度
```
   表示为需要检查的变量里原始值的字符串长度
```

默认值
```
   当取值失败，或者取值超范围时，以默认值做为返回值，同时发出一个错误信息
```

说明
```
   参数格式的表达过于技术化，需要有给产品或业务相关人员看得懂的说明，更好的表达这些设置的目的
```

可选格式[格式定义](format)

```
   基础数据格式: int,float,date,time,datetime,string,text 
   扩展格式及其定义:
   email, date, time, datetime 为限定好类型的数据格式
   phone, mobile 为限定好类型的数据格式
   base64, MD5 为限定好类型的数据格式
   gender: "string{男,女}"
```


### Interface Format 
```
    // Format Syntax: "[*|!]<format_name>[data range][:length][#default_value]//COMMENT"
		// data range syntax:
		// 	int float double: (1, 100), (1,100], [1,100),[1,100] 
		//  date time: 
		//  string : enum {papa,mama,grandpa,grandma,grandma-inlaw}
		// example: "role":"*string{papa, mama}:4#papa//role name 
```