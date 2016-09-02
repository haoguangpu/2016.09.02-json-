# 2016.09.02-json-
个人收集整理的一些json数据处理资料
#### json结构：对象和数组
        JSON(JavaScript Object Notation) 是一种轻量级的数据交换格式，采用完全独立于语言的文本格式，是理想的数据交换格式。
    同时，JSON是 JavaScript 原生格式，这意味着在 JavaScript 中处理 JSON数据不须要任何特殊的 API 或工具包。
        一个对象以“{”（左括号）开始，“}”（右括号）结束。每个“名称”后跟一个“:”（冒号）；“‘名称/值’ 对”之间运用 “,”（逗号）
    分隔.名称用引号括起来；值如果是字符串则必须用括号，数值型则不须要。
    
            例如： var jsonObj={"name":"HGP","age":18,"height":"183cm","dataTime":"2016-09-02"}；   
            
       数组是值（value）的有序集合。一个数组以“[”（左中括号）开始，“]”（右中括号）结束。值之间运用 “,”（逗号）分隔。
        
            例如： var jsonArr=[{"name":"HGP","age":18},{"height":"183cm","dataTime":"2016-09-02"}];
            
#### json传输转换：

        在数据传输流程中，json是以文本，即字符串的形式传递的，而JS操作的是JSON对象，所以，JSON对象和JSON字符串之间的相
    互转换是关键。
    
    JSON字符串:

    var jsonStr = '{ "name": "HGP", "sex": "man" }';

    JSON对象:

    var jsonObj = { "name": "HGP", "sex": "man" };
    
    var jsonArr=[{"name":"HGP","age":18},{"height":"183cm","dataTime":"2016-09-02"}];
    
    一、JSON字符串转换为JSON对象

    要运用上面的jsonStr，必须要将json字符串转化为JSON对象：

    var jsonObj = eval('(' + jsonStr + ')');//由JSON字符串转换为JSON对象
    
    var jsonObj = strjsonStr.parseJSON(); //由JSON字符串转换为JSON对象
   
    var jsonObj = JSON.parse(jsonStr); //由JSON字符串转换为JSON对象
    
    二、JSON对象转换为JSON字符串
    
    JQ： $.parseJSON( jsonStr ); //jQuery.parseJSON(jsonStr),可以将json字符串转换成json对象
    
    BOM：JSON.stringify(jsonObj); //可以将json对象转换成json对符串 
    
    js： obj.toJSONString(); //将JSON对象转化为JSON字符
    
#### json对象的读取：
        
    Alert(obj.name);//输出 HGP

    Alert(obj.sex);// 输出 man
    
    Alert(jsonArr[0].name);// 输出 HGP

    特别留心：如果obj本来就是一个JSON对象，那么运用eval（）函数转换后（哪怕是多次转换）还是JSON对象，但是运用       
   
    parseJSON（）函数处理后会有疑问（抛出语法异常）。
    
#### json对象的修改：
        
    var jsonArr=[{"name":"HGP","age":18},{"height":"183cm","dataTime":"2016-09-02"}];
    
    jsonArr[0].name = "郝光谱";
        
    Alert(jsonArr[0].name);// 输出 郝光谱
    
#### 参考资料：

 [json在线校验工具](http://www.bejson.com/ "点击前往json在线校验")
 
 [XML与JSON数据转换](http://tools.jb51.net/code/xmljson "点击前往json在线校验")
 
 [json优化/压缩/转换](http://tools.jb51.net/code/jsoncodeformat "点击前往json在线校验")
