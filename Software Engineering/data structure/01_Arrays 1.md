

If we focus on the functionality of arrays at a high, semi-abstract level, the array data structure has a few key characteristics:
- It stores a collection of data.
- Its elements can be accessed by index.
- Elements don’t have to be accessed sequentially; that is, if I need the 10th element of an array, I can access it directly without having to read the 9 elements stored in the array before it.

Here’s a clean, simple explanation of those points with clear intuition:

---

## ✅ **1. Arrays are stored in one continuous block of memory**

When you create an array (like `int arr[5]`), the computer reserves **one uninterrupted chunk of memory** big enough to hold all elements.

Example:  
If an `int` takes **4 bytes**, then an array of 5 integers takes **20 bytes**, all placed next to each other:

```
| 4 bytes | 4 bytes | 4 bytes | 4 bytes | 4 bytes |
```

![[Pasted image 20251122153232.png]]

### **Why this is efficient?**

- **Fast access**: If you know the starting address and each element’s size, you can compute the address of any element instantly:
    
    ```
    address = base + index * size_of_type
    ```
    
- **Good for caching**: CPUs love sequential memory → better performance.
    

---

## ✅ **2. Arrays store elements of the same type**

This is required because:

- All elements must have **equal size**.
    
- The program must know how far to jump in memory to reach element `i`.
    

If the types varied, the compiler wouldn’t know how big each element is, destroying the fast O(1) indexing.

Example:

- If every element is 4 bytes → jump in fixed-size steps.
    
- If elements differ → you’d have to search sequentially, like a linked list → slow.
    

So, **same type = constant size = fast access**.

---

## ✅ **3. Array size must be known at creation (fixed size)**

Because the memory block is continuous, the system must know **exactly how large the block** should be before allocating it.

For example:

- You request:  
    `int arr[1000]`  
    → computer finds a free memory block big enough for **4000 bytes**.
    

If you try to “resize” it later, that would require:

1. Allocating a new, larger continuous block,
    
2. Copying old elements to the new location,
    
3. Freeing the old block.
    

This is too expensive → so **built-in arrays cannot grow**.

Dynamic structures like **lists, vectors, ArrayList, std::vector** handle resizing internally by allocating new arrays when needed.

---

## ⭐ Summary (super short)

|Property|Why it exists|
|---|---|
|**Continuous memory block**|Fast indexing, cache-friendly|
|**Same data type**|Fixed-size elements → instant address calculation|
|**Fixed size**|Need to know total block size for contiguous allocation|

