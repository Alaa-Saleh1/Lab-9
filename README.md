# Lab-9

<img width="583" alt="OrderFoodDelivery" src="https://github.com/user-attachments/assets/beccf5fb-13ba-4b62-8f2f-1cf9bf552a3d">

user Table 
id: INT, Primary Key, Auto Increment.

username: VARCHAR(20), Not Null, Unique.

password: VARCHAR(18), Not Null.

email: VARCHAR(30), Not Null, Unique.

phone_number: VARCHAR(15), Not Null, Unique.

address: VARCHAR(40), Not Null.

create_at: TIMESTAMP, Default CURRENT_TIMESTAMP.


restaurant Table
id: INT, Primary Key, Auto Increment.

name: VARCHAR(40), Not Null.

location: VARCHAR(40), Not Null.

phone_number: VARCHAR(15), Not Null, Unique.

type_of_food: VARCHAR(25), Not Null.

create_at: TIMESTAMP, Default CURRENT_TIMESTAMP.


driver Table
id: INT, Primary Key, Auto Increment.

name: VARCHAR(20), Not Null.

phone_number: VARCHAR(15), Not Null, Unique.

veicle_type: VARCHAR(20), Not Null.

create_at: TIMESTAMP, Default CURRENT_TIMESTAMP.



menuItems Table
id: INT, Primary Key, Auto Increment.

itemName: VARCHAR(30), Not Null.

description: VARCHAR(60), Not Null.

price: INT, Not Null, Check price > 0.

available: BOOLEAN, Default TRUE.

restaurantId: INT, Foreign Key references restaurant(id).

created_at: TIMESTAMP, Default CURRENT_TIMESTAMP.



Order Table
Id: INT, Primary Key, Auto Increment.

menuItemId: INT, Foreign Key references menuItems(id).

userId: INT, Foreign Key references user(id).

driverId: INT, Foreign Key references driver(id).

status: VARCHAR(15), Not Null, Check status in ('waiting', 'in kitchen', 'in way', 'delivered').

totalPrice: INT, Check totalPrice > 0.

totalAmount: INT, Check totalAmount > 0.

order_date: TIMESTAMP, Default CURRENT_TIMESTAMP.


