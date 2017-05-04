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
            
filter() 用于将array的某些元素过滤掉 filter()接收一个函数 将传入的函数一次作用于每个人元素，返回true或false

        例：var arr=[1,2,3,4,5];

            arr.filter(function(x){
      
            return x % 2 != 0   //返回奇数

              })

        例：数组去重

            var arr=['a','b','c','c',1,2,4,1,3,3,'a'];

            arr.filter(function(element,index,self){
            
            //indexOf()  元素在数组中首次出现的位置

            return (self.indexOf(element)===index);

            })

sort() 排序 但是不会很容易排到你要的结果 ，不过sort是高阶函数
它还可以接收一个比较函数来实现自定义的排序。
    
        例：var arr=[1,3,23,3]

            arr.sort(function(x,y){

              if(x<y){

                return -1;

              }

              if(x>y){

                return 1;

              }

              return 0;

              })

闭包   高阶函数可以返回值将其运算 ，但是当不想让其运算，返回一个方法，
当调用时再进行处理，可以运用多次，一个函数返回一个函数，内部的局部变量
还能被新的函数引用（闭包运用还是比较困难，具体的理解也不是很深刻）

            例：

            function count() {
                var arr = [];
                for (var i=1; i<=3; i++) {
                    arr.push((function (n) {
                        return function () {
                            return n * n;
                        }
                    })(i));
                }
                return arr;
            }

            var results = count();
            var f1 = results[0];
            var f2 = results[1];
            var f3 = results[2];

            f1(); // 1
            f2(); // 4
            f3(); // 9

            (function (x) {
                return x * x;
            })(3); // 9

箭头函数 x=>x*x  等价于function(x){return x*x}    （确实省事很多）
对于this的指向问题也做了修改 作用域绑定了

            简化了写法   多个参数 或者表达式过多依旧要加括号

            (x, y, ...rest)=>{

              if(){
                .......
              }
            }

            this指向

            var run={
              name:'run'
              get:function(){
                this.name;//指向run
                var a=function(){
                  this.name;//指向window或者undefined
                }
                var b=()=>this.name;//指向run
              }

            }

generator（生成器）是ES6标准引入的新的数据类型。一个generator看上去像一个函数，但可以返回多次。






