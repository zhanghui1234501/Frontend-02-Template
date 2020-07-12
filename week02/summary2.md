学习总结

一、JS语言通识
    1.泛用语言分类方法
      语言按语法分类
          非形式语言 ：语法没有严格的定义
                      例子：中文、英文
          形式语言 ：非常的严谨严格(乔姆斯基谱系)
              形式语言的分类 ：
                        1.0型 无限制文法
                        2.1型 上下文相关文法
                        3.2型 上下文无关文法
                        4.3型 正则文法(所有被正则表达式表达的文法)
              这四种文法是上下包含的关系
    2.什么是产生式  BNF详细了解
      产生式(BNF：最常用的描述方法-巴斯科-诺尔范式)----贯穿整个前端课程
        1.用尖括号括起来的名称来标识语法结构名
        2.语法结构分成基础结构和需要用其他语法结构定义的复合结构
          基础结构称终结符
          复合结构称非终结符 
        3.引号和中间的字符标识终结符  --用字符串来表示终结符
        4.可以有括号  ：用括号括起来表示一组。
        5.*表示重复多次
        6.|表示或
        7.+表示至少一次
        不同文档中有不同的表达方式。
    BNF的定义是可以递归的。
    用产生式(BNF)描述四则运算：
       乘法运算 ： 
           <MultiplicativeExpression>::=<Number>|
                                         <MultiplicativeExpression>"*"<Number>|
                                         <MultiplicativeExpression>"/"<Number>|
        加法运算：
           <AddtiveExpression>::=<MultiplicativeExpression> |
                                 <AddtiveExpression> "+"<MultiplicativeExpression>|
                                 <AddtiveExpression>"-"<MultiplicativeExpression>
        
        终结符： Number + - * /
        非终结符：MultiplicativeExpression，AddtiveExpression
    3.深入理解产生式
      通过产生式理解乔姆斯基谱系
            0型  无限制文法
                 ?::=?  左右两侧可以有多个非终结符
            1型  ?<A>?::=?<b>?
            2型  <A>::=? 左边只能有一个非终结符
            3型  <A>::=<A>?如果是递归定义的，不允许定义A出现在尾巴上
      JavaScript整体上属于上下文无关文法。其中的表达式部分大部分属于正则文法。
    4. 现代语言的分类
       除了按照文法进行分类，其他的分类方式
       按照用途进行分类：
            数据表述语言：存储纯粹的数据---本身没有办法进行编程
                         HTML，CSS，XAML，SQL，JSON
            编程语言： C，C++，C#，java，Python，Ruby，Perl，
                      VB, PHP, JSP,go语言
                      Lisp，T-SQL，Clojure，Haskell，JavaScript
        按照表达方式进行分类
            1.声明式语言：告诉结果是什么
                HTML，CSS，XAML，SQL，JSON
                Lisp，Clojure，Haskell
            2.命令时语言：告诉达成这个结果的步骤是怎么样。
                C，C++，C#，java，Python，Ruby，Perl，
                JavaScript
       
    5.编程语言的性质
       1.图灵完备性 --这是所有的编程语言都具备的一个条件
            命令式---图灵机 
                用goto或者if/while实现图灵完备性
            声明式----lambda演算
                通过递归来实现图灵完备。
        2.动态和静态
            动态：一定实在用户的设备/在线服务器上进行运行的。
                  运行的时机实在产品实际运行时/runtime
            静态：在程序员的设备上
                  产品开发时/Compiletime
        3：类型系统
           分为静态类型系统和动态类型系统
           弱类型 Stirng + Number 会默认的将Number类型转化为String类型
           强类型 String == Boolean  先把Boolean转换成Numbe类型进行比较
           复合类型 ： 结构体和函数签名
           子类型
           泛型
    6.一般命令式编程语言的设计方式
       原子级---变量名/直接量
       表达式 --可以级联的结构
       语句-----已经具有图灵完备
       结构体      
二、JS类型
    1.Number
    2.String
    3.Boolean : true ;flse
    4.Object 对象
    5.Null :是一个关键字，不能被赋值
    6.Undefined : 不是关键字，是一个全局的变量
    7.Symbol

    javaScript中的对象
    两个要素：
       属性：属性的解和 property  描述状态和行为
       原型 prototype。----原型链。获取属性的行为沿着原型的指向一直找上去。

    javaScript中的属性是一个kv对。---根据k找到v
      K :string
         symbol  
           只能通过变量去引用他。---属性访问的权限控制。

      v:两种形态 ： 数据属性。任意类型的值 attribute
                访问器属性

    特殊的对象：
        Function对象，Array对象(数组对象)等。---具有特殊的行为