# N-ary Tree Preorder Traversal

### Problem - 

Given the root of an N-ary Tree, populate and return a list that contains all the elements of the N-ary tree in an preorder fashion.

Definition of a Node &rarr; 

```
class Node {
    public int val;
    public List<Node> children;

    public Node() {}

    public Node(int _val) {
        val = _val;
    }

    public Node(int _val, List<Node> _children) {
        val = _val;
        children = _children;
    }
}
```

---

### Algorithm -

Preorder traversal ⇒ root &rarr; left &rarr; right

*solve( )*</br>
Step 1 - Base condition for recursive function - if the current root node has an empty children list, that is, root.children = null, then we return the list.</br>
Step 2 - Since we are required to perform preorder traversal, first add the '*val*' of the current node to the list.</br>
Step 3 - Recursively call the method *solve( )* for each of the children of the current root node and pass that children node as the respective root node in each call.</br>
Step 4 - Return the list.</br>

---

### JAVA logic to solve the problem - 

```
public ArrayList<Integer> solve(Node root, ArrayList<Integer> list){
    if(root.children == null){
        return list;
    }
    list.add(root.val);
    for(int i = 0; i < root.children.size(); i++){
        solve(root.children.get(i), list);
    }
    return list;
}
public List<Integer> preorder(Node root) {
    ArrayList<Integer> list = new ArrayList<>();
    if(root == null) return list;
    return solve(root, list);
}
```

---

<h3>Time complexity - </h3>Each node is visited exactly once, hence, time complexity is <strong>O(N)</strong>, where N is the number of nodes, that is, the size of tree.
</br>
<h3>Space complexity - </h3>The entire tree is stored in the list, therefore, <strong>O(N)</strong>.
