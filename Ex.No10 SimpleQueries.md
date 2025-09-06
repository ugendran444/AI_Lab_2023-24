# Ex.No: 10  Logic Programming –  Simple queries from facts and rules
### DATE: 06-09-2025                                                                            
### REGISTER NUMBER : 212222060283
### AIM: 
To write a prolog program to find the answer of query. 
###  Algorithm:
 Step 1: Start the program <br> 
 Step 2: Convert the sentence into First order Logic  <br> 
 Step 3:  Convert the sentence into Horn clause form  <br> 
 Step 4: Add rules and predicates in a program   <br> 
 Step 5:  Pass the query to program. <br> 
 Step 6: Prolog interpreter shows the output and return answer. <br> 
 Step 8:  Stop the program.
### Program:
### Task 1:
Construct the FOL representation for the following sentences <br> 
1.	John likes all kinds of food.  <br> 
2.	Apples are food.  <br> 
3.	Chicken is a food.  <br> 
4.	Sue eats everything Bill eats. <br> 
5.	 Bill eats peanuts  <br> 
   Convert into clause form and Prove that John like Apple by using Prolog. <br> 
### Program:
```
likes(john,X):-food(X).
eats(sue,X):-eats(bill,X).
eats(bill,peanuts).
food(apple).
food(chicken).
```

### Output:
![Screenshot 2025-03-19 111719](https://github.com/user-attachments/assets/50998768-9e43-4624-aae3-6985b66518c6)

### Task 2:
Consider the following facts and represent them in predicate form: <br>              
1.	Steve likes easy courses. <br> 
2.	Science courses are hard. <br> 
3. All the courses in Have fun department are easy <br> 
4. BK301 is Have fun department course.<br> 
Convert the facts in predicate form to clauses and then prove by resolution: “Steve likes BK301 course”<br> 

### Program:
```
:- discontiguous likes/2.
have_fun_dept(bk301). 
likes(steve, X) :- easy(X).
hard(X) :- science_course(X).  
easy(X) :- have_fun_dept(X).
```

### Output:
![Screenshot 2025-03-19 111947](https://github.com/user-attachments/assets/79df4021-a042-4870-be59-9280b29661cd)

### Task 3:
Consider the statement <br> 
“This is a crime for an American to sell weapons to hostile nations. The Nano , enemy of America has some missiles and its missiles were sold it by Colonal West who is an American” <br> 
Convert to Clause form and prove west is criminal by using Prolog.<br> 
### Program:
```
crime(X):-american(X),weapon(Y),hostile(Z),sells(X,Y,Z).
weapon(X):-missile(X).
hostile(X):-enemy(X,Y).
enemy(nano,america).
sells(west,X,nano):-owns(nano,X),missile(X).
missile(m1).
owns(nano,m1).
american(west).
```

### Output:
![Screenshot 2025-03-19 112058](https://github.com/user-attachments/assets/8f85793e-58fe-4466-8d89-43cd95c8adb0)

### Result:
Thus the prolog programs were executed successfully and the answer of query was found.
