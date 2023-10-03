A queue is a linear data structure that follows the First-In, First-Out (FIFO) principle. It's similar to a line of people waiting for a service, where the first person in line gets served first. In a queue, elements are added at the rear (enqueue) and removed from the front (dequeue).

Here are the key characteristics and operations associated with a queue:

### Characteristics:

1. **First-In, First-Out (FIFO)**:
   - The first element added to the queue is the first one to be removed.

2. **Operations**:
   - `Enqueue`: Add an element to the rear of the queue.
   - `Dequeue`: Remove and retrieve the element from the front of the queue.
   - `Front`: Retrieve the element from the front of the queue without removing it.
   - `isEmpty`: Check if the queue is empty.
   - `Size`: Get the number of elements in the queue.

3. **Implementation**:
   - Queues can be implemented using arrays or linked lists.

4. **Applications**:
   - Process scheduling, breadth-first search, handling requests in web servers, print queues, etc.

### Operations:

#### 1. **Enqueue**:

- **Algorithm**:
   1. Create a new node or allocate memory for the new element.
   2. Set the data of the new element.
   3. Set the `next` pointer to point to null (since it's added to the rear).
   4. Update the `rear` pointer to point to the new element.

- **Code Example (C++ with Linked List)**:
   ```cpp
   void enqueue(Node*& front, Node*& rear, int data) {
       Node* newNode = new Node(data);
       newNode->next = nullptr;
       if (isEmpty(front)) {
           front = rear = newNode;
       } else {
           rear->next = newNode;
           rear = newNode;
       }
   }
   ```

#### 2. **Dequeue**:

- **Algorithm**:
   1. Check if the queue is empty. If it is, return an error or indication (e.g., -1).
   2. Create a temporary pointer to the front element.
   3. Update the front pointer to point to the next element.
   4. Retrieve and store the data of the front element.
   5. Delete the temporary pointer.

- **Code Example (C++ with Linked List)**:
   ```cpp
   int dequeue(Node*& front, Node*& rear) {
       if (isEmpty(front)) {
           return -1; // Queue is empty
       }
       Node* temp = front;
       int data = temp->data;
       front = front->next;
       delete temp;
       if (front == nullptr) {
           rear = nullptr; // If queue becomes empty
       }
       return data;
   }
   ```

#### 3. **Front**:

- **Algorithm**:
   - Simply return the data of the front element without modifying the queue.

- **Code Example (C++ with Linked List)**:
   ```cpp
   int frontValue(Node* front) {
       if (isEmpty(front)) {
           return -1; // Queue is empty
       }
       return front->data;
   }
   ```

#### 4. **isEmpty**:

- **Algorithm**:
   - Check if both the front and rear pointers are null, indicating that the queue is empty.

- **Code Example (C++ with Linked List)**:
   ```cpp
   bool isEmpty(Node* front) {
       return front == nullptr;
   }
   ```

#### 5. **Size**:

- **Algorithm**:
   - Traverse the queue and count the number of elements.

- **Code Example (C++ with Linked List)**:
   ```cpp
   int size(Node* front) {
       int count = 0;
       Node* current = front;
       while (current != nullptr) {
           count++;
           current = current->next;
       }
       return count;
   }
   ```

### Example Usage:

```cpp
int main() {
    Node* front = nullptr;
    Node* rear = nullptr;

    enqueue(front, rear, 10);
    enqueue(front, rear, 20);
    enqueue(front, rear, 30);

    cout << "Front element: " << frontValue(front) << endl;

    while (!isEmpty(front)) {
        cout << "Dequeued: " << dequeue(front, rear) << endl;
    }

    cout << "Is queue empty? " << (isEmpty(front) ? "Yes" : "No") << endl;

    return 0;
}
```

This will output:

```
Front element: 10
Dequeued: 10
Dequeued: 20
Dequeued: 30
Is queue empty? Yes
```

This example demonstrates basic operations in a queue implemented with a linked list

--------
A queue can be implemented using either an array or a linked list. Each representation has its own advantages and trade-offs.

### Array Representation of a Queue:

In this representation, a fixed-size array is used to store the elements of the queue. The front of the queue is typically at index 0, and the rear is at the last index.

**Characteristics**:
- **Fixed Size**: The size of the array is fixed, which means there is a maximum limit to the number of elements the queue can hold.
- **Efficient Access**: Accessing elements in an array is efficient because you can directly access an element using its index.

**Operations**:
1. **Enqueue**:
   - Add an element to the rear of the queue. This involves incrementing the rear index and placing the element at that index.

2. **Dequeue**:
   - Remove and retrieve the element from the front of the queue. This involves incrementing the front index.

3. **Front**:
   - Retrieve the element from the front of the queue without removing it. This is simply accessing the element at the front index.

4. **isEmpty**:
   - Check if the queue is empty. This is typically done by comparing the front and rear indices.

5. **isFull**:
   - Check if the queue is full. This is determined by comparing the rear index to the maximum size of the array.

**Example Code (C++)**:
```cpp
const int MAX_SIZE = 100; // Maximum size of the queue
int queue[MAX_SIZE];      // Array to hold queue elements
int front = -1, rear = -1; // Initialize front and rear indices

void enqueue(int data) {
    if (rear == MAX_SIZE - 1) {
        cout << "Queue Overflow" << endl;
        return;
    }
    if (front == -1) {
        front = 0;
    }
    queue[++rear] = data;
}

int dequeue() {
    if (front == -1) {
        cout << "Queue Underflow" << endl;
        return -1; // Return a sentinel value indicating underflow
    }
    int data = queue[front++];
    if (front > rear) {
        front = rear = -1; // Reset front and rear when queue becomes empty
    }
    return data;
}

int frontValue() {
    if (front == -1) {
        cout << "Queue is Empty" << endl;
        return -1; // Return a sentinel value indicating empty queue
    }
    return queue[front];
}

bool isEmpty() {
    return front == -1;
}

bool isFull() {
    return rear == MAX_SIZE - 1;
}
```

### Linked List Representation of a Queue:

In this representation, a linked list is used to store the elements of the queue. Each node in the linked list represents an element in the queue. The front of the queue is represented by the head of the linked list, and the rear is represented by the tail.

**Characteristics**:
- **Dynamic Size**: The size of the queue can dynamically grow or shrink based on the number of elements.

- **Efficient Enqueue and Dequeue**: Inserting and removing elements at the front and rear of a linked list is efficient.

**Operations**:
1. **Enqueue**:
   - Add an element to the rear of the queue. This involves creating a new node and updating the next pointer of the tail node.

2. **Dequeue**:
   - Remove and retrieve the element from the front of the queue. This involves updating the head pointer.

3. **Front**:
   - Retrieve the element from the front of the queue without removing it. This is simply accessing the data of the head node.

4. **isEmpty**:
   - Check if the queue is empty. This is typically done by checking if the head pointer is null.

**Example Code (C++)**:
```cpp
class Node {
public:
    int data;
    Node* next;

    Node(int val) : data(val), next(nullptr) {}
};

Node* front = nullptr;
Node* rear = nullptr;

void enqueue(int data) {
    Node* newNode = new Node(data);
    if (isEmpty()) {
        front = rear = newNode;
    } else {
        rear->next = newNode;
        rear = newNode;
    }
}

int dequeue() {
    if (isEmpty()) {
        cout << "Queue Underflow" << endl;
        return -1; // Return a sentinel value indicating underflow
    }
    Node* temp = front;
    int data = temp->data;
    front = front->next;
    delete temp;
    if (front == nullptr) {
        rear = nullptr; // If queue becomes empty
    }
    return data;
}

int frontValue() {
    if (isEmpty()) {
        cout << "Queue is Empty" << endl;
        return -1; // Return a sentinel value indicating empty queue
    }
    return front->data;
}

bool isEmpty() {
    return front == nullptr;
}
```

Both representations have their strengths and weaknesses, and the choice between them depends on the specific requirements and constraints of the application.

-----------
A queue can be implemented using either an array or a linked list. Each representation has its own advantages and trade-offs.

### Array Representation of a Queue:

In this representation, a fixed-size array is used to store the elements of the queue. The front of the queue is typically at index 0, and the rear is at the last index.

**Characteristics**:
- **Fixed Size**: The size of the array is fixed, which means there is a maximum limit to the number of elements the queue can hold.
- **Efficient Access**: Accessing elements in an array is efficient because you can directly access an element using its index.

**Operations**:
1. **Enqueue**:
   - Add an element to the rear of the queue. This involves incrementing the rear index and placing the element at that index.

2. **Dequeue**:
   - Remove and retrieve the element from the front of the queue. This involves incrementing the front index.

3. **Front**:
   - Retrieve the element from the front of the queue without removing it. This is simply accessing the element at the front index.

4. **isEmpty**:
   - Check if the queue is empty. This is typically done by comparing the front and rear indices.

5. **isFull**:
   - Check if the queue is full. This is determined by comparing the rear index to the maximum size of the array.

**Example Code (C++)**:
```cpp
const int MAX_SIZE = 100; // Maximum size of the queue
int queue[MAX_SIZE];      // Array to hold queue elements
int front = -1, rear = -1; // Initialize front and rear indices

void enqueue(int data) {
    if (rear == MAX_SIZE - 1) {
        cout << "Queue Overflow" << endl;
        return;
    }
    if (front == -1) {
        front = 0;
    }
    queue[++rear] = data;
}

int dequeue() {
    if (front == -1) {
        cout << "Queue Underflow" << endl;
        return -1; // Return a sentinel value indicating underflow
    }
    int data = queue[front++];
    if (front > rear) {
        front = rear = -1; // Reset front and rear when queue becomes empty
    }
    return data;
}

int frontValue() {
    if (front == -1) {
        cout << "Queue is Empty" << endl;
        return -1; // Return a sentinel value indicating empty queue
    }
    return queue[front];
}

bool isEmpty() {
    return front == -1;
}

bool isFull() {
    return rear == MAX_SIZE - 1;
}
```

### Linked List Representation of a Queue:

In this representation, a linked list is used to store the elements of the queue. Each node in the linked list represents an element in the queue. The front of the queue is represented by the head of the linked list, and the rear is represented by the tail.

**Characteristics**:
- **Dynamic Size**: The size of the queue can dynamically grow or shrink based on the number of elements.

- **Efficient Enqueue and Dequeue**: Inserting and removing elements at the front and rear of a linked list is efficient.

**Operations**:
1. **Enqueue**:
   - Add an element to the rear of the queue. This involves creating a new node and updating the next pointer of the tail node.

2. **Dequeue**:
   - Remove and retrieve the element from the front of the queue. This involves updating the head pointer.

3. **Front**:
   - Retrieve the element from the front of the queue without removing it. This is simply accessing the data of the head node.

4. **isEmpty**:
   - Check if the queue is empty. This is typically done by checking if the head pointer is null.

**Example Code (C++)**:
```cpp
class Node {
public:
    int data;
    Node* next;

    Node(int val) : data(val), next(nullptr) {}
};

Node* front = nullptr;
Node* rear = nullptr;

void enqueue(int data) {
    Node* newNode = new Node(data);
    if (isEmpty()) {
        front = rear = newNode;
    } else {
        rear->next = newNode;
        rear = newNode;
    }
}

int dequeue() {
    if (isEmpty()) {
        cout << "Queue Underflow" << endl;
        return -1; // Return a sentinel value indicating underflow
    }
    Node* temp = front;
    int data = temp->data;
    front = front->next;
    delete temp;
    if (front == nullptr) {
        rear = nullptr; // If queue becomes empty
    }
    return data;
}

int frontValue() {
    if (isEmpty()) {
        cout << "Queue is Empty" << endl;
        return -1; // Return a sentinel value indicating empty queue
    }
    return front->data;
}

bool isEmpty() {
    return front == nullptr;
}
```

Both representations have their strengths and weaknesses, and the choice between them depends on the specific requirements and constraints of the application.


--------------------
A double-ended queue, often abbreviated as deque, is a versatile linear data structure that supports insertion and deletion of elements from both ends. This means you can add or remove elements from both the front and the rear of the queue.

The main operations of a deque are:

1. **Insert at Front** (also known as `push_front` or `enqueue_front`): Add an element to the front of the deque.
2. **Insert at Rear** (also known as `push_back` or `enqueue_back`): Add an element to the rear of the deque.
3. **Remove from Front** (also known as `pop_front` or `dequeue_front`): Remove an element from the front of the deque.
4. **Remove from Rear** (also known as `pop_back` or `dequeue_back`): Remove an element from the rear of the deque.
5. **Get Front Element** (also known as `front`): Retrieve the element from the front without removing it.
6. **Get Rear Element** (also known as `back`): Retrieve the element from the rear without removing it.
7. **Check if Empty** (also known as `isEmpty`): Determine if the deque is empty.

### Example Code (C++):

```cpp
#include <iostream>
#include <deque>

int main() {
    std::deque<int> myDeque;

    myDeque.push_front(10); // Insert at front
    myDeque.push_back(20);  // Insert at rear

    std::cout << "Front element: " << myDeque.front() << std::endl;
    std::cout << "Rear element: " << myDeque.back() << std::endl;

    myDeque.pop_front(); // Remove from front
    myDeque.pop_back();  // Remove from rear

    std::cout << "Is deque empty? " << (myDeque.empty() ? "Yes" : "No") << std::endl;

    return 0;
}
```

In this example, we use the `std::deque` container from the C++ Standard Template Library (STL) to implement a deque. The operations are demonstrated as comments in the code.

Keep in mind that a deque is a versatile data structure and can be used in a wide range of scenarios where insertion and deletion operations are required at both ends.