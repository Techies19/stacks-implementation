# stacks-implementation

### stack using queue
class Stack {
    queue<int> q;
public:
    void push(int x) {
        q.push(x);
        for (int i=1; i<q.size(); i++) {
            q.push(q.front());
            q.pop();
        }
    }
    void pop() {
        q.pop();
    }

    int top() {
        return q.front();
    }

    bool empty() {
        return q.empty();
    }
};
                                  
                                
### stack using array
class StackUsingArray {
	int *data;
	int nextIndex;
	int capacity;	
	public :
	StackUsingArray(int totalSize) {
		data = new int[totalSize];
		nextIndex = 0;
		capacity = totalSize;
	}
	// return the number of elements present in my stack
	int size() {
		return nextIndex;
	}
	bool isEmpty() {
		return nextIndex == 0;
	}
	// insert element
	void push(int element) {
		if(nextIndex == capacity) {
			cout << "Stack full " << endl;
			return;
		}
		data[nextIndex] = element;
		nextIndex++;
	}
	// delete element
	int pop() {
		if(isEmpty()) {
			cout << "Stack is empty " << endl;
			return INT_MIN;	
		}
		nextIndex--;
		return data[nextIndex];
	}
	int top() {
		if(isEmpty()) {
			cout << "Stack is empty " << endl;
			return INT_MIN;	
		}
		return data[nextIndex - 1];
	}
};

                                
