
package StationeryItem;


import java.util.ArrayList;
import java.util.Arrays;
import java.util.Collections;

public class InventoryManagement1 {

    // Initialize an inventory array with some items
    static ArrayList<String> inventory = new ArrayList<>(Arrays.asList("Pen", "Notebook", "Eraser", "Marker", "Stapler"));

    // Function to display the current inventory
    public static void displayInventory(ArrayList<String> items) {
        System.out.println("Current Inventory:");
        if (items.isEmpty()) {
            System.out.println("The inventory is empty.");
        } else {
            for (int i = 0; i < items.size(); i++) {
                System.out.println((i + 1) + ". " + items.get(i));
            }
        }
    }

    // Function to add items to the inventory
    public static void addItem(ArrayList<String> items, String newItem) {
        items.add(newItem);
        System.out.println(newItem + " has been added to the inventory.");
    }

    // Function to remove the last item from the inventory
    public static void removeLastItem(ArrayList<String> items) {
        if (!items.isEmpty()) {
            String removedItem = items.remove(items.size() - 1);
            System.out.println(removedItem + " has been removed from the inventory.");
        } else {
            System.out.println("The inventory is already empty.");
        }
    }

    // Function to remove the first item from the inventory
    public static void removeFirstItem(ArrayList<String> items) {
        if (!items.isEmpty()) {
            String removedItem = items.remove(0);
            System.out.println(removedItem + " has been removed from the inventory.");
        } else {
            System.out.println("The inventory is already empty.");
        }
    }

    // Function to add items to the beginning of the inventory
    public static void addItemToBeginning(ArrayList<String> items, String newItem) {
        items.add(0, newItem);
        System.out.println(newItem + " has been added to the beginning of the inventory.");
    }

    // Function to reverse the inventory order
    public static void reverseInventory(ArrayList<String> items) {
        Collections.reverse(items);
        System.out.println("Inventory has been reversed.");
    }

    // Function to join all inventory items into a string
    public static String joinInventory(ArrayList<String> items, String separator) {
        String inventoryString = String.join(separator, items);
        System.out.println("Inventory joined into a string: " + inventoryString);
        return inventoryString;
    }

    // Function to convert inventory to a string
    public static String inventoryToString(ArrayList<String> items) {
        String inventoryString = String.join(", ", items);
        System.out.println("Inventory as a string: " + inventoryString);
        return inventoryString;
    }

    // Function to remove an item from the inventory
    public static void removeItem(ArrayList<String> items, int index) {
        if (index >= 0 && index < items.size()) {
            String removedItem = items.remove(index);
            System.out.println(removedItem + " at index " + index + " has been removed.");
        } else {
            System.out.println("Invalid index. No item removed.");
        }
    }

    // Function to search for an item in the inventory
    public static int searchItem(ArrayList<String> items, String item) {
        int index = items.indexOf(item);
        if (index != -1) {
            System.out.println(item + " found at index " + index + ".");
        } else {
            System.out.println(item + " not found in the inventory.");
        }
        return index;
    }

    // Function to sort the inventory alphabetically
    public static void sortInventory(ArrayList<String> items) {
        Collections.sort(items);
        System.out.println("Inventory has been sorted alphabetically.");
    }

    // Function to get a slice of the inventory
    public static ArrayList<String> getInventorySlice(ArrayList<String> items, int start, int end) {
        ArrayList<String> slice = new ArrayList<>(items.subList(start, end));
        System.out.println("Inventory slice from index " + start + " to " + end + ": " + slice);
        return slice;
    }

    // Function to delete an item from the inventory
    public static void deleteItem(ArrayList<String> items, int index) {
        if (index >= 0 && index < items.size()) {
            items.set(index, null);
            System.out.println("Item at index " + index + " has been deleted.");
        } else {
            System.out.println("Invalid index. No item deleted.");
        }
    }

    public static void main(String[] args) {
        System.out.println("Initial inventory:");
        displayInventory(inventory);

        addItem(inventory, "Highlighter");
        removeLastItem(inventory);
        removeFirstItem(inventory);
        addItemToBeginning(inventory, "Scissors");
        reverseInventory(inventory);

        System.out.println("\nUpdated inventory:");
        displayInventory(inventory);

        joinInventory(inventory, ", ");
        inventoryToString(inventory);
        removeItem(inventory, 2);

        System.out.println("\nInventory after removal:");
        displayInventory(inventory);

        searchItem(inventory, "Notebook");
        sortInventory(inventory);

        System.out.println("\nSorted inventory:");
        displayInventory(inventory);

        getInventorySlice(inventory, 1, 3);
        deleteItem(inventory, 1);

        System.out.println("\nFinal inventory:");
        displayInventory(inventory);
    }
}

