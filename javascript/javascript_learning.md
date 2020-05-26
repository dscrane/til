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

5/12 [
  Working through some of the Wes Boss Javascript30 class. Worked on making a simple JS driven clock with transform/rotate
    interesting to see the simple ways to annimate things with js
  
  also kept going through the Dan Abramov JustJavascript course. There was a lot of really interesting ideas and mental models in there that I still need some more time to get my head around but they really seem to be a good way of putting things together and understanding what is happening when we think about our code in JS. I am really curious to start putting some of it into practice when I make decisions about my code.
]

5/17 [
  Still working through the Wes Boss class and just went through the dev tools section which was really interesing. Seeing all of the different ways to leverage the power of the console to display rich information in the console will be really helpful.
    console.table() seems like a really nice thing to have as long as the data you want to display is uniform
    styling a console.log("%c.....", "style") seems like a good way to make sure you can see the important information you want to see when you are debugging
    console.time() is something I am going to start using to make sure the processing time can be as low as possible from the start rather than need to go back and work out the lag time
    console.group() is also something I might use when I want to make sure the data I am iterating through is coming out correctly
]

5/18 [
  Looked at some introductions to testing and the idea of TTD and how that can save time and money in the long run if the testing suit is well set up
    Automated testing is a great way to save some fear about merging updates and bug fixes because the changes can all be tested before the production build is changed
    It can be tough to implement at the start, esspecially in the design of code that is easily tested as well as making the actual tests parameters to run
    Interested to keep going there are still a lot of nuances that are going right over my head
  
  Promises
    Another ground up explanation of promises but this time it was a little more helpful because it went over what the previous alternatives to async callbacks were and how the use of promises is a huge helpful addition to JS
    The way .then() can be set up so that is takes advantage of the bubbling of promises so that all the .then()s can be success only and any and all errors can be caught in with the .catch() method
    Another benefit to promises being that async handling can be ported and implemented in a variety of locations in the code with different handlers added at different points in the code
    There are still some issues with promises because it is still tough to access the value of a promise globally and still hard to ensure that the code outside the promise chain will not run until the promis value returns --> this may be where async/await begins to steal the show

  Journaling
    Read an article about the power of journaling during the coding process for both a checklist of things that need to be done and a way to have some security in putting little things to the side without the fear of those being lost in the past if they are important
    Found a nice command line journal that I am going to start trying to use from inside VSCode to see how I can do at keep tabs on progress and TODOs for a project 
    Gotta give an update on this down the line to see if it is something I manage to do well
]

5/25 [
  More work with promises and getting another view of how they work and their importance in JS
  Also looked into the way the JS acutally handles its async functionality and "mutli thread" nature with web workers
    How each thread works as an independently async process passing information back and forth through the queue
    Also how concurrent proccessing differs from async proccessing happens when the two proccess interact with eachother
  
  APIs 
    How they are prevasive through the internet and how much of the internet would be fundementally different without them
    They can differ pretty widly in functionality and presentation and that within a code base anytime there is "coversation" between two sets of programs they are accessing the others
      API

]