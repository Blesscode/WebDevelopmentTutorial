# JavaScript

# 1 Basic

- word vs keyword
- var const let
- the difference
- window object
- browser context api
- stack
- heap memory
- execution context
- lexical environment
- hoisting
- Difference between undefined and not-defined
- types in js
- how to copy reference values >>ARRAY & OBJ
- conditionals
- truthly vs falsy
- switch \*
- loop => for while foreach forin do-while
- functions
- callback fncs
- first class fns => fn can used as value eg. var a= function(){};
- parms and arg => arg= real values jo hum dete hain fn chlate time parms= var jinse value store hoti hai arg vali
- arrays => eek se Zada bande ki baat var arr=[1,2,3,4];
- push pop shift unshift splice => arr.push(8) arr.pop() arr.unshift(0):add data to the front of arr arr.shift(0):htata hai 1 value saamne se arr.splice(2,1):2nd index se kitni value htani hai
- how array are made behind the scenes
- why we can make -ve indexes array in js \*
- objects => eek bnde ke baare me saari baat
- props vs methods \*
- updating object props \*
- how to delete obj prop

# 2 FUNCTIONS IN JS

- higher order fn
- constructor fn
- first class fns
- new keywords
- iife =>immediately invoked fn expression
  =>fn ko turant chlane ki kala,is treeke se ki hum log koi private
- prototype
- prototypal inheritance
- this call apply bind
- pure &impure fns
- closures

# 3 Asynchronous Js

- sync and async kya hota hai
- kaise pta chlega ki hm ksisi code ko sync melikhe ya async me
  - setTimeout
- async js hai kya
- js is not asynchronous
- full story of async
- single threading and multi threading
- callbacks
- promises
- then and catch
- try and catch
- async await
- 5 use cases of real world
- concept aside
- concurrency and parallelism
- throttling

# 4 DOM

- Pillar of dom
  ### Selecting html elem
  ### changing html
  ### changing css
  ### event listner

---

## The Difference

-` ES5``>>old ` : only has var -` ES6``>>new ` : has only let and const
->we use both ES5&ES6 : var & let & const

