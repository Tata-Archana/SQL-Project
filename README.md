Go Green Nursery Summary

Go Green plant nursery is an organization that specializes in cultivation, propagation, and sales of plants. This organization typically grows a wide range of plant species, including flowers, in-door plants, shrubs, and ornamental plants. We often focus on specific plant categories, such as annuals, perennials, herbs, or succulents.
Our organization's primary objective is to produce healthy and high-quality plants that are suitable for various purposes, such as gardening, landscaping, and agricultural production. We sell plants through various channels, such as direct-to-consumer sales, wholesale to landscapers and garden centers, and online sales. We may also offer additional services, such as consultations, delivery, installation, and maintenance.
To enhance sales, our organization requires extensive knowledge of horticulture, business management, and marketing, including careful planning and management of inventory, effective pricing, and sales strategies, and maintaining good relationships with suppliers and customers. Another challenge is to stay up to date with industry trends and innovations to remain competitive in a rapidly changing marketplace.

Problem Statement

As our organization is planning to extend to a medium-scale business it is required to store all the information about plants and their requirements. We must monitor the availability of gardening tools, fertilizers, pesticides to monitor the health of plants and customer needs.
Below are some of reasons why we need to maintain a SQL database:
Inventory management: A SQL database can help the nursery keep track of its inventory levels, including stock quantities, plant varieties, and supplier information. This can help with forecasting demand, identifying slow-moving products, and reducing wastage.
Sales and customer management: A SQL database can help the nursery keep track of customer orders, invoices, and payments. This can help with managing customer relationships, improving customer service, and tracking sales performance.
Plant care and maintenance: A SQL database can help the nursery keep track of plant care information, such as watering schedules, fertilization requirements, and pest control measures. This can help with ensuring consistent plant quality, reducing plant losses, and improving productivity.
Reporting and analysis: A SQL database can provide the nursery with valuable insights into its operations, such as sales trends, inventory turnover rates, and plant performance. This can help with decision-making, identifying areas for improvement, and optimizing business processes.
Overall, maintaining a SQL database can help the nursery operate more efficiently, reduce costs, and improve customer satisfaction.
Thus, Go Green plant nursery decided to maintain a Relational Database for their business to address the above problems.

Entities, Attributes and Relationships
Primary entities along with their attributes that are required in the Go Green Nursery are:
1)	Plant and Plant Requirements: Plant scientific name, Requirement id, Plant type, etc.
2)	Customer: Customer id, Customer first name, Customer last name, Customer payment method, etc.
3)	Order and Order Detail: Order id, Order status, Order detail id, etc.
4)	Supplier: Supplier id, Supplier name, Supplier address, etc.
5)	Transaction: Transaction id, Transaction price, etc.
6)	Gardening tools: Gardening tool id, Gardening 
7)	Fertilizers: Fertilizer id, Fertilizer Name, Fertilizer type, etc. 
8)	Pesticides: Pesticide id, Pesticide name, Pesticide type, etc.
9)	Appointment: Appointment id, Appointment slot, etc.
10)	Services: Service id, Service name, Service description, etc.

Relationships: 
•	Plant and Plant Requirements(M:M)
•	Customer and Plant(M:M)
•	Plant and Order(M:M)
•	Customer and Order(1:M)
•	Plant and Garden Tools(M:M)
•	Order and Order Detail(1:M)
•	Plant and Supplier(M:M)
•	Order and Transaction(1:M)
•	Plant requirement and Fertilizer (M:M) 
•	Plant requirement and Pesticide (M:M)
•	Customer and Service (M:M)
•	Service and Appointment (M:1)
•	Customer and Appointment (1:M)
•	Appointment and Transaction (1:M)

Functional Requirements

•	The database contains data i.e., plant itinerary, supplier, customer information, order and transaction details which are necessary to operate our Go Green Nursery. 
•	This would allow employees of Go Green Nursery to search for the plant and other requirements.  It also enables to get the customer details such as customer name, address for the shipment, track orders details and payment information. 
•	The database will also be able to store and retrieve plant information such as availability, supplier, pricing, and quantity.
•	Customers will be able to make orders for plants, request for services and can maintain track of their order detail.	
•	This database will also keep a track of all transactions and their prices.
•	Data on gardening tools, fertilizers, pesticides, services, and appointments is also stored in the database.  

Conceptual Database Design
REVISED ER- DIAGRAM
 ![image](https://github.com/Tata-Archana/SQL-Project/assets/29245288/b3f3ea5b-a346-46db-8e84-cb25d377fe97)

Entities	Attributes
•	Plant
•	Plant Requirement
•	Customer
•	Order
•	Order Details
•	Supplier
•	Transaction
•	Gardening Tool
•	Fertilizer
•	Pesticide
•	Service
•	Appointment	•	Plant: plant_id (Primary Key, Unique Constraint), plant_scientific_name, plant_common_name , plant_type,plant_price, plant_description. plant_image_url, plant_availability, plant_quantity,order_id
•	Plant Requirement: requirement_id(Primary Key, Unique Constraint), requirement_name, requirement_description,fertilizer_id,pesticide_id (Foreign Key)
•	Customer: customer_id(Primary Key, Unique Constraint), customer_first_name, customer_last_name, customer_email_id, customer_phone_number, customer_address , customer_payment_method customer_preference_plant_ty
•	Order: order_id (Primary Key, Unique Constraint), customer_id, order_date, order_status, total_price
•	Order Details: order_detail_id Primary Key, Unique Constraint), order_id, plant_id, order_quantity, unit_price
•	Supplier: supplier_id (Primary Key, Unique Constraint), supplier_name, contact_person, email_id, phone_number, supplier_address
•	Transaction: transaction_id (Primary Key, Unique Constraint), transaction_price, transaction_mode, appointment_id, order_id
•	Gardening Tool: gardening_tool_id(Primary Key, Unique Constraint) gardening_tool_name, gardening_tool_type, gardening_tool_description, gardening_tool_price
•	Fertilizer: fertilizer_id(Primary Key, Unique Constraint), fertilizer_name, fertilizer_type, fertilizer_nutrient_content, fertilizer_storage_condition, fertilizer_expiry_date
•	Pesticide: pesticide_id(Primary Key, Unique Constraint), pesticide_name, pesticide_type, pesticide_target_pest, pesticide_expiry_date, pesticide_storage_condition
•	Service: service_id(Primary Key, Unique Constraint), service_name, service_description
•	Appointment: appointment_id(Primary Key, Unique Constraint), appointment_slot, appointment_service


