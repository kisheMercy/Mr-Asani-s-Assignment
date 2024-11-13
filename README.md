# Mr-Asani-s-Assignment
#Inser operation
class BinaryTreeNode:
    def __init__(self, data):
        self.data = data
        self.leftChild = None
        self.rightChild = None

def insert(root, data):
    tempNode = BinaryTreeNode(data)
    
    # If tree is empty, create root node
    if root is None:
        root = tempNode
        return root
    
    current = root
    parent = None
    
    while True:
        parent = current
        
        # Go to left of the tree
        if data < parent.data:
            current = current.leftChild
            
            # Insert to the left
            if current is None:
                parent.leftChild = tempNode
                return root
        
        # Go to right of the tree
        else:
            current = current.rightChild
            
            # Insert to the right
            if current is None:
                parent.rightChild = tempNode
                return root

# Example usage:
root = None
root = insert(root, 10)
root = insert(root, 5)
root = insert(root, 20)
root = insert(root, 3)
root = insert(root, 7)

#Search operation
class BinaryTreeNode:
    def __init__(self, data):
        self.data = data
        self.leftChild = None
        self.rightChild = None

def search(root, data):
    current = root
    print("Visiting elements: ", end="")

    while current is not None and current.data != data:
        print(current.data, end=" ")
        
        if data < current.data:
            current = current.leftChild
        else:
            current = current.rightChild

    if current is None:
        print("\nData not found")
        return None
    
    print("\nData found")
    return current

# Example usage:
root = BinaryTreeNode(10)
root.leftChild = BinaryTreeNode(5)
root.rightChild = BinaryTreeNode(20)
root.leftChild.leftChild = BinaryTreeNode(3)
root.leftChild.rightChild = BinaryTreeNode(7)

result = search(root, 7)
if result is not None:
    print(f"Node found with data: {result.data}")
else:
    print("Node not found")


