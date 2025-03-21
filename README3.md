
CREATE TABLE Gym1 (
    GymID INT PRIMARY KEY,
    GymName VARCHAR(100),
    Address VARCHAR(100),
    City VARCHAR(50),
    PhoneNumber VARCHAR(15),
    Email VARCHAR(100),
    OwnerName VARCHAR(100)
);

CREATE TABLE GymManager1 (
    ManagerID INT PRIMARY KEY,
    GymID INT,
    ManagerName VARCHAR(100),
    ManagerPhone VARCHAR(15),
    ManagerEmail VARCHAR(100),
    FOREIGN KEY (GymID) REFERENCES Gym1(GymID) ON DELETE CASCADE
);

CREATE TABLE GymMember1 (
    MemberID INT PRIMARY KEY,
    GymID INT,
    MemberName VARCHAR(100),
    MemberDOB DATE,
    MemberPhone VARCHAR(15),
    MemberEmail VARCHAR(100),
    JoinDate DATE,
    FOREIGN KEY (GymID) REFERENCES Gym1(GymID) ON DELETE CASCADE
);
CREATE TABLE GymFee1 (
    FeeID INT PRIMARY KEY,
    GymID INT,
    FeeAmount DECIMAL(10, 2),
    FeeType VARCHAR(50),
    StartDate DATE,
    EndDate DATE,
    FOREIGN KEY (GymID) REFERENCES Gym1(GymID) ON DELETE CASCADE
);

CREATE TABLE GymMembership1 (
    MembershipID INT PRIMARY KEY,
    MemberID INT,
    GymID INT,
    FeeID INT,
    MembershipType VARCHAR(100),
    StartDate DATE,
    EndDate DATE,
    Status VARCHAR(100),
    PaymentStatus VARCHAR(100),
    FOREIGN KEY (MemberID) REFERENCES GymMember1(MemberID) ON DELETE CASCADE,
    FOREIGN KEY (GymID) REFERENCES Gym1(GymID) ON DELETE CASCADE,
    FOREIGN KEY (FeeID) REFERENCES GymFee1(FeeID) ON DELETE CASCADE
);

CREATE TABLE GymTrainer1 (
    TrainerID INT PRIMARY KEY,
    GymID INT,
    TrainerName VARCHAR(100),
    TrainerSpecialty VARCHAR(100),
    TrainerPhone VARCHAR(15),
    TrainerEmail VARCHAR(100),
    FOREIGN KEY (GymID) REFERENCES Gym1(GymID) ON DELETE CASCADE
);

CREATE TABLE GymEquipment1 (
    EquipmentID INT PRIMARY KEY,
    GymID INT,
    EquipmentName VARCHAR(100),
    EquipmentType VARCHAR(50),
    PurchaseDate DATE,
    Condition VARCHAR(50),
    FOREIGN KEY (GymID) REFERENCES Gym1(GymID) ON DELETE CASCADE
);

CREATE TABLE GymDietPlan1 (
    DietPlanID INT PRIMARY KEY,
    GymID INT,
    DietName VARCHAR(100),
    DietDescription varchar(100),
    Price integer,
    FOREIGN KEY (GymID) REFERENCES Gym1(GymID) ON DELETE CASCADE
);



