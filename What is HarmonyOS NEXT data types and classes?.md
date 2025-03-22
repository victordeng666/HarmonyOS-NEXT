data types

```
//boolean
let isDone: boolean = false;

//number
let decLiteral: number = 2023; //decimalism
let binaryLiteral: number = 0b11111100111; //binary system
let octalLiteral: number = 0o3747; //Octal
let hexLiteral: number = 0x7e7; //hexadecimal
console.log("decLiteral",decLiteral);
console.log("binaryLiteral",binaryLiteral);
console.log("octalLiteral",octalLiteral);
console.log("hexLiteral",hexLiteral);

//String, using double quotes (") or single quotes (') to represent the string
let username: string = "Jacky";

//array
let list1: number[] = [1, 2, 3]; //方式1
let list2: Array<number> = [1, 2, 3]; //方式2

//Tuples, tuple types allow representing an array with a known number and type of elements, and the types of each element do not need to be the same.
let x: [string, number];
x = ['hello', 10]; // OK
x = [10, 'hello']; // Error

//enum
enum Color {Red, Green, Blue};
let c: Color = Color.Green;

//union
let myFavoriteNumber: string | number;
myFavoriteNumber = 'seven';
myFavoriteNumber = 7;

//Unknown
let notSure: unknown = 4;
notSure = 'may be string';
console.log("notSure",notSure);
notSure = false;
console.log("notSure",notSure);

//Null and Undefined
let u: undefined = undefined;
let n: null = null;
```

class
example
```
//Class definition
class Person {
  private name: string; //attribute
  private age: number; //attribute

  //Constructor function
  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }

  //method
  public getPersonInfo(): string {
    return `My name is ${this.name} and age is ${this.age}`;
  }
}

//Class call
let person1 = new Person('Jacky', 18);
let info1 = person1.getPersonInfo();
console.log(info1);

//class inheritance
class Employee extends Person {
  private department: string;

  constructor(name: string, age: number, department: string) {
    super(name, age); //Call the parent constructor
    this.department = department;
  }

  public getEmployeeInfo(): string {
    return this.getPersonInfo() + ` and work in ${this.department}`;
  }
}

let person2 = new Employee('Tom', 28, 'HuaWei');
let info2= person2.getPersonInfo();
let eInfo2 = person2.getEmployeeInfo();
console.log(info2);
console.log(eInfo2);
```

    As applications grow larger, it is common to split code into multiple files, known as modules. Modules can be loaded onto each other and special instructions such as export and import can be used to exchange functionality and call functions of another module.

export:
```
export class Person {
  private name: string; //attribute
  private age: number; //attribute

  //Constructor function
  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }

  //method
  public getPersonInfo(): string {
    return `My name is ${this.name} and age is ${this.age}`;
  }
}
```

import:
```
import { Person } from './Person';

//Class call
let person1 = new Person('Jacky', 18);
let info1 = person1.getPersonInfo();
console.log(info1);
```

interface 
```
//interface 
interface People {
    say(msg:string):void
}

class Chinese implements People{
    say(msg:string){
        console.log("中国人说",msg);
    }
}

class British implements People{
    say(msg:string){
        console.log("The British say",msg);
    }
}

let man:People=new Chinese();
man.say("中国欢迎您");
man=new British();
man.say("Welcome to the UK")
```

