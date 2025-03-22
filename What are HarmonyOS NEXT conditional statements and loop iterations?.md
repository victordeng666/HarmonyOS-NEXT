conditional statements
Usage rules
Supports if, else, and else if statements.
The conditional statements following 'if' and 'else' can use state variables or regular variables (state variables: changes in value can render the UI in real-time, while regular variables: changes in value will not render the UI in real-time).
Allow use within container components to construct different sub components through conditional rendering statements.
Conditional rendering statements are "transparent" when it comes to parent-child relationships between components. When there are one or more if statements between parent and child components, the rules of the parent component regarding the use of child components must be followed.
Each branch's internal building function must follow the rules of building functions and create one or more components. An empty constructor function that cannot create a component will result in a syntax error.
Some container components restrict the type or quantity of child components, and when conditional rendering statements are used within these components, these restrictions will also apply to the components created within the conditional rendering statements. For example, the sub components of the Grid container component only support the GridItem component. When using conditional rendering statements within the Grid, only the GridItem component is allowed to be used within the conditional rendering statements.

If statement
```
let num:number = 5
if (num > 0) { 
   console.log('This number is greater than 0') 
}

if (num % 2==0) { 
    console.log(num+' is even'); 
} else {
    console.log(num+' is odd'); 
}

if(num > 0) { 
    console.log(num+' is a positive number') 
} else if(num < 0) { 
    console.log(num+' is a negative number') 
} else { 
    console.log(num+' neither positive nor negative') 
}
```

switch…case statement
```
let grade:string = 'A'; 
switch(grade) { 
    case 'A': { 
        console.log('excellent'); 
        break; 
    } 
    case 'B': { 
        console.log('good'); 
        break; 
    } 
    case 'C': {
        console.log('pass'); 
        break;    
    } 
    case 'D': { 
        console.log('fail'); 
        break; 
    }  
    default: { 
        console.log('illegal input'); 
        break;              
    } 
}
```

loop iterations
When an object implements the Symbol.iterator property, we consider it iterable. Some built-in types such as Array, Map, Set, String, Int32Array, Uint32Array, etc. have iterability.
```
let list = ["red", "yellow", "green"];
//  index→   0       1       2

//while
console.log("--------while--------");
let i=0;
while(i<list.length){
    console.log(i+":"+list[i]); // 0:red，1:yellow，2:green
    i++;// i=i+1
}

//do while execute at least once
console.log("--------do while--------");
i=0;
do{
    console.log(i+":"+list[i]); // 0:red，1:yellow，2:green
    i++;
}while(i<list.length);

//for
console.log("--------for--------");
for(let i=0;i<list.length;i++){
    console.log(i+":"+list[i]); // 0:red，1:yellow，2:green
}

//for in
console.log("--------for in--------");
for(let index in list) {
    console.log(index+":"+list[index]); // 0:red，1:yellow，2:green
}

//for of
console.log("--------for of--------");
for(let item of list) {
    console.log(item); // red，yellow，green
}
```

