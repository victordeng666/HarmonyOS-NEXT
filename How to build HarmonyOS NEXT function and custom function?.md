function
example
```
// named function
function add(x:number, y:number) {
  return x + y;
}
console.log("add",add(1,2)); 

// Anonymous function (lambda expression)
let myAdd = (x:number, y:number) => {
  return x + y;
};
console.log("myAdd",myAdd(1,2)); 

//How does typescript ensure the accuracy of input and output
//1. Enter the specified data type as a parameter
console.log("add2",add(1,'2')); 
//2. Function specifies data type
function newAdd(x:number, y:number):number {
  return "newAdd："+x+y;
}
console.log("newAdd",newAdd(1,2)); 

//Optional parameters
function buildName(firstName: string, lastName?: string):string {
    if (lastName)
        return firstName + ' ' + lastName;
    else
        return firstName;
}
let result1 = buildName('Bob');
let result2 = buildName('Bob', 'Adams');
console.log("result1",result1);
console.log("result2",result2);

//Remaining parameters, unlimited number of optional parameters. It can be none at all, or there can be any of them. Define using ellipsis (...)
function getEmployeeName(firstName: string, ...restOfName: string[]):string {
  return firstName + ' ' + restOfName.join(' ');
}
let employeeName = getEmployeeName('Joseph', 'Samuel', 'Lucas', 'MacKinzie');
console.log("employeeName",employeeName);
```

Custom Build Function
ArkUI provides a lightweight UI element reuse mechanism @ Builder, with a fixed internal UI structure that only transfers data with the user. Developers can abstract reused UI elements into a method and call it in the build method.

To simplify the language The functions decorated by @Builder are also known as "custom build functions".

There are two ways to use the @Builder decorator, which are private custom build functions defined within custom components and global custom build functions defined globally.

Private custom build functions defined within custom components:
```
@Entry
@Component
struct BuilderDemo {
  @Builder
  showTextBuilder() {
    Text('Hello World')
      .fontSize(30)
      .fontWeight(FontWeight.Bold)
  }
  @Builder
  showTextValueBuilder(param: string) {
    Text(param)
      .fontSize(30)
      .fontWeight(FontWeight.Bold)
  }
  build() {
    Column() {
      // No parameters
      this.showTextBuilder()
      // Have parameters
      this.showTextValueBuilder('Hello @Builder')
    }
  }
}
```

Global custom build function defined globally
```
@Builder
function showTextBuilder() {
  Text('Hello World')
    .fontSize(30)
    .fontWeight(FontWeight.Bold)
}
@Entry
@Component
struct BuilderDemo {
  build() {
    Column() {
      showTextBuilder()
    }
  }
}
```

parameter passing rule
There are two types of parameter passing for custom build functions: value passing and reference passing, both of which must follow the following rules:
The type of the parameter must be consistent with the declared type of the parameter, and expressions that return undefined or null are not allowed.
Within functions decorated with @Builder, it is not allowed to change parameter values.
The UI syntax in @Builder follows the rules of UI syntax.
Only when a parameter is passed in, and the parameter needs to be passed directly to the object literal, will it be passed by reference. All other passing methods are passed by value.

Passing parameters by value:
The function decorated by @Builder is passed by value by default. When the parameter passed is a state variable, the change in the state variable will not cause a UI refresh within the @Builder method. So when using state variables, it is recommended to use pass by reference.

Passing parameters by reference:
When passing parameters by reference, the parameters passed can be state variables, and changes in the state variables will cause UI refresh within the @Builder method.
