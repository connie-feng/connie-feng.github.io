---
layout: page
title:  "Technical Interview Study Guide"
date:   2020-06-08
categories:
  - blog
  - tech
teaser: "WIP: Building a study guide for when I need to start doing tech interviews again."
---

## Concepts

#### Big O Notation
1. Time
* think about how runtime changes as N gets bigger
* O(1) - constant
* O(N) - linear
* O(logN) - cutting the problem space in half each time (binary search)
* O(NlogN) - merge sort
* O(branches^depth) - recursive functions
* it's possible for O(N) to run faster than O(1) for specific inputs
* do this, then when you're all done, do that - add runtimes
* do this for each time you do that - multiply runtimes
* if there are multiple inputs, don't use N for all of them!

2. Space
* O(N) space - creating array of size n
* O(N^2) space - creating a two-dimensional array of size NxN
* [stack space in recursive calls](https://py3.codeskulptor.org/#user307_IR2jhP5XNx_0.py){:target="_blank"}

#### Stack vs. Heap Allocation
* heap used when amount of memory required is not known in advance
* known by the compiler at compile time typically goes on the stack; dynamically allocated at runtime - on the heap

#### TODO
* bit manipulation
* recursion
* dynamic programming

#### Compiled vs. Interpreted Language
* compiled language - can optimize, makes the code more efficient
* interpreted - has to go line by line

***

## Data Structures
* arrays
* linked lists
* trees, tries, graphs
* stacks & queues
* heaps
* hashmaps


#### Hashmaps
* simple implementation: array of linked lists + hash code function
* O(1) lookup time

#### Arrays (resizable)
* O(1) insertion time (amortized)

#### Array vs. Linked List
* arrays are good for random access
* linked lists are good for adding or removing items (array has to resize and copy over), or when you're not sure how many items will be in the list

***

## Algorithms
* BFS
* DFS
* [binary search](http://tpcg.io/ZNXRVT){:target="_blank"}
* [merge sort](http://tpcg.io/K5POW9){:target="_blank"}
* [quick sort](http://tpcg.io/PSACYA){:target="_blank"}
* BUD optimization (bottlenecks, unnecessary work, duplicated work)

## Notes
* point out any error checking that you'd do

#### TODO
* DFS vs. BFS
* abstract vs. interface
* dynamic programming
* [longest palindrome](http://www.codeskulptor.org/#user40_9kU6XL8njr_1.py){:target="_blank"}
* [pascal's triangle](http://www.codeskulptor.org/#user40_RUTIiY3yBb_1.py){:target="_blank"}
* [fibonacci](http://www.codeskulptor.org/#user40_5HpDWjI6xF_1.py){:target="_blank"}
* [roman numerals](https://py3.codeskulptor.org/#user305_bZoAtXI4Pd_0.py){:target="_blank"}
* much much more

## Questions
* What are your favorite things about working here?
* How would you describe the company culture?
* What does a typical day look like for you?
* What typical meetings would I be expected to attend?
* What is your expectation for a successful candidate to get up to speed?
* What did the company do during the 2020 pandemic to help manage and support employees?