INSERT INTO Gym1 VALUES(1, 'FitWorld', '123 Fitness St', 'New York', '123-456-7890', 'contact@fitworld.com', 'naitik')
INSERT INTO Gym1 VALUES(2, 'PowerHouse Gym', '456 Muscle Ave', 'Los Angeles', '987-654-3210', 'info@powerhouse.com', 'prince')
INSERT INTO Gym1 VALUES(3, 'Iron Temple Fitness', '789 Iron Rd', 'Chicago', '555-212-3434', 'contact@irontemple.com', 'hina')
INSERT INTO Gym1 VALUES(4, 'Muscle Lab', '101 Strength Ln', 'Houston', '555-342-4545', 'info@musclelab.com', 'umesh')
INSERT INTO Gym1 VALUES(5, 'Peak Performance Gym', '202 Peak Blvd', 'Miami', '555-564-6767', 'support@peakperformance.com', 'manasvi')
INSERT INTO Gym1 VALUES(6, 'FlexFit Studios', '303 Flex St', 'Los Angeles', '555-676-7878', 'flexfit@studio.com', 'naitik')
INSERT INTO Gym1 VALUES(7, 'StrengthZone', '404 Power Dr', 'Austin', '555-898-9090', 'contact@strengthzone.com', 'prince')
INSERT INTO Gym1 VALUES(8, 'BodyCraft Gym', '505 Body Rd', 'Dallas', '555-213-4321', 'info@bodycraft.com', 'umesh')
INSERT INTO Gym1 VALUES(9, 'EliteFit', '606 Elite Ave', 'San Francisco', '555-234-5454', 'contact@elitefit.com', 'hina')
INSERT INTO Gym1 VALUES(10, 'The Workout Hub', '707 Workout St', 'Seattle', '555-345-6565', 'support@workouthub.com', 'manasvi')




INSERT INTO GymManager1 VALUES(1, 1, 'Charlie Brown', '111-222-3333', 'charlie@fitworld.com')
INSERT INTO GymManager1 VALUES(2, 2, 'David Lee', '444-555-6666', 'david@powerhouse.com')
INSERT INTO GymManager1 VALUES(3, 3, 'Eva Green', '555-123-2345', 'eva@irontemple.com')
INSERT INTO GymManager1 VALUES(4, 4, 'George Clark', '666-234-3456', 'george@musclelab.com')
INSERT INTO GymManager1 VALUES(5, 5, 'Hannah White', '777-345-4567', 'hannah@peakperformance.com')
INSERT INTO GymManager1 VALUES(6, 6, 'Isaac Young', '888-456-5678', 'isaac@flexfit.com')
INSERT INTO GymManager1 VALUES(7, 7, 'Jack Carter', '999-567-6789', 'jack@strengthzone.com')
INSERT INTO GymManager1 VALUES(8, 8, 'Karen Scott', '101-678-7890', 'karen@bodycraft.com')
INSERT INTO GymManager1 VALUES(9, 9, 'Leo King', '202-789-8901', 'leo@elitefit.com')
INSERT INTO GymManager1 VALUES(10, 10, 'Monica Davis', '303-890-9012', 'monica@workouthub.com')

INSERT INTO GymMember1 VALUES(1, 1, 'Raj Kumar', '12 mar 1995', '9876543210', 'raj.kumar@gym.com', '15 jan 2023')
INSERT INTO GymMember1 VALUES(2, 2, 'Anjali Sharma', '25 jun 1988', '9876543211', 'anjali.sharma@gym.com', '10 feb 2023')
INSERT INTO GymMember1 VALUES(3, 3, 'Vikram Singh', '30 jul 1992', '9876543212', 'vikram.singh@gym.com', '5 mar 2023')
INSERT INTO GymMember1 VALUES(4, 4, 'Priya Patel', '14 sep 1996', '9876543213', 'priya.patel@gym.com', '10 jan 2023')
INSERT INTO GymMember1 VALUES(5, 5, 'Ravi Yadav', '20 feb 1990', '9876543214', 'ravi.yadav@gym.com', '1 apr 2023')
INSERT INTO GymMember1 VALUES(6, 6, 'Maya Gupta', '4 dec 1994', '9876543215', 'maya.gupta@gym.com', '22 feb 2023')
INSERT INTO GymMember1 VALUES(7, 7, 'Suresh Verma', '18 nov 1997', '9876543216', 'suresh.verma@gym.com', '18 mar 2023')
INSERT INTO GymMember1 VALUES(8, 8, 'Sneha Mehta', '9 jan 1993', '9876543217', 'sneha.mehta@gym.com', '5 may 2023')
INSERT INTO GymMember1 VALUES(9, 9, 'Karan Joshi', '22 oct 1991', '9876543218', 'karan.joshi@gym.com', '25 mar 2023')
INSERT INTO GymMember1 VALUES(10, 10, 'Deepa Reddy', '4 aug 1998', '9876543219', 'deepa.reddy@gym.com', '10 jun 2023')



