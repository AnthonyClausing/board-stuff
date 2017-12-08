# Big O Notation

## What is it ?
* Big O - "Order of Magnitude" (Big omega)
* A measurement of how 'efficient' an algorithm is, in comparison to other runtimes for the same algorithm.
* Big O, is the WORST case secenario of an algorithm. (upper bound on how bad things are)
* We have two separate big O notation for any algorithm
    * Time complexity
    * Space complexity

## When do we reallyyyy care about big O ? 
* When input size gets 'arbitrarily' large.
* When we want the time of something to be predictable or 'realtime'
* When we care about not using too much memory.

## What is it not?
* It is not a measurement of how long it will take. 
* Not the best case scenario (big omega) - lower bound on how good things can get. 
* Not the average case (big theta) - average.

## Common Types 
* o(1) - constant time. 
    * Any size input will take the same amount of time/space of output.
    * ex. find the 5th element in an array. 
* o(log (n)) - logarithmic time. 
    * As we increase our size n we still see an increase in time/space but decreasingly so.
    * ex. Binary search tree. Sorted array algorithms. 
* o(n) - linear time.
    * The time it takes for an output scales directly with input.
    * An array of 2 elements takes 2 seconds, an array of 10 elements takes 10 seconds
    * ex. Looping through an array (any linear search algorithm)

```
function someAlgo(arr){
    for(let i = 0; i < arr.length; i++){

    }
    for(let i = 0; i < arr.length; i++){
        
    }
    return 5;
}
// o(2n) => o(n)

```
* o(n * log(n)) - loglinear time. 
    * Things aren't quite quadratic, and still increase slowly at large inputs.
    * Merge sort algorithms.

```
    [3,2,4,1,5,7,3,7]
    [3,2,4,1][5,7,3,7]
    [3,2][4,1][5,7][3,7]
    [3][2][4][1][5][7][3][7] ...
    [2,3][1,4][5,7]
    [1,2,3,4][5,7]
    [1,2,3,4,5,7]

time: big(o) => o(n log(n))
space: big(o) => o(n) 
```
* o (n ^ 2) - quadratic time
    * as the size of input increases there is a disproportionate increase in the amount of time/space it takes to complete.
    * nested loops (not adjacent loops)
    * When it is two separate arrays or loops, we have o(n * m)

```
indexOf 'puppy'.indexOf('u') => 1
        'puppy'.indexOf('upp') => 1
    
    function indexOf(str, substr){
        for(let i = 0; i < str.length - substr.length; i++){
            for(let j = 0; j < substr.length; j++){
                if(str[i + j] !== substr[j]){
                    break; 
                }
                if(j === substr.length - 1) return i;
            }
        }
    }

    o(n * m) ==> o(n * n)
```

* o (2 ^ n) ==> Best case for traveling salesman problem
    * Every option breaks into two parts for all n.
    * Fibonacci!!

```
    function fibonacci(n){
        if(n < 2) return 1; 
        return fibonacci(n - 2) + fibonaccia(n - 1);
    }
```

* o(n!) ==> traveling salesman problem.
    * for every n value we must go through (n - 1) ... through (n -2) ...

## Strategies for improvement
* Memoization: Cacheing results.
```
{
    1: 1,
    2: 1,
    3: 2,
    4: 3
}
```




