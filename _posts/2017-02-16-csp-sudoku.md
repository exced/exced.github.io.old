---
title:      "Constraint Satisfaction Problem"
---

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

Here is the simple backtrack example :

[Sources](https://github.com/exced/csp-sudoku)

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
Now we can use constraints to reduce the domain at each iteration and reduce the number of iterations.

### Arcs consistency : AC-3

Each time you test a value you propagate the constraints to neighbors and remove this value of their domains.
Now that you've changed the domain of neighbors, you have to propagate the change to their neighbors etc...
The process stops if any domain becomes unavalaible (0 possibility).

[Python sources](https://github.com/exced/CSP)

### Results

I tested the number of backtrack calls and here are the results on 5 grids :

![results](/img/2017-02-16-csp-sudoku/results.png)

4500 time less iterations on the hardest grid !
