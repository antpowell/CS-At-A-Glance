# CS At A Glance

## Data Structures/Algorithms

### Arrray

1. Contiguous block of memory.
2. All same size.
3. 0 base indexing.
4. Lookup by index O(1).
5. Lookup by value O(n).
6. Append to simple array O(n), because of copy.
7. Prepend to simple array O(n), because of copy.
8. Insertion into simple array O(n), because of copy.
9. Remove into simple array O(n), because of copy.

#### GOOD FOR

When constant lookup is needed and an index is avaliable.

#### NOT GOOD FOR

### Dynamic Array

1. Contigouse block of memeory.
2. All same size.
3. 0 base indexing.
4. Lookup by index O(1).
5. Lookup by value A(1).
6. Append to simple array A(1).
7. Prepend to simple array O(n).
8. Insertsion into simple array O(n).
9. Remove into simple array A(1).

#### GOOD FOR

Instances where you don't know how much space you will have or need.

#### NOT GOOD FOR

Saftey Critical Real Time, because of the instances when O(n) hits.

### List

1. Singly

   1. Lookup by index O(n).
   2. Lookup by value O(n).
   3. Append O(n), if pointer to end is present O(1).
   4. Prepend O(1).
   5. Insert in between list O(n), **(general case)**.
   6. Insert in between list O(1), **(if given pointer to exact node)**.

2. Doubley

### Stack

### Queue

### Dequeue

1. Dynamic Array with allocation on both sides, front and back.

### Priority Queue

### Tree (BBST)

### Heap

#### GOOD FOR

Priority Que implementation.

#### NOT GOOD FOR

### Hash Map

### Binary Search

### Merge Sort

### Quick Sort

### Bucket Sort

### MSD/LSD/ Radix Sort

### Basic Graph Search

### Invariants

### Recursion/TCO

#### Fibanocci: API-preserving wrapper

- Brute Force
  1. Solve for base case
  2. Solve for individual problem
  3. Individual problems to repeat reducing the problem to simpler forms until base case is met
  - Python
    ```python
    def fib(n):
    # base cases
     if(n == 0 ):
       return 0
     if(n == 1):
       return 1
      # solution for individual problem
     return fib(n-1)+fib(n-2)
    ```
  - Javascript
    ```javascript
    const fib = function(n) {
    	// base cases
    	if (n === 0) return 0;
    	if (n === 1) return 1;
    	// solution for individual problem
    	return fib(n - 1) + fib(n - 2);
    };
    ```
- Memoization

  1. Apply steps from 'Brute Force' method
  2. Add memory to hold repetitive data
  3. Preserve API

  - Python

    ```python
    # outer calling function retains API requirements
    def fib(n):
    # setup memory to hold repetition
     memo = [None] * n
     # same old brute force with small tweaks
     def fib_inner(n, memo):
      if memo[n] is None:
        if n == 0:
          memo[n] = 0
        elif n == 1:
          memo[n] = 1
        else:
          memo[n] = fib_inner(n-1, memo) + fib_inner(n-2, memo)
      return memo[n]

     return fib_inner(n, memo)
    ```

  - Javascript

    ```javascript
    const fib = function(n) {
    	// setup memory to hold repetition
    	const memo = [];

    	// same old brute force with small tweaks
    	const fib_inner = function(n, memo) {
    		if (memo[n] === undefined) {
    			if (n === 0) memo[n] = 0;
    			else if (n === 1) memo[n] = 1;
    			else memo[n] = fib_inner(n - 1, memo) + fib_inner(n - 2, memo);
    		}
    		return memo[n];
    	};
    	return fib_inner(n, memo);
    };
    ```

#### Tail Call Optimization(TCO)

1. Recursive calling function must not include manipulating the data

- Python

  ```python
  def fib(n):
    def fib_inner(n, first, second):
      if n == 0:
        return first
      if n == 1:
        return second
      # notice second call
      return fib_inner(n, first+second, second)

    return fib_inner(n, 0, 1);
  ```

- Javascript

  ```javascript
  const fib = function(n) {
  	const fib_inner = function(n, first, second) {
  		if (n === 0) return first;
  		if (n === 1) return second;
  		return fib_inner(n, first + second, second);
  	};
  	return fib_inner(n, 0, 1);
  };
  ```

- Closed Form Expression
  - Python
    ```python
    def fib(n):
     if(n == 0 ):
       return 0
     if(n == 1):
       return 1
     return fib(n-1)+fib(n-2)
    ```
  - Javascript
    ```javascript
    const fib = function(n) {
    	if (n === 0) return 0;
    	if (n === 1) return 1;
    	return fib(n - 1) + fib(n - 2);
    };
    ```

### Dynamic Programming

This is one way to find optimal answers to problems.

Must haves:

1. repeated independent sub-problems (allows use of memoization)
2. optimal sub-structure (Optimization)

   1. combine optimal solution to sub-problems into an optimal solution to current problem

   ```python

   ```

#### GOOD FOR

Finding the optimal solution i.e. (find the largest, smallest)

#### NOT GOOD FOR

### Graphs

$$
n(n+1)/n^2 = \sum_1^n 1+2+3+4+...+n-1+n
$$

## Database

### Basic SQL

### Tables/Joins

### Indexes

### Transactions

### Isolation Levels

### Migrations

### Views

### NoSQL Basics

## Software Concepts

### Object, Classes, Types

### Constructor/Destructor

### Methods

### Polymorphism

### Iteration

### Higher Order Functions

### Concurrency/Parrallelism

### Pass By Reference, Pass By Value

### Stack, Heap

### Big O

### Immutability

### Functinal

### Base 2, 8, 10, 16

### Recursion

## Math

### Algebra, Geometry, Trigonometry

### Basic Calculus

### Basic Probability

### Basic Linear Algebra

## Questions to code

1. Given a linked list tell me if it is cyclic or not.
2. Insert a node into the middle of a linked in.
