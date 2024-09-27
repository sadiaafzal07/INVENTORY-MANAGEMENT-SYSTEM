-----INVENTORY-------
import java.util.Scanner;
public class Inventory {
    private Product[] products;
    private int size;

    public Inventory(int capacity) {
        products = new Product[capacity];
        size = 0;
    }

    public void addProduct(Product product) {
        if (size < products.length) {
            products[size++] = product;
            System.out.println("Product added successfully!");
        } else {
            System.out.println("Inventory is full!");
        }
    }

    public void removeProduct(int id) {
        for (int i = 0; i < size; i++) {
            if (products[i].getId() == id) {
                products[i] = products[size - 1];
                products[--size] = null;
                System.out.println("Product removed successfully!");
                return;
            }
        }
        System.out.println("Product not found!");
    }

    public Product searchProductById(int id) {
        for (int i = 0; i < size; i++) {
            if (products[i].getId() == id) {
                return products[i];
            }
        }
        return null;
    }

    public Product searchProductByName(String name) {
        for (int i = 0; i < size; i++) {
            if (products[i].getName().equalsIgnoreCase(name)) {
                return products[i];
            }
        }
        return null;
    }

    public void sortProductsByName() {
        for (int i = 0; i < size - 1; i++) {
            for (int j = 0; j < size - 1 - i; j++) {
                if (products[j].getName().compareToIgnoreCase(products[j + 1].getName()) > 0) {
                    Product temp = products[j];
                    products[j] = products[j + 1];
                    products[j + 1] = temp;
                }
            }
        }
        System.out.println("Products sorted by name.");
    }

    public void sortProductsByPrice(boolean ascending) {
        for (int i = 0; i < size - 1; i++) {
            for (int j = 0; j < size - 1 - i; j++) {
                if ((ascending && products[j].getPrice() > products[j + 1].getPrice()) ||
                    (!ascending && products[j].getPrice() < products[j + 1].getPrice())) {
                    Product temp = products[j];
                    products[j] = products[j + 1];
                    products[j + 1] = temp;
                }
            }
        }
        System.out.println("Products sorted by price.");
    }

    public void sortProductsByQuantity(boolean ascending) {
        for (int i = 0; i < size - 1; i++) {
            for (int j = 0; j < size - 1 - i; j++) {
                if ((ascending && products[j].getQuantity() > products[j + 1].getQuantity()) ||
                    (!ascending && products[j].getQuantity() < products[j + 1].getQuantity())) {
                    Product temp = products[j];
                    products[j] = products[j + 1];
                    products[j + 1] = temp;
                }
            }
        }
        System.out.println("Products sorted by quantity.");
    }

    public void displayInventory() {
        if (size == 0) {
            System.out.println("Inventory is empty.");
        } else {
            for (int i = 0; i < size; i++) {
                System.out.println(products[i]);
            }
        }
    }
    public static void main(String[] args) {
    Inventory inventory = new Inventory(10);
    Scanner scanner = new Scanner(System.in);

    while (true) {
        System.out.println("\nInventory Management System");
        System.out.println("1. Add Product");
        System.out.println("2. Remove Product");
        System.out.println("3. Search Product by ID");
        System.out.println("4. Search Product by Name");
        System.out.println("5. Sort Products by Name");
        System.out.println("6. Sort Products by Price");
        System.out.println("7. Sort Products by Quantity");
        System.out.println("8. Display Inventory");
        System.out.println("9. Exit");
        System.out.print("Choose an option: ");
        int choice = scanner.nextInt();

        if (choice == 1) {
            System.out.print("Enter Product ID: ");
            int id = scanner.nextInt();
            scanner.nextLine();  // Consume newline
            System.out.print("Enter Product Name: ");
            String name = scanner.nextLine();
            System.out.print("Enter Product Price: ");
            double price = scanner.nextDouble();
            System.out.print("Enter Product Quantity: ");
            int quantity = scanner.nextInt();
            Product product = new Product(id, name, price, quantity);
            inventory.addProduct(product);
        } else if (choice == 2) {
            System.out.print("Enter Product ID to Remove: ");
            int id = scanner.nextInt();
            inventory.removeProduct(id);
        } else if (choice == 3) {
            System.out.print("Enter Product ID to Search: ");
            int id = scanner.nextInt();
            Product searchResultById = inventory.searchProductById(id);
            System.out.println(searchResultById != null ? searchResultById : "Product not found.");
        } else if (choice == 4) {
            System.out.print("Enter Product Name to Search: ");
            scanner.nextLine();  // Consume newline
            String name = scanner.nextLine();
            Product searchResultByName = inventory.searchProductByName(name);
            System.out.println(searchResultByName != null ? searchResultByName : "Product not found.");
        } else if (choice == 5) {
            inventory.sortProductsByName();
        } else if (choice == 6) {
            System.out.print("Sort by price ascending? (true/false): ");
            boolean ascending = scanner.nextBoolean();
            inventory.sortProductsByPrice(ascending);
        } else if (choice == 7) {
            System.out.print("Sort by quantity ascending? (true/false): ");
            boolean ascending = scanner.nextBoolean();
            inventory.sortProductsByQuantity(ascending);
        } else if (choice == 8) {
            inventory.displayInventory();
        } else if (choice == 9) {
            scanner.close();
            System.exit(0);
        } else {
            System.out.println("Invalid choice. Try again.");
        }
    }
}

}
------PRODUCTS-----
public class Product {
    private int id;
    private String name;
    private double price;
    private int quantity;

    public Product(int id, String name, double price, int quantity) {
        this.id = id;
        this.name = name;
        this.price = price;
        this.quantity = quantity;
    }

    public int getId() {
        return id;
    }

    public String getName() {
        return name;
    }

    public double getPrice() {
        return price;
    }

    public int getQuantity() {
        return quantity;
    }

    public void setQuantity(int quantity) {
        this.quantity = quantity;
    }

    @Override
    public String toString() {
        return "Product [ID=" + id + ", Name=" + name + ", Price=" + price + ", Quantity=" + quantity + "]";
    }
}


