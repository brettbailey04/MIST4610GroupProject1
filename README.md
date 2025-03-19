# Group 1 MIST 4610 Group Project 1 
# Team Name:
21479 Group 1

# Team Members: 
1) Brett Bailey [@brettbailey04](https://github.com/brettbailey04)
2) Brooke Credendino [@BrookeCredendino](https://github.com/BrookeCredendino)
3) Mohammed Omar [@momo103103](https://github.com/momo103103)
4) Evan Langley [@elangley424](https://github.com/elangley424)
5) Soham Gupta [@GHSohamGupta](https://github.com/GHSohamGupta)

 

# Scenario Description: 
The scenario we have been given is to model and create a relational database for the basic functions of a Ski Resort. The central entity of the model is the Hotel entity. The Hotel entity represents the various residential buildings the resort obtains throughout the entirety of its limits. The hotel is operated alongside the restaurants within them, the rental shop within them, and the respective reservations/excursions guests within them have booked. We are interested in creating high fidelity models of these relationships, having accurate and descriptive attributes, generating and populating sample data, and displaying valuable insights. Information gathered from queries will be important to the Ski Resort and many of its daily operations as it strives to efficiently utilize its various provided amenities and accommodations. 

# Data Model: 
Explanation of data model: 

Our model is structured around a ski resort and the various amenities housed within.

The core entity we begin with is Hotel. The hotel entity refers to the various hotel buildings scattered around the resort. Each hotel has various hotel staff that work singularly to that hotel (one-to-many). Within each hotel there are many rooms that comprise the building (one-to-many).Multiple rooms can be a part of one reservation but more than one reservation can not spill into the same room (one-to-many). 

A reservation can contain many guests but guests can not be in more than one reservation (one-to-many). Within the reservation there can also be various lessons (one-to-many). Each lesson is attributed to one trail and each trail to one respective lift (one-to-one). A lesson can have many instructors and the instructors can each teach many lessons (many-to-many/associative).

Back towards the hotel, each hotel contains various types and cuisine of restaurants and those restaurants are present solely within each respective hotel (one-to-many). The restaurant has many restaurant staff that each work independently to that respective restaurant (one-to-many). 

Each hotel also has its own personal rent shop (one-to-one). The rent shop has various employees that work at them, and each rental shop has a wide array of various Ski equipment designated specifically for their respective shop (one-to-many). 


![image](https://github.com/user-attachments/assets/df10cd73-77bd-4207-9994-aa319c743be6)


# Data Dictionary: 





<img width="616" alt="Screenshot 2025-03-17 at 6 37 22 PM" src="https://github.com/user-attachments/assets/17baa2c9-1d2c-4fcf-8d38-465274c96e51" />
<img width="616" alt="Screenshot 2025-03-17 at 6 37 45 PM" src="https://github.com/user-attachments/assets/7812c4de-bb41-460a-b1fd-6b11e318ce8f" />
<img width="616" alt="Screenshot 2025-03-17 at 6 37 55 PM" src="https://github.com/user-attachments/assets/6c775643-93a3-4ba7-845f-6819ccc3b9d7" />
<img width="616" alt="Screenshot 2025-03-17 at 6 38 05 PM" src="https://github.com/user-attachments/assets/c9b03663-d738-4992-bc0b-9c9b27444994" />
<img width="616" alt="Screenshot 2025-03-17 at 6 38 17 PM" src="https://github.com/user-attachments/assets/d22bfc65-f3e2-48d4-a4b1-1181d75c9f26" />



                                                                                             



# Queries: 

<img width="1227" alt="Screenshot 2025-03-17 at 8 00 38 PM" src="https://github.com/user-attachments/assets/b20e1707-4900-49c5-9aad-240ceb93d9d9" />





Query 1: This query lists all upcoming reservations with Check In and Check Out dates. This query would be useful for a resort manager to know so that they do not book more than one party at each available location or allow a location to be vacant as to maximize reveunes of the resort. 

<img width="677" alt="Screenshot 2025-03-17 at 4 31 23 PM" src="https://github.com/user-attachments/assets/bd24ccef-a1d5-4901-8514-2b82ce248496" />



Query 2: This query lists out the total number of guests currently staying at the resort. This could be useful for a resort manager to see how many people have reservations at the resort in real time. This could also be useful to maximize profit similarly to Query 1.

<img width="846" alt="Screenshot 2025-03-16 at 6 08 43 PM" src="https://github.com/user-attachments/assets/6bf3a655-8521-4004-8436-68f275484bfa" />



Query 3:  This query shows all available rental equipment. This is important for a manager because it allows them to see what equipment is available at the resort in real time. This is useful to have because a manager would want to know what equipment, equipment types, and equipment sizes are not readily available. 

<img width="846" alt="Screenshot 2025-03-16 at 6 26 04 PM" src="https://github.com/user-attachments/assets/db34cde1-1a16-43e7-9c48-10ca396366a2" />



Query 4:  This query shows all hotel names and locations. This is important because it allows the manager to view all individual hotels and their corresponding locations as well as their maximum capacities. This ensures that any one hotel is not overbooked. 

<img width="846" alt="Screenshot 2025-03-16 at 6 30 06 PM" src="https://github.com/user-attachments/assets/e71d1ded-ceff-4235-8ddc-e3b335c0728d" />



-- Complex queries 5-10


Query 5: This query allows the manager to view the most expensive room in each hotel. This information would be useful to a resort manager to ensure that the most expensive rooms receive proper maintenance, maintain customer satisfaction for high-end rooms, and maintain a competitive edge in terms of pricing when comparing to other resorts. 

<img width="846" alt="Screenshot 2025-03-16 at 6 40 58 PM" src="https://github.com/user-attachments/assets/1c66428a-6934-4db3-9e18-bed63f35a17d" />



Query 6: This Query show revenue from room bookings per hotel. This would be useful to a manager to track financial progress of a hotel, manage pricing and revenue, create accurate budgets, and provide insight for expansion and further investments for each hotel under the firm's management. Because this data is snapshot in time, many data values are similar to query 5 but would differ as different rooms are booked at different times. 

<img width="846" alt="Screenshot 2025-03-16 at 6 42 26 PM" src="https://github.com/user-attachments/assets/d2c8f18a-4319-4bd5-a06e-b96947c20e1b" />



Query 7: This query shows instructors who are currently available and assigned to a lesson. This is important to a manager so they know if an instructor is not present for an event, to ensure guest satisfaction during excursions, and to monitor the performance of each instructor. 

<img width="836" alt="Screenshot 2025-03-17 at 4 32 02 PM" src="https://github.com/user-attachments/assets/770ebedf-038f-4c36-b51f-53771e1f5c07" />



Query 8: This query allows the resort manager to view the hotels with the highest ratings. This is useful because it allows the manager to understand and identify areas where the resort is doing well in terms of customer satisfaction. It could also allow the manager learn what customers liked and why they rated the hotels as highly as they did in order to allign the resort's practices with guests' expectations. 

<img width="628" alt="Screenshot 2025-03-17 at 3 07 00 PM" src="https://github.com/user-attachments/assets/ccefdde5-4ae3-4864-8dea-8921f7576fcf" />




Query 9: This query allows the resort manager to view all ski trails and their respective diffulty rankings. This is important for a manager to know to ensure guest safety, allocate appropriate resources to each trail, configure responses for emergencies that may arise, and plan for ski events depending on skill levels for guests. 



<img width="836" alt="Screenshot 2025-03-17 at 4 32 38 PM" src="https://github.com/user-attachments/assets/4b84f509-8cd4-41aa-a30b-baee5e47bc0b" />


Query 10: This query displays the highest-paid rental shop employee at each equipment rental shop. This query is important for a resort manager to know so they are able to accurately manage each rental shop's budget, identify employees and determine their performance, recognize talented employees, and compare and standardize employee salaries for each loaction. 

<img width="1023" alt="Screenshot 2025-03-17 at 4 33 11 PM" src="https://github.com/user-attachments/assets/0d6a7a16-6995-4ca9-8e17-ea3ab692152e" />


# Database Information:                                                                                                                      
Name of database: ns_Sp25_21479_Group1;

Additional information: Each query listed above is marked in the database using stored procedures which can be called using the following format: CALL TP_Q#();
