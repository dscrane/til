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