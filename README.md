import java.util.HashMap;
import java.util.Scanner;

public class CakeSystem {

    static HashMap<String, String> users = new HashMap<>();
    static HashMap<String, Integer> inventory = new HashMap<>();
    static HashMap<String, Double> prices = new HashMap<>();
    static Scanner sc = new Scanner(System.in);

    static double lastTotal = 0;
    static boolean hasOrder = false;

    public static void main(String[] args) {

        // Default users
        users.put("admin", "admin123");
        users.put("user", "user123");

        // Inventory
        inventory.put("Chocolate Cake", 5);
        inventory.put("Vanilla Cake", 3);
        inventory.put("Strawberry Cake", 0);

        // Prices
        prices.put("Chocolate Cake", 500.0);
        prices.put("Vanilla Cake", 450.0);
        prices.put("Strawberry Cake", 480.0);

        startSystem();
    }

    // =============================
    // SYSTEM MENU
    // =============================
    public static void startSystem() {

        while (true) {
            System.out.println("\n=== SYSTEM MENU ===");
            System.out.println("1. Login");
            System.out.println("2. Register");
            System.out.println("3. Exit");

            int choice = getValidNumberInput("Choose: ");

            switch (choice) {
                case 1:
                    loginProcess();
                    break;
                case 2:
                    registerUser();
                    break;
                case 3:
                    System.out.println("Exiting...");
                    System.exit(0);
                default:
                    System.out.println("Invalid choice!");
            }
        }
    }

    // =============================
    // LOGIN
    // =============================
    public static void loginProcess() {

        System.out.print("Enter Username: ");
        String username = sc.nextLine();

        System.out.print("Enter Password: ");
        String password = sc.nextLine();

        if (users.containsKey(username) && users.get(username).equals(password)) {

            if (username.equals("admin")) {
                adminHub();
            } else {
                customerDashboard();
            }

        } else {
            System.out.println("❌ Invalid Login!");
        }
    }

    // =============================
    // REGISTER
    // =============================
    public static void registerUser() {

        System.out.print("Enter new username: ");
        String username = sc.nextLine();

        // ❌ blank check
        if (username.trim().isEmpty()) {
            System.out.println("❌ Username cannot be empty!");
            return;
        }

        // ❌ letters only
        if (!username.matches("[a-zA-Z]+")) {
            System.out.println("❌ Username must contain letters only!");
            return;
        }

        if (username.equalsIgnoreCase("admin")) {
            System.out.println("❌ Cannot register as admin!");
            return;
        }

        if (users.containsKey(username)) {
            System.out.println("❌ Username already exists!");
            return;
        }

        System.out.print("Enter password: ");
        String password = sc.nextLine();

        // ❌ blank password
        if (password.trim().isEmpty()) {
            System.out.println("❌ Password cannot be empty!");
            return;
        }

        users.put(username, password);
        System.out.println("✅ Registered successfully!");
    }

    // =============================
    // ADMIN MENU
    // =============================
    public static void adminHub() {

        while (true) {
            System.out.println("\n=== ADMIN MENU ===");
            System.out.println("1. Update Prices");
            System.out.println("2. Edit Inventory");
            System.out.println("3. Logout");

            int choice = getValidNumberInput("Choose: ");

            switch (choice) {
                case 1:
                    updatePricesMenu();
                    break;
                case 2:
                    editInventoryMenu();
                    break;
                case 3:
                    return;
                default:
                    System.out.println("Invalid choice!");
            }
        }
    }

    // =============================
    // UPDATE PRICES
    // =============================
    public static void updatePricesMenu() {

        System.out.println("\n=== UPDATE PRICES ===");

        int i = 1;
        String[] items = new String[prices.size()];

        for (String item : prices.keySet()) {
            items[i - 1] = item;
            System.out.println(i + ". " + item + " (₱" + prices.get(item) + ")");
            i++;
        }

        int choice = getValidNumberInput("Select product number: ");

        if (choice < 1 || choice > items.length) {
            System.out.println("❌ Invalid choice!");
            return;
        }

        String product = items[choice - 1];

        double newPrice = getValidDoubleInput("Enter new price: ");

        prices.put(product, newPrice);
        System.out.println("✅ Price updated!");
    }

    // =============================
    // EDIT INVENTORY
    // =============================
    public static void editInventoryMenu() {

        System.out.println("\n=== EDIT INVENTORY ===");

        int i = 1;
        String[] items = new String[inventory.size()];

        for (String item : inventory.keySet()) {
            items[i - 1] = item;
            System.out.println(i + ". " + item + " (Stock: " + inventory.get(item) + ")");
            i++;
        }

        int choice = getValidNumberInput("Select product number: ");

        if (choice < 1 || choice > items.length) {
            System.out.println("❌ Invalid choice!");
            return;
        }

        String product = items[choice - 1];

        int qty = getValidNumberInput("Enter new quantity: ");

        inventory.put(product, qty);
        System.out.println("✅ Inventory updated!");
    }

    // =============================
    // CUSTOMER DASHBOARD
    // =============================
    public static void customerDashboard() {

        while (true) {
            System.out.println("\n=== CUSTOMER DASHBOARD ===");
            System.out.println("1. Order");
            System.out.println("2. Logout");

            int choice = getValidNumberInput("Choose: ");

            switch (choice) {
                case 1:
                    customerOrder();
                    break;
                case 2:
                    return;
                default:
                    System.out.println("Invalid choice!");
            }
        }
    }

    // =============================
    // CUSTOMER ORDER
    // =============================
    public static void customerOrder() {

        double total = 0;

        while (true) {

            System.out.println("\n=== CAKE MENU ===");

            int i = 1;
            String[] items = new String[inventory.size()];

            for (String item : inventory.keySet()) {
                items[i - 1] = item;
                System.out.println(i + ". " + item + " - ₱" + prices.get(item) +
                        " (Stock: " + inventory.get(item) + ")");
                i++;
            }

            int choiceNum = getValidNumberInput("Select product number: ");

            if (choiceNum < 1 || choiceNum > items.length) {
                System.out.println("❌ Invalid choice!");
                continue;
            }

            String choice = items[choiceNum - 1];

            if (inventory.get(choice) == 0) {
                System.out.println("❌ Out of stock!");
                continue;
            }

            int qty = getValidNumberInput("How many do you want? ");

            if (qty > inventory.get(choice)) {
                System.out.println("❌ Not enough stock!");
                continue;
            }

            total += prices.get(choice) * qty;
            inventory.put(choice, inventory.get(choice) - qty);

            System.out.println("✅ Added to cart!");

            System.out.print("Checkout now? (yes/no): ");
            String answer = sc.nextLine();

            if (answer.equalsIgnoreCase("yes")) {
                System.out.println("\n💵 Total: ₱" + total);
                System.out.println("✅ Order placed!");

                lastTotal = total;
                hasOrder = true;
                return;
            }
        }
    }

    // =============================
    // INPUT VALIDATION (NUMBERS ONLY)
    // =============================
    public static int getValidNumberInput(String prompt) {

        while (true) {
            System.out.print(prompt);
            String input = sc.nextLine();

            if (input.matches("\\d+")) {
                return Integer.parseInt(input);
            } else {
                System.out.println("❌ Please enter numbers only!");
            }
        }
    }

    // =============================
    // INPUT VALIDATION (DOUBLE)
    // =============================
    public static double getValidDoubleInput(String prompt) {

        while (true) {
            System.out.print(prompt);
            String input = sc.nextLine();

            try {
                return Double.parseDouble(input);
            } catch (Exception e) {
                System.out.println("❌ Please enter a valid number!");
            }
        }
    }
}
