# Javascript Objects |  Mr Yenagandula

### Objects In Detail
- Normally Every programming language is contains objects and it support object oriennted programming concepts 
- Java Script also supports OOPS programming.
- In Javascript Objects are like containing properties, functions and methods.
- We can add and remove properties from that objects.
- In Javascript we can create objects in different ways.

### Steps:
- create variable in javascript file the name as person.
- the person contains firstname, lastname , gender , height etc.

### Example (1)

```bash

  const person ={
    firstName : 'Koseksi',
    lastName :'P',
    gender: 'Male',
    height:'5.7'
  }

  console.log(typeof person);
  console.log(person)

  /** We can add the properties dynamically by using person.favColor ='white'  or person["favColor"] ='white' */
  /** person.favColor= "white" */
  person["favColor"]= "yellow" 

  /** We can get the specific property by using person.fistName or person["fistName"]  */
  console.log(person.firstName) 
  console.log(person["firstName"]) 
  console.log(person)

  /** To delete properties from object use delete person.favColor or delete person["favColor"] */
  /** delete person.favColor */
  delete person["favColor"]
  console.log(person)

```


### Example (2)

```bash
const person2 ={
    firstName : 'Koseksi',
    lastName :'P',
    gender: 'Male',
    height:'5.7',
    fullName(){
        console.log(`${this.firstName} ${this.lastName}`);
    }
}

console.log(person2)
person2.fullName();

/** We can add methods from outside also by using reference type */
person2.getHeight= function(){
    console.log(this.height);
}

person2.getHeight();

```

### Example (3)

```bash
class Movie {
    constructor(name,year, review){
        this.name=name;
        this.year=year;
        this.review=review;
    }

    updateReviews(review){
        this.review= review;
        return this;
    }

    getMovieNameAndYear(){
        return { year: this.year , name :this.name }
    }

}

/** To create object we need to use new keyword */
const movie1 = new Movie('RRR','2022','3.9');
console.log(movie1.updateReviews("4.2"));
console.log(movie1.getMovieNameAndYear());


const movie2 = new Movie('KGF Chapter2','2022','3.7');
console.log(movie2.updateReviews("4.0"));
console.log(movie2.getMovieNameAndYear());

```

### Example (4)

```bash
class Movie2 {
    constructor(name,year, review){
        this.name=name;
        this.year=year;
        this.review=review;
    }

    updateReviews(review){
        this.review= review;
        return this;
    }

    getMovieNameAndYear(){
        return { year: this.year , name :this.name }
    }
}

class Hollywood extends Movie2{
    constructor(name,year, review, budget){
        super(name,year,review);
        this.budget =budget;
    }

    getMovieYear(){
        return this.year;
    }
}

const hyMovie = new Hollywood('Peter Rabbit','2021','3.2','High');
console.log(hyMovie.getMovieNameAndYear())
console.log(hyMovie.updateReviews('4.2'))
```

### Example (5)
```bash

function Laptop(brand, processor, price, reviews) {
    this.brand = brand;
    this.processor = processor;
    this.price = price;
    this.reviews = reviews;
    this.getBrand = function(){
        return this.brand;
    }
}


const laptop1 = new Laptop('HP','I5','50000','3.2k');
console.log(laptop1)
console.log(laptop1.getBrand())
const laptop2 = new Laptop('Acer','I5','45000','2.9k');
console.log(laptop2)
console.log(laptop2.getBrand())

```

### Example (6)
```bash
function Laptop2(brand, processor, price, reviews) {
    this.brand = brand;
    this.processor = processor;
    this.price = price;
    this.reviews = reviews;
}

Laptop2.prototype.getBrand = function(){
    return this.brand;
}

const ilaptop = new Laptop2('HP','I5','50000','3.2k');
ilaptop.reviews='3.5k'
console.log(ilaptop)
console.log(ilaptop.getBrand())

const ilaptop1 = new Laptop2('Acer','I5','45000','2.9k');
console.log(ilaptop1)
console.log(ilaptop1.getBrand())

/**Adding inheritance using prototype */
function AppleLaptop(...args){
    Laptop2.apply(this,args);
}

AppleLaptop.prototype = Object.create(Laptop2.prototype);

AppleLaptop.prototype.getPrice=function(){
    return this.price;
}
const appleLap = new AppleLaptop('Apple','Apple','150000','4.0k');
console.log(appleLap);
console.log(appleLap.getBrand())
console.log(appleLap.getPrice())

```