INSERT INTO GymFee1 VALUES(1, 1, 50.00, 'Monthly', '1 jan 2023', '31 dec 2023')
INSERT INTO GymFee1 VALUES(2, 2, 60.00, 'Monthly', '1 jan 2023', '31 dec 2023')
INSERT INTO GymFee1 VALUES(3, 3, 55.00, 'Quarterly','1 jan 2023', '31 mar 2023')
INSERT INTO GymFee1 VALUES(4, 4, 100.00, 'Yearly', '1 jan 2023','31 dec 2023')
INSERT INTO GymFee1 VALUES(5, 5, 45.00, 'Monthly', '1 jan 2023', '31 dec 2023')
INSERT INTO GymFee1 VALUES(6, 6, 80.00, 'Bi-Monthly', '1 jan 2023','30 jun 2023')
INSERT INTO GymFee1 VALUES(7, 7, 70.00, 'Monthly', '1 jan 2023', '31 dec 2023')
INSERT INTO GymFee1 VALUES(8, 8, 90.00, 'Yearly', '1 jan 2023', '31 dec 2023')
INSERT INTO GymFee1 VALUES(9, 9, 65.00, 'Monthly', '1 jan 2023', '31 dec 2023')
INSERT INTO GymFee1 VALUES(10, 10, 85.00, 'Quarterly', '1 jan 2023', '31 mar 2023')



INSERT INTO GymMembership1 VALUES(1, 1, 1, 1, 'Gold', '1 jan 2023', '31 dec 2023', 'Active', 'Paid')
INSERT INTO GymMembership1 VALUES(2, 2, 2, 2, 'Silver', '1 jan 2023', '31 dec 2023',  'Active', 'Paid')
INSERT INTO GymMembership1 VALUES(3, 3, 3, 3, 'Platinum', '1 jan 2023',  '31 dec 2023', 'Active', 'Pending')
INSERT INTO GymMembership1 VALUES(4, 4, 4, 4, 'Gold', '1 jan 2023',  '31 dec 2023', 'Active', 'Paid')
INSERT INTO GymMembership1 VALUES(5, 5, 5, 5, 'Silver', '1 jan 2023', '31 dec 2023', 'Active', 'Paid')
INSERT INTO GymMembership1 VALUES(6, 6, 6, 6, 'Platinum', '1 jan 2023',  '31 dec 2023', 'Inactive', 'Pending')
INSERT INTO GymMembership1 VALUES(7, 7, 7, 7, 'Gold','1 jan 2023',  '31 dec 2023', 'Active', 'Paid')
INSERT INTO GymMembership1 VALUES(8, 8, 8, 8, 'Silver', '1 jan 2023',  '31 dec 2023', 'Active', 'Paid')
INSERT INTO GymMembership1 VALUES(9, 9, 9, 9, 'Platinum', '1 jan 2023', '31 dec 2023', 'Active', 'Paid')
INSERT INTO GymMembership1 VALUES(10, 10, 10, 10, 'Gold', '1 jan 2024', '31 dec 2023', 'Active', 'Paid')


INSERT INTO GymEquipment1 values(1, 1, 'Treadmill', 'Cardio', '15 may 2022', 'Good')
INSERT INTO GymEquipment1 values(2, 2, 'Dumbbells', 'Strength Training', '20 jul 2021', 'Needs Repair')
INSERT INTO GymEquipment1 values(3, 3, 'Exercise Bike', 'Cardio', '10 feb 2022', 'Good')
INSERT INTO GymEquipment1 values(4, 4, 'Elliptical Trainer', 'Cardio', '25 jan 2023', 'Excellent')
INSERT INTO GymEquipment1 values(5, 5, 'Rowing Machine', 'Cardio', '30 aug 2021', 'Good')
INSERT INTO GymEquipment1 values(6, 6, 'Leg Press Machine', 'Strength Training', '18 mar 2022', 'Needs Maintenance')
INSERT INTO GymEquipment1 values(7, 7, 'Chest Press Machine', 'Strength Training', '10 apr 2023', 'Good')
INSERT INTO GymEquipment1 values(8, 8, 'Free Weights', 'Strength Training', '5 jun 2021', 'Good')
INSERT INTO GymEquipment1 values(9, 9, 'Smith Machine', 'Strength Training', '1 dec 2022', 'Excellent')
INSERT INTO GymEquipment1 values(10, 10, 'Pull-up Bar', 'Bodyweight Training', '15 oct 2020', 'Good')


