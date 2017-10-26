# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: Constraint propagation reduces the problem domain, and usually used iteratively with a search algorithm to reach a solution. Naked twins is a strategy of applying constraint propagation to Sudoko puzzle solving by taking advantage of the puzzle rules. First two boxes are selected that have exactly same two values and in the same peer proximity i.e. same, row, column, or three by three box. We can not know for sure which box has either value, but we know for sure that no other box in the same constraint peer can have either value, so we eliminate these values and get closer to the solution.
The implementation is done via filtering the puzzle for boxes with two potential values then searching for boxes with exactly same value in same peer proximity. Set comparison is used to account for out of order placement. Then we iterate through twin pairs and remove any occurance of their values from other peers.

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: We add the two main daignoal lines of the puzzle to the list of row, column, and 3x3 box constraints. This forces the puzzle solver to consider the existance of a number only once in main daigonal lines in addition to the previous constaints.

### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project. 
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solution.py` - Fill in the required functions in this file to complete the project.
* `test_solution.py` - You can test your solution by running `python -m unittest`.
* `PySudoku.py` - This is code for visualizing your solution.
* `visualize.py` - This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the `assign_value` function provided in solution.py

### Submission
Before submitting your solution to a reviewer, you are required to submit your project to Udacity's Project Assistant, which will provide some initial feedback.  

The setup is simple.  If you have not installed the client tool already, then you may do so with the command `pip install udacity-pa`.  

To submit your code to the project assistant, run `udacity submit` from within the top-level directory of this project.  You will be prompted for a username and password.  If you login using google or facebook, visit [this link](https://project-assistant.udacity.com/auth_tokens/jwt_login) for alternate login instructions.

This process will create a zipfile in your top-level directory named sudoku-<id>.zip.  This is the file that you should submit to the Udacity reviews system.

