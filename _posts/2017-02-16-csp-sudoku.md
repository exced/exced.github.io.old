---
title:      "Constraint Satisfaction Problem"
---

[Github link](https://github.com/exced/csp-sudoku)

### Definition of CSP

In a CSP we have :
1. Variables
2. Domain : possible values of variables
3. Constraints

What about our sudoku problem ?
1. There are 81 variables in a 9x9 sudoku
2. Domain : [1..9]
3. Constraints : Only one occurence of a number in each row, each colum and unit.

### Sudoku - solver
We use a simple backtracking algorithm to solve the problem.

We have implemented the sudoku with a graph : 
- Vertex : Variable
- Edges : Constraint between 2 variables (aka binary constraint)

{% highlight ocaml linenos %}
let rec backtrack ltodo = 
match ltodo with
    | [] -> display (); (* Found a solution *)
    | h::t ->
        List.iter (fun n ->
            if (not (invalid (G.V.label h).x (G.V.label h).y n)) then
                (G.Mark.set h n;
                backtrack t;
                G.Mark.set h 0;
        )) domain;;
{% endhighlight %}

We iterated through the domain of each variables to solve the sudoku.
Now we can use constraints to reduce the domain at each iteration.


### Results : 
- simple backtrack : thousands of tests
- backtrack with AC-3 constraint propagation : number of blank variables tests (strict minimum)

