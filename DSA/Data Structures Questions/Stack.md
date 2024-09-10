
1. What is  stack?
A stack is a linear data structure that follows the Last-In-First-Out principle. It is like a vertical tower.
push() to add to the top 
pop() to remove from the top

2. What operations are performed on a stack?
push -> insert an element
pop -> remove top element
peek -> view top element

3. How is a stack implemented in an array?
A stack can be implemented in an array by maintaining a pointer to the top of the stack

4. What is time complexity of stack operations?
All of them have O(1).

5. What are the applications of a stack?
function calls, recursion, expression evaluation and parsing

6. What is stack overflow?
when stack exceeds its allocated memory

7. what is stack underflow?
When a stack is empty and a pop is attempted

8. what is a postfix expression?
an expression where the operator follows the operand.

9. How can stacks be used to evaluate postfix expressions?
pushing operands into the stack and performing operations when operations are encountered
(3+4)×5−6

The equivalent postfix expression would be: 
34+5×6−

push 3 then 5,
pop both and + them. push 7 in
push 5
pop 7 and 5 and multiply. push  35
pop 35 and 6. 35 -6.
push 29.
29 final number


operands are values and operators are operation symbols

10. What is a prefix expression?
operator precedes the operands

11. How can a stack be used to evaluate a prefix expressions?
pushing operators onto the stack and performing operations when operands are encountered.

prefix expression: `- * + 3 4 5 6`

push all numbers into stack
pop them and perform the operations


12. How can a stack be used to check for parenthesis?
- initialise stack
- traverse expression from left to right
- if char is open parenthesis, push into stack
	-  if stack is empty, there is  no corresponding parenthesis
	-  if not empty, pop top element.Check if the current close parenthesis matches the top element. if not then it is not balanced
- After traversal, if stack is empty, the expression if balance. Otherwise its not.