+------+----------------------------------------------------------------------+
| var | function scope hota hai{apne parent fn me khai bhi use ho skta hai |
+------+----------------------------------------------------------------------+
+----------------------------------------------------------------------+
| Add itself to the window object |
+----------------------------------------------------------------------+
+------------+----------------------------------------------------------------+
| let&const | braces scope{sirf braces ke andr ke scope me use hoga |
+------------+----------------------------------------------------------------+
+----------------------------------------------------------------------+
| Don't add itself to the window object |
+----------------------------------------------------------------------+

eg. function abcd(){
for(var i=0;i<12;i++);{
console,log(i); //1 to 11
}
console.log(i); //12 **\*\*\***
}
abcd();

> > output
> > var:
> > 1 to 11 for loop
> > 12 \***\*parent fn me khai bhi use hoskta hai var and vha parent fn hai var ka abcd toh abcd ke and khai bhi use krlo i ko\*\***

Let:
1-11
error

## The window object

- window is an object
- acess->browser me jake ctrl+shift+j->window likho console me->aagya window obj
- js language me aisi bhut se features hote hain jo usme available nhi hote par hm tabhi unhe use krte hain par kaise? : toh js language jata hai window ke pass ise as a box maano jisme bhut saare features hain toh js language window box ke pass jata hai and vo feature le aata hai jo uske pass nhi hai ya js lang ka part nhi hain and unhe use krta hai
- window browser ka part hai ye features browser deta hai window ko
- eg alert,console,promt,document

APPLICATION
-> var a=12;
let b=15;

> > console me jao->window likho->

              a:12 add hogya hoga window obj me par let vala nhi hua hoga => kyuki var khudko window me add kr deta hai =>THIS IS NOT GOOD since ye aapke data ko window me expose kr deta hai

## Browser Context API

- Vo cheezen jo browser deta hai

        +-------------------+

  |Browser context API|
  +-------------------+


    /           |             \

      /             |               \

+------+ +-------------+ +-------+
|window| | stack | | heap |
+------+ +-------------+ +-------+

## Stack

- fn me use hota hai

## Heap Memory

- aap jitney bhi variable ya data ya intermediate data bnate hain unhe khai toh store krna pdega
- uske liye heap memory hai

- EG. 1+2+3+4 ko hme solve krna hai toh computer eeksath toh kr nhi dega vo phele 2 ko krega then usme aage ka data add krega

1+2= 3 yhape ye jo 3 aaya hai ise intermidate data khenge and ye hme khai store krna pdega
/+ tabhi toh addition hoga and isko store hm krenge heap mem me  
 3 = 6
/+  
 4 = 10 final ans

## Execution context

- jab hm function `chlate` hain tab function apna khudka imaginary container bna leta hai jisme uski teen cheezen hogi:

  - 1.  variables -> jo tum us fn ke andr bnaoge
  - 2.  functions -> aur nye fns jo tum us fn ke andr bnaoge
  - 3.  lexical Environment of that fn-> aage padhoge

- ye jo container hai imagrinary hai and ise hi hm execution context khte hain

- EG.
  function abcd(){
  var a=12;
  function fn2(){
  var b=15;
  }
  }

> > abcd ->img container
> > +-----------------------+
> > | var fns |
> > | |
> > | |
> > | lexical env |
> > +-----------------------+

## Lexical Environment

- eek chart jisme likha hota hai ke aapke particular function kis cheezon ko access kr ksta hai and kisko nhi
- mtlb holds : scope & scope chain

## Hoisting

- var and fn are hoisted that means their declaration is moved on the top of code
- var ko bnane se phele usko use kr kste hain

- eg. console.log(a);
  var a=12;

       output:  behind the scenes

  +--------------------------------------------------+
  |var a; ****\*****declaration top pe phuch gya |  
  |console.log(a); |
  |a=12; |
  +--------------------------------------------------+

## Difference between undefined and not-defined

+-----------+---------------------------------------------------------+
| undefine | existence hai var ki par pta nhi hai ki value kya hai |
+-----------+---------------------------------------------------------+

+---------------+------------------------------------------------------------------------------+
| not-undefine | jis cheez(var) ka existence hi nhi hai ki par pta nhi hai ki value kya hai |
+---------------+------------------------------------------------------------------------------+

## types in js

- refrence: aisi koi bhi cheez jisko copy krne par real copy nhi hota hai ,balki main value ka ref pass hojata hai

- premitive: aur jise copy krne par real copy ho jaye vo

               +---------+
        	     | 2 types |
               +---------+

      /                 \
        /                     \

  +---------+ +-------------+  
   |Primitive| | reference |  
   +---------+ +-------------+  
   | |
  | |
  +-------------+ +---------------+
  | num | | [] |
  | string | | {} |
  | Boolean | | () |
  +-------------+ +---------------+

                                     |
                                     tum agar is type ki seedha copy nhi bna skte
      				eg. var a=[1,2,3,4] **** a ke pass hai khud ka 1234
      				    var b=a;        **** b ke pass hai a ka 1234 *reference

## how to copy reference values >>bina ref vali copy

### ARRAY

- Use `spread operator` i.e. `...`
- EG. var a=[1,2,3,4,5,6,7]; var b=[...a];

### Object

- EG. var obj={name:"isha"}; var b={...a};

## conditionals

- if else
- else-if

## truthly vs falsy

- js mein kuchbi likho vo main 2 type mese kisi eeko belong kregi

+---------------------------------------------------+
|FALSEY : 0 false undefined null NaN document.all |
+---------------------------------------------------+

eg. if(7){ 7!=0 therefore truthy
console.log("hey");
}
else{
console.log("hellow");
}

if(-1){ -1!=0 therefore truthy
console.log("hey");
}
else{
console.log("hellow");
}

if(NaN){ NaN=falsey therefore false
console.log("hey");
}
else{
console.log("hellow");
}

## Loop

### foreach >>ARRAY

+---------------------------------+
| foreach sirf array pe chlta hai |---------------------------------------------------------
| for each array ki org vale ko change nhi krta vo vs img copy me changes krke de deta hai |
| for each anonmus fun ko accept krta hai --------------------------------------------------
|---------------------------------|
| var a=[]; |
|a.forEach(function(val_of_a){ |
| console.log(val+2); |
| }) |
+---------------------------------+

### forin >>Object

var obj_ka_naam={
name : "isha",
age : 22
}
for(var key in obj_ka_naam){ \*\*\*\*in yha obj hai

    console.log(key)          ************************* name,age
    console.log(obj_ka_name[key])          ************************* isha,22

}

## callback fncs >> Async js ka part hai

- aisa code jo baadme chlta hai use hm eek fn de dete hain ki jab uski chance aaye tab ye fn chlva dena
- and jo fn hm dete hain vobhi eek normal fn hota hai called callback fn

## first class fns

- Eg.

function abcd(a){
a(); \
} \
 \
 -----------------------------
abcd(function(){console.log("YO");})

## how array are made behind the scenes

- Array obj hota hai!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
- proof: var arr=[33,55,3,77]arr[-1]=99 >> [33 ,55,3,77,-1:99]

- tab check kaise kren ki array kab array hai and kab obj :
  Array.isArray([]); >>true
  Array.isArray({}); >>false

## how to delete obj prop

- var a={ name:"isha", age:22}

- use `delete `
- delete a.age;

---

[3]

## sync and async kya hota hai

- eek ke baad eek kaam krna -> jabtak eek kaam khtm nhi hoga dusra shuru nhi hoga :synchronous
- asynchronous: jab saare kaam eek saath `shuru krdo` khtm hote rhenge vo apne time pe and jaise jaise vo khtm hote jayenge hm us chees ko dekhte rhenge

sync : line ko eek eek krke chlata hai
async : sari line ko eeksath chla deta hai

## kaise pta chlega ki hm ksisi code ko sync melikhe ya async me

agar khai bhi code me inmese koi dikh gya : toh async hai

- setTimeout
- setInterval
- promises
- axios
- XMLHttpRequest

> > sab asynchronous hain

## async js hai kya

- kai baar aapka final code kisi ke servwee pe dependent hota hai , isme hme nhi pta ki ans kab plt ke aayega toph hm isme use krte hain asyn code taki blocking na ho
- jab ans aajyae tab koi particular cheez ya line ya fn chlana

- eg. setTimeout

  ### setTimeout

  - syntax
    +--------------------------------+
    | setTimeout(callback,time in ms) |
    +--------------------------------+
    callback hot hai fn
    ye tab chlta hai jab async/setTimeout ka execution khtm ho jata hai

          1 setTimeout(function(){},2000) ye chlajayega sideme and lineno 2 apna execute hogi and 2min baad ye function chlne lgega jo set time out ke and hote hain
          2

## js is not asynchronous

## full story of async

    - jobhi main stack me hota hai vo chlta hai and jo side stack mehota hai vo behind the sene chlta hai and jab vo chl ke khtm ho jate hain then unhe main stack me lake execute kiya ja skta hai

    - jab main stack khali hota hai tabhi side stack ke ans ko lake main stack me dala jata hai
    - async jata hai side stack me || sync jata hai main stack me
    - ye side stack se main stack me sid stack ke khtm hogye ans ko execute krane ke liye lane ka kaam event loop ka hota hai

    - eg
    console.log("hey1");
    console.log("hey2");
    setTimeout(function(){console.log("hey3");},0)
    console.log("hey4");

    >> hey1 hey2 hey4 hey3

## single threading and multi threading

    - async kay ye mtlb nhi kisab saaathmechlne lge
    - js hai single thread
    - toh ye 2 task ke beech me fast fats switch krke unko complete krti hai

## ASYNC KA CODE chlane ke liye >> sending req

    - fetch
    - axios >>package
    - promise
    - setTimeout
    - setInterval

## REQUEST Vaps aane baad kya krna hai

### callbacks

      #### ASYNC KA CODE >> sending req
    - fetch
    - axios >>package
    - promise
    - setTimeout
    - setInterval
     #### REQUEST Vaps aane baad kya krna hai
    - then catch
    - callbacks
    - async await

    eg. var a=fetch("http:\\google.com) ******wrong
    	console.log(a);
    >>here fetch is making a req and hmnenhipta is req ka res kab aayega ya ayega bhi ya nhi

### promises

    - ise hote hain 2part
             /         \
        /           \
          resolve      reject
            |		 |
       then         catch

    - promise(fncion(){})
    - ab yha promise ko chahiye hai yatoh resolve krao yatoh reject krao
    - promise(fncion(res,rej){})
    - ab promise ke andr async fn bnao jiska ns promise capture krega
    - promise(fncion(res,rej){ setTikmeout(function(){},2000})
    - ab agar promise se response aaya hai toh check kro ki agar kaamka hai toh then else beakr hai toh error btao

- eg
  var ans=new promise((res,rej)=>{
  if(true){
  return res;
  }
  else{
  return rej;
  }
  })
  ab agar result aat hai toh ab uska use kro, vrna uska error btao
  ans
  .then(function(){})
  .catch(function(){})

[EXCERSISE] : user will ask for a no b/w 0 to 9 and if a no is below 9 resolve else rej

var ans=new promise((res,rej)=>{
//ask for a no
var no=Math.floor(Math.random()\*10)//0-9
if(no<9){
return res;
}
else{
return rej;
}
})

ans
.then(function(){
console.log("your num")})
.catch(function(){l
console.log("error")})

## execute async task in synchronous way

- EG
  sabse phele ghr ao
  gate Kholo
  khana bnao
  khao
  soojao

> > > > p1->

    |->p2
    |->p3
        |-> ...............

    var p1=new promise((res,rej)=>{}){
    	//rej ko abhi ignore krte hain
    	return res("sabse phele ghr ao"); //""=res ka data
    }
    var p2=p1.then(function(data){
    	console.log(data); //promise 1 ke pure hote ki ye kaam kro
    	new promise((res,rej)=>{}){
    		//rej ko abhi ignore krte hain
    		return res("sabse phele ghr ao"); //""=res ka data
    	}

    })
    p2.then()

- then and catch
- try and catch

## async await

    - koi bhi esa fn jisme aap async code likhte hain->toh aap usme promise ka use kr skte hain uska ans handel krne ke liye ->jab uska ans aata hai tab aap then lgate hain->to avoid using then we used async and await
    - 1 then = 1 await

    - Jha async code use hua hai vha uske parent fn ko async bnado
    - then make the async code await
    - eg

function abcd(){
fetch("https://instagram.com/api")
.then(function(raw){
return raw.jason();
})
.then(function(data){
console.log(data);
})
}

async function abcd(){
|
------>let raw=await fetch("https://instagram.com/api")
let data=await raw.jason()
console.log(data);
})
}

## 5 use cases of real world

    - node meain jab db
    - react fetch
    - setTimeout
    - setInterval

# concept aside

## concurrency

    - sync and async code eek sath chl rhe hain -> main stack and side stack

## parallelism

    - focus krta hai diff processors and unke core par

## throttling

    - kisi code the no of execution pe control krna

---

[4]

## Pillar of DOM

    ### Selecting html elem
    	`var a=document.querySelector("")`
    ### changing html
    	`a.innerHTML="hello"`
    ### changing css
    	`a.style.color="red"` //camel case
    ### event listner
    	`a.addEventListner("event",function(){})`
