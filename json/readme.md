encoding/json 默认会对 html 标记 <, >, & 做转换, 但是狗日的腾讯不识别,  
所以只能 hack 标准的 json 库, 去掉这三个字符的转换(从 go1.5 encoding/json fork 而来).  

修改的文件有:

encode.go:  
注释掉 789-792行, 增加 793-796 行  
注释掉 869-872行, 增加 873-876 行  

indent.go:  
注释掉 21-29 行  