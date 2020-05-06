4/25 [
  working with a code snipet I found making use of modals to enlarge pictures in a gallery
  still somethings to work out with sizing the images so the look better within the modal but on the whole everything works! It just doesn't look perfect yet
  it also has some jQuery involved to make things a little easier
]

5/4 [
  async js
    call stack for js -> first in first out
    js is single thread -> can only do one thing at a time
    js leverages power of the browswer with callback functions to work on multiple processes at the same time


  ES2015 Fundementals!
    array helper functions
      forEach, map, filter, find, some, every, reduce
    trying to minimize the amount of for loops being used in code 
      to reduce acutal code and possible mistakes that could be hard to debug
    
    an interesting use of reduce 
      solving a balance params whiteboard problem
        cosnt balanceParams = (string) => {
          return !string.split('').reduce((acc, char) => {
            if (acc < 0) {return acc};
            if (char === ')') {return ++acc};
            if (char === '(') {return --acc};
            return acc;
          }, 0);
        };
]

5/5 [
  More ES2015 Fudementals!
  let/const 
  template literals
  arrow functions
  enhanced object literals
  defualt arguments
  rest/spread
  destructuring
  classes

  the destructuring section was the most enlightening just because of the number of ways it can be used 
    also how it can be nested with {props: [prop]} to get the first element of an array that is the prop of an object
    also seeing how you can use destructing with arguments is a big help
  
  everything else was a welcome review and some better explaination of why things happen the way they do that i had before
  now i need to find ways to implement these concepts to make sure I understand them correctly

  getting back into JS has been really nice and a refreshing change of pace from pure HTML/CSS recently
   
]

5/6 [
  generator functions and using them with the for...of loop
   declaring generators with the function* () {...} syntax
    iterating through objects using Symbol.iterator and the power of generators with for...of loops
      being able to iterate through any data structure using this method
      setting Symbol iterators using this set up
      class ExampleObject {
        key: value
        otherKey: value
        [Symbol.iterator]: function* () {
          yield key;
          yield otherKey;
        }
      }
    being able to use the for...of loop to avoid having to use .next() for iterating through generator functions
    some examples of when generator functions could be useful in real world
      with an object that represents a team that has some sub teams and you need to pull out the names of all the team members
        and the members of the sub teams
      with a site like reddit's comment set up with a tree structure using Symbol.iterator makes accessing all the nodes easier
  
  Promises and fetch
    the importance of promises to the functionality of async functionalty in JS
    return of promises being resolve and reject
    chaining .then() statements onto a promise
     like this: 
      promise
        .then(() => {
            // some code to run
          })
        .then(() => {
          // other code to run if needed
        })
        .catch(() => {
          // code when things fail
        })
    I am curious about how this impacts the use of async/await at this point because that seems like a more elegant method for promises
    also learned about fetch
      the curious aspect of needing to run .json on the response before being able access the data
      like this:
        fetch(url)
          .then(res => res.json())
          .then(data => // do something with data)
      the other curious aspect where even if you get an error message back from the server fetch does not fall into catch 
        it only falls into catch if there is an outright request failure
      these two aspects make fetch a bit of a weird choice it seems esspecially against other 3rd part libs for HTTP requests

  This was a big day with alot of information to get my head around but it opens some interesting possiblities for uses for what came up! Overall very interesting day!!
]