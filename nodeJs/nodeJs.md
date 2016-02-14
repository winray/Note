###node.js
###概念
- 回调
- 同步/异步
- I/O
- 单线程/多线程
- 阻塞/非阻塞
- 事件
- 事件驱动
- 基于事件驱动的回调
- 事件循环
- 作用域
- 上下文(call函数, this指针)


######回调：     
回调函数就是一个通过函数指针调用的函数。如果你把函数的指针（地址）作为参数传递给另一个函数，当这个指针被用来调用其所指向的函数时，我们就说这是回调函数。回调函数不是由该函数的实现方直接调用，而是在特定的事件或条件发生时由另外的一方调用的，用于对该事件或条件进行响应。 
类A调用类B的方法b（传入相关信息），类B的方法在执行完后，会将结果写到（再回调）类A的方法a，完成动作。（其实方法a就是传说中的回调方法啦）
```javascript
function back(something) {
	console.log("Call back is " + something + " !");
}
function call(back, something) {
	return back(something);
}
call(back, "function");
```

