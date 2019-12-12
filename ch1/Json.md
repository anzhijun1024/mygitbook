# 3.JSON数据

## JSON 简介
    JSON（JavaScript Object Notation，即 JavaScript 对象表示法）是一种轻量级的数据交换格式。
    目前大多数接口返回的数据格式为 JSON,因此进行接口测试必须掌握 JSON。
    
### JSON 语法

    语法规则
        •  数据在键/值对中
        •  数据由逗号分隔
        •  {花括号}保存对象
        •  [方括号]保存数组
        
### JSON 键/值对：
        JSON 数据的书写格式是： key:value 键值对。比如："Name" : "51zxw"
        JSON 值可以是：
            •  数字（整数或浮点数）        "status_code":200
            •  字符串（在双引号中）        "Name" : "51zxw"
            •  逻辑值（true 或 false）    "result":true
            •  数组（在方括号中）          "user":["51zxw","zxw2018","zxw666"]
            •  对象（在花括号中）
            •  null
            
        JSON 对象
            JSON 对象在花括号中书写： 对象可以包含多个键/值对：
            { "firstName":"John" , "lastName":"Doe" }
            Tips:在接口测试过程中，一般都是返回 JSON 对象类型。
            
        JSON 数据嵌套
            比如在数组中含多个对象：
            {
            "employees": [
            { "firstName":"John" , "lastName":"Doe" },
            { "firstName":"Anna" , "lastName":"Smith" },
            { "firstName":"Peter" , "lastName":"Jones" }
            ]
            }
            在上面的例子中，对象 "employees" 是包含三个对象的数组。每个对象代表一条关于某人（有姓和名）的记录。
            
### JSON 数据解析
    Python3 中可以使用 json 模块来对 JSON 数据进行编解码，它包含了两个方法：
        •  json.dumps(): 将 python 数据转化为 Json 数据
        •  json.loads(): 将 json 数据类型转为 Python 数据类型
JSON 库官方文档 https://docs.python.org/3/library/json.html   


    json.dumps()
    将 python 数据转化为 Json 数据 json_dumps.py
            
            