Relationships

Entity	Relationship	Connectivity	Entity
Plant	Requires	M:M	Plant Requirement
Customer	Purchases	M:M	Plant
Plant 	Belongs To	M:M	Order
Customer	Places	1:M	Order
Plant	Needs	M:M	Garden Tool
Order 	Contains	1:M	Order Detail
Plant	Supplied By	M:M	Supplier
Order	Involves	1:M	Transaction
Plant Requirement	Requires Fertilizer	M:M	Fertilizer
Plant Requirement	Requires Pesticide	M:M	Pesticide
Customer	Requests	M:M	Service
Service 	Can Be Part of	M:1	Appointment
Customer	Has	1:M	Appointment
Appointment	Has	1:M	Transaction

•	Plant and Plant Requirement (M:M) 
A nursery can have many plants. A plant can have multiple requirements such as sunlight requirement, water requirement, soil requirement, propagation method, and pest control method. Each requirement can be associated with multiple plants. 
•	Customer and Plant (M:M)
A customer can purchase many plants, and a plant can be purchased by many customers.   When a customer purchased plants, a transaction will be made. 
•	Plant and Order (M:M)
A plant can belong to one or more orders, and an order can include one or more plants. 
•	Customer and order (1:M) 
A customer can place many orders, and each order can be placed by single customer.
•	Plant and Garden Tool (M:M)
A plant may need the help of many garden tools and each garden tool can use for many plants. 
•	Order and Order Detail (1:M)
Each Order (Invoice) can have multiple plant details and many order details will be in single order.
•	Plant and Supplier (M:M)
A plant can be supplied by one or more suppliers, and a supplier can supply one or more plants. 
•	Order and Transaction (1:M)
Each Order can have multiple transactions, and each transaction will be made for one order. 
•	Plant requirement and Fertilizer (M:M) 
Each plant would require at least one fertilizer and each fertilizer could be used by one or more plants. 
•	Plant requirement and Pesticide (M:M)
Each plant requires one or more pesticides, and each pesticide can be used by one or more plants. 
•	Customer and Service (M:M)
Each customer can request one or more services, and each service can be requested by one or more customers.
•	Service and Appointment (M:1)
An appointment can have one or more services. 
•	Customer and Appointment (1:M)
A customer can have many appointments.
•	Appointment and Transaction (1:M)
One Appointment has one or many transactions. 


Assumptions

Below are the assumptions that were assumed while creating the Go Green Database:  
•	The transaction made by a customer can be performed in multiple payment modes. 
Example: A customer can pay a transaction through 40% via Cash and 60% via Online payment. 

•	A customer can request multiple services in a single appointment.
Example: A customer might request Watering of Plants, trimming and fertilizing of plants in a single appointment. 

•	An order contains a single record for all the plants order, whereas order_ details contain a record for each plant purchased.
Example: A customer ordered Rose and Aloe vera plant.
•	Below is the table for order and order _details:

 

•	A relationship between pesticide and plant requirement has one-to-many relationship meaning that a single pesticide can be used for multiple plant requirements, but each plant requirement can only have one pesticide.
•	The relationship between fertilizer and plant requirement has one-to-many relationship meaning that a single fertilizer can be used for multiple plant requirements, but each plant requirement can only have one fertilizer.

Normalization

Normalization is a process of organizing data in a database to reduce data redundancy and increase data integrity. There are different levels of normalization, with the most used being the first, second, and third normal forms (1NF, 2NF, and 3NF).
1NF: The first normal form requires that all data in a table must be atomic, meaning it cannot be further divided into smaller pieces. This ensures that each table has a unique primary key and that there is no repeating data.
2NF: The second normal form requires that all non-key columns in a table must be fully dependent on the primary key. In other words, each column in a table must depend only on the primary key, and not on any other non-key columns.
3NF: The third normal form requires that all non-key columns in a table must not have transitive dependencies. This means that if a non-key column depends on another non-key column, then that column should be moved to a separate table.

