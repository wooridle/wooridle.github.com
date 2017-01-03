# Lecture Note

## 1월 3일(화)



### #Self Quiz 

- ### 1조(2조 풀이)

```javascript

function Trapezoid(up, down, height){
 this.up = Math.floor(Math.random() * 6 + 5);
 this.down = Math.floor(Math.random() * 6 + 5);
 this.height = Math.floor(Math.random() * 6 + 5);
}

Trapezoid.prototype.area = function(){
 return ((this.up + this.down) * this.height) / 2;
}

Trapezoid.prototype.toString = function(){ //object의 toString을 override
 return 'up : ' + this.up + 'down : ' + this.down +
   'height  : ' + this.height + 'area : ' + this.area();
}
/////////////////객체 설계 끝////////////////////

function doCalc(){
 return new Promise(function(resolve, reject){
 let arr = [];
 for(var i = 0; i < 5;  i++){
   arr[i] = new Trapezoid();
 }
 resolve(arr);
 });
}

doCalc().then(function(arr){
 arr.sort(function(obj1, obj2){
   return obj1.area - obj2.area;
 })
 return arr;
}).then(function(arr){
 arr.forEach(function(element, index){
   console.log('Index : ' + index + 'Element : ' + element);
 })
})
```



- ### 2조(1조풀이)


```javascript
///우리조 풀이

var arr1 = { 'name' : '이은수',  'age' : 31, 'gender' : '남', 'score' : 74};
var arr2 = { 'name' : '김동진',  'age' : 30, 'gender' : '남', 'score' : 31};
var arr3 = { 'name' : '이의령',  'age' : 28, 'gender' : '남', 'score' : 96};
var arr4 = { 'name' : '장용재',  'age' : 26, 'gender' : '남', 'score' : 99};

var arrAll = [arr1, arr2, arr3, arr4];




function doTask(data, errFn, printFn) {
   try {
        data.sort( function compare(obj1, obj2){
           return obj1.score-obj2.score;
        });
        printFn(data);
   }
   catch (e) {
       errFn(e)
   }
}


doTask( arrAll, 
   (err) => {
   console.log( 'unexpected error!' );
   },
     
   (arrAll) => {
   for(let i =0; i<arrAll.length; i++) {
       for (let prop in arrAll[i]){
           console.log( prop + " : " + arrAll[i][prop] );
       }
     console.log("-----------------------------");
   }
});

/////////////////////////////////////////////////////////////////
//####1조 풀이#####

/*
1. 객체생성
2. 생선된 객체를 받아, 배열에 저장
3. 각 배열에 저장된 property 중 성적순으로
4. 정렬
5. 출력
*/


function Group(n,a,g){
  this.name =n;
  this.age = a;
  this.grade = g;
}

Group.prototype.toString = function(){
  return ' name' + this.name : ' age:' + this.age + ' grade : ' : +this.grade;
}

function doTask(callback, done){
    let stdArr = [];
    std[0] = new Group('이은수' , 31, 74);
    std[1] = new Group('김동진', 30, 31);
    std[2] = new Group('이의령', 28, 95);
    std[3] = new Group('장용재', 26, 99);

    callback(stdArr, done);
}

function doSort(data, callback){
  data.sort(function(obj1,obj2){
    return obj2.grade - obj1.grade;
  });
  callback(data);
}


function doPrint(data){
  data.forEach(function(element, index){
    console.log(index + ":" + element);
  })
}

doTask(doSort, doPrint);

```

- ### 3조(6조풀이)

```javascript
/*
  1-100 임이의 홀수 10개 배열저장
  배열정렬
  배열안의 총합더해서 출력(promise)
  */

function doTask(){
  var arr = [];
  for(let i = 0; i < 10; i++){
    arr[i] = (Math.floor(Math.random()*50)) *2+1;
  }
  return new Promise(function(resolve, reject){
    arr.sort((elem1, elem2) => {
      return elem1 - elem2;
    });
    resolve(arr);
  })
}

doTask().then(function(arr) {
  console.log(arr);
  let sum = 0;
  for (let i = 0; i < arr.length; i++) {
    sum += arr[i];
  }
  return sum;
}).then(function(sum){
  console.log('결과 : ' + sum);
});
```

- ### 4조(5조풀이)

```javascript
var 
```

  ​

  ​
