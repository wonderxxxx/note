1.11个：各个箱子分别放置的数量为：1,2,4,8,16,32,64,128,256,512,1024,976

2.(64\*1024\*1024)/4=16M

3.B）gnirt，第五行存在语法错误`ReferenceError: length is not defined`，没有定义length变量，应该改为`s.length-1`；修正该问题之后输出为gnirt。s的长度为6，那么p依次进入的是s[5]g,s[4]n,s[3]i,s[2]r,s[1]t；最后的s[0]不会被取到，所以不会输出。

4.C）没有输出，按照当前的变量值`m=0,n=0`，不满足if的条件`n>0`，最外层也没有`else`语句，所以下面的分支语句块将不会被执行。

5.E

6.[31,20,16,14,7,6,8,2,10,1]

7.[1,2,6,10,7,8,16,14,31,20]

8.(n<sup>2</sup>+n)*0.5+1

```javascript
function calc_line_spaces((n) 
{ 
let line = parseInt(n); 
let part = (Math.pow(line,2) + line)/2 +1;
return part;
} 
```

9.2n<sup>2</sup>-n+1

```javascript
function calc_zig_spaces(n)
{
    let line = parseInt(n); 
let part = 2*Math.pow(line,2) - line +1;
return part;
}
```

10.

```javascript
class ArrayQueue {
  constructor() {
    this.array = [];
  }

  insert(item, pos) {
    if (pos < 0 || pos > this.array.length) {
      return false;
    }
    for (let i = this.array.length; i > pos; i--) {
      this.array[i] = this.array[i - 1];
    }
    this.array[pos] = item;
    return true;
  }

  delete(pos) {
    if (pos < 0 || pos >= this.array.length) {
      return null;
    }
    let r = this.array[pos];
    for (let i = pos; i < this.array.length; i++) {
      this.array[i] = this.array[i + 1];
    }
    this.array.length--;
    return r;
  }

  enqueue(item) {
    return this.insert(item, this.array.length);
  }

  dequeue() {
    return this.delete(0);
  }
}
function triangle(n) {
  if (n < 1) {
    return null;
  }
  let out = [];
  out[0] = [1];
  for (let i = 2; i <= n; i++) {
    // 构建第i行的数组
    let lineI = new ArrayQueue();
    lineI.enqueue(i);
    let lineI_1 = out[i - 2];
    for (let j = 0; j < lineI_1.length - 1; j++) {
      lineI.enqueue(lineI_1[j] + lineI_1[j + 1]);
    }
    lineI.enqueue(i);
    out[i - 1] = lineI.array;
  }
  return out;
}
let n = Number(process.argv[2]);
let out = triangle(5);
console.log(out);

```

11.
```javascript
function my_atof(str){
return Math.max(Math.min(parseFloat(str.trim().match(/^[+|-]?\d+/)||0), Math.pow(2,31)-1), -Math.pow(2,31))
}

12.

```javascript
let stackM=[];
let stackS=[];
class Queue{
    constructor() {
	this.data = [];
	this.length = 0;
    }
    enqueue(item) {
        stackM.push(node);
    }

    dequeue() {
        if(stackS.length){
            return stackS.pop();
        }else{
            if(stackM.length){
                for(var i=0;i<stackM.length;i++){
                    stack2.push(stackM.pop());
                }
                return stackS.pop()
            }else{
                 return null
            }
             
        }
    }
    isEmpty() {
        if(stackM.length==0){
            return true;
        }else{
            return(false);
        }
    }
}

let q = new Queue();
for(let i = 1; i < 10; i++) {
    q.enqueue(i);
}

while(!isEmpty(q)) {
    console.log(q.dequeue());
}
```

13.

```javascript
 function createNum(){
    var arr=[];  

    while(arr.length<6){
        var num = Math.floor(Math.random()*33)+1;
        if(-1 == arr.indexOf(num)){
            num = parseInt(num,10);
            arr.push(num);    
        }
    }        
    while(arr.length<7){
        var num = Math.floor(Math.random()*16)+1;
        if(-1 == arr.indexOf(num)){
            num = parseInt(num,10);
            arr.push(num);    
        }
    }    
    console.log(arr);
}

```