•	All tables in our database have a primary key that uniquely identifies each record.
•	Each column in every table depends only on the primary key and does not depend on any non-key columns.
•	There are no transitive dependencies between non-key columns.
For example, in the Plant table, plant_id is the primary key, and all other columns depend on it directly. There are no transitive dependencies between the columns. Similarly, all other tables have a well-defined primary key and columns that depend only on that key. Therefore, the schema is in 3NF. 
•	Plant: plant_id (Primary Key, Unique Constraint), plant_scientific_name, plant_common_name , plant_type,plant_price, plant_description. plant_image_url, plant_availability, plant_quantity,order_id
•	Plant Requirement: requirement_id(Primary Key, Unique Constraint), requirement_name, requirement_description,fertilizer_id,pesticide_id (Foreign Key)
•	Customer: customer_id(Primary Key, Unique Constraint), customer_first_name, customer_last_name, customer_email_id, customer_phone_number, customer_address , customer_payment_method customer_preference_plant_ty
•	Order: order_id (Primary Key, Unique Constraint), customer_id, order_date, order_status, total_price
•	Order Details: order_detail_id Primary Key, Unique Constraint), order_id, plant_id, order_quantity, unit_price
•	Supplier: supplier_id (Primary Key, Unique Constraint), supplier_name, contact_person, email_id, phone_number, supplier_address
•	Transaction: transaction_id (Primary Key, Unique Constraint), transaction_price, transaction_mode, appointment_id, order_id
•	Gardening Tool: gardening_tool_id(Primary Key, Unique Constraint) gardening_tool_name, gardening_tool_type, gardening_tool_description, gardening_tool_price
•	Fertilizer: fertilizer_id(Primary Key, Unique Constraint), fertilizer_name, fertilizer_type, fertilizer_nutrient_content, fertilizer_storage_condition, fertilizer_expiry_date
•	Pesticide: pesticide_id(Primary Key, Unique Constraint), pesticide_name, pesticide_type, pesticide_target_pest, pesticide_expiry_date, pesticide_storage_condition








Database Implementation
Here are all the details of all the tables of our Go Green Nursery:
Plant
Column Name	Key Type	Null/Not Null	Data Type	Max Length	FK Reference Table
plant_id	PK(Auto Increment)	Not Null	INT		
plant_scientific_name	 	Null	VARCHAR	255	 
plant_common_name	 	Not Null	VARCHAR	255	 
plant_type	 	Null	VARCHAR	255	 
plant_description	 	Null	TEXT	500	 
plant_image_url	 	Null	VARCHAR	255	 
plant_availability	 	Boolean,Not Null,Default True	TINYINT	2	 
plant_quantity	 	Not Null	INT		 
plant_price	 	Null	DECIMAL	(10,2)	 
order_id		Not Null	INT		

Gardening Tool					
Column Name	Key Type	Null/Not Null	Data Type	Max Length	FK Reference Table
gardening_tool_id	PK(Auto Increment)	Not Null	INT		 
gardening_tool_name	 	Not Null	VARCHAR	255	 
gardening_tool_type	 	Null	VARCHAR	255	 
gardening_tool_description	 	Null	TEXT	500	 
gardening_tool_price	 	Not Null	DECIMAL	(10,2)	 

Supplier               					
Column Name	Key Type	Null/Not Null	Data Type	Max Length	FK Reference Table
supplier_id	PK (Auto Increment)	Not Null	INT		 
supplier_name	 	Not Null	VARCHAR	255	 
contact_person	 	Null	VARCHAR	255	 
email_id	 	Null	VARCHAR	255	 
phone_number	 	Not Null	VARCHAR	20	 
address	 	 Null	TEXT	500	 

Pesticide					
Column Name	Key Type	Null/Not Null	Data Type	Max Length	FK Reference Table
pesticide_id	PK (Auto Increment)	Not Null	INT		 
pesticide_name	 	Null	VARCHAR	255	 
pesticide_type	 	Null	VARCHAR	255	 
pesticide_target_pest	 	Null	VARCHAR	255	 
pesticide_expiry_date	 	Not Null	DATE	 	 
pesticide_storage_Condition	 	Null	VARCHAR	255	 

Plant Requirement					
Column Name	Key Type	Null/Unique	Data Type	Max Length	FK Reference Table
requirement_id	PK (Auto Increment)	Not Null	INT		 
requirement_name	 	Not Null	VARCHAR	255	 
requirement_description	 	Null	TEXT	500	 
fertilizer_id	FK	Null	INT		
pesticide_id	FK	Null	INT		

Customer 
					
Column Name	Key Type	Null/Not Null	Data Type	Max Length	FK Reference Table
customer_id	PK(Auto Increment)	Not Null	INT		 Order
customer_first_name	 	Not Null	VARCHAR	255	 
customer_last_name	 	Not Null	VARCHAR	255	 
customer_emial_id	 	 	VARCHAR	255	 
customer_phone_number	 	 Not Null	VARCHAR	20	 
customer_address	 	 	TEXT	500	 
customer_payment_method	 	 	VARCHAR	255	 
customer_preference_plant_type	 	 	VARCHAR	255	 
					
Order 					
Column Name	Key Type	Null/Unique	Data Type	Max Length	FK Reference Table
order_id	PK(Auto Increment)	Not Null	INT		 
customer_id	FK	Not Null	INT		Customer_id from customer table
order_date	 	Not Null	TIMESTAMP NOT NULL DEFAULT	 	 
order_status	 	Null	VARCHAR	255	 
total_price	 	 Not Null	DECIMAL	(10,2)	 

