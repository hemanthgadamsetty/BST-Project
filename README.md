BinarySearchTreeDemo 
Overview
This Java program demonstrates basic operations on a Binary Search Tree (BST), including insertion, search, and deletion of elements. It also includes methods for traversing the tree in in-order, pre-order, and post-order sequences. The program provides a command-line interface for users to interact with the BST.

Features
Insert elements into the BST.
Search for an element in the BST.
Delete an element from the BST.
Display the BST elements in in-order, pre-order, and post-order sequences.
Prerequisites
Java Development Kit (JDK) installed on your machine.
An IDE or a text editor to write and run Java code.
Command-line interface or terminal to execute the program.
Classes and Methods
TreeNode
The TreeNode class represents a node in the BST.

Attributes:
int value: The value stored in the node.
TreeNode leftChild, rightChild: References to the left and right children of the node.
Constructor:
TreeNode(int item): Initializes a new node with the given value.
BinarySearchTreeOperations
The BinarySearchTreeOperations class contains methods for performing operations on the BST.

Attributes:
TreeNode root: The root node of the BST.
Constructor:
BinarySearchTreeOperations(): Initializes an empty BST.
Methods:
void addValue(int value): Adds a value to the BST.
TreeNode insertNodeRecursively(TreeNode root, int value): Recursively inserts a value into the BST.
boolean findValue(int value): Searches for a value in the BST.
boolean searchNodeRecursively(TreeNode root, int value): Recursively searches for a value in the BST.
void removeValue(int value): Removes a value from the BST.
TreeNode deleteNodeRecursively(TreeNode root, int value): Recursively deletes a value from the BST.
int findMinValue(TreeNode root): Finds the minimum value in the BST.
void inOrderTraversal(TreeNode root, ArrayList<Integer> result): Performs in-order traversal of the BST.
void preOrderTraversal(TreeNode root, ArrayList<Integer> result): Performs pre-order traversal of the BST.
void postOrderTraversal(TreeNode root, ArrayList<Integer> result): Performs post-order traversal of the BST.
ArrayList<Integer> getInOrderElements(): Returns a list of BST elements in in-order sequence.
ArrayList<Integer> getPreOrderElements(): Returns a list of BST elements in pre-order sequence.
ArrayList<Integer> getPostOrderElements(): Returns a list of BST elements in post-order sequence.
BinarySearchTreeDemo
The BinarySearchTreeDemo class contains the main method and provides a command-line interface for interacting with the BST.

Methods:
public static void main(String[] args): The entry point of the program. Handles user input and performs BST operations based on user choices.
Conclusion
This program provides a simple and interactive way to learn about and work with binary search trees. It covers essential BST operations and demonstrates different tree traversal techniques. Feel free to modify and expand the program to explore more advanced BST functionalities.
