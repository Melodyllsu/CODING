- 为什么要引入内联函数呢？  
用于替代C语言中表达式形式的宏定义来解决程序中的函数调用效率问题。
- 内联函数的使用场合  
1. 使用inline可以完全替代表达式形式的宏定义。  
2. 在C++类中使用最广的应该是用来定义存取函数。访问类的私有或者保护成员，这样会有比较好的效率。 
- 为什么不把所有的函数都定义成内联函数。  
内联函数是以代码膨胀为代价的，仅仅省去了函数调用的开销，从而提高函数的执行效率，如果执行函数代码时间相比于函数调用开销较大，
那么效率的收获就会很少，反而消耗了内存空间。以下为不适合使用内联的情况：  
1. 如果函数体内代码较长，使用内联将导致内存消耗代价较高。
2. 函数体内出现循环，那么执行函数体内代码的时间要比函数调用的开销大。
3. 不要随意将构造函数和析构函数的定义体放在类声明中。一个好的编译器会根据函数的定义，自动取消不值得的内联（这说明了inline不应该出现在函数的声明中）
- 内联函数与宏的区别  
1. 内联函数在编译时展开，宏在预编译时展开。
2. 在编译时，内联函数可以直接镶嵌到目标代码中，而宏只是一个简单的文本替换。
3. 内联函数可以完成诸如类型检测、语句是否正确等编译的功能，宏只是文本替换。 
4. 宏不是函数，inline函数是函数。
5. 内联函数定义时不会出现二义性。 

  
