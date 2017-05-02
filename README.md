# Learning website

https://www.zhihu.com/question/22146521/answer/94842197     master

https://dwqs.gitbooks.io/frontenddevhandbook/content/practice/front-end-skills.html



map() 个人理解 相当于循环将数组的每个元素进行处理

      例：var arr=[1,2,3,4,5];

          function fun(){

          return x*2;

          }

          arr.map(fun);   //会得到 [2,4,6,8,10]  

          arr.map(string);//会得到 ["1","2","3","4","5"]

          map接受一个参数   对自身做处理   上面的例子将 数组的每个元素进行fun方法处理*2

reduce() 数组的reduce方法 将函数作用在数组上 ，函数会有两个参数

          reduce()把结果继续和序列的下一个元素做累积计算

           [x1, x2, x3, x4].reduce(f) = f(f(f(x1, x2), x3), x4)

        例：var arr=[1,2,3,4,5]

            arr.reduce(function(x,y){

              return x+y   
              
            })      //返回了数组的和
            
           
