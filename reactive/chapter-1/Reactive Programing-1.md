# Reactive Programing-1

## 何为响应式编程

​        **响应式编程是一种面向数据流和变化传播的编程范式，数据更新是相关联的。** 这意味着可以在编程语言中很方便地表达静态或动态的数据流，而相关的计算模型会自动将变化的值通过数据流进行传播。
​	以响应式编程方式进行思考，意味着要放弃命令式且带状态的编程习惯，并且强迫你的大脑以一种不同的方式去工作。
​	响应式编程提高了代码的抽象层级，所以你可以只关注定义了业务逻辑的那些相互依赖的事件，而非纠缠于大量的实现细节。它可以简化项目，特别是处理嵌套回调的异步事件、复杂的列表过滤和变换，或时间相关问题。



## 交互式编程VS响应式编程

​	平时我们使用最多的便是“交互式（Interactive）”的编程方式，采用的是组件之间的相互调用来表现逻辑。例如，对象A向对象B请求数据并等待返回，待对象B完成并返还数据之后A才继续进行后面的操作。
​	响应式编程是一种基于“改变”的编程方式。例如在交互式编程中，A = B + C这样的表达式意味着将B与C之和赋给A，而此后B与C的改变都与A无关。而在响应式编程中，A会去“响应”B或C的变化，即一旦B或C改变之后，A的值也会随之变化。响应式编程的一个典型应用便是GoF23中的观察者模式。



## 响应式系统模型

**Actor模型**

**函数式响应式编程**

**响应式扩展**



## 异步程序处理的思维转变

​	在异步事件处理程序中，常常通过回调函数来处理事件，这是建立在观察者模式的一种处理方式。这种方式有几点问题：

> 1. 回调函数常常带有副作用，会导致回调函数和监听对象共享的变量（可变状态）发生改变
> 2. 难以通过简单的监听对象实现更高的抽象，事件句柄很难进行组合
> 3. 导致了“回调地狱（call-back hell）”，回调函数构成的网络难以理解和追踪

​	为了解决传统情况带来的困境，响应式编程从函数式编程之中借鉴了基本的元素和思想，得到了**可组合的事件抽象（composable event abstractions）** ：

> 1. 事件是一等成员
> 2. 事件常常表现为消息
> 3. 事件处理程序同样是一等的
> 4. 复杂的处理程序(complex handlers)可以由基础的程序组合而成

​	要学习响应式编程，我们首先要理解monad这个函数式设计模式，由于响应式编程并不是纯函数式的，故我们还需要将纯函数式编程和现实世界（包含了可变状态和非确定性计算）结合起来。有了上面两点做基础，我们还要学习使用future对事件进行抽象，使用observable对事件流进行抽象。最后再学习基于消息传递的系统架构——actor模型，以至于构建分布式的actor系统。



