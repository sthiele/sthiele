+++
title = "PyASP basics"
date = 2015-10-01

[taxonomies]
tags = ["ASP"]
+++

This post explains the basics on how to use the PyASP library.
<!-- more -->

I assume that `pyasp` is already installed on the system.
This tutorial has been tested with Python 3 and [pyasp 1.4.1](https://pypi.python.org/pypi/pyasp/1.4.1).
You can download the logic programs that are used in this example here
-> [queens.lp](queens.lp) and [facts.lp](facts.lp)

* Import the library

  ```python
  from pyasp.asp import *
  ```

* Create a solver object.

  Before creating a solver object you need to declare what options your solver should run with. There are two kind of options the options for the grounder (see gringo documentation) and the options for the solver (see clasp documentation). In this example our only solver option is '2' which means we are looking for atmost 2 solutions.
  ```python
  goptions = ''
  soptions = '2'
  solver   = Gringo4Clasp(gringo_options=goptions, 
                          clasp_options=soptions)
  ```

* Running the solver on some input.

  Just like gringo the run method of the solver object accepts a list of input files. Here we use the encoding of the queens problems and solve it for a size of 10 as declared in facts.lp.
  ```python
  encoding = 'queens.lp'
  facts    = 'facts.lp'
  result   = solver.run([encoding, facts],
                        collapseTerms=True,
                        collapseAtoms=False)
  ```

  The result is a list of the solutions as TermSets.

  ```python
  print(result)
  [TermSet({Term('q',['8','3']), Term('q',['10','9']), Term('q',['1','1']), Term('q',['3','4']), Term('q',['6','2']), Term('q',['5','7']), Term('q',['2','10']), Term('q',['7','5']), Term('q',['4','8']), Term('q',['9','6'])}), 
   TermSet({Term('q',['10','9']), Term('q',['8','6']), Term('q',['6','3']), Term('q',['3','4']), Term('q',['5','7']), Term('q',['9','5']), Term('q',['1','1']), Term('q',['7','2']), Term('q',['4','8']), Term('q',['2','10'])})]
  ```

* Create your own set of facts.

  You can also create your own facts from within python and feed it as input to the solver. So far we have solved the 10-queens problem. Now we create a new set of facts including d(11) and solve the 11-queens problem.
 
  ```python
  newfacts = TermSet()
  newterm  = Term('d', ["11"])
  newfacts.add(newterm)
  result   = solver.run([encoding, facts, newfacts.to_file()],
                        collapseTerms=True, 
                        collapseAtoms=False)
  ```

  Now the result contains 2 solutions to the 11-queens problem.

  ```python
  print(result)
  [TermSet({Term('q',['11','11']), Term('q',['10','8']), Term('q',['5','2']), Term('q',['6','1']), Term('q',['4','9']), Term('q',['2','5']), Term('q',['8','4']), Term('q',['7','6']), Term('q',['9','10']), Term('q',['3','7']), Term('q',['1','3'])}),
   TermSet({Term('q',['1','3']), Term('q',['2','7']), Term('q',['5','2']), Term('q',['3','1']), Term('q',['11','11']), Term('q',['9','10']), Term('q',['4','8']), Term('q',['10','5']), Term('q',['7','6']), Term('q',['6','9']), Term('q',['8','4'])})]
  ```

* Parse and pretty print your solutions.

  ```python
  for s in result : 
    for a in s :
      args= ",".join(a.args())
      print(a.pred(),'(',args,')',sep='',end=' ')
    print()

  q(11,11) q(10,8) q(5,2) q(6,1) q(4,9) q(2,5) q(8,4) q(7,6) q(9,10) q(3,7) q(1,3) 
  q(1,3) q(2,7) q(5,2) q(3,1) q(11,11) q(9,10) q(4,8) q(10,5) q(7,6) q(6,9) q(8,4) 
  ```
