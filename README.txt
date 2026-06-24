===========================================================
 PASTIMES – Second-Hand Clothing E-Store
 WEDE6021 POE Final Submission
===========================================================

1. REQUIRED SOFTWARE
   - XAMPP (with Apache and MySQL) or any PHP 8.0+ / MySQL 5.7+ environment.
   - A modern web browser (Chrome, Firefox, Edge).

2. PROJECT SETUP
   a) Extract the 'Pastimes' folder into the 'htdocs' directory of XAMPP
      (e.g., C:\xampp\htdocs\Pastimes).
   b) Start Apache and MySQL from the XAMPP Control Panel.

3. DATABASE SETUP
   a) Open a browser and go to:
      http://localhost/Pastimes/CreateDB.php
      This creates the database 'ClothingStore' if it doesn't exist.

   b) To build all tables and insert 30 sample rows per table, run:
      http://localhost/Pastimes/loadClothingStore.php
      This script uses the file 'myClothingStore.sql' (located in the
      project root) which contains all DDL and INSERT statements.

   c) Alternatively, the database structure and sample data can be
      imported directly via phpMyAdmin using the file:
      Pastimes/myClothingStore.sql

4. TEST CREDENTIALS
   Administrator:
      Username: admin
      Email:    admin@pastimes.co.za
      Password: password123

   Verified Buyer (pre-loaded):
      Username: johndoe
      Email:    j.doe@abc.co.za
      Password: password123

   Verified Seller (pre-loaded, after running loadClothingStore.php):
      Username: (varies; the script creates seller accounts.
                You can also register a new seller and verify
                them via the admin panel.)
      Password: password123 (for all generated test users)

5. NAVIGATION
   - Home page:       http://localhost/Pastimes/
   - User Login:      http://localhost/Pastimes/login.php
   - Registration:    http://localhost/Pastimes/register.php
   - Admin Login:     http://localhost/Pastimes/admin_login.php

6. IMPORTANT NOTES
   - The Cart is implemented as a PHP class (includes/Cart.php) with
     member functions: addItem(), removeItem(), updateQuantity(),
     getItems(), getTotal(), emptyCart(), checkout().
   - Passwords are hashed using bcrypt; the default password for all
     test users is "password123".
   - The 'stock_quantity' column in tblClothes is used for inventory
     tracking. It is decremented on successful checkout.
   - The messaging system and seller rating feature are fully
     functional; you need a delivered order to test rating.
   - The project uses sessions; ensure cookies are enabled in your
     browser.
   - If you encounter a "Class 'Cart' not found" error, verify that
     includes/Cart.php is present and contains the Cart class.
   - All code files are extensively commented for easier marking.

7. PROJECT STRUCTURE (key files)
   Pastimes/
   ├── css/style.css              - Professional styling
   ├── includes/
   │   ├── DBConn.php             - Database connection
   │   ├── Cart.php               - Shopping cart class
   │   ├── header.php             - Reusable page header
   │   └── footer.php             - Reusable page footer
   ├── data/                      - Text files with sample data
   ├── uploads/                   - Product images
   ├── myClothingStore.sql        - Full database dump
   ├── loadClothingStore.php      - Recreates all tables + loads data
   ├── createTable.php            - Creates tblUser from userData.txt
   ├── register.php / login.php   - Authentication
   ├── index.php                  - Product browsing & filtering
   ├── product.php / cart.php     - Product details & cart management
   ├── checkout.php               - Order placement
   ├── orders.php                 - Purchase history with total
   ├── admin_login.php            - Admin authentication
   ├── admin_dashboard.php        - User & product management
   ├── add_clothes.php            - Admin add item
   ├── edit_clothes.php           - Admin edit item
   ├── delete_clothes.php         - Admin delete item
   ├── messages.php               - Buyer-seller messaging
   ├── compose_message.php        - Send a message
   ├── view_message.php           - Read a message
   ├── rate_seller.php            - Post-purchase rating
   └── ...                        - Additional support files
===========================================================