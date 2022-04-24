# DIGITAL ASSIGNMENT : Merkle Tree 

### Name: Bella Babu
### Reg.No:20BCE0558

## **Introduction:**
_Merkle tree is a tree data structure where non-leaf nodes are a hash of its child nodes and leaf nodes are a hash of a block of data. Also known as a hash tree is a data structure used for data verification and synchronization. All the leaf nodes are at the same depth and are as far left as possible. It maintains data integrity and uses hash functions for this purpose.⋅⋅
_Merkle tree is a fundamental part of blockchain technology. It is a mathematical data structure composed of hashes of different blocks of data, and which serves as a summary of all the transactions in a block. It also allows for efficient and secure verification of content in a large body of data. It also helps to verify the consistency and content of the data. Both Bitcoin and Ethereum use the Merkle Trees structure. ⋅⋅
## **Architecture:**
⋅⋅*	**Hash function** is a function that takes a set of inputs and maps them into a table or data structure. The output generated by the hash function is unique for every input. This helps in fingerprinting data. The hash functions vary from one application to another.
**Merkle tree representation**
![image](https://user-images.githubusercontent.com/76433840/164987009-dd5ff419-ecfe-44de-a0b3-982886a081a4.png)
 
**Structure of the node of the binary Merkle tree**
⋅⋅⋅It contains four variables:
⋅⋅*	It contains a key variable.
⋅⋅*	It contains a value variable
⋅⋅*	It contains two links.

## **Algorithm:**
**a).	Find function :**
⋅⋅⋅Step 1: We will take the tree and key as parameters.
⋅⋅⋅Step 2: If the tree is null then we will return null.
⋅⋅⋅Step 3: If the tree->key is equal to the key we will return the tree.
⋅⋅⋅Step 4: If the key is smaller than tree->key then we will return find(tree->left, key)
⋅⋅⋅Step 5: else return find (tree->right, key)
**b).	Add node function:**
...Step 1: We will take key and value as parameters.
...Step 2: Take the hash(key) and store it in a variable called index.
...Step 3: store (struct node*) arr[index].head in a pointer called tree of datatype node.
...Step 4: create a new node with its key as key and value as value and both links as null.
...Step 5: If the tree is null then assign the new node to the head and increment the size by 1.
...Step 6: If the tree is not null then we will check if the key is already present in the tree using the find function.
...Step 7: If the key is already present in the tree then we will update the value.
...Step 8: If it is not present in the tree then we will use the insert function to insert the element.
**c)	Insert function.**
...Step 1: It will take tree and item pointers of node data type as parameters.
...Step 2: If item->key is smaller than tree->key and tree->left is null then assign the item to tree->left.
...Step 3: If item->key is smaller than tree->key and tree->left is not null then call insert function with tree->left and item as parameters.
...Step 4: If item->key is greater than tree->key and tree->right is null then assign the item to tree->right.
...Step 5: If item->key is greater than tree->key and tree->right is not null then call insert function with tree->right and item as parameters.

**d)	Delete a node function**
...Step 1: We will take a key as a parameter.
...Step 2: Take the hash(key) and store it in a variable called index.
...Step 3: store (struct node*) arr[index].head in a pointer called tree of datatype node.
...Step 4: If the tree is null then the key is not present.
...Step 5: If the tree is not null then we will check if the key is already present in the tree using the find function.
...Step 6: If the find function returns null then the key is not present in the tree.
...Step 7: If it is not null then we will use the remove function to delete the element.
**e)Remove function.**
Step 1: It will take tree and key as parameters.
...Step 2: If the tree is null then return null.
...Step 3: If the key is smaller than the tree->key then tree->left is equal to remove (tree->left, key) and return tree.
...Step 4: If the key is greater than the tree->key then tree->right is equal to remove (tree->right, key) and return tree.
...Step 5: else if the tree->left is equal to null and the tree->right is equal to null then decrement the size and return tree->left.
...Step 6: else if the tree->left is not equal to null and the tree->right is equal to null then decrement the size and return tree->left.
...Step 7: else if tree->left is equal to null and tree->right is not equal to null then decrement the size and return tree->right.
...Step 8: else assign tree->left to a pointer called left of data type node.
...Step 9: While left->right is not equal to null, left is equal to left->right.
...Step 10: tree->key is equal to left->key.
...Step 11: tree->value is equal to left->value.
...Step 12: tree->left is equal to remove(tree->left, tree->key).
...Step 13: Return tree.

## **Applications of Merkle tree:**
...a)	Apache Cassandra uses Merkle Trees to detect inconsistencies.
...b)	Git uses a merkle tree to store its data.
...c)	Ethereum uses a Merkle Patricia Trie.
...d)	It is a fundamental part of the blockchain.

