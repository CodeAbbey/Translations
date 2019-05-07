<!-- #Fahrenheit to Celsius -->
这个编程练习与在循环中计算总和大致相同，但是这个需要稍微多一点的计算。       

<div class="text-center">
	<img alt="fahrenheit and celsius" src="https://codeabbey.github.io/data/fahrenheit_celsius.png"/>
</div>

*注意：在[Rounding](./rounding--zh)问题中解释的约数算法会在这个任务中被用到。*   

有两个被广泛使用的测量温度的系统 —— 摄氏度和华氏度。第一个在欧洲相当流行，第二个使用也很广泛，例如在美国。  

使用摄氏温度计测量水的冰点温度为0度，沸腾温度为100度。使用华氏温度计测量水的冰点温度为32度，沸腾温度为212度。你
可以从[wikipedia on Fahrenheit][wiki]来了解更多。使用这两个点来转换两种温度。   

[wiki]: http://en.wikipedia.org/wiki/Fahrenheit

你将要编写程序来将华氏度转换为摄氏度。   

**输入数据** 包含`N+1`个值，第一个是N自己（**注意**你不应该转换它）。    
**答案** 应该包含确切的`N`个结果，约到最近的整数，并使用空格分隔。  

示例：

    数据：
    5 495 353 168 -39 22
    答案：
    257 178 76 -39 -6

*请注意，第一个`5`不是温度，而是要转换的值的个数！*    
