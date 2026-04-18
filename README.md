<!DOCTYPE html>
<html>
<head>
    <title>Red Ribbon Bakeshop</title>

    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script&family=Pacifico&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
    <style>
        body {
            margin: 0;
            margin-top: 80px;
            font-family: Arial, sans-serif;
            background-color: #f8f8f8;
        }

        header {
            display: flex;
            align-items: center;
            justify-content: space-between;
            background-color: #cc0000;
            padding: 15px;
            position: fixed;
            top: 0;
            width: 100%;
            height: 60px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.2);
        }

        .logo {
            height: 55px;
        }

        nav a {
            color: white;
            margin: 25px;
            text-decoration: none;
            font-size: 18px;
            padding: 10px 15px;
            border-radius: 20px;
            transition: 0.3s;
        }

        nav a:hover {
            background-color: white;
            color: #c40000;
        }

        section {
            padding: 80px 20px;
        }

        html {
            scroll-behavior: smooth;
        }

        #home {
            background-image: url("https://dynl.mktgcdn.com/p/4twNGJuO2UypM7Ciz99mpOIO1pJsJr4hZlej-4amInU/1280x960.jpg");
            background-size: cover;
            background-position: center;
            text-align: center;
            color: white;
            min-height: 100vh;
        }

        #home h1 {
            font-family: 'Dancing Script', cursive;
            font-size: 70px;
            margin-top: 120px;
            text-shadow: 2px 2px 5px red;
        }

        #home p {
            font-size: 22px;
            background: rgba(0,0,0,0.5);
            display: inline-block;
            padding: 10px 20px;
            border-radius: 10px;
        }

       
        #about {
            background-color: white;
            text-align: center;
        }

        .about-container {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 25px;
            max-width: 1100px;
            margin: auto;
            margin-top: 30px;
        }

        .about-card {
            background: #ffffff;
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }

        .about-card:hover {
            transform: translateY(-5px);
        }

        .about-card h2 {
            color: #cc0000;
        }

       
        .product-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 30px;
            max-width: 1100px;
            margin: auto;
            margin-top: 30px;
        }

        .product-card {
            background: white;
            padding: 15px;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }

        .product-card:hover {
            transform: scale(1.05);
        }

        .product-card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 10px;
            cursor: pointer;
        }

        .product-card p {
            margin-top: 10px;
            font-weight: bold;
            color: #cc0000;
        }

        #contact {
            background-color: #cc0000;
            color: white;
            text-align: center;
        }

        .contact-info p {
            font-size: 18px;
            margin: 10px 0;
        }
        .social-links {
    margin-top: 20px;
    text-align: center;
}
    .social-links a {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    margin: 10px;
    padding: 12px 22px;
    background: #ffffff;
    color: #cc0000;
    text-decoration: none;
    border-radius: 30px;
    font-weight: bold;
    font-size: 16px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    transition: all 0.3s ease;
}
    .social-links a:hover {
    background: #cc0000;
    color: white;
    transform: translateY(-3px);
    }
    .social-links i {
    font-size: 18px;
}

        .modal {
            display: none;
            position: fixed;
            z-index: 999;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.85);
        }

        .modal-content {
            display: block;
            margin: auto;
            max-width: 80%;
            max-height: 80%;
            margin-top: 80px;
            border-radius: 10px;
        }

        .close {
            position: absolute;
            top: 20px;
            right: 35px;
            color: white;
            font-size: 40px;
            cursor: pointer;
        }

       
        @media (max-width: 900px) {
            .about-container {
                grid-template-columns: 1fr;
            }

            .product-grid {
                grid-template-columns: 1fr;
            }

            nav a {
                display: block;
                margin: 10px 0;
            }

            header {
                flex-direction: column;
                height: auto;
            }
        }

    </style>
</head>

<body>

<header>
    <img src="https://upload.wikimedia.org/wikipedia/en/5/58/Red_Ribbon_Bakeshop_Logo.webp" class="logo">

    <nav>
        <a href="#home">Home</a>
        <a href="#about">About</a>
        <a href="#product">Product</a>
        <a href="#contact">Contact</a>
    </nav>
</header>

<section id="home">
    <h1>Red Ribbon Bakeshop</h1>
    <p><b>Welcome to my Red Ribbon Bakeshop</b></p>
</section>

<section id="about">
    <h1>About</h1>

    <div class="about-container">
        <div class="about-card">
            <h2>What is Red Ribbon?</h2>
            <p>Red Ribbon is a well-known bakery chain from the Philippines, famous for its cakes, pastries, and comfort food.</p>
        </div>

        <div class="about-card">
            <h2>Background</h2>
            <p>Founded in 1979 in Quezon City. Now owned by Jollibee Foods Corporation.</p>
        </div>

        <div class="about-card">
            <h2>Popular Products</h2>
            <p>Black Forest Cake, Mango Supreme, Chocolate Mousse, Ensaymada, Ube Cake.</p>
        </div>

        <div class="about-card">
            <h2>Locations</h2>
            <p>Philippines, U.S., Canada, Middle East.</p>
        </div>
    </div>
</section>

<section id="product">
    <h1>Products</h1>

    <div class="product-grid">
        <div class="product-card">
            <img src="https://raw.githubusercontent.com/reantimonelcoc-commits/Image./main/Red-Ribbon-Philippines-Menu-Prices%20%281%29.webp">
            <p>Menu Selection</p>
        </div>

        <div class="product-card">
            <img src="https://raw.githubusercontent.com/reantimonelcoc-commits/Image./main/Red-Ribbon-Philippines-Menu-Prices.webp">
            <p>Cake Varieties</p>
        </div>

        <div class="product-card">
            <img src="https://raw.githubusercontent.com/reantimonelcoc-commits/Image./main/images%20%2835%29.jpeg">
            <p>Pastries & Desserts</p>
        </div>
    </div>
</section>

<section id="contact">
    <h1>Contact</h1>
    <p>We’d love to hear from you!</p>

    <div class="contact-info">
        <p>Email: rean.timonel.coc@phinmaed.com</p>
        <p>Email: axam.blaya.coc@phinmaed.com</p>
        <p>Email: reva.villamor.coc@phinmaed.com</p>
        <p>Email: ambe.balansi.coc@phinmaed.com</p>
    </div>
<div class="social-links">
    <div class="social-item">
        <i class="fab fa-facebook"></i> Facebook
    </div>

    <div class="social-item">
        <i class="fab fa-twitter"></i> Twitter (X)
    </div>

    <div class="social-item">
        <i class="fab fa-instagram"></i> Instagram
    </div>
</div>
</section>

<div id="imgModal" class="modal">
    <span class="close">&times;</span>
    <img class="modal-content" id="modalImg">
</div>

<script>
const modal = document.getElementById("imgModal");
const modalImg = document.getElementById("modalImg");
const closeBtn = document.querySelector(".close");

document.querySelectorAll(".product-card img").forEach(img => {
    img.addEventListener("click", function () {
        modal.style.display = "block";
        modalImg.src = this.src;
    });
});

closeBtn.onclick = function () {
    modal.style.display = "none";
};

modal.onclick = function (e) {
    if (e.target === modal) {
        modal.style.display = "none";
    }
};
</script>

</body>
</html>        prices.put("Chocolate Cake", 500.0);
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
