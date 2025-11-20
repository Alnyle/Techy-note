
## So It's First Generate a Random Weights For Each Word And Store Them For Easy Access?

Exactly ✅

When you create the `Embedding` layer, Keras:

1. **Creates an embedding matrix** of shape:
    
    ```
    (vocab_size, embedding_dim)
    ```
    
    * Each row = one word in the vocabulary.
        
    * Each column = one dimension in the embedding vector.
        
2. **Fills it with random numbers** (usually small values) using a weight initializer (default: `uniform(-0.05, 0.05)` for embeddings).
    
3. **Stores it in memory** so that when you pass in a word’s index (like `0` for `"king"`), it can instantly **look up** the corresponding row.
    
4. **Updates those weights during training** via backpropagation so that similar words get similar vectors.
    

* * *

So initially, it’s like this random dictionary:

| Word | Vector (random at start) |
| --- | --- |
| king | [ 0.02, -0.11, 0.04 ] |
| queen | [ -0.07, 0.05, 0.09 ] |
| dog | [ 0.01, -0.02, 0.08 ] |

And after training, it becomes:

| Word | Vector (learned meaning) |
| --- | --- |
| king | [ 0.21, 0.48, -0.10 ] |
| queen | [ 0.22, 0.45, -0.09 ] |
| dog | [ -0.31, 0.02, 0.27 ] |



