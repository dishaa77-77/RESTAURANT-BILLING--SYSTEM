The Restaurant Billing System is a console-based application developed in C language
to automate the process of managing a restaurant’s menu and generating customer bills efficiently.
This system allows restaurant administrators to maintain menu details such as item name, category, 
price, and available stock, while also enabling billing operations that include item selection, quantity validation,
tax calculation, discounts, and stock updates.

Designed with file handling, the system saves and retrieves menu and sales data from text files,
ensuring that information is not lost when the program closes. It offers a password-protected admin
module to secure critical functionalities like adding, updating, deleting, and viewing inventory details.
-----------------------------------------------------------------------------------

🍽 Restaurant Billing System (C Language)

This project is a console-based Restaurant Billing Management System written in C.
It helps restaurant admins to manage menu items, update stock, and generate customer bills with tax and discount options.

------------------------------------------------------------------------------------------------------------------------

📌 Features

✔ Admin Login (Password Protected)
✔ Add, Delete & Update Menu Items
✔ Search Items by Name
✔ Sort Menu (By Name / Price)
✔ Stock Management with Low Quantity Alerts
✔ Generate Bill (With Discount + GST)
✔ Saves Menu & Sales Records to Files
✔ Displays Updated Inventory After Billing
✔ Supports Dine-In & Takeaway Orders
✔ Data Persistence using menu.txt and sales.txt
---------------------------------------------------------------------------

🧠 Structure Explanation

Menu Item Structure

typedef struct {
    int id;
    char name[50];
    char category[30];
    float price;
    int quantity;
} MenuItem;

Each menu item stores:

id → Unique item code

name → Food item name

category → Food category (e.g., Drinks, Snacks)

price → Price in ₹ (Rupees)

quantity → Available stock
--------------------------------------------------------------------------------------------------------

📂 File Handling

File Name	Purpose

menu.txt	Stores menu items (persistent data)
sales.txt	Stores final billing history with timestamp
bill.txt	Can be extended to store printed bills


Menu automatically saves when data changes.
--------------------------------------------------------------------------------------------------

🔒 Admin Authentication

if(strcmp(pass, "admin123") != 0)

Only users with password admin123 can access system features.

If wrong password is entered → program exits.
------------------------------------------------------------------------
📋 Major Functionalities

1️⃣ Display Menu & Admin View

Displays items with price and category (for customers),
Admin view shows quantity + internal data.

2️⃣ Add / Delete / Update Items

Adds new items without overwriting old data

Prevents duplicate IDs

Updates name, price, quantity individually


3️⃣ Search Item

strcasecmp(menu[i].name, nameSearch) == 0

Case-insensitive item search by name.


4️⃣ Sorting

Two modes:

By Name

By Price


Both use simple comparison-based sorting.

5️⃣ Billing System

Allows:

Selection of multiple items

Validation of stock

Stock reduction after billing

Warning for low stock (< 5)

Discount + GST included
--------------------------------------------------------------------------------------------------------------------

📌 Bill Summary Example

Subtotal     : ₹500.00
Discount     : ₹50.00
GST          : ₹25.00
Final Total  : ₹475.00

Saves final bill to sales.txt with date/time:

Bill: ₹475 Date: Wed Nov 22 12:30:10 2025
--------------------------------------------------------------------------------------------

📌 Bill Summary Example

Subtotal     : ₹500.00
Discount     : ₹50.00
GST          : ₹25.00
Final Total  : ₹475.00

Saves final bill to sales.txt with date/time:

Bill: ₹475 Date: Wed Nov 22 12:30:10 2025
------------------------------------------------------------------

⚠ Low Stock Alert

if(menu[index].quantity < 5)
    printf("⚠ Low Stock Warning!\n");
---------------------------------------------------------------------

▶ How to Run

gcc restaurant.c -o restaurant
./restaurant