INSERT INTO GymDietPlan1 VALUES(1, 1, 'Weight Loss', 'Low-calorie diet for fat burning', 1000)
INSERT INTO GymDietPlan1 VALUES(2, 2, 'Muscle Gain', 'High-protein diet for muscle building', 1500)
INSERT INTO GymDietPlan1 VALUES(3, 3, 'Keto Diet', 'High-fat, low-carb diet for weight loss', 1200)
INSERT INTO GymDietPlan1 VALUES(4, 4, 'Balanced Diet', 'A balanced mix of protein, carbs, and fats', 1100)
INSERT INTO GymDietPlan1 VALUES(5, 5, 'Vegan Diet', 'Plant-based diet for overall wellness', 900)
INSERT INTO GymDietPlan1 VALUES(6, 6, 'Detox Diet', 'Detoxifying diet for cleansing the body', 950)
INSERT INTO GymDietPlan1 VALUES(7, 7, 'Low-Carb Diet', 'Diet focused on reducing carbohydrate intake', 1050)
INSERT INTO GymDietPlan1 VALUES(8, 8, 'High-Protein Diet', 'High-protein diet to build lean muscle', 1400)
INSERT INTO GymDietPlan1 VALUES(9, 9, 'Paleo Diet', 'A diet based on whole, unprocessed foods', 1250)
INSERT INTO GymDietPlan1 VALUES(10, 10, 'Intermittent Fasting', 'Diet plan focused on fasting intervals', 1000)


INSERT INTO GymTrainer1 VALUES(1, 1, 'John Doe', 'Strength Training', '9876543210', 'johndoe@gym.com')
INSERT INTO GymTrainer1 VALUES(2, 2, 'Alice Smith', 'Yoga', '9876543211', 'alice.smith@gym.com')
INSERT INTO GymTrainer1 VALUES(3, 3, 'Bob Brown', 'Cardio', '9876543212', 'bob.brown@gym.com')
INSERT INTO GymTrainer1 VALUES(4, 4, 'Charlie Davis', 'Pilates', '9876543213', 'charlie.davis@gym.com')
INSERT INTO GymTrainer1 VALUES(5, 5, 'David Miller', 'CrossFit', '9876543214', 'david.miller@gym.com')
INSERT INTO GymTrainer1 VALUES(6, 6, 'Eva White', 'Zumba', '9876543215', 'eva.white@gym.com')
INSERT INTO GymTrainer1 VALUES(7, 7, 'Frank Green', 'Bodybuilding', '9876543216', 'frank.green@gym.com')
INSERT INTO GymTrainer1 VALUES(8, 8, 'Grace Adams', 'Kickboxing', '9876543217', 'grace.adams@gym.com')
INSERT INTO GymTrainer1 VALUES(9, 9, 'Hank Lewis', 'Strength & Conditioning', '9876543218', 'hank.lewis@gym.com')
INSERT INTO GymTrainer1 VALUES(10, 10, 'Ivy Wilson', 'Aerobics', '9876543219', 'ivy.wilson@gym.com')



Q1: Find gym cities where more than 1 gyms are present

SELECT City, COUNT(GymID) AS GymCount
FROM Gym1
GROUP BY City
HAVING COUNT(GymID) > 1;

Q2: Find Total no. of Active and Inactive Members

select Status,Count(MemberID) as totalMember
from GymMembership1
group by Status
having count(MemberID) > 5;

