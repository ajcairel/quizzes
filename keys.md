# SEI Week 1 Quiz - Answer Key

### Bash/Zsh (Terminal)

#### For EACH and EVERY question in this section, assume you are in the `~/fridge` directory, and send the correct commands:

## Bash/Zsh (Terminal)

#### For EACH question in this section, assume you are in the `~/fridge` directory and answer with what terminal commands(s) will perform the following...

1. Make a `vegetables` and a `cakes` directories inside of `~/fridge`.

    ### Solution

    **Accept all answers that perform the desired result, for example:**

    ```
    mkdir vegetables cakes
    ```

2. Create two files, `onion.txt` and `lettuce.txt`, within the new `vegetables` directory.

    ### Solution

    **Accept all answers that perform the desired result, for example:**

    ```
    touch vegetables/onion.txt vegetables/lettuce.txt
    ```

3. Delete the `vegetables` directory (and everything inside it).

    ### Solution

    **Accept all answers that perform the desired result, for example:**

    ```
    rm -rf vegetables
    ```
    or
    ```
    rm -r vegetables
    ```

## JS Variables

4. Assign the string "SEI" to a variable named `course`.

    ### Solution

    ```js
    let course = 'SEI';
    ```

## Data Structures - JS Arrays

5. Define an array named `weekend` with just the string 'Saturday' in it.

    ### Solution

    ```js
    const weekend = ['Saturday'];
    ```

6. Write the line of code that will add the string 'Sunday' to the end of the `weekend` array.

    ### Solution

    ```js
    weekend.push('Sunday');
    ```

7. Knowing that the `weekend` array now contains the string 'Saturday' followed by the string 'Sunday', write the line of code that will access the string of 'Saturday' in `weekend` and assign it to a variable named `day`.

    ### Solution

    ```js
    let day = weekend[0];
    ```

## Data Structures - JS Objects

8. Assign an object literal to a variable named `brain` having a property with a key of `energyLevel` and a numeric value of `10`.

    ### Solution

    ```js
    const brain = {energyLevel: 10};
    ```

## JS Functions

9. Write a function declaration named `computeArea` that has two parameters, `length` & `width`, and **returns** the area of a rectangle (the `length` multiplied by the `width`).

    ### Solution

    ```js
    function computeArea(length, width) {
      return length * width;
    }
    ```

## JS Control Flow

```js
// Car and trip data
let milesPerGallon = 25;
let gallonsLeft = 3;
let milesToGo = 100;
```

10. Write an `if` statement that uses all three of the above variables in its conditional expression and will `console.log('SOS!')` if the "car" does not have enough gallons of gas to travel at least the number of `milesToGo` (no need to write a function, just the `if` statement please).

    ### Solution

    ```js
    if (milesPerGallon * gallonsLeft < milesToGo) console.log('SOS!');
    ```


# `SEI` Week 2 Quiz - Answer Key

## Functions

1. What do we call a function that's passed to another function as an argument?

    ```
    callback function
    ```

2. What do we call functions that either receive functions as arguments or return a function?

    ```
    higher-order functions
    ```

3. True or False: `getElementById()` considered a higher-order function?

    ```
    False
    ```

## OOP/Classes

4. What are classes used for in OOP?

    ```
    To create objects
    ```

5. What is the purpose of a class' `constructor` method?

    ```
    To initialize the properties on the shiny new object
    ```

6. True or False:  A **prototype** method is called on an instance of a class?
    
    ```
    True
    ```

7. What principle in Object Oriented Programming refers to the bundling of related data and behavior together?

    ```
    Encapsulation
    ```

8. What principle in Object Oriented Programming is it where a class specializes another class?

    ```
    Inheritance
    ```

## The `this` Keyword

9. True or False:  The value of `this` can always be determined by examining the definition of a non-arrow function?

    ```
    False
    ```

## Array Iterator Methods

10. If you call the `map` iterator method on an array with 50 elements, how many elements will be in the returned array?

    ```
    50
    ```

# SEI Week 4 Quiz

## For this quiz, please slack your instructors the answers, in numbered order. Do not include the questions. For example:
    
```
1. Ashton Kutcher played Chewbacca
2. Yolo
```
<br>

## Full-Stack Development

### (1) What two parts/components of an HTTP Request are used to match routes defined in Express and many other web frameworks?

#### Solution

```
The HTTP Method/Verb and the Path/Endpoint
```

### (2) What two HTML elements are used in web pages to send HTTP Requests to a web server?

#### Solution

```
<a></a> and <form></form> Elements
```

<br>

## Routing

