# first-go-program
just some simple go program for fun

延迟调用defer的最大优势是，即便函数执行出错，依然能保证回收资源等操作得以执行
go tool objdump -s "main\.main" test
编译器将defer处理成两个函数调用，deferproc 定义一个延迟调用对象，然后在函数结束前通过deferreturn完成最终调用
参数被复制到了defer对象后面的内存空间
在某些性能要求高的场合，应该避免使用defer