Q3: Find members who are active and city = 'Los Angeles'

select gm.MemberId, g.GymID, Status, City 
from GymMembership1 gm inner join Gym1 g
on g.GymID = gm.GymID
where city = 'Los Angeles' and Status = 'Active'


Q4: Find Members Having 'Gold' Membership and are Paying fees 'Quarterly'

select gm.MemberId, gm.GymID, g.FeeID , FeeType , MembershipType 
from GymMembership1 gm inner join GymFee1 g
on g.FeeID = gm.FeeID
where MembershipType = 'Gold' and FeeType = 'Quarterly'


Q5: List all gym members with their membership status and payment status.

SELECT gm.MemberName, m.MembershipType, m.Status, m.PaymentStatus 
FROM GymMember1 gm 
JOIN GymMembership1 m ON gm.MemberID = m.MemberID;


Q6: Find all gyms and their available equipment.

SELECT g.GymName, e.EquipmentName, e.EquipmentType, e.Condition 
FROM Gym1 g 
JOIN GymEquipment1 e ON g.GymID = e.GymID;


Q7: Find gyms with more than 5 members.


SELECT GymName 
FROM Gym1 
WHERE GymID IN (
    SELECT GymID FROM GymMember1 
    GROUP BY GymID HAVING COUNT(*) > 5
);


Q8: List members who have an active membership.

select * from GymMember1 where MemberID in (
select MemberID from GymMembership1 where Status = 'Active');

Q9: Find gyms that have trainers specializing in 'Bodybuilding'.

select * from Gym1 Where GymID in(
select GymID from GymTrainer1 where TrainerSpecialty = 'Bodybuilding');


Q10: Find gyms that have diet plans priced over 1200rs. .

select GymID,GymName from Gym1 where GymID In (
select GymID from GymDietPlan1 where Price > 1200);


Q11: List all gyms with their highest membership fee.


select GymID,FeeAmount from GymFee1 where FeeAmount in ( select max(FeeAmount) from GymFee1 group by GymID)


Q12: List gyms with the number of active members.


SELECT g.GymID,count(gm.MemberID) AS NO_OF_ACTIVEMEMBERS
FROM Gym1 g
JOIN GymMembership1 gm ON g.GymID = gm.GymID
where Status = 'Active' 
group by g.GymID;


Q13: Find members with their gym, membership type, and fee amount.


select gm.MemberID,MemberName,g.GymID,GymName,MembershipType,FeeAmount
from GymMember1 gm, Gym1 g, GymMembership1 gmm, GymFee1 gf
where gm.GymID = g.GymID and gm.MemberID = gmm.MemberID and gmm.FeeID = gf.FeeID


Q14: Find gyms where the total collected fees exceed 80rs .


select g.GymID
from Gym1 g, GymFee1 gf
where g.GymID = gf.GymID 
group by g.GymID 
having sum(FeeAmount) > 80

OR

select * from Gym1 where GymID in(select GymID from GymFee1 group by GymID having sum(FeeAmount) >80)



Q15: List gym managers and the number of trainers they oversee.

SELECT g.GymID, gm.ManagerID, COUNT(gt.TrainerID) AS TrainerCount
FROM Gym1 g, GymManager1 gm, GymTrainer1 gt
WHERE g.GymID = gm.GymID AND g.GymID = gt.GymID
GROUP BY g.GymID, gm.ManagerID;


Q16: Display member details who joined after 1-1-2023 along with the gym name

select g.MemberId,g.MemberName,g.MemberDOB,StartDate,Gym1.GymID from GymMember1 g, GymMembership1 gm, Gym1
where g.MemberID = gm.MemberID and g.GymID = Gym1.GymID and gm.StartDate > '1 jan 2023'

Q17: Find managers managing gyms in a specific city (e.g., 'Mumbai')

SELECT gm.ManagerName
FROM Gym1 g, GymManager1 gm
WHERE g.GymID = gm.GymID AND g.City = 'Los Angeles';


