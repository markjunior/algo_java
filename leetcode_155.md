**155**. Min Stack
Design a stack that supports push, pop, top, and retrieving the minimum element in constant time.

* push(x) -- Push element x onto stack.
* pop() -- Removes the element on top of the stack.
* top() -- Get the top element.
* getMin() -- Retrieve the minimum element in the stack.



```
public class MinStack {
    Stack<Long> test= new Stack<Long>();
    long mini;
    /** initialize your data structure here. */
    public MinStack() {

    }

    public void push(int x) {
        if(test.empty()){
            test.push(0L);
            mini=x;
        }else{
            test.push(x-mini);
            if(x<mini){
                mini=x;
            }
        }
    }

    public void pop() {
        if(test.empty()){
            return;
        }
        long tmp=test.pop();
        if(tmp<0){
            mini=mini-tmp;
        }

    }

    public int top() {
        if(test.peek()>=0){
            return (int)(test.peek()+mini);
        }
            else{
                return (int)mini;
            }
    }

    public int getMin() {
        return (int)mini;
    }
}

/**
 * Your MinStack object will be instantiated and called as such:
 * MinStack obj = new MinStack();
 * obj.push(x);
 * obj.pop();
 * int param_3 = obj.top();
 * int param_4 = obj.getMin();
 */
```
```
public class MinStack {
    Stack<Integer> test= new Stack<Integer>();
    int mini=Integer.MAX_VALUE;
    /** initialize your data structure here. */
    public MinStack() {

    }

    public void push(int x) {
        if(mini>=x){
            test.push(mini);
            mini=x;
        }
        test.push(x);
    }

    public void pop() {

        if(test.pop()==mini){
            mini=test.pop();
        }

    }

    public int top() {
        return test.peek();
    }

    public int getMin() {
        return mini;
    }
}

/**
 * Your MinStack object will be instantiated and called as such:
 * MinStack obj = new MinStack();
 * obj.push(x);
 * obj.pop();
 * int param_3 = obj.top();
 * int param_4 = obj.getMin();
 */  
 ```