For the below questions on routing (#3 thru #6), assume the following:

- The data resource we're CRUDing is `puppies`.
- The puppies router was mounted in server.js using `app.use('/puppies', puppiesRouter);` 
- A controller was required in routes/puppies.js as `puppiesCtrl`.

### (3) Finish defining the following route for the `index` functionality:

```js
router._________________;
```

#### Solution

```js
router.get('/', puppiesCtrl.index);
```


### (4) Finish defining the following route for the `create` functionality:

```js
router._________________;
```

#### Solution

```js
router.post('/', puppiesCtrl.create);
```

### (5) Finish defining the following route for the `delete` functionality:

```js
router._________________;
```

#### Solution

```js
router.delete('/:id', puppiesCtrl.delete);
```

### (6) What's the problem with how the following routes are being defined?


```js
router.get('/:id', puppiesCtrl.show);
router.get('/new', puppiesCtrl.new);
```

#### Solution

```
Need to define the new route before the show route.
The new route can never be matched because a "GET /puppies/new" request will always match the show route.
```

<br>

## Route Parameters

Assuming the following route defined:

```js
router.get('/:id', puppiesCtrl.show);
```

and the following hyperlink on a page:

```html
<a href="/puppies/123">Spot</a>
```

### (7) Finish the line of code below that would assign the value of the route parameter ("123") to the `pupId` variable in the following controller function?

```js
function show(req, res) {
  const pupId = ______________;
  ...
}
```

#### Solution

```js
function show(req, res) {
  const pupId = req.params.id;
  ...
}
```

<br>

## Middleware

### (8) What is the name of the middleware we need to install and mount in server.js used to change a POST request into a DELETE or PUT request?

#### Solution

```
method-override (methodOverride is also acceptable)
```

<br>

## HTML & EJS Views

### (9) Write a line of HTML that when clicked, would result in a list of all puppies being displayed?

#### Solution

```html
<a href="/puppies">View All Puppies</a>  <!-- "View All Puppies" can be anything -->
```

### (10) What would you replace the `???` below with to link to the show page for each puppy using its `id` and following RESTful routing?

```html
<% puppies.forEach(function(pup) { %>
  <a href="???"><%= pup.name %></a>
<%> }); %>
```

#### Solution

```html
<% puppies.forEach(function(pup) { %>
  <a href="/puppies/<%= pup.id %>"><%= pup.name %></a>
<%> }); %>
```

# SEI Week 5 Quiz

## For this quiz, please slack your instructors the answers, in numbered order. Do not include the questions. For example:
    
```
1. Ashton Kutcher played Chewbacca
2. Yolo
```
<br>

## RESTful Routing

**For questions #1 thru #4, please identify the proper route (HTTP Method & Path) assuming a `Post --< Comment` data relationship...**

### (1) Create a comment for a post.

#### Solution

```
POST /posts/:id/comments
```

### (2) Display a single post.

#### Solution

```
GET /posts/:id
```

### (3) Delete a comment.

#### Solution

```
DELETE /comments/:id
```

### (4) See a form used to edit a post.

#### Solution

```
GET /posts/:id/edit
```

## Mongoose

### (5) What is the best Mongoose Model query method to use if you need to find a single document and you have its '_id'?

#### Solution

```
findById()
```

### (6) What is the best Mongoose Model query method to use if you need all documents that meet a certain criteria?

#### Solution

```
find()
```

### (7) When defining a Mongoose schema, what data type do we use for a property that needs to reference another document?

#### Solution

```
ObjectId
```

### (8) Assuming we're implementing a data relationship of `User --< Order` - should we use embedding or referencing?

#### Solution

```
Referencing.

Note: We don't want to bloat the user document, plus, having orders in its own collection makes it easier for a business to query for, and analyze orders.
```

## Javascript Promises

### (9) Promises are an alternative to __________ functions when working with asynchronous operations.

#### Solution

```
callback
```

### (10) A promise object has a __________ method used to obtain the resolved value.

#### Solution

```
then()
```

# SEI Week 7 Quiz

## For this quiz, please slack your instructors the answers, in numbered order. Do not include the questions. For example:
    
```
1. Ashton Kutcher played Chewbacca
2. Yolo
```
<br>

## Python Control Flow

### (1) Is an empty list, e.g., `[]`, in Python truthy or falsy?

#### SOLUTION

```
falsy
```

### (2) What would be returned by the following Python expression?

  ```python
  {} and "I love coding in Python"
  ```

#### SOLUTION

```
{}
```

### (3) What value will printed out last by the following code?

  ```python
  cur_num = 10
  while True:
    if cur_num == 0:
      break
    print( cur_num )
    cur_num -= 1
  ```

#### SOLUTION

```
1
```

## Python Containers

### (4) What's the key difference between a list and a tuple?

#### SOLUTION

```
lists are mutable while tuples are immutable
```

### (5) Dictionaries in Python are similar to ________ in JavaScript

#### SOLUTION

```
objects
```

### (6) What does a list comprehension in Python always return?

#### SOLUTION

```
A new list
```

### (7) True or False: The following code's output will be as expected?

  ```python
  colors = ('purple', 'orange', 'red')
  for i, c in enumerate(colors):
    print( f'{i + 1} - {c.upper()}' )
  ```
  **Expected output:**
  ```
  1 - PURPLE
  2 - ORANGE
  3 - RED
  ```

#### SOLUTION

```
True
```

## Python Functions

### (8) Why won't the following code work as intended?

  ```Python
  def get_net_worth(cash, other_assets, *args, long_term_debt):
    short_term_debt = 0
    for arg in args:
      short_term_debt += arg
    print(f'Net Worth: {(cash + other_assets) - (short_term_debt + long_term_debt)}')
  ```

#### SOLUTION

```
The *args must be the last parameter (listed after long_term_debt)
```

## Python Classes

### (9) What method in a class is automatically called by Python when a new instance of a class is being created?

#### SOLUTION

```
The __init__() method
```

## Python Miscellaneous

### (10) What would be printed by the following Python code?

  ```python
  nums = list(range(0, 6, 2))
  print(nums)
  ```

#### SOLUTION

```
[0, 2, 4]
```

# SEI Week 8 Quiz

## For this quiz, please slack your instructors the answers, in numbered order. Do not include the questions. For example:
    
```
1. Ashton Kutcher played Chewbacca
2. Yolo
```
<br>

## Django Routes

### (1) Which Django route below is defined correctly?
    
```
A)  path('/cats', views.index, name='index')
B)  path('cats/', views.index, name='index')
C)  path('/cats/', views.index, name='index')
```

#### SOLUTION

```
B
```

### (2) What two things are wrong with the following Django route? (assume views.CatList is a CBV)

```python
path('cats', views.CatList, name='cat_index')
```

#### SOLUTION

```
1) The path is missing a trailing slash. Should be: `'cats/'`
2) The CBV is missing the `as_view()` call.  Should be:  `views.CatList.as_view()`
```

## Django Models

### (3) After you create a model, what command(s) must you run in terminal to synchronize the databases's schema with the app's models?

#### SOLUTION

```
python3 manage.py makemigrations
python3 manage.py migrate
``` 

### (4) In a `Trip --< Place` relationship, which Entity/Model will need to hold the `models.ForeignKey` field?

```
A)  Trip
B)  Place
C)  Either A or B
D)  None of the above
```

#### SOLUTION

```
B
```

### (5) Assuming an object named `concert` in a `Concert --< Ticket` relationship, which would return the `concert` object's tickets? 

```
A)  concert.tickets.all()
B)  concert.ticket_set.all()
C)  Either A or B
D)  None of the above
```

#### SOLUTION

```
B
```

### (6) Assuming an object named `ticket` in a `Concert --< Ticket` relationship, which would most likely return the concert object for the `ticket`? 

```
A)  ticket.objects.concert
B)  ticket.concert
C)  ticket.objects.filter(concert=concert_id)
D)  Either of the above
E)  None of the above
```

#### SOLUTION

```
B
```

### (7) When using the `models.ManyToManyField`, Django will automatically/transparently create a _____ table in the database necessary to implement the relationship.

#### SOLUTION

```
join
```

### (8) Assuming a `Trip >--< Tag` relationship, which would correctly model the relationship in Django:

```
A)  On the Trip Model:
      tags = models.ManyToManyField(Tag)
B)  On the Tag Model:
      trips = models.ManyToManyField(Trip)
C)  Either A or B
D)  None of the above
```

#### SOLUTION

```
C
```

### (9) Assuming a `Trip >--< Tag` relationship and `trip` & `tag` objects, which line of code would likely create an association between them:

```
A)  tag.trip_set.add(trip)
B)  trip.tags_set.add(tag)
C)  Either A or B
D)  None of the above
```  

#### SOLUTION

```
A
```

## Django Authentication

### (10) In a View Function, which line of code would return the object for the logged in user:

```
A)  loggedInUser
B)  self.request.user
C)  request.user
D)  Either of the above
E)  None of the above
```

#### SOLUTION

```
C
```

# SEI Week 10 Quiz

## For this quiz, please slack your instructors the answers, in numbered order. Do not include the questions. For example:
    
```
1. Ashton Kutcher played Chewbacca
2. Yolo
```
<br>

## React JSX and Props

### (1) What JSX would render a `<Person>` component, passing to it a `name` prop with a value of "Fred"?

#### SOLUTION

```jsx
<Person name="Fred" />
```

### (2) In the code below, what would you replace the `<...>` with in order to pass the entire `person` object as the value for the `person` prop?: 

```jsx
import Person from './Person';

const person = {
  first: "Sammy",
  last: "Hagar",
  company: "Cabo Wabo Cantina"
};

export default function App() {
  return (
    <>
      <h1>Person Page</h1>
      <Person person=<...> />
    </>
  );
}
```

#### SOLUTION

```jsx
{person}
Like this: <Person person={person} />
```

### (3) Assuming the `<App>` component above and the `<Person>` component below, re-write the single line of code so that the `<Person>` component will render as intended.

```jsx
export default function Person() {
  return (
    <article>
      <h5>{props.first} {props.last}</h5>
      <p>Company: {props.company}</p>
    </article>
  );
}
```

#### SOLUTION

```jsx
export default function Person(props) {
```

### (4) Assuming the `<Info>` component below, what text will be displayed in the browser by rendering the `<Info>` component?

```jsx
export default function Info() {
  const title = 'Tesla';
  const engineType = 'Electric';
  const isFast = true;
  return (
    <article>
      <p>{title}</p>
      <p>Type: {engineType}</p>
      <p>Fast: {isFast}</p>
    </article>
  );
}
```

#### SOLUTION

```
Tesla
Type: Electric
Fast:

Note: Booleans don't render any text
```

## React State and Hooks

### (5) Given the code below, what will the data type of the variable `resultOfCallingUseState` be?

```js 
const resultOfCallingUseState = useState(null);
```

#### SOLUTION

```
Array/Object
```
 
### (6) Assuming the code below within a component, what is `setTodo` used for?

```js
const [todo, setTodo] = useState(null);
```

#### SOLUTION

```
It's a setter function used to update the value of the `todo` state
```

### (7) Given the `<Person>` component below, what would be logged in the console when the `<button>` is clicked for the first time?

```jsx
export default function Person() {
  const [name, setName] = useState('Jenny');

  function changeName() {
    setName('Jorge');
    console.log(name);
  }

  return (
    <article>
      <h5>{name}</h5>
      <button onClick={changeName}>Change Name to Jorge</button>
    </article>
  );
}
```

#### SOLUTION

```
Jenny
```

## React Event Handling

## (8) What change to the code below is necessary to make it work as intended when the `<button>` is clicked?

```jsx
export default function Person() {
  const [name, setName] = useState('Jenny');

  return (
    <article>
      <h5>{name}</h5>
      <button onClick={setName('Jorge')}>Change name to Jorge</button>
    </article>
  );
}
```

#### SOLUTION

```
onClick={() => setName('Jorge')}
Wrap the call to setName with a function
```

## Array Iterator Methods

### (9) What is the best array iterator method for converting an array of objects into an array of components to be rendered?

#### SOLUTION

```
map
```

### (10) What is the best array **iterator method** for returning a new array that no longer contains a certain object?

#### SOLUTION

```
filter
```

# SEI Week 11 Quiz - Answer Key

## Promises, Fetch and Async/Await

### (1) What will the following async function `helloWorld` always return when invoked?

  ```js
  async function helloWorld() {
    return 'hello world!';
  }
  ```

  #### Solution

  ```
  A promise.
  Note: The promise in this case will resolve to the string 'hello world'
  ```


### (2) What two arguments can be provided to the `fetch(arg1, arg2)` function?

  #### Solution

  ```
  arg1 --> the URL/path/endpoint of the request
  arg2 --> the optional "options" object used to configure the request
  ```

### (3) What does the promise returned by `fetch()` resolve to?

  #### Solution

  ```
  An object that represents the response
  ```

## `useEffect` and `useRef`

### (4) What is the first argument we provide to the useEffect hook?

  #### Solution

  ```
  A callback function that contains the code we want useEffect to run
  ```

### (5) If no second argument is provided to the `useEffect` hook, when does the callback function run?

  #### Solution

  ```
  After every render
  ```

### (6) If we pass an empty array as the second argument to the useEffect hook, when does the callback function run?

  #### Solution

  ```
  After the first render only
  ```

### (7) Is the use case of `useRef` more similar to that of `useState` or `useEffect`?

  #### Solution

  ```
  useState because useRef is used to remember a value (like useState) whereas useEffect is for running code after a render
  ```

## Mongoose

### (8) A ________ property on a Mongoose schema is a "computed" property that is not actually saved in the document.

  #### Solution

  ```
  virtual
  ```

### (9) We can add custom _________ methods callable on a Mongoose model (hint: a model is a class).

  #### Solution

  ```
  static
  'class' is also acceptable
  ```

### (10) What Mongoose model query method should we use to find a single document that belongs to a certain user and isn't paid?

  #### Solution

  ```
  findOne
  ```

  