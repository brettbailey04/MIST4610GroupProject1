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
-- 1: Lists all active reservations w/ check in and check out dates 

Create Procedure TP_Q1()
SELECT reservationID, checkInDate, checkOutDate 
FROM Reservation 
WHERE checkOutDate >= '2025-03-12';

Output:


-- 2: Total number of guests staying at the resort 

CREATE Procedure TP_Q2()
SELECT COUNT(guestID) AS totalGuests 
FROM Guest;

Output:


-- 3: Shows all available rental equipment 

CREATE Procedure TP_Q3()
SELECT equipmentID, equipmentType, equipmentSize 
FROM Equipment 
WHERE equipmentAvailability = 'Available';

Output:



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



