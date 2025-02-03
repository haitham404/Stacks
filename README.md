# Stack 

📚 **Understand: What is a Stack?**
A stack is a linear data structure that follows the **LIFO (Last In, First Out)** principle. Imagine a stack of plates:
- You can only add a new plate on top.
- You can only remove the top plate first.

### **Key Operations:**
1. **Push**: Add an element to the stack.
2. **Pop**: Remove the top element from the stack.
3. **Peek**: View the top element without removing it.
4. **IsEmpty**: Check if the stack is empty.

---
#### **Stack ADT Operations:**
1. `push(i)`: Insert `i` at the top.
2. `pop()`: Remove and return the top element.
3. `peek()`: Return the top element without removing it.
4. `isEmpty()`: Return `true` if the stack is empty.
5. `isFull()`: Return `true` if the stack is full (for fixed-size stacks).

![Image](https://github.com/user-attachments/assets/c3f9957b-60ca-48a0-b467-85ab35193e5b)

---

### **Implementations**
- A stack can be implemented using **arrays** or **linked lists**.
1. **Stack Using Array**
 ```java

class Stack {
    private int arr[];
    private int top;
    private int capacity;

    Stack(int size) {
        arr = new int[size];
        capacity = size;
        top = -1;
    }

    // Push operation
    public void push(int i) {
        if (isFull()) {
            System.out.println("Stack Overflow");
            return;
        }
        arr[++top] = i;
    }

    // Pop operation
    public int pop() {
        if (isEmpty()) {
            System.out.println("Stack Underflow");
            return -1;
        }
        return arr[top--];
    }

    // Peek operation
    public int peek() {
        if (isEmpty()) {
            System.out.println("Stack is empty");
            return -1;
        }
        return arr[top];
    }

    // Check if stack is empty
    public boolean isEmpty() {
        return top == -1;
    }

    // Check if stack is full
    public boolean isFull() {
        return top == capacity - 1;
    }

    public void printStack() {
        for (int i = top; i >= 0; i--) {
            System.out.println(arr[i]);
        }
    }
}

```
2. **Stack Using Linked List**

```java

class Stack {
    private Node top;

    public Stack() {
        this.top = null;
    }

    // Push operation
    public void push(int data) {
        Node newNode = new Node(data);
        if (top == null) {
            top = newNode;
        } else {
            newNode.next = top;
            top = newNode;
        }
        System.out.println(data + " pushed to stack");
    }

    // Pop operation
    public int pop() {
        if (isEmpty()) {
            System.out.println("Stack Underflow");
            return -1;
        }
        int popped = top.data;
        top = top.next;
        return popped;
    }

    // Peek operation
    public int peek() {
        if (isEmpty()) {
            System.out.println("Stack is empty");
            return -1;
        }
        return top.data;
    }

    // Check if stack is empty
    public boolean isEmpty() {
        return top == null;
    }

    // Print the stack
    public void printStack() {
        if (isEmpty()) {
            System.out.println("Stack is empty");
            return;
        }
        Node current = top;
        System.out.println("Stack elements:");
        while (current != null) {
            System.out.println(current.data);
            current = current.next;
        }
    }
}

```

---
### **Java’s Built-in Stack Class**
 ```java
   import java.util.Stack;

public class BuiltInStackExample {
    public static void main(String[] args) {
        Stack<Integer> stack = new Stack<>();

        stack.push(10);
        stack.push(20);
        stack.push(30);

        System.out.println("Top element: " + stack.peek()); // Output: 30
        System.out.println("Popped element: " + stack.pop()); // Output: 30
        System.out.println("Is stack empty? " + stack.isEmpty()); // Output: false
    }
}

```

## **Examples**
1. **Balanced Parentheses Problem**:
   
    Our goal is to check if a given string has balanced parentheses. A string is considered balanced if:
    
      - Every opening parenthesis ((, {, [) has a corresponding closing parenthesis (), }, ]).
      - Parentheses are correctly nested, meaning that the first opened parenthesis must be closed first.
   
``` java

import java.util.Stack;

public class BalancedParentheses {
    public static boolean isBalanced(String str) {
        Stack<Character> stack = new Stack<>();

        for (char ch : str.toCharArray()) {
            if (ch == '(' || ch == '{' || ch == '[') {
                stack.push(ch);
            } else if (ch == ')' || ch == '}' || ch == ']') {
                if (stack.isEmpty()) {
                    return false;
                }
                char top = stack.pop();
                if (!isMatchingPair(top, ch)) {
                    return false;
                }
            }
        }
        return stack.isEmpty();
    }

    private static boolean isMatchingPair(char opening, char closing) {
        return (opening == '(' && closing == ')') ||
               (opening == '{' && closing == '}') ||
               (opening == '[' && closing == ']');
    }
}
```



3. **Reverse a String Using Stack**:


   our goal  is to reverse a given string


   ```java

import java.util.Stack;

public class ReverseString {
    public static String reverseString(String str) {
        Stack<Character> stack = new Stack<>();

        // Push all characters to stack
        for (char i : str.toCharArray()) {
            stack.push(i);
        }

        // Pop characters to get reversed string
        StringBuilder reversed = new StringBuilder();
        while (!stack.isEmpty()) {
            reversed.append(stack.pop());
        }

        return reversed.toString();
    }
}


   ```

---

