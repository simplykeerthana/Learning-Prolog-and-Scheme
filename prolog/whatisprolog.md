What is Prolog?

Prolog is a logic programming language that is mostly used for language associated with Artificial Intelligence and computational liguistics. 

- Prolog uses First-Order Lgic, and it is also known as a declarative programming language. 
- The program itself is represented as relationship like with facts and rules. 
- A computation is initiated by running a query over the relations or predicates declared.
- Predicate and horn clauses are Turing-complete.  

Syntax and Semantics

- Relations are declared by clauses. 
  - Pure Prolog are restricted to Horn clauses. 
- Queries will return true or false. 

Data Types

- term is the single data type it can be a atom, numbers, variables or compund terms. 
- compound terms are list, adn strings. 
  - list [1,2,3] or [red, green, blue]
  - strings "to be, or not ot be"

Rules and Facts

- There are two types or clauses: facts and rules. 
- A Rule is Head :- Body, it will read as "Head is true if Body is true". 
- A rules body consists calls to predicated which are called the rule's goals. 
- Operator , means and or conjuction of the goals. 
- Operator ; means or , disjuncttion 
- Conjucntion and Disjunction can appear only in body not the head of the rule. 

- Clauses with empty body are called facts like car(jeep) which is equivalent to car(jeep) :- true. 

- so if we query `?- car(jeep).`it will return Yes
- so if we query `?- car(X). ` it will return X = jeep

- clauses with bodies are also called rule. Example `motor(X) :- car(X).` if we query `?- moter(X).` it will return X = jeep. 

- As for as lists. using length we can determine the length of a list. `length(List, L)`. We can use append to append to list `append(ListA, ListB)`. We can also split a given list using `(append(X, Y, List), List)`. 

- Prolog has built in predicates to porcess input/output.
  - prdicate `write` would display a term on the screen. 

Execution

- Prolog execution strategy is called backtracking. Backtracking is a algorithm, it will abadon a candidate as soon as it determines that the candidate cannot possibly be completed to a valid solution. 


`mother_child(trude, sally).
 
father_child(tom, sally).
father_child(tom, erica).
father_child(mike, tom).
 
sibling(X, Y)      :- parent_child(Z, X), parent_child(Z, Y).
 
parent_child(X, Y) :- father_child(X, Y).
parent_child(X, Y) :- mother_child(X, Y).`

Take for example this scenario. 

- so we need to prove sibling(sally, erica) it will be Yes, so first query to look at is `(parent_child(Z, sally), parent_child(Z, erica)).`
- now we have to prove that `parent_child(Z, sally)` is true. since this matches the computer will check for `father_child(Z, sally)`, here Z will be tom then using binding. next we have to prove parent_child(tom, erica) and this matches the fact. 


Loops and Recursion 

- In prolog, iterative algorihtms can be implemented as recursive predicates. 


Hello world in Prolog

`?- write('Hello World!'), nl.`
`Hello World!`
`true.`
`?-`

