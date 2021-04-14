# Stacks & Queues

# Stacks

![images](https://i.ytimg.com/vi/Us4N22SEbM0/maxresdefault.jpg) 

- The stack implements LIFO i.e. Last In First Out.
- This means that the elements pushed last are the ones that are popped first.
- the method that can we deal with it in stack 
1. boolean empty()
    - Tests if this stack is empty. Returns true if the stack is empty, and returns false if the stack contains elements.
2. Object peek( )
    - Returns the element on the top of the stack, but does not remove it.
3. Object pop( )
    - Returns the element on the top of the stack, removing it in the process.
4. Object push(Object element)
    - Pushes the element onto the stack. Element is also returned.
5. int search(Object element)
    - Searches for element in the stack. If found, its offset from the top of the stack is returned. Otherwise, -1 is returned.

# Queues

![images](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRZ3l6eHjjFyFCFrMYfvICQagKLYWXqhhy9ng&usqp=CAU) 

- The queue implements FIFO i.e. First In First Out.
- This means that the elements entered first are the ones that are deleted first.
- a queue is open at both its ends
- One end is always used to insert data (enqueue) and the other is used to remove data (dequeue).
- Queue operations may involve initializing or defining the queue, utilizing it, and then completely erasing it from the memory.
    1. enqueue() − add (store) an item to the queue.
    2. dequeue() − remove (access) an item from the queue.
    3. peek() − Gets the element at the front of the queue without removing it.
    4. isfull() − Checks if the queue is full.
    5. isempty() − Checks if the queue is empty.