Fertilizer					
Column Name	Key Type	Null/Unique	Data Type	Max Length	FK Reference Table
fertilizer_id	PK(Auto Increment)	Not Null	INT		 
fertilizer_name	 	Not Null	VARCHAR	255	 
fertilizer_type	 	Not Null	VARCHAR	255	 
fertilizer_nutrient_content	 	 	TEXT	500	 
fertilizer_storage_condition	 	 Null	VARCHAR	255	 
fertilizer_expiry_date	 	 Not Null	DATE	 	 
Transaction 					
Column Name	Key Type	Null/Unique	Data Type	Max Length	FK Reference Table
transaction_id	PK(Auto Increment)	Not Null	INT		 
transaction_price	 	Not Null	DECIMAL	(10,2)	 
transaction_mode	 	Not Null	VARCHAR	255	 
Service					
Column Name	Key Type	Null/Unique	Data Type	Max Length	FK Reference Table
service_id	PK(Auto Increment)	Not Null	INT		 
service_name	 	Not Null	VARCHAR	255	 
service_description	 	 Null	TEXT	500	 
servcie_price	 	 	DECIMAL	(10,2)	 
Service_availability		Not Null	TIMESTAMP		

Appointment 					
Column Name	Key Type	Null/Unique	Data Type	Max Length	FK Reference Table
appointment_id	PK(Auto Increment)	Not Null	INT		 
appointment_slot	 	Not Null	DATETIME		 
appointment_service	 FK	Null	INT		 
customer_id			INT		
Order 
					
Column Name	Key Type	Null/Unique	Data Type	Max Length	FK Reference Table
order_detail_id 	PK(Auto Increment)	Not Null	INT		 
order_id	PK	Not Null	INT		
plant_id		Not Null	INT		
order_quantity	 	Null	INT		 
unit_price	 	Null	DECIMAL	(10,2)	 
					
Create Database and Data Insert Script
 
   CREATE TABLE `Plant` (
  `plant_id` int NOT NULL AUTO_INCREMENT,
  `plant_scientific_name` varchar(255) DEFAULT NULL,
  `plant_common_name` varchar(255) NOT NULL,
  `plant_type` varchar(255) DEFAULT NULL,
  `plant_price` decimal(10,2) DEFAULT NULL,
  `plant_description` text,
  `plant_image_url` varchar(255) DEFAULT NULL,
  `plant_availability` tinyint(1) NOT NULL DEFAULT '1',
  `plant_quantity` int NOT NULL,
  PRIMARY KEY (`plant_id`),
  UNIQUE KEY `unique_plant_name` (`plant_common_name`)
)

CREATE TABLE Supplier (
  supplier_id INT NOT NULL AUTO_INCREMENT,
  supplier_name VARCHAR(255) NOT NULL,
  contact_person VARCHAR(255) NULL,
  email_id VARCHAR(255) NULL,
  phone_number VARCHAR(20) NOT NULL,
  supplier_address TEXT(500),
  PRIMARY KEY (supplier_id)
);


CREATE TABLE Plant_Requirement (
  requirement_id INT NOT NULL AUTO_INCREMENT,
  requirement_name VARCHAR(255) UNIQUE NOT NULL,
  requirement_description TEXT(500),
  fertilizer_id INT NOT NULL,
  pesticide_id INT NOT NULL,
  PRIMARY KEY (requirement_id),
  FOREIGN KEY (fertilizer_id) REFERENCES Fertilizer (fertilizer_id),
  FOREIGN KEY (pesticide_id) REFERENCES Pesticide(pesticide_id)
);

 CREATE TABLE `plant_has_plantrequirement` (
 `plant_id` INT NOT NULL, 
`requirement_id` INT NOT NULL, 
 PRIMARY KEY (`plant_id`,`requirement_id`),
 KEY `requirement_id` (`requirement_id`) 
);

  CREATE TABLE Customer (
  customer_id INT NOT NULL AUTO_INCREMENT,
  customer_first_name VARCHAR(255) NOT NULL,
  customer_last_name VARCHAR(255) NOT NULL,
  customer_email_id VARCHAR(255) ,
  customer_phone_number VARCHAR(20) NOT NULL,
  customer_address TEXT(500),
  customer_payment_method VARCHAR(255),
  customer_preference_plant_type VARCHAR(255),
  PRIMARY KEY (customer_id)
);

  CREATE TABLE `Order` (
  order_id INT NOT NULL AUTO_INCREMENT,
  customer_id INT NOT NULL,
  order_date DATETIME NOT NULL,
  order_status VARCHAR(255),
  total_price DECIMAL(10,2) NOT NULL,
  PRIMARY KEY (order_id),
  FOREIGN KEY (customer_id) REFERENCES Customer(customer_id)
);


  CREATE TABLE ‘Order_Detail’ (
  order_detail_id INT NOT NULL AUTO_INCREMENT,
  order_id INT NOT NULL,
  plant_id INT NOT NULL,
  order_quantity INT NOT NULL,
  unit_price DECIMAL(10,2) NOT NULL,
  PRIMARY KEY (order_detail_id),
  FOREIGN KEY (order_id) REFERENCES `Order`(order_id),
  FOREIGN KEY (plant_id) REFERENCES Plant(plant_id)
);


  CREATE TABLE ‘Transaction’(
  transaction_id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
  transaction_mode VARCHAR(255) NOT NULL,
  transaction_price DECIMAL(10,2) NOT NULL,
  order_id INT,
  appointment_id INT,
  FOREIGN KEY (order_id) REFERENCES `order`(order_id),
  FOREIGN KEY (appointment_id) REFERENCES appointment(appointment_id)
);

   CREATE TABLE `Gardening Tool` (
  `gardening_tool_id` int PRIMARY KEY NOT NULL AUTO_INCREMENT,
  `gardening_tool_name` varchar(255) UNIQUE NOT NULL,
  `gardening_tool_type` varchar(255) DEFAULT NULL,
  `gardening_tool_description` text,
  `gardening_tool_price` decimal(10,2)
)

  CREATE TABLE ‘Fertilizer’ (
  fertilizer_id INT NOT NULL AUTO_INCREMENT,
  fertilizer_name VARCHAR(255) NOT NULL,
  fertilizer_type VARCHAR(255) NOT NULL,
  fertilizer_nutrient_content TEXT(500),
  fertilizer_storage_condition VARCHAR(255),
  fertilizer_expiry_date DATE NOT NULL,
  PRIMARY KEY (fertilizer_id) );
 
  CREATE TABLE ‘Pesticide’ (
  pesticide_id INT NOT NULL AUTO_INCREMENT,
  pesticide_name VARCHAR(255) NOT NULL,
  pesticide_type VARCHAR(255) NULL,
  pesticide_target_pest VARCHAR(255) NULL,
  pesticide_expiry_date DATE NOT NULL,
  pesticide_storage_condition VARCHAR(255) NULL,
  PRIMARY KEY (pesticide_id)
);

    CREATE TABLE ‘Service’ (
    service_id INT NOT NULL AUTO_INCREMENT,
    service_name VARCHAR(255) NOT NULL UNIQUE,
    service_description TEXT(500),
    service_price DECIMAL(10,2) NOT NULL,
    service_availability VARCHAR(255) NOT NULL,
    PRIMARY KEY (service_id)
);

   CREATE TABLE ‘Appointment’ (
    appointment_id INT NOT NULL AUTO_INCREMENT ,
    appointment_slot DATETIME NOT NULL,
    appointment_service INT NOT NULL,
    customer_id INT NOT NULL,
    PRIMARY KEY (appointment_id),
    FOREIGN KEY (appointment_service) REFERENCES Service(service_id)
);
  CREATE TABLE ‘plant_needs_gardening_tool’ (
  plant_id INTEGER NOT NULL,
  gardening_tool_id INTEGER NOT NULL,
  primary key (plant_id, gardening_tool_id),
  FOREIGN KEY (plant_id) REFERENCES plant (plant_id),
  FOREIGN KEY (gardening_tool_id) REFERENCES gardening_tool (gardening_tool_id)
);
 
  CREATE TABLE ‘supplier_supplies_plant’ (
  plant_id INT NOT NULL,
  supplier_id INT NOT NULL,
  PRIMARY KEY (plant_id, supplier_id),
  FOREIGN KEY (plant_id) REFERENCES plant(plant_id),
  FOREIGN KEY (supplier_id) REFERENCES supplier(supplier_id)
);

  CREATE TABLE ‘plant_has_plantrequirement’ (
  plant_id INT NOT NULL,
  requirement_id INT NOT NULL,
  PRIMARY KEY (plant_id, requirement_id),
  FOREIGN KEY (plant_id) REFERENCES plant(plant_id),
  FOREIGN KEY (requirement_id) REFERENCES plant_requirement(requirement_id)
);



