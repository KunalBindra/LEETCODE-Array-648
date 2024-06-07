# LEETCODE-Array-648
Sure! Let's perform a dry run of the provided code with an example to understand how it works step by step.

### Example:

- **Dictionary**: `["cat", "bat", "rat"]`
- **Sentence**: `"the cattle was rattled by the battery"`

### Step-by-Step Execution:

1. **Initialize TrieTree**:
    - Create a new instance of `TrieTree`, which initializes its `root` node.

2. **Insert words from dictionary into TrieTree**:
    - **Insert "cat"**:
        - Start at the root node.
        - For 'c' (index 2): Create a new node since there is no child at index 2.
        - For 'a' (index 0): Create a new node since there is no child at index 0.
        - For 't' (index 19): Create a new node since there is no child at index 19.
        - Mark the node corresponding to 't' as a leaf node.
    - **Insert "bat"**:
        - Start at the root node.
        - For 'b' (index 1): Create a new node since there is no child at index 1.
        - For 'a' (index 0): Create a new node since there is no child at index 0.
        - For 't' (index 19): Create a new node since there is no child at index 19.
        - Mark the node corresponding to 't' as a leaf node.
    - **Insert "rat"**:
        - Start at the root node.
        - For 'r' (index 17): Create a new node since there is no child at index 17.
        - For 'a' (index 0): Create a new node since there is no child at index 0.
        - For 't' (index 19): Create a new node since there is no child at index 19.
        - Mark the node corresponding to 't' as a leaf node.

3. **Replace words in the sentence**:
    - Split the sentence into tokens: `["the", "cattle", "was", "rattled", "by", "the", "battery"]`.
    - For each token, find the closest root from the TrieTree.
    
    - **Token "the"**:
        - Start at the root node.
        - For 't' (index 19): No child node, return "the".
    - **Token "cattle"**:
        - Start at the root node.
        - For 'c' (index 2): Move to the child node.
        - For 'a' (index 0): Move to the child node.
        - For 't' (index 19): Move to the child node which is a leaf, return "cat".
    - **Token "was"**:
        - Start at the root node.
        - For 'w' (index 22): No child node, return "was".
    - **Token "rattled"**:
        - Start at the root node.
        - For 'r' (index 17): Move to the child node.
        - For 'a' (index 0): Move to the child node.
        - For 't' (index 19): Move to the child node which is a leaf, return "rat".
    - **Token "by"**:
        - Start at the root node.
        - For 'b' (index 1): Move to the child node.
        - For 'y' (index 24): No child node, return "by".
    - **Token "the"**:
        - Same as the first token, return "the".
    - **Token "battery"**:
        - Start at the root node.
        - For 'b' (index 1): Move to the child node.
        - For 'a' (index 0): Move to the child node.
        - For 't' (index 19): Move to the child node which is a leaf, return "bat".

4. **Construct the final sentence**:
    - The transformed tokens are: `["the", "cat", "was", "rat", "by", "the", "bat"]`.
    - Join the tokens with spaces: `"the cat was rat by the bat"`.

### Conclusion:
The provided code correctly replaces words in a sentence with the shortest possible root words from a dictionary. The dry run demonstrates how the TrieTree is used to efficiently find and replace these words.
