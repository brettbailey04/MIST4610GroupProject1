# Ski-Resort-
Project 1 - Ski resort 

Team Members: Brett Bailey, Brooke Credendino, Mohammed Omar, Evan Langley, Soham Gupta

Links to each GitHub repository: 
Brett: https://github.com/brettbailey04/Ski-Resort-.git
Brooke: 
Mohammed: 
Evan: 
Soham: 

Scenario Description: Our business model is that of a Ski Resort. This firm manages a portfolio of various Ski Resorts over the world. The model keeps track of the resort and its various amenities. This includes Equipment, Food, Housing, Recreational Events, Skiing Courses, and the various intricacies that are pertinent to a functioning resort. 

Data Model:
![image](https://github.com/user-attachments/assets/df10cd73-77bd-4207-9994-aa319c743be6)


Data Dictionary: 


Queries: 

Query 1: This query lists all active reservations with Check In and Check Out dates. This query would be useful for a resort manager to know so that they do not book more than one party at each available location or allow a location to be vacant as to maximize reveunes of the resort. 

<img width="846" alt="Screenshot 2025-03-16 at 6 01 45 PM" src="https://github.com/user-attachments/assets/949137ca-1076-43f0-b68a-9c3f1e6cf1ca" />

Query 2: This query lists out the total number of guests currently staying at the resort. This could be useful for a resort manager to see how many people have reservations at the resort in real time. This could also be useful to maximize profit similaryly to Query 1.

<img width="846" alt="Screenshot 2025-03-16 at 6 08 43 PM" src="https://github.com/user-attachments/assets/6bf3a655-8521-4004-8436-68f275484bfa" />



Query 3:  This query shows all available rental equipment. This is important for a manager because it allows them to see what equipment is available at the resort in real time. This is useful to have because a manager would want to know what equipment, equipment types, and equipment sizes are not readily available. 

<img width="846" alt="Screenshot 2025-03-16 at 6 11 36 PM" src="https://github.com/user-attachments/assets/2efcdd19-897e-4a1e-b595-2fa1e0c06290" />



-- 4: Shows all hotel names and locations 

CREATE Procedure TP_Q4()
SELECT hotelName, hotelLocation 
FROM Hotel;

Output:


-- Complex queries 5-10


-- 5: Find the most expensive room booked in each hotel

CREATE Procedure TP_Q5()
SELECT Hotel.hotelName, Room.roomType, Room.roomPrice
FROM Room
JOIN Hotel ON Room.hotelID = Hotel.hotelID
WHERE Room.roomPrice = (SELECT MAX(Room.roomPrice) FROM Room WHERE Room.hotelID = Hotel.hotelID);

Output:



-- 6: Show revenue from room bookings per hotel 

CREATE Procedure TP_Q6()
SELECT Hotel.hotelName, SUM(Room.roomPrice) AS Revenue
FROM Room
JOIN Hotel ON Room.hotelID = Hotel.hotelID
WHERE Room.reservationID IS NOT NULL
GROUP BY Hotel.hotelName;

Output:



-- 7: Show instructors who are currently available and assigned to a lesson

CREATE Procedure TP_Q7()
SELECT Instructor.instructorName, Lesson.lessonDate, Lesson.lessonTime, Trail.trailName
FROM Instructor
JOIN Instructor_has_Lesson ON Instructor.instructorID = Instructor_has_Lesson.instructorID
JOIN Lesson ON Instructor_has_Lesson.lessonID = Lesson.lessonID
JOIN Trail ON Lesson.trailID = Trail.trailID
WHERE Instructor.instructorAvailability = 'Available';

Output:



-- 8:  Find the hotels with the highest ranking 

CREATE Procedure TP_Q8()
SELECT Hotel.hotelName, Restaurant.restaurantName, Hotel.hotelRating
FROM Hotel
JOIN Restaurant ON Hotel.hotelID = Restaurant.hotelID
WHERE Hotel.hotelRating = (SELECT MAX(Hotel.hotelRating) FROM Hotel);

Output:



-- 9:  Find trails with an operational lift and their difficulty level

CREATE Procedure TP_9()
SELECT Trail.trailName, Trail.trailDifficulty
FROM Trail
JOIN Lift ON Trail.trailID = Lift.trailID
GROUP BY Trail.trailName, Trail.trailDifficulty;

Output:



-- 10: Displays the highest-paid rental shop employee at each rental shop 

CREATE Procedure TP_Q10()
SELECT RentalShop.rentalShopName, rentalShopStaff.staffName, rentalShopStaff.staffSalary
FROM rentalShopStaff
JOIN RentalShop ON rentalShopStaff.rentalShopID = RentalShop.rentalShopID
WHERE rentalShopStaff.staffSalary = (SELECT MAX(rentalShopStaff.staffSalary) FROM rentalShopStaff WHERE rentalShopStaff.rentalShopID = RentalShop.rentalShopID);

Output:



