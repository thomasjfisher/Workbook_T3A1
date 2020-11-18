// declaring the class Car
class Car {

// defining the attribute of the class Car
  constructor(brand) {
    this.carname = brand;
  }
  
// defining a function that all class of "Car" has
  present() {
  
// car.present() will return the cars brand 
    return 'I have a ' + this.carname;
  }
}

// declares that the class Model extends from Car, therefore inheriting all the attributes of // the class Car
class Model extends Car {

// Model is inheriting brand from Car via the use of super
  constructor(brand, mod) {
    super(brand);
    this.model = mod;
  }
  
 // a new class function show is defined which is adding model information when returned
  show() {
    return this.present() + ', it was made in ' + this.model;
  }
}

// declares an array named 'makes' with three strings inside.
let makes = ["Ford", "Holden", "Toyota"]

// array.from is creating a shallow-copied array 40 times
// (x,i) => i + 1980 is a map funciton, which returns the value of each index of an array and adds 1980 to it.
let models = Array.from(new Array(40), (x,i) => i + 1980)

// function returns a min and max value using Math.floor to round the nuber down to a whole 
// number
function randomIntFromInterval(min,max) { // min and max included
    return Math.floor(Math.random()*(max-min+1)+min);
}

// for loop declared of model of models
for (model of models) {

//randomly selects from the array make
  make = makes[randomIntFromInterval(0,makes.length-1)]
  
// when run in my terminal, this returns the make of the car from either 1980, 1981 or 1982, as 
// the array that contains makes has only 3 values 
  model = models[randomIntFromInterval(0,makes.length-1)]
  
// a new model class is made with the attributes generated randomly 
  mycar = new Model(make, model);
  
// logs to the console 40 times, with the newly generated strings as defined previously in make
// and model classes
  console.log(mycar.show())
}