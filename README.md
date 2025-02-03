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

![Image](https://github.com/user-attachments/assets/ace21835-a281-444c-9eea-e2f6e97baf00)


---
#### **Stack ADT Operations:**
1. `push(i)`: Insert `i` at the top.
2. `pop()`: Remove and return the top element.
3. `peek()`: Return the top element without removing it.
4. `isEmpty()`: Return `true` if the stack is empty.
5. `isFull()`: Return `true` if the stack is full (for fixed-size stacks).

![Image](https://github.com/user-attachments/assets/c3f9957b-60ca-48a0-b467-85ab35193e5b)

---

### **Key Points:**
- A stack can be implemented using **arrays** or **linked lists**.
- The **time complexity** for `push()` and `pop()` is **O(1)**.
- The **space complexity** depends on the implementation (**O(n)** for arrays).

---

## **Implementations**
1. **Stack Using Array**: [ArrayStack/Stack.java](ArrayStack/Stack.java)
2. **Stack Using Linked List**: [LinkedListStack/Stack.java](LinkedListStack/Stack.java)
3. **Balanced Parentheses Problem**: [BalancedParentheses/BalancedParentheses.java](BalancedParentheses/BalancedParentheses.java)
4. **Reverse a String Using Stack**: [ReverseString/ReverseString.java](ReverseString/ReverseString.java)
5. **Java’s Built-in Stack Class**: [BuiltInStack/BuiltInStackExample.java](BuiltInStack/BuiltInStackExample.java)

---

