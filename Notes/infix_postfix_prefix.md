# Infix Postfix Prefix
**(p+q)'*'(m-n)**    -> Infix <br>
**'*'+pq-mn**      -> Postfix <br>
**pq+mn-'*'**      -> Prefix
---
## Infix to postfix
- Use a stack
- if char is operation push && operation is less than top element push it in stack
- if current charectar is greater than the top element remove it
- else char is ( push it
- if char is ) remove until you find )
