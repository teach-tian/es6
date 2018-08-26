```
1.let和var的区别：let声明的变量只有所在的代码块有效。
 if(true){
        var fruit="apple" //let fruit="apple"
    }
    console.log(fruit)
2.const声明一个常量（恒量）。一旦声明，常量的值就不能改变。const一旦声明变量，就必须立即初始化，不能留到以后赋值。
    const arr=[];
    arr.push("apple");
    arr.push("banana");
    arr=[]
    console.log(arr);
3.解构赋值
  3.1>“模式匹配”为变量赋值
    function breakfast() {
        return ['dessert','drink','fruit'];
    }
    var list=breakfast();
    a=list[0],b=list[1],c=list[2];
    console.log(a,b,c);
    let [a,b,c]=breakfast();
    console.log(a,b,c)
    3.2>不完全解构，即等号左边的模式，只匹配一部分的等号右边的数组。
    let [a, [b], d] = [1, [2, 3], 4];
     a // 1
     b // 2
     d // 4
4.使用解构语法 我们可以解构对象
   function breakfast() {
        return {dessert:"蛋糕",drink:"饮料",fruit:"水果"}
    }
    let {dessert:a,drink:b,fruit:c}=breakfast();
    console.log(a,b,c)
5.使用字符模板

    let fruit="水果",dessert="蛋糕";
    let breakfast="今天的早餐是"+fruit+"和"+dessert+"!";
    console.log(breakfast)
    let breakfast=`今天的早餐是${fruit}和${dessert}!`
    console.log(breakfast)
    //使用字符模板，很容易把一行显示成多行
    let breakfast=`今天的早餐是
    ${fruit}和${dessert}!`;
    console.log(breakfast);
6.带标签的模板字符串
         let dessert="蛋糕",
         drink="饮料";
     let breakfast=kitchen`今天的早餐是\n${dessert}与${drink}!`

    function kitchen(strings,...value) { //标签函数  
        //strings指的是字符， value指的是变量
        //strings参数里还有raw，就是原始的没有处理过的字符  
        console.log(strings,value)
    }
    如果想控制台正常输出模板字符串里的东西
     function kitchen(strings,...value) {
          let result='';
          for (var i=0;i<value.length;i++){
              result+=strings[i];
              result+=value[i];
          }
          result+=strings[strings.length-1];
        return result;
    }
    console.log(breakfast)
7.默认参数
     function breakfast(dessert="蛋糕",drink="饮料") {
      return `今天的早餐是${dessert}和${drink}！`

  }
  console.log(breakfast())
  console.log(breakfast("包子","啤酒"))
8.判断字符串里是否包含其他字符
    let dessert="蛋糕",
       drink="饮料";
  let breakfast= `今天的早餐是${dessert}和${drink}！`
  console.log(breakfast.startsWith("今天"))
    console.log(breakfast.endsWith("！"))
9.展开操作符 ...value
      let arr=["dessert",'fruit'],
        foods=["orange",...arr];

    console.log(arr);//["dessert",'fruit']
    console.log(...arr);//dessert fruit
    console.log(foods);//["orange", "dessert", "fruit"]
10.剩余操作符（一般用在函数的参数里面）

  function breakfast(drink,dessert,...foods) {
        console.log(drink,dessert,foods)
    }
    breakfast('weather','ico','apple','banana');//weather ico ["apple", "banana"]

11.解构参数

     function breakfast(dessert,drink,{location,restaurant}={}) {
         console.log(dessert,drink,location,restaurant);
     }
     breakfast("ico",'pear',{location:'南锣鼓巷',restaurant:"董小姐"});//ico pear 南锣鼓巷 董小姐
12函数的name属性

     let breakfast=function repeatBreakfast() {

     }
     console.log(breakfast.name)；repeatBreakfast
13.箭头函数  arrow function

      let breakfast=function(food) {
        return food;
       }
   // 参数=>返回的值  
   let breakfast=foot=>food;
    let breakfst= () => {console.log("123")};//函数没有参数的话，我们需要一个空白的括号
14.对象表达式
      let dessert="ico",
        drink="pear";
    let food={dessert, drink,chef(){}}
    console.log(food);//{dessert: "ico", drink: "pear"}
15.class
      class chef {
        constructor(food){  //这个类创建实例时 会自动执行
            this.food=food;
        }
        cook(){
            console.log(this.food);
        }
    }
    let xiaopang=new chef("water");
     xiaopang.cook();
16.在类里面我们可以设置一些 get()或set()

17.set 就是一堆东西的集合  就像数组 不过和数组不同的是set里面不能有重复的东西

  
    let foods=new Set("pear");
    foods.add("o");
    foods.add("o")
    console.log(foods);
    console.log(foods.size);
    console.log(foods.has("e"));
    foods.delete("r")
    console.log(foods);
    foods.forEach(food=>{console.log(food)});
    foods.clear();//清空Set的方法
简单来说，Set于Array的区别在于：Array中允许出现重复的元素，例如[1,2,2,3]；而Set中的所有元素都是唯一的，只能是{1,2,3}。利用这一特性，我们就可以迅速地去掉数组中重复的元素
应用：
var arr = [1,2,2,3,4] // 需要去重的数组

var set = new Set(arr) // {1,2,3,4}
var newArr = Array.from(set) // 再把set转变成array

console.log(newArr) // [1,2,3,4]

18.Map 数据类型
      let foods=new Map();
    let food={},drink=function () {},dessert='甜点';
    foods.set(food,'breakfast');
    foods.set(drink,'milk');
    foods.set(dessert,'cook')

    console.log(foods);
    console.log(foods.size);
    console.log(foods.get(drink));
    foods.delete(dessert);
    console.log(foods.has(dessert))

    foods.forEach((val,key)=>{console.log(`${key}=${val}`)})

    foods.clear()
    console.log(foods)
19.导出 导入
   export {fruit,dessert}
   import {fruit,dessert} from './module/vue'
   import * as food from '.module/vue'

```
https://www.cnblogs.com/benpaodexiaopangzi/p/6085519.html







   
