# CMPS 2200  Recitation 01

**Name (Team Member 1):** Isaiah Kushner  
**Name (Team Member 2):** Davis Voelkel

In this recitation, we will investigate asymptotic complexity. Additionally, we will get familiar with the various technologies we'll use for collaborative coding.

To complete this recitation, follow the instructions in this document. Some of your answers will go in this file, and others will require you to edit `main.py`. All tests are in `test_main.py`.

## Install Python Dependency

We need Python library of "tabulate" to visualize the results in a good shape. Please install it by running 'pip install tabulate' or 'pip install -r requirements.txt' in Shell Tab of Repl.  

## Running and testing your code

- To run tests, from the command-line shell, you can run
  + `pytest test_main.py` will run all tests
  + `pytest test_main.py::test_one` will just run `test_one`
  + We recommend running one test at a time as you are debugging.

## Turning in your work

- Once complete, click on the "Git" icon in the left pane on repl.it.
- Enter a commit message in the "what did you change?" text box
- Click "commit and push." This will push your code to your github repository.
- Although you are working as a team, please have each team member submit the same code to their repository. One person can copy the code to their repl.it and submit it from there.

## Comparing search algorithms

We'll compare the running times of `linear_search` and `binary_search` empirically.

`Binary Search`: Search a sorted array by repeatedly dividing the search interval in half. Begin with an interval covering the whole array. If the value of the search key is less than the item in the middle of the interval, narrow the interval to the lower half. Otherwise, narrow it to the upper half. Repeatedly check until the value is found or the interval is empty.

- [ ] 1. In `main.py`, the implementation of `linear_search` is already complete. Your task is to implement `binary_search`. Implement a recursive solution using the helper function `_binary_search`. 

  Complete

- [ ] 2. Test that your function is correct by calling from the command-line `pytest test_main.py::test_binary_search`

  Complete

- [ ] 3. Write at least two additional test cases in `test_binary_search` and confirm they pass.

  Complete

- [ ] 4. Describe the worst case input value of `key` for `linear_search`? for `binary_search`? 

  For linear search, the worst case is an element that does not exist. For binary search, its a key that forces the list down to the smallest search space.

- [ ] 5. Describe the best case input value of `key` for `linear_search`? for `binary_search`? 

  Best case is the first element searched for either search function, meaning first in the list or middle of the list respectively.

- [ ] 6. Complete the `time_search` function to compute the running time of a search function. Note that this is an example of a "higher order" function, since one of its parameters is another function.

  Complete

- [ ] 7. Complete the `compare_search` function to compare the running times of linear search and binary search. Confirm the implementation by running `pytest test_main.py::test_compare_search`, which contains some simple checks.

- [ ] 8. Call `print_results(compare_search())` and paste the results here:

|        n |   linear |   binary |
|----------|----------|----------|
|       10 |    0.000 |    0.000 |
|      100 |    0.000 |    0.000 |
|     1000 |    0.000 |    0.000 |
|    10000 |    0.000 |    0.000 |
|   100000 |    9.232 |    0.000 |
|  1000000 |   41.864 |    0.000 |
| 10000000 |  444.715 |    1.963 |

- [ ] 9. The theoretical worst-case running time of linear search is $O(n)$ and binary search is $O(log_2(n))$. Do these theoretical running times match your empirical results? Why or why not?

  Because of external variables and the time taken to start up a program, real world results will never exactly match theoretical times. For linear search, we are supposed to get a 10x speed decline when the list size increases 10x, but the actual increase is slightly larger than that.

- [ ] 10. Binary search assumes the input list is already sorted. Assume it takes $\Theta(n^2)$ time to sort a list of length $n$. Suppose you know ahead of time that you will search the same list $k$ times. 
  + What is worst-case complexity of searching a list of $n$ elements $k$ times using linear search? $\Theta(kn)$
  + For binary search? $\Theta(n^2) + \Theta(klogn)$
  + For what values of $k$ is it more efficient to first sort and then use binary search versus just using linear search without sorting? $\Omega(n)=k$
