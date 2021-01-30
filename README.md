# codec-proj-11-MealMaker
//Created a three-course meal based on what is available on a menu


const menu = {
  _courses: {
    appetizers: [],
    mains: [],
    desserts: [],
  },
  get appetizers() {
    return this._courses.appetizers;
  },
  get mains() {
    return this._courses.mains;
  },
  get desserts() {
    return this._courses.desserts;
  },
  set appetizers(appetizers) {
    this._courses.appetizers = appetizers;
  },
  set mains(mains) {
    this._courses.mains = mains;
  },
  set desserts(desserts) {
    this._courses.desserts = desserts;
  },
  get courses() {
    return {
      appetizers: this.appetizers,
      mains: this.mains,
      desserts: this.desserts,
    };
  },
  addDishToCourse(courseName, dishName, dishPrice) {
    const dish = {
      name: dishName,
      price: dishPrice,
    };
    return this._courses[courseName].push(dish);
  },
  getRandomDishFromCourse(courseName) {
    const dish = this._courses[courseName];
    const randomIndex = Math.floor(Math.random() * dishes.length);
    return dishes[randomIndex];
  },
  generateRandomMeal() {
    const appetizer = this._getRandomDishFromCourse('appetizers');
    const main = this._getRandomDishFromCourse('mains');
    const dessert = this._getRandomDishFromCourse('desserts');
    const totalPrice = appetizers.price + main.price + dessert.price;
    return `Your meal is ${appetizer.name}, ${main.name}, and ${dessert.name}, and the total price is ${totalPrice}`;
  }
};
menu.addDishToCourse('appertizers', 'wings', 4.0);
menu.addDishToCourse('appetizers', 'salad', 4.50);
menu.addDishToCourse('appetizers', 'fries', 5.00);

menu.addDishToCourse('mains', 'chicken alfredo', 10.25);
menu.addDishToCourse('mains', 'cheeseburger', 7.75);
menu.addDishToCourse('mains', 'steak', 11.20);

menu.addDishToCourse('desserts', 'ice cream', 3.00);
menu.addDishToCourse('desserts', 'chocolate cake', 3.00);
menu.addDishToCourse('desserts', 'cookies', 3.25);

const meal = menu.generateRandomMeal();
console.log(meal);

