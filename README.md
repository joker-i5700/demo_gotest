# go test命令   
## 1)go test --cover   
执行gotest测试用例，输出总体覆盖率   
$ go test --cover   
PASS   
coverage: 42.9% of statements  
ok      _/C_/Users/xl/My_Documents/gotest       0.361s  

## 2)go test -coverprofile=coverage.out  
生成覆盖率报告原文件，文件名：coverage.out  

# 3)go tool cover -html=coverage.out
在临时文件夹生成html格式报告，并直接使用浏览器打开  

# 4)go test -covermode=count -coverprofile=count.out fmt
通过参数covermode的设定覆盖率统计模式  
set     缺省模式, 只记录语句是否被执行过  
count   记录语句被执行的次数  
atomic  记录语句被执行的次数，并保证在并发执行时的正确性  

# 5)go tool cover -func=count.out  
直接输出函数覆盖率情况  
$ go tool cover -func=count.out  
fmt/format.go:54:       clearflags      100.0%  
fmt/format.go:58:       init            100.0%  
fmt/format.go:64:       writePadding    86.7%  
fmt/format.go:90:       pad             100.0%  
fmt/format.go:108:      padString       100.0%  
fmt/format.go:126:      fmtBoolean      100.0%  
fmt/format.go:135:      fmtUnicode      100.0%  
fmt/format.go:194:      fmtInteger      98.5%  
......  

## 6)go tool cover -html=count.out  
在临时文件夹生成html格式报告，并直接使用浏览器打开  

## 7)go get github.com/t-yuki/gocover-cobertura  
下载用于生成XML格式报告的工具  

## 8)gocover-cobertura < coverage.out > ./coverage.xml  
生成xml格式覆盖率报告用于在JENKINS上展示  