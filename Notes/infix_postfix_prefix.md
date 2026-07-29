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

## Code
```java
import java.util.*;
public class Main
{
	public static void main(String[] args) {
		String a = "(p+q)*(m-n)";
		ArrayDeque<Character> stack = new ArrayDeque<>();
        String b ="";
        for(int i=0;i<a.length();i++){
           char ch = a.charAt(i);
           
           if(ch == '(') stack.push(ch);
           
           else if(ch>='A' && ch<='Z' ||ch>='a' && ch<='z' ||ch>='0' && ch<='9'){
              b = b+ch;
           }
           
           else if(stack.isEmpty() || priority(ch)>=priority(stack.peek()) && ch !='('){
               stack.push(ch);
           }
           
           else if(ch==')'){
                while(!stack.isEmpty() && stack.peek()!='('){
                    b =b+stack.peek();
                    stack.pop();
                }
                    stack.pop();
            }
           
           else {
                while(priority(ch)<priority(stack.peek())){
                   b =b+stack.peek();
                   stack.pop();
                }
            }
            
	    }
	    while(!stack.isEmpty()){
	        b=b+stack.pop();
	    }
	    System.out.print(b);
	}
	static int priority(char ch){
	    if(ch == '+'|| ch == '-') return 1;
	    else if(ch == '/' || ch == '*') return 2;
	    else if (ch == '^') return 3;
	    return -1;
	}
}
```
