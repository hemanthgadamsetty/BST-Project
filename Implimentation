import java.util.ArrayList;
import java.util.Scanner;

class TreeNode {
    int value;
    TreeNode leftChild, rightChild;

    public TreeNode(int item) {
        value = item;
        leftChild = rightChild = null;
    }
}

class BinarySearchTreeOperations {
    TreeNode root;

    BinarySearchTreeOperations() {
        root = null;
    }

    void addValue(int value) {
        root = insertNodeRecursively(root, value);
    }

    TreeNode insertNodeRecursively(TreeNode root, int value) {
        if (root == null) {
            root = new TreeNode(value);
            return root;
        }

        if (value < root.value)
            root.leftChild = insertNodeRecursively(root.leftChild, value);
        else if (value > root.value)
            root.rightChild = insertNodeRecursively(root.rightChild, value);

        return root;
    }

    boolean findValue(int value) {
        return searchNodeRecursively(root, value);
    }

    boolean searchNodeRecursively(TreeNode root, int value) {
        if (root == null) {
            return false;
        }
        if (root.value == value) {
            return true;
        }
        if (root.value > value) {
            return searchNodeRecursively(root.leftChild, value);
        }
        return searchNodeRecursively(root.rightChild, value);
    }

    void removeValue(int value) {
        root = deleteNodeRecursively(root, value);
    }

    TreeNode deleteNodeRecursively(TreeNode root, int value) {
        if (root == null) return root;

        if (value < root.value)
            root.leftChild = deleteNodeRecursively(root.leftChild, value);
        else if (value > root.value)
            root.rightChild = deleteNodeRecursively(root.rightChild, value);
        else {
            if (root.leftChild == null)
                return root.rightChild;
            else if (root.rightChild == null)
                return root.leftChild;

            root.value = findMinValue(root.rightChild);

            root.rightChild = deleteNodeRecursively(root.rightChild, root.value);
        }

        return root;
    }

    int findMinValue(TreeNode root) {
        int minValue = root.value;
        while (root.leftChild != null) {
            minValue = root.leftChild.value;
            root = root.leftChild;
        }
        return minValue;
    }

    void inOrderTraversal(TreeNode root, ArrayList<Integer> result) {
        if (root != null) {
            inOrderTraversal(root.leftChild, result);
            result.add(root.value);
            inOrderTraversal(root.rightChild, result);
        }
    }

    void preOrderTraversal(TreeNode root, ArrayList<Integer> result) {
        if (root != null) {
            result.add(root.value);
            preOrderTraversal(root.leftChild, result);
            preOrderTraversal(root.rightChild, result);
        }
    }

    void postOrderTraversal(TreeNode root, ArrayList<Integer> result) {
        if (root != null) {
            postOrderTraversal(root.leftChild, result);
            postOrderTraversal(root.rightChild, result);
            result.add(root.value);
        }
    }

    ArrayList<Integer> getInOrderElements() {
        ArrayList<Integer> result = new ArrayList<>();
        inOrderTraversal(root, result);
        return result;
    }

    ArrayList<Integer> getPreOrderElements() {
        ArrayList<Integer> result = new ArrayList<>();
        preOrderTraversal(root, result);
        return result;
    }

    ArrayList<Integer> getPostOrderElements() {
        ArrayList<Integer> result = new ArrayList<>();
        postOrderTraversal(root, result);
        return result;
    }
}

public class BinarySearchTreeDemo {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        BinarySearchTreeOperations bstOperations = new BinarySearchTreeOperations();

        System.out.print("Enter the number of elements to insert: ");
        int numberOfElements = scanner.nextInt();

        System.out.println("Enter " + numberOfElements + " elements:");
        for (int i = 0; i < numberOfElements; i++) {
            int value = scanner.nextInt();
            bstOperations.addValue(value);
        }

        boolean running = true;

        while (running) {
            System.out.println("\nCurrent BST (In-Order): " + bstOperations.getInOrderElements());
            System.out.println("Current BST (Pre-Order): " + bstOperations.getPreOrderElements());
            System.out.println("Current BST (Post-Order): " + bstOperations.getPostOrderElements());

            System.out.println("\nMenu:");
            System.out.println("1. Insert an element");
            System.out.println("2. Search for an element");
            System.out.println("3. Delete an element");
            System.out.println("4. Exit");
            System.out.print("Choose an option: ");
            int choice = scanner.nextInt();

            switch (choice) {
                case 1:
                    System.out.print("Enter value to insert: ");
                    int insertValue = scanner.nextInt();
                    bstOperations.addValue(insertValue);
                    System.out.println("Inserted " + insertValue);
                    break;

                case 2:
                    System.out.print("Enter value to search: ");
                    int searchValue = scanner.nextInt();
                    boolean found = bstOperations.findValue(searchValue);
                    if (found) {
                        System.out.println("Search " + searchValue + ": Found");
                    } else {
                        System.out.println("Search " + searchValue + ": Not Found");
                    }
                    break;

                case 3:
                    System.out.print("Enter value to delete: ");
                    int deleteValue = scanner.nextInt();
                    bstOperations.removeValue(deleteValue);
                    System.out.println("Deleted " + deleteValue);
                    break;

                case 4:
                    running = false;
                    System.out.println("Exiting...");
                    break;

                default:
                    System.out.println("Invalid option. Please try again.");
                    break;
            }
        }

        scanner.close();
    }
}
