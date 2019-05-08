<div class="text-center">
	<img src="https://codeabbey.github.io/data/min_of_two.gif" alt="Choosing minimum animation"/>
</div>

很多程序应该能够做一些选择和决断。我们将要练习包含条件的程序。    
它通常通过`if...else`语句来完成，就像下面这样:   

    IF some_condition THEN
	    do_something
	ELSE
	    do_other_thing
	ENDIF

不同的程序设计语言语法会有一些不同，并且`else`部分几乎总是可选的。你可以读维基百科上的文章
[Conditional statements][cond]来获取更多内容。     

[cond]: http://en.wikipedia.org/wiki/Conditional_(computer_programming)

请从两个数中选择一个最小的值。会有几对数值用于测试。   

**输入数据** 将会在第一行包含测试用例的个数。     
接下来的每一行都会包含一对数值用于比较     
对于**答案**，请输入相同数量的最小值，并用空格分隔。例如：    

    数据：
    3
    5 3
    2 8
    100 15
    
    答案：
    3 2 15
