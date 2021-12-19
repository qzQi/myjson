# myjson
* json是什么
* 序列化与反序列化又是什么


## 关于json的基础知识
json是轻量级的数据交换格式，由于他的易于编写、阅读、解析很快流行。  


* json与序列化  
简单来说，序列化：对象--字符串；反序列化：字符串--对象。


## 开发准备
准备设计一个类似于nodejs里面的使用，先来体验一把js里面的设计。
```js
let test={
    "lover":null
};
// 动态加入的特性
test.name="qizhiyun";
let family={
    "mother":"li",
    "father":"qi",
    "sister":"lin lin"
}
test.family=family;

let str=JSON.stringify(test);

let obj=JSON.parse(str);
```

## json简介：   
不提供注释的句法，一个有效的JSON文档的根节点必须是一个对象或一个数组。
[json_document](http://www.json.org/json-zh.html);   

**基本数据类型：**  
* 数值；
* 字符串：
* boolean：
* 数组：
* 对象：  
   若干无序的“键-值对”(key-value pairs)，其中键只能是字符串。建议但不强制要求对象中的键是独一无二的。对象以花括号{开始，并以}结束。键-值对之间使用逗号分隔。键与值之间用冒号:分割。
* 空值：

json可以为以上几种类型中的任意类型，但是在网络传输、数据交换的时候有一些限制。

JSON在网络交换中编码为UTF-8格式的文档，一个json*数组或对象*可以作为一个独立的json文档。虽然我们可以把任意json类型转化为文档，一个有效的JSON文档的根节点必须是一个对象或一个数组。
## 分析与设计  
阅读JSON文档，明确JSON的格式


一个json数组与对象可以作为一个独立的json文档，所以对json的解析就是对json对象、数组的解析。对象是我们最常用的传输格式。  



json对象与数组可以含有任意json数据类型，也就是json数据结构是一个树状的数据结构。

计划实现的主要接口：
```c++
JSON::parse();
// 把json文档解析为内部的数据结构
JSON::Stringfy();
// 把json数据结构序列化（格式化输出）为json文档
```

**选择数据结构：**  





## 鸣谢
`json for modern C++`  
`json-tutorials`  
