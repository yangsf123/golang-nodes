# Go官方库RPC开发指南 
> `https://studygolang.com/articles/8497`

Go官方提供的RPC库: net/rpc
> 包rpc提供了通过网络访问一个对象的方法的能力，服务器注册对象，通过对象的类型名暴露这个服务。注册后这个对象的输出方法就可以远程调用，这个库封装了底层传输的细节，包括序列化。服务器可以注册多个不同类型的对象，但是注册相同类型的多个对象的时候会报错

`func (t *T) MethodName(argType T1, replyType *T2) error`
- The method's type is exported 方法的类型是可输出的
- The method is exported 方法本身也是可输出的
- The method has two arguments, both exported or builtin types 方法必须由两个参数，必须是输出类型或是内建类型
- The method's second argument is a pointer 方法的第二个参数是指针类型
- The method has return type error 方法返回类型为error

    这里的T、T1、T2能够被encoding/gob序列化，