Data insertion for the tables 

Plant
INSERT INTO `nursery`.`plant` (`plant_scientific_name`, `plant_common_name`, `plant_type`, `plant_price`, `plant_description`, `plant_image_url`, `order_id`, `plant_quantity`) VALUES 
('Aloe vera', 'Aloe vera', 'Succulent', '5.98', 'A succulent plant with thick, fleshy leaves that can grow up to 1 foot tall. It is often grown for its medicinal properties and ability to purify the air.', 'https://hips.hearstapps.com/hmg-prod/images/aloe-vera-plant-outside-jpg-1522875135.jpg', '1', '50'),
('Chlorophytum comosum', 'Spider plant', 'House Plant', '14.98', 'A popular houseplant with long, narrow leaves that can grow up to 3 feet long. It produces small, white flowers and is known for its air-purifying abilities.', 'https://m.mediaamazon.com/images/I/51wtlZUB5ML._AC_.jpg', '2', '10'),
('Sansevieria trifasciata', 'Snake plant', 'succulent', '22.98', 'A hardy plant with stiff, sword-shaped leaves that can grow up to 3 feet tall. It is also known for its air-purifying properties and ability to tolerate low light conditions.', 'https://mobileimages.lowes.com/productimages/1b24ade4-b769-421b-975f-8d35bc0a21ef/02964735.jpg?size=pdhism', '3', '33'),
('Aglaonema spp.', 'Chinese evergreen', 'House Plant', '15.98', 'A tropical plant with variegated leaves that can grow up to 3 feet tall. It is prized for its ornamental value and ability to thrive in low light conditions.', 'https://mobileimages.lowes.com/productimages/b543dab8-62d8-4170-8261-4ba9c5cdee10/02811786.jpg?size=pdhism ', '2', '10'),
('Spathiphyllum spp.', 'Peace lily', 'House Plant', '13.98', 'A popular houseplant with glossy, dark green leaves and white, spoon-shaped flowers. It is knownfor its ability to purify the air and thrive in low light conditions.', 'https://mobileimages.lowes.com/productimages/21f1cafd-e82c-4364-9176-bbd5f918a554/49044411.jpg?size=pdhism', '3', '43'),
('Ficus elastica', 'Rubber plant', 'House Plant', '27.98', ' A large, tropical plant with shiny, rubbery leaves that can grow up to 8 feet tall. It is often grown as a statement plant and can tolerate low light conditions.', 'https://mobileimages.lowes.com/productimages/6b31a7f4-f2cd-4b2b-94ed-cbb577c91553/62236959.jpg?size=pdhism ', '4', '20'),
('Epipremnum aureum', 'Pothos', 'House Plant', '14.98', 'A trailing vine with heart-shaped leaves that can grow up to 6 feet long. It is a low-maintenance plant that can tolerate
 low light conditions and is often grown in hanging baskets.',  'https://i5.walmartimages.com/asr/5a22cde7-f8c9-4e36-a600-f6c1ae2d0d80.d80111246be3725d3c33e962ce2df5b0.png?odnHeight=612&odnWidth=612&odnBg=FFFFFF ', '4', '1'),
('Zamioculcas zamiifolia', 'ZZ plant', 'Succulent', '29.98', 'A tropical plant with glossy, dark green leaves that can grow up to 3 feet tall. It is known for its low-maintenancerequirements and ability to thrive in low light conditions.', 'https://mobileimages.lowes.com/productimages/d2d55133-e2e2-4466-aec2-fd9aca50f3cb/04299209.jpg?size=pdhism ', '5', '154'),
('Ficus lyrata', 'Fiddle leaf fig', 'Bush plant', '22.98', 'A popular houseplant with large, violin-shaped leaves that can grow up to 10 feet tall. It is often grown as a statement plant and requires bright, indirect light.',  'https://mobileimages.lowes.com/productimages/a02fab72-0efb-4c14-8ba1-b748180f666a/11025258.jpg?size=pdhism', '4', '14'),
('Nephrolepis exaltata', 'Boston fern', 'Bush plant', '17.98', 'A popular fern with delicate, feathery fronds that can grow up to 3 feet long. It is known for its air-purifying properties and is often grown in hanging baskets.',  'https://mobileimages.lowes.com/productimages/6537ccd7-3c7f-4d55-bacd-cb01350f6391/62600242.jpg?size=pdhism', '5', '17'),
('Rosa rubiginosa', 'Rose', 'perennial shrubs', '19.71', 'A popular fern with delicate, feathery fronds that can grow up to 3 feet long. It is known for its air-purifying properties and is often grown in hanging baskets.', 'https://mobileimages.lowes.com/productimages/366c8396-2d35-4caf-b3b5-a48db95c1ea1/16152869.jpg?size=pdhism', '3', '18');

Supplier
INSERT INTO Supplier (supplier_name, contact_person, email_id, phone_number, supplier_address)
VALUES ('ABC Suppliers', 'John Doe', 'johndoe@example.com', '555-123-4567', '123 Main St'),
    ('XYZ Suppliers', 'Jane Smith', 'janesmith@example.com', '555-987-6543', '456 Oak Ave'),
    ('123 Supplies', 'Bob Johnson', 'bobjohnson@example.com', '555-555-5555', '789 Maple Rd'),
    ('Acme Supplies', 'Sally Johnson', 'sallyjohnson@example.com', '555-555-1212', '456 Elm St'),
    ('Green Industries', 'Tom Green', 'tgreen@example.com', '555-222-3333', '567 Pine Ave'),
    ('Smith and Sons', 'Chris Smith', 'csmith@example.com', '555-444-5555', '789 Oak St'),
    ('Jones Enterprises', 'Frank Jones', 'fjones@example.com', '555-888-9999', '345 Maple Ave'),
    ('Blue Supplies', 'Mary Blue', 'maryblue@example.com', '555-777-7777', '567 Elm St'),
    ('Sunshine Co.', 'Sam Sunshine', 'ssunshine@example.com', '555-123-7890', '123 Oak Ave'),
    ('Rainbow Industries', 'Anna Rainbow', 'arainbow@example.com', '555-456-7890', '345 Pine St');
Plant Requirement
INSERT INTO `plant_requirement` (requirement_name, requirement_description,fertilizer_id,pesticide_id)
VALUES 
    ('Sunlight', 'This plant requires full sunlight for at least 6 hours a day.',1,8),
    ('Watering', 'This plant requires to be watered once a week.',2,9),
    ('Humidity', 'This plant requires high humidity levels.',3,10),
    ('Temperature', 'This plant requires a temperature between 65-75°F.',4,11),
    ('Fertilizer', 'This plant requires regular fertilization every two weeks.',5,12),
    ('Pruning', 'This plant requires periodic pruning to maintain its shape and health.',2,13),
    ('Potting', 'This plant requires repotting every 1-2 years.',3,14),
    ('Pest Control', 'This plant requires regular pest control measures.',4,9),
    ('Support', 'This plant requires support for its stem or branches.',5,8),
    ('Soil Type', 'This plant requires well-draining soil with a pH of 6-7.',2,10);

Customer
INSERT INTO `customer` (customer_first_name, customer_last_name, customer_email_id, customer_phone_number, customer_address, customer_payment_method,customer_preference_plant_type)
VALUES 
('Aravind' , 'Anupindi' ,  'aravind.anupindi@gmail.com', '+1 9803279745','605 Sharview Cir , ' , 'Credit Card' , 'Rose and Aloevera' ),
('Subbu', 'Narravula' , 'subbu.thanneru@gmail.com' , '+1 9803279747' ,'805 Habersham Point Cir' , 'Zelly' , 'Spider, Aloe vera'),
('Suraj','Korrapti' , 'suraj.korrapti@gmail.com' ,  '+1 9803279749' , '6000 Scarlet Sky Lane','Cerdit Card' , 'Chinese evergreen'),
(' Smith',' William','smith.william@gmail.com','+19803279741','7815 Calibre Crossing Drive','Zelly','Bostan fern'),
('Andrew','John','andrew.john@gmail.com','+1 9803279742','11010 Northlake Landing Drive','Cash','Rose'),
('Samantha', 'John' , 'samantha.john@gmail.com' , '+1 9803279743' , '425 West 5th Street', 'Credit card' , 'rose , spider plant , bostan ferns , pothos, ZZ plant'),
('Emily', 'Sarah' , 'emily.sarah@gmail.com', '+ 1 9803279800' , '200 Brook Arbor Dr' ,'Cash' , 'ZZ plant,rose'),
('Robert', 'Christopher' , 'robert.christopher@gmail.com' , '+ 1 9803278900' , '5110 Alston Glen Dr.' ,'credit card' , 'Peace lilly , Pothos , ZZ plant Fiddle leaf fig , snake plant')


Fertilizer
INSERT INTO `fertilizer` (fertilizer_name, fertilizer_type, fertilizer_nutrient_content, fertilizer_storage_condition, fertilizer_expiry_date)
VALUES 
('Nitrogen','','contain mostly nitrogen and are used to promote leafy growth','cool, dry place','2025-04-15'),
('Phosphorus','','contain mostly phosphorus and are used to promote root growth and flowering.','cool, dry place','2025-03-15'),
('Potassium','','contain mostly potassium and are used to promote overall plant health, stress tolerance, and fruit development','cool, dry place','2025-03-15'),
('Organic','','made from natural materials like compost, manure, and bone meal.','cool, dry place','2025-04-15'),
('Liquid','','mixed with water and applied directly to the soil or foliage','cool, dry place','2025-02-15')




Pesticide
INSERT INTO `pesticide` (pesticide_name, pesticide_type,pesticide_target_pest,pesticide_expiry_date,pesticide_storage_condition)
VALUES 
('Neem oil','Organic pesticide','Targets a wide range of pests, including aphids, whiteflies, and spider mites.','2025/04/15','Store in a cool, dry place.'),
('Pyrethrin','','Targets a variety of pests, including beetles, caterpillars, and aphids','2026/03/04','Store in a cool, dry place.'),
('Bacillus thuringiensis (Bt)','Natural','Targets caterpillars and other larvae','2023/03/24','Store in a cool, dry place.'),
('Spinosad','Natural','Targets a variety of pests, including thrips, spider mites, and caterpillars.','2024/04/23','Store in a cool, dry place.'),
('Imidacloprid','Synthetic','targets sucking insects like aphids, mealybugs, and scale.','2025/05/24','Store in a cool, dry place.'),
('Malathion','Synthetic','targets a variety of insects, including aphids, spider mites, and thrips.','2027/4/23','Store in a cool, dry place.'),
('Carbaryl','Synthetic','targets a variety of pests, including caterpillars, beetles, and aphids.','2024/3/2','Store in a cool, dry place.')

Gardening tool
INSERT INTO `gardening_tool` (gardening_tool_name, gardening_tool_type, gardening_tool_description,gardening_tool_price)
VALUES 
    ('Trowel', '','A hand tool with a pointed, scoop-shaped blade used for digging small holes for planting or transplanting seedlings. Trowels can 
    also be used for removing weeds and cultivating soil in small areas.','15'),
    ('Garden fork', 'Digging tool','A tool with several pointed prongs used for loosening soil 
    and removing weeds. Garden forks can also be used for turning compost piles.','13.3'),
    ('Pruning shears', 'Pruning tool','known as secateurs, pruning shears are used for cutting small branches and stems. 
    They come in various sizes and styles, including bypass, anvil, and ratchet pruners.','21'),
    ('Garden gloves', 'Protective tool','Protective gloves worn while working in the garden to prevent blisters and cuts. Garden gloves come in
    various materials, including leather, rubber, and cotton.','10.99'),
    ('Garden shovel','Digging tool', 'A tool with a long handle and a scoop-shaped blade used for digging, planting, and moving soil. Garden shovels come in various 
    styles, including spade shovels, round point shovels, and square point shovels.','20.00')

Service 
INSERT INTO `service` (service_name, service_description, service_price, service_availability)
VALUES 
('Watering', 'Watering plants once a week', 20, 'Monday-Friday'),
('Trimming', 'Trimming plants every two weeks', 35, 'Monday, Wednesday, Friday'),
('Fertilizing', 'Fertilizing plants once a month', 50, 'Tuesday, Thursday'),
('Repotting', 'Repotting plants as needed', 75, 'By appointment only'),
('Pest control', 'Spraying for pests once a month', 45, 'Wednesday'),
('Plant styling', 'Creating stylish plant displays', 100, 'By appointment only'),
('Consultation', 'Expert advice on plant care', 60, 'By appointment only'),
('Delivery', 'Delivery of plants and supplies', 25, 'Monday-Saturday');
Appointment 
INSERT INTO appointment (appointment_slot, appointment_service,customer_id)
VALUES
('2023-04-27 14:30:00', 1, 1),
('2023-04-30 15:30:00', 1, 2),
('2023-04-28 13:00:00', 1, 3),
('2023-04-29 11:00:00', 1, 4),
('2023-05-01 13:00:00', 1, 5),
('2023-05-03 15:00:00', 1, 6);
Order
INSERT INTO `order` (customer_id,order_date,order_status,unit_price)
VALUES
(1,'2023-04-20 14:30:00','completed',20.96),
(2,'2023-04-19 10:30:00','transaction in progress',5.98),
(8,'2023-04-21 11:30:00','transaction in progress',29.98),
(4,'2023-04-18 10:00:00','completed',27.98),
(8,'2023-04-18 10:00:00','completed',22.98

Order detail
INSERT INTO order_detail (order_id,plant_id,order_quantity,total_price)
VALUES
(1,1,1,5.98),
(1,2,1,14.98),
(2,1,1,5.98),
(3,8,1,29.98),
(4,6,1,27.98),
(5,9,1,22.98);

Transaction
INSERT INTO transaction (transaction_mode,transaction_price,order_id,appointment_id)
VALUES
('Credit Card', 20.96, 1,NULL),
('Cash', 5.98, 2,null),
('Zelly', 29.98, 3,NULL),
('Credit Card', 27.98, 4,NULL),
('Zelly', 22.98,5,NULL),
('Credit Card',20.00,NULL,1);
INSERT INTO customer_service(customer_id, service_id)
VALUES
(1,1),
(2,1),
(3,1),
(4,1),
(5,1),
(6,1);
Fertilizer
INSERT INTO fertilizer_requirement(requirement_id,fertilizer_id)
VALUES
(15,1),
(16,3),
(17,4);

Gardening tool
INSERT INTO plant_gardening_tool(plant_id,gardening_tool_id)
VALUES
(1,6),
(1,7),
(2,8),
(2,9),
(3,10);

Plant requirements
INSERT INTO plant_plant_requirement(plant_id,requirement_id)
VALUES
(1,1),
(1,4),
(1,7),
(2,2),
(2,5),
(2,8),
(3,3),
(3,6),
(3,9);

Database Queries: 
1.	ALTER TABLE order_detail ADD CONSTRAINT fk_plant FOREIGN KEY (plant_id) REFERENCES plant(plant_id) ;

2.	ALTER TABLE order_detail ADD COLUMN unit_price decimal(10,2) NOT NULL;

3.	ALTER TABLE `transaction` MODIFY COLUMN transaction_price DECIMAL(10,2) NOT NULL;
 
4.	ALTER TABLE plant_gardening_tool RENAME TO plant_needs_gardening tool;

1.Query to retrieve the top 5 popular plants:
SELECT 
    p.plant_common_name,
    SUM(od.order_quantity) AS total_quantity_sold
FROM
    Plant p
        INNER JOIN
    `Order_detail` od ON p.plant_id = od.plant_id
GROUP BY p.plant_id
ORDER BY total_quantity_sold DESC
LIMIT 5;
 
2.Query to retrieve list of plants with their requirements.
SELECT
p.plant_common_name,
GROUP_CONCAT(pr.requirement_name
SEPARATOR ', ') AS requirements
FROM
Plant p
JOIN
plant_has_plantrequirement ppr ON p.plant_id = ppr.plant_id
JOIN
plant_requirement pr ON pr.requirement_id = ppr.requirement_id
GROUP BY p.plant_common_name;

3.  Query to retrieve to give a list of services that were performed by each customer and how much did they pay for those services during the between 15th April and 30th April,2023.
SELECT
c.customer_first_name,
c.customer_last_name,
s.service_name,
t.transaction_price
FROM
Customer c
JOIN Appointment a ON c.customer_id = a.customer_id
JOIN Service s ON a.appointment_service = s.service_id
JOIN Transaction t ON a.appointment_id = t.appointment_id
WHERE
a.appointment_slot BETWEEN '2023-04-15 00:00:00' AND '2023-04-30 23:59:59';

4. Query to retrieve information about customers' plant purchases, including the total number of plants purchased, the names of the plants, and the total revenue generated. Sort the results in descending order based on the number of plants purchased and group the results by each customer's first and last name.
SELECT
c.customer_first_name,
c.customer_last_name,
COUNT(od.order_quantity) AS num_plants_purchased,
GROUP_CONCAT(p.plant_common_name
SEPARATOR ', ') AS plants,
SUM(od.unit_price) AS total_revenue
FROM
`order` o
JOIN
order_detail od ON o.order_id = od.order_id
JOIN
plant p ON od.plant_id = p.plant_id
JOIN
Customer c ON c.customer_id = o.customer_id
GROUP BY c.customer_first_name , c.customer_last_name
ORDER BY num_plants_purchased DESC;

5.Write a trigger to update the plant table after inserting a record in order_detail.
DELIMITER //
CREATE TRIGGER minus_plant_quantity AFTER INSERT ON order_detail
FOR EACH ROW
BEGIN
UPDATE plant
SET plant_quantity = plant_quantity - NEW.order_quantity
WHERE plant_id = NEW.plant_id;
END
//
DELIMITER ;

6.Write a trigger to ensure that a pesticide with an expiry date that has already passed cannot be inserted into the Pesticide table.

CREATE TRIGGER pesticide_expiry_trigger
BEFORE INSERT ON Pesticide
FOR EACH ROW
BEGIN
    IF NEW.pesticide_expiry_date < CURDATE() THEN
        SIGNAL SQLSTATE '45000'
        SET MESSAGE_TEXT = 'Cannot insert. Expiry date is in the past.';
    END IF;
END;

7.Write a function to schedule an appointment for a customer.

 This function allows a customer to schedule an appointment for a service.
DELIMITER $$
CREATE FUNCTION schedule_appointment(customer_id INT, service_id INT, appointment_slot DATETIME)
RETURNS INT
DETERMINISTIC
BEGIN
DECLARE appointment_id INT;
INSERT INTO Appointment (appointment_slot, appointment_service, customer_id)
VALUES (appointment_slot, service_id, customer_id);
SET appointment_id = LAST_INSERT_ID();
RETURN appointment_id;
END $$
DELIMITER ;
 
 
 




