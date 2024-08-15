DROP TABLE IF EXISTS Enrollment;
DROP TABLE IF EXISTS Section;
DROP TABLE IF EXISTS Staff;
DROP TABLE IF EXISTS Instructor;
DROP TABLE IF EXISTS Manager;
DROP TABLE IF EXISTS Employee;
DROP TABLE IF EXISTS Equipment;
DROP TABLE IF EXISTS Member;
DROP TABLE IF EXISTS Class;
DROP TABLE IF EXISTS Branch;

CREATE TABLE Branch (BranchID varchar(20) not null,
BranchStreet  VARCHAR(30)    NOT NULL,
BranchCity    VARCHAR(20)    NOT NULL,
BranchState   CHAR(2)        NOT NULL,
BranchZipCode INT            NOT NULL,
CONSTRAINT BranchPK PRIMARY KEY(BranchID));

CREATE TABLE Class(
       ClassID        INTEGER       NOT NULL,      
	   ClassName      VARCHAR(20)   NOT NULL,
       BranchID       VARCHAR(20)   NOT NULL,     
CONSTRAINT ClassPK PRIMARY KEY(ClassID),
CONSTRAINT ClassFK FOREIGN KEY(BranchID) REFERENCES Branch(BranchID));



CREATE TABLE Member(
       MemberID            INTEGER          NOT NULL,    
       MemberFirstName     VARCHAR(20)      NOT NULL,
       MemberLastName      VARCHAR(20)      NOT NULL,
       PhoneNumber         VARCHAR(15)      NOT NULL,
       Email               VARCHAR(20),
       MemberStreet        VARCHAR(30)      NOT NULL,
       MemberCity          VARCHAR(30)	    NOT NULL,
       MemberState         CHAR(2)          NOT NULL,
       MemberZipCode       INT 		        NOT NULL,
       BranchID            VARCHAR(20)      NOT NULL,    
       MembershipType      VARCHAR(7)       NOT NULL,
       StartDate           DATE             NOT NULL,
       EndDate             DATE             NOT NULL,
CONSTRAINT MemberPK PRIMARY KEY(MemberID),
CONSTRAINT MemberFK FOREIGN KEY(BranchID) REFERENCES Branch(BranchID),
CONSTRAINT Check_MembershipType CHECK (MembershipType IN ('Bronze', 'Silver', 'Gold')));

CREATE TABLE Equipment(
       EquipmentID       INTEGER        NOT NULL,
       EquipmentName     VARCHAR(30)    NOT NULL,
       BranchID          VARCHAR(20)     NOT NULL,
CONSTRAINT EquipmentPK PRIMARY KEY(EquipmentID),
CONSTRAINT EquipmentFK FOREIGN KEY(BranchID) REFERENCES Branch(BranchID));

CREATE TABLE Employee(
       EmployeeID		    INT			    NOT NULL,
       EmployeeFirstName	VARCHAR(30)		NOT NULL,
       EmployeeLastName	    VARCHAR(30)		NOT NULL,
       EmployeeStreet		VARCHAR(30)		NOT NULL,
       EmployeeCity		    VARCHAR(30)		NOT NULL,
       EmployeeState		CHAR(2)			NOT NULL,
       EmployeeZipCode		INT	 		    NOT NULL,
       EmployeePhone		VARCHAR(15)		NOT NULL,
       EmployeeType		    CHAR(1)		    NOT NULL,
       BranchID             VARCHAR(20)     NOT NULL, 
CONSTRAINT EmployeePK PRIMARY KEY(EmployeeID),
CONSTRAINT EmployeeFK FOREIGN KEY(BranchID) REFERENCES Branch(BranchID),
CONSTRAINT Check_EmployeeType CHECK (EmployeeType IN ('M','I','S')));


CREATE TABLE Manager(
       ManagerID      INTEGER       NOT NULL,    
CONSTRAINT ManagerPK PRIMARY KEY(ManagerID),
CONSTRAINT ManagerFK FOREIGN KEY(ManagerID) REFERENCES Employee(EmployeeID));

CREATE TABLE Instructor(
       InstructorID      INTEGER       NOT NULL,    
       Certification     VARCHAR(100)  NOT NULL,
CONSTRAINT InstructorPK PRIMARY KEY(InstructorID),
CONSTRAINT InstructorFK FOREIGN KEY(InstructorID) REFERENCES Employee(EmployeeID));

CREATE TABLE Staff(
       StaffID       INTEGER       NOT NULL,   
       Skill         VARCHAR(100)  NOT NULL,
CONSTRAINT StaffPK PRIMARY KEY(StaffID),
CONSTRAINT StaffFK FOREIGN KEY(StaffID) REFERENCES Employee(EmployeeID));


CREATE TABLE Section(
       SectionID        INTEGER     NOT NULL,    
       Days             VARCHAR(3)  NOT NULL,
       Time             VARCHAR(5)  NOT NULL,
       StartDate        DATE        NOT NULL,
       EndDate          DATE        NOT NULL,
       ClassID          INTEGER     NOT NULL,      
       InstructorID     INTEGER     NOT NULL,      
CONSTRAINT SectionPK PRIMARY KEY(SectionID),
CONSTRAINT SectionFK1 FOREIGN KEY(ClassID) REFERENCES Class(ClassID),
CONSTRAINT SectionFK2 FOREIGN KEY(InstructorID) REFERENCES Instructor(InstructorID));

CREATE TABLE Enrollment(
       EnrollmentID     INTEGER   NOT NULL,     
       MemberID         INTEGER   NOT NULL,      
       SectionID        INTEGER   NOT NULL,      
       CompletedYN      CHAR(1)   NOT NULL,
CONSTRAINT EnrollmentPK PRIMARY KEY(EnrollmentID),
CONSTRAINT EnrollmentFK1 FOREIGN KEY(MemberID) REFERENCES Member(MemberID),
CONSTRAINT EnrollmentFK2 FOREIGN KEY(SectionID) REFERENCES Section(SectionID),
CONSTRAINT Check_Completed CHECK (CompletedYN IN ('Y','N')));


INSERT INTO Branch VALUES(1,'1243 leonard','Grand Rapids','MI',49505);
INSERT INTO Branch VALUES(2,'474 century ln','Holland','MI',49423);
INSERT INTO Branch VALUES(3,'4413 s westnedge ave','Kalamazoo','MI',49008);

INSERT INTO Class VALUES(1,yoga,1);
INSERT INTO Class VALUES(2,pilates,1);
INSERT INTO Class VALUES(3,hiit,1);
INSERT INTO Class VALUES(4,boxing,1);
INSERT INTO Class VALUES(5,zumba,1);

INSERT INTO Class VALUES(6,yoga,2);
INSERT INTO Class VALUES(7,pilates,2);
INSERT INTO Class VALUES(8,hiit,2);
INSERT INTO Class VALUES(9,boxing,2);
INSERT INTO Class VALUES(10,zumba,2);

INSERT INTO Class VALUES(11,yoga,3);
INSERT INTO Class VALUES(12,pilates,3);
INSERT INTO Class VALUES(13,hiit,3);
INSERT INTO Class VALUES(14,boxing,3);
INSERT INTO Class VALUES(15,zumba,3);



INSERT INTO Section VALUES(1, 'MW', '07:00', '2024-01-01', '2024-03-01', 24, 1);
INSERT INTO Section VALUES(2, 'TTH', '07:00', '2023-01-01', '2023-03-01', 24, 1);
INSERT INTO Section VALUES(3, 'MW', '08:00', '2024-01-01', '2024-03-01', 25, 2);
INSERT INTO Section VALUES(4, 'TTH', '08:00', '2023-01-01', '2023-03-01',25, 2);
INSERT INTO Section VALUES(5, 'MW', '09:00', '2023-01-01', '2023-03-01', 26, 3);
INSERT INTO Section VALUES(6, 'TTH', '09:00', '2024-01-01', '2024-03-01', 26, 3);
INSERT INTO Section VALUES(7, 'MW', '16:00', '2024-01-01', '2024-03-01', 27, 4);
INSERT INTO Section VALUES(8, 'TTH', '16:00', '2023-01-01', '2023-03-01', 27, 4);
INSERT INTO Section VALUES(9, 'MW', '18:00', '2024-01-01', '2024-03-01', 28, 5);
INSERT INTO Section VALUES(10, 'TTH', '18:00', '2023-01-01', '2023-03-01', 28, 5);

INSERT INTO Section VALUES(11, 'MW', '07:00', '2024-01-01', '2024-03-01', 29, 6);
INSERT INTO Section VALUES(12, 'TTH', '07:00', '2023-01-01', '2023-03-01', 29, 6);
INSERT INTO Section VALUES(13, 'MW', '08:00', '2024-01-01', '2024-03-01', 30, 7);
INSERT INTO Section VALUES(14, 'TTH', '08:00', '2023-01-01', '2023-03-01',30, 7);
INSERT INTO Section VALUES(15, 'MW', '09:00', '2024-01-01', '2024-03-01', 31, 8);
INSERT INTO Section VALUES(16, 'TTH', '09:00', '2023-01-01', '2023-03-01', 31, 8);
INSERT INTO Section VALUES(17, 'MW', '16:00', '2024-01-01', '2024-03-01', 32, 9);
INSERT INTO Section VALUES(18, 'TTH', '16:00', '2023-01-01', '2023-03-01', 32, 9);
INSERT INTO Section VALUES(19, 'MW', '18:00', '2024-01-01', '2024-03-01', 33, 10);
INSERT INTO Section VALUES(20, 'TTH', '18:00', '2023-01-01', '2023-03-01', 33, 10);

INSERT INTO Section VALUES(21, 'MW', '07:00', '2024-01-01', '2024-03-01', 34, 11);
INSERT INTO Section VALUES(22, 'TTH', '07:00', '2023-01-01', '2023-03-01', 34, 11);
INSERT INTO Section VALUES(23, 'MW', '08:00', '2024-01-01', '2024-03-01', 35, 12);
INSERT INTO Section VALUES(24, 'TTH', '08:00', '2023-01-01', '2023-03-01',35, 12);
INSERT INTO Section VALUES(25, 'MW', '09:00', '2024-01-01', '2024-03-01', 36, 13);
INSERT INTO Section VALUES(26, 'TTH', '09:00', '2024-01-01', '2024-03-01', 36, 13);
INSERT INTO Section VALUES(27, 'MW', '16:00', '2023-01-01', '2023-03-01', 37, 14);
INSERT INTO Section VALUES(28, 'TTH', '16:00', '2023-01-01', '2023-03-01', 37, 14);
INSERT INTO Section VALUES(29, 'MW', '18:00', '2024-01-01', '2024-03-01', 38, 15);
INSERT INTO Section VALUES(30, 'TTH', '18:00', '2023-01-01', '2023-03-01', 38, 15);

INSERT INTO Equipment VALUES( 1 ,'SEATED DIP MACHINE' ,1);
INSERT INTO Equipment VALUES( 2,'CHEST FLY MACHINE' ,1);
INSERT INTO Equipment VALUES( 3,'BENCH PRESS' ,1);
INSERT INTO Equipment VALUES( 4,'TREADMILL' ,1);
INSERT INTO Equipment VALUES( 5,'INCLINE BENCH PRESS' ,1);

INSERT INTO Equipment VALUES( 6,'SEATED DIP MACHINE' ,2);
INSERT INTO Equipment VALUES( 7,'BENCH PRESS' ,2);
INSERT INTO Equipment VALUES( 8,'INCLINE BENCH PRESS' ,2);
INSERT INTO Equipment VALUES(9 ,'CHEST FLY MACHINE' ,2);
INSERT INTO Equipment VALUES(10 ,'TREADMILL' ,2);

INSERT INTO Equipment VALUES(11,'SEATED DIP MACHINE' ,3);
INSERT INTO Equipment VALUES(12 ,'TREADMILL' ,3);
INSERT INTO Equipment VALUES(13 ,'CHEST FLY MACHINE' ,3);
INSERT INTO Equipment VALUES(14 ,'BENCH PRESS' ,3);
INSERT INTO Equipment VALUES(15,'INCLINE BENCH PRESS' ,3);

INSERT INTO Member VALUES(1961,'Timothy','Thomas','225-659-9488','t.thomas@live.com','907 Sherwood Drive','Kinder','MI',49505,1,'B','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(1962,'Allison','Sanders','208-791-7115','a.l.sanders@outlook.com','23 Meadow Lane','Sun Valley','MI',49505,1,'B','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(1963,'Ashley','Cooper','571-712-5090','a_cooper@outlook.com','345 Penn Street','Jarratt','MI',49505,1,'B','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(1964,'Aubrey','Peterson','856-580-3894','a_l_peterson68@hotmail.com','1714 Lincoln Street','Oakland','MI',49505,1,'B','2022-01-01','2023-01-01');
INSERT INTO Member VALUES(1965,'Julian','Martinez','907-887-3787','j_r_martinez@yahoo.com','29324 Elizabeth Street','Minto','MI',49505,1,'B','2022-01-01','2023-01-01');
INSERT INTO Member VALUES(1966,'Amelia','Robinson','228-621-3916','an@ymail.com','5690 Sherwood Drive','Shaw','MI',49505,1,'B','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(1967,'Austin','Hayes','458-206-2396','austin.hayes@gmail.com','880 Center Street','Creswell','MI',49505,1,'B','2022-01-01','2023-01-01');
INSERT INTO Member VALUES(1968,'Samantha','Hill','518-636-1411','shill@live.com','24 Cambridge Court','Rushville','MI',49505,1,'B','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(1969,'Emily','Jones','702-538-3651','e.jones1@aol.com','546 Warren Street','Gerlach','MI',49505,1,'S','2022-01-01','2023-01-01');
INSERT INTO Member VALUES(1970,'Justin','Moore','331-516-6004','jrmoore41@yahoo.com','55926 Colonial Drive','Lostant','MI',49505,1,'S','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(1971,'Samuel','Allen','580-359-1875','sallen@rocketmail.com','24638 Broadway','Fairview','MI',49505,1,'S','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(1972,'Mateo','Reed','239-303-8389','m_m@ymail.com','91 4th Street North','Eustis','MI',49505,1,'S','2022-01-01','2023-01-01');

INSERT INTO Member VALUES(1973,'Theodore','White','505-293-1150','t.white@aol.com','293 Prospect Avenue','Tijeras','MI',49505,1,'G','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(1974,'Natalie','Morris','331-647-6364','nmorris7@yahoo.com','25 Colonial Drive','Bone Gap','MI',49505,1,'G','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(1975,'Aaron','Flores','304-544-3830','aaron.ray@outlook.com','4722 Myrtle Avenue','Bradley','MI',49505,1,'G','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(1976,'Julian','Mitchell','406-690-7677','j_mitchell@aol.com','51 Pennsylvania Avenue','Loma','MI',49505,1,'G','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(1977,'Matthew','Price','385-248-3102','matthewprice@ymail.com','55582 Franklin Street','Vernal','MI',49505,1,'G','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(1978,'Owen','Collins','505-702-1855','owen_francis@aol.com','325 Laurel Lane','Mora','MI',49505,1,'G','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(1979,'Jennifer','Murphy','319-417-8743','jenniferanne43@outlook.com','474 Front Street','Farley','MI',49505,1,'G','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(1980,'Brittany','Jones','802-977-3112','brittany_jones83@yahoo.com','31 Durham Road','Morrisville','MI',49505,1,'G','2023-01-01','2025-01-01');


INSERT INTO Member VALUES(2001,'Danielle','Roberts','702-880-3634','d_a_roberts5@outlook.com','453 2nd Street East','Ruth','MI',49423,2,'B','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2002,'Theodore','Martin','734-189-4971','theodoreedwardmartin@gmail.com','37319 4th Avenue','Germfask','MI',49423,2,'B','2022-01-01','2023-01-01');
INSERT INTO Member VALUES(2003,'Oliver','Perry','719-491-8217','oliverjohnperry@yahoo.com','8580 Meadow Lane','Swink','MI',49423,2,'B','2022-01-01','2023-01-01');
INSERT INTO Member VALUES(2004,'Brianna','Torres','605-846-2750','brianna.jane@yahoo.com','73 Grant Street','Reva','MI',49423,2,'B','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2005,'Ryan','Johnson','843-495-8856','r.s.johnson30@rocketmail.com','614 King Street','Bath','MI',49423,2,'S','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2006,'Isaac','Hernandez','425-374-7320','i_hernandez@yahoo.com','638 2nd Street West','Stanwood','MI',49423,2,'S','2022-01-01','2023-01-01');
INSERT INTO Member VALUES(2007,'Steven','Gray','331-938-6020','steven.gray@live.com','5540 Church Road','Bone Gap','MI',49423,2,'S','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2008,'Sean','Robinson','331-730-7803','s_robinson87@gmail.com','275 2nd Street East','Tovey','MI',49423,2,'S','2022-01-01','2023-01-01');
INSERT INTO Member VALUES(2009,'Henry','Gonzales','534-638-2845','henry.gonzales81@gmail.com','723 Surrey Lane','Withee','MI',49423,2,'S','2022-01-01','2023-01-01');
INSERT INTO Member VALUES(2010,'Brian','Peterson','828-312-6913','b_peterson37@ymail.com','353 2nd Avenue','Colfax','MI',49423,2,'S','2023-01-01','2025-01-01');

INSERT INTO Member VALUES(2011,'Daniel','Carter','410-401-3779','danielcarter@aol.com','57339 Route 30','Whaleyville','MI',49423,2,'G','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2012,'Kevin','Bell','605-498-6656','kbell@hotmail.com','71485 5th Street North','Lantry','MI',49423,2,'G','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2013,'Ashley','Davis','802-126-4478','ashleydavis@ymail.com','604 Myrtle Avenue','Newport Center','MI',49423,2,'G','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2014,'Amanda','Ross','410-738-2603','amanda.jean.ross@hotmail.com','2846 Front Street','Port Tobacco','MI',49423,2,'G','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2015,'John','Hughes','252-399-6585','john_hughes@live.com','988 Buckingham Drive','Greenville','MI',49423,2,'G','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2016,'Andrew','Roberts','423-487-8080','andrew.j@aol.com','322 2nd Street East','Maynardville','MI',49423,2,'G','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2017,'Alyssa','Simmons','605-677-4794','a.simmons@yahoo.com','97914 2nd Street','Canton','MI',49423,2,'G','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2018,'Charlotte','Ward','843-706-3332','charlotte32@ymail.com','8475 Heather Lane','Bath','MI',49423,2,'G','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2019,'Steven','Martinez','410-914-2467','sa@live.com','7927 Lincoln Avenue','Pocomoke City','MI',49423,2,'G','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2020,'Alexis','Cooper','325-474-8678','alexisdcooper@outlook.com','32 Poplar Street','Mcfaddin','MI',49423,2,'G','2023-01-01','2025-01-01');

INSERT INTO Member VALUES(2061,'Matthew','Lee','620-510-3619','mh@rocketmail.com','8495 Hickory Lane','Clayton','MI',49001,3,'B','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2062,'Christina','Bell','228-741-8212','c.f.bell@yahoo.com','662 Adams Street','Pace','MI',49001,3,'B','2022-01-01','2023-01-01');
INSERT INTO Member VALUES(2063,'Patrick','Gray','302-511-3595','p_j_gray@yahoo.com','5241 Lincoln Avenue','Odessa','MI',49001,3,'B','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2064,'Brian','Bryant','505-981-5727','brianbryant@rocketmail.com','1580 Highland Drive','Villanueva','MI',49001,3,'B','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2065,'Victoria','Campbell','702-101-6487','v_campbell@hotmail.com','48638 Park Street','Minden','MI',49001,3,'B','2022-01-01','2023-01-01');
INSERT INTO Member VALUES(2066,'Victoria','Collins','325-365-2828','v_k_collins@yahoo.com','9405 Clark Street','Rusk','MI',49001,3,'S','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2067,'Ethan','Price','702-856-4344','ethan@outlook.com','96734 Mill Street','Lovelock','MI',49001,3,'S','2022-01-01','2023-01-01');
INSERT INTO Member VALUES(2068,'Grace','Hayes','719-876-6575','gracehayes@hotmail.com','16 Jackson Street','Salida','MI',49001,3,'S','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2069,'Ashley','Hall','308-229-7453','ashley_r@hotmail.com','527 Fairview Avenue','Bellevue','MI',49001,3,'S','2022-01-01','2023-01-01');
INSERT INTO Member VALUES(2070,'Victoria','Rogers','401-855-4821','vrogers24@yahoo.com','61 1st Avenue','Clayville','MI',49001,3,'S','2022-01-01','2023-01-01');
INSERT INTO Member VALUES(2071,'William','Lee','401-120-1738','wlee@ymail.com','64 Hillcrest Drive','Clayville','MI',49001,3,'S','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2072,'Richard','Young','606-837-1422','r.young@yahoo.com','5578 Beech Street','Covington','MI',49001,3,'S','2023-01-01','2025-01-01');

INSERT INTO Member VALUES(2073,'Anna','Simmons','304-664-9233','anna.marie.simmons@gmail.com','3650 Hamilton Street','Berkeley Springs','MI',49001,3,'G','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2074,'Jessica','Adams','571-671-2759','jessica.adams@yahoo.com','662 Jefferson Street','Oakton','MI',49001,3,'G','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2075,'Oliver','Turner','385-928-1998','oliver_james@ymail.com','204 Front Street','Midvale','MI',49001,3,'G','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2076,'Evelyn','Walker','228-895-4506','evelyn@gmail.com','576 11th Street','Hickory Flat','MI',49001,3,'G','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2077,'Oliver','King','843-919-7767','oliver_ray_king@yahoo.com','70 Woodland Drive','Pineville','MI',49001,3,'G','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2078,'Isaac','Peterson','308-206-6966','i_peterson@live.com','7321 Elm Street','Madrid','MI',49001,3,'G','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2079,'Isaac','Reed','239-773-8342','isaac_reed60@live.com','7125 Meadow Lane','Lake Como','MI',49001,3,'G','2023-01-01','2025-01-01');
INSERT INTO Member VALUES(2080,'Maria','Williams','410-233-5605','maria.mary.williams@live.com','3 Front Street North','Brooklyn','MI',49001,3,'G','2023-01-01','2025-01-01');

INSERT INTO Enrollment VALUES(1,1973,1,n);
INSERT INTO Enrollment VALUES(2,1973,8,y);
INSERT INTO Enrollment VALUES(3,1974,1,n);
INSERT INTO Enrollment VALUES(4,1975,9,n);
INSERT INTO Enrollment VALUES(5,1977,4,y);
INSERT INTO Enrollment VALUES(6,1977,5,y);
INSERT INTO Enrollment VALUES(7,1977,7,n);
INSERT INTO Enrollment VALUES(8,1979,6,n);
INSERT INTO Enrollment VALUES(9,1980,3,n);

INSERT INTO Enrollment VALUES(10,2011,15,n);
INSERT INTO Enrollment VALUES(11,2011,12,y);
INSERT INTO Enrollment VALUES(12,2011,14,y);
INSERT INTO Enrollment VALUES(13,2012,11,n);
INSERT INTO Enrollment VALUES(14,2012,12,y);                   
INSERT INTO Enrollment VALUES(15,2013,15,n);
INSERT INTO Enrollment VALUES(16,2013,17,n);
INSERT INTO Enrollment VALUES(17,2014,16,y);
INSERT INTO Enrollment VALUES(18,2014,19,n);
INSERT INTO Enrollment VALUES(19,2016,18,y);
INSERT INTO Enrollment VALUES(20,2016,13,n);
INSERT INTO Enrollment VALUES(21,2018,13,n);
INSERT INTO Enrollment VALUES(22,2018,16,y);
INSERT INTO Enrollment VALUES(23,2018,12,y);
INSERT INTO Enrollment VALUES(24,2019,11,n);
INSERT INTO Enrollment VALUES(25,2020,19,n);
INSERT INTO Enrollment VALUES(26,2020,20,y);

INSERT INTO Enrollment VALUES(27,2074,21,n);
INSERT INTO Enrollment VALUES(28,2074,22,y);
INSERT INTO Enrollment VALUES(29,2075,23,n);
INSERT INTO Enrollment VALUES(30,2075,24,y);
INSERT INTO Enrollment VALUES(31,2075,25,n);
INSERT INTO Enrollment VALUES(32,2076,30,y);
INSERT INTO Enrollment VALUES(33,2077,28,y);
INSERT INTO Enrollment VALUES(34,2077,29,n);
INSERT INTO Enrollment VALUES(35,2078,26,n);
INSERT INTO Enrollment VALUES(36,2078,27,y);
INSERT INTO Enrollment VALUES(37,2078,28,y);
INSERT INTO Enrollment VALUES(38,2079,28,y);
INSERT INTO Enrollment VALUES(39,2080,29,n);
INSERT INTO Enrollment VALUES(40,2080,30,y);


INSERT INTO Employee VALUES(21,'Maria','Rodriguez','58496 10th Street','Grand Rapids','MI',49505,'615-402-5132','M',1);
INSERT INTO Employee VALUES(22,'Jonathan','Diaz','1320 Fairway Drive','Holland','MI',49423,'775-218-1620','M',2);
INSERT INTO Employee VALUES(23,'Michael','Jenkins','79 Woodland Avenue','Kalamazoo','MI',49001,'508-482-8619','M',3);

INSERT INTO Employee VALUES(24,'Charles','Wilson','9197 Lafayette Avenue','Grand Rapids','MI',49505,'775-499-4625','I',1);
INSERT INTO Employee VALUES(25,'Lauren','Jenkins','5411 Green Street','Grand Rapids','MI',49505,'260-177-2789','I',1);
INSERT INTO Employee VALUES(26,'Amelia','Cooper','94 Cedar Lane','Grand Rapids','MI',49505,'515-914-7055','I',1);
INSERT INTO Employee VALUES(27,'Ava','Scott','17 College Avenue','Grand Rapids','MI',49505,'240-397-5821','I',1);
INSERT INTO Employee VALUES(28,'Brianna','Sanders','6117 Clark Street','Grand Rapids','MI',49505,'303-648-7413','I',1);

INSERT INTO Employee VALUES(29,'Samantha','Diaz','32 Poplar Street','Holland','MI',49423,'402-357-7694','I',2);
INSERT INTO Employee VALUES(30,'Brandon','James','60863 Academy Street','Holland','MI',49423,'406-513-6154','I',2);
INSERT INTO Employee VALUES(31,'Ethan','Miller','8437 Belmont Avenue','Holland','MI',49423,'904-943-2244','I',2);
INSERT INTO Employee VALUES(32,'Brianna','Kelly','74947 Colonial Drive','Hollands','MI',49423,'539-506-7100','I',2);
INSERT INTO Employee VALUES(33,'Amber','Simmons','21 11th Street','Holland','MI',49423,'501-955-7846','I',2);

INSERT INTO Employee VALUES(34,'Eric','Perez','556 Franklin Street','Kalamazoo','MI',49001,'539-464-3745','I',3);
INSERT INTO Employee VALUES(35,'Lillian','King','3 6th Street North','Kalamazoo','MI',49001,'920-699-4827','I',3);
INSERT INTO Employee VALUES(36,'Christina','Brooks','96 Fairview Avenue','Kalamazoo','MI',49001,'775-885-3861','I',3);
INSERT INTO Employee VALUES(37,'Timothy','Reed','26 Jefferson Avenue','Kalamazoo','MI',49001,'616-536-3446','I',3);
INSERT INTO Employee VALUES(38,'Brianna','Reed','7203 Brookside Drive','Kalamazoo','MI',49001,'234-288-2030','I',3);

INSERT INTO Employee VALUES(39,'Alexander','Brooks','475 Jefferson Street','Grand Rapids','MI',49505,'616-393-9590','S',1);
INSERT INTO Employee VALUES(40,'Charles','Ross','15217 Grant Street','Grand Rapids','MI',49505,'515-553-5060','S',1);
INSERT INTO Employee VALUES(41,'Joshua','Phillips','51 Front Street North','Grand Rapids','MI',49505,'508-249-5928','S',1);
INSERT INTO Employee VALUES(42,'Jose','Davis','5262 Center Street','Grand Rapids','MI',49505,'501-321-4442','S',1);

INSERT INTO Employee VALUES(43,'Brian','Rivera','98 Mill Road','Holland','MI',49423,'775-392-8378','S',2);
INSERT INTO Employee VALUES(44,'Tiffany','Washington','3023 Grant Street','Holland','MI',49423,'315-183-8198','S',2);
INSERT INTO Employee VALUES(45,'Anthony','Hughes','2506 Pennsylvania Avenue','Holland','MI',49423,'272-712-7283','S',2);
INSERT INTO Employee VALUES(46,'Tiffany','Long','81 Colonial Drive','Holland','MI',49423,'956-548-9454','S',2);

INSERT INTO Employee VALUES(47,'Rebecca','Diaz','6655 School Street','Kalamazoo','MI',49001,'501-233-9559','S',3);
INSERT INTO Employee VALUES(48,'Rebecca','Murphy','235 Bridge Street','Kalamazoo','MI',49001,'515-537-6356','S',3);
INSERT INTO Employee VALUES(49,'Gabriel','Coleman','9141 Maple Avenue','Kalamazoo','MI',49001,'904-232-3522','S',3);
INSERT INTO Employee VALUES(50,'Aaron','Jenkins','44264 King Street','Kalamazoo','MI',49001,'240-393-5381','S',3);


INSERT INTO Manager VALUES(21);
INSERT INTO Manager VALUES(22);
INSERT INTO Manager VALUES(23);

INSERT INTO Instructor VALUES(24,'International Association of Yoga Therapists (IAYT), British Wheel of Yoga');
INSERT INTO Instructor VALUES(25,'STOTT PILATES,BASI Pilates');
INSERT INTO Instructor VALUES(26,'ISSA (International Sports Sciences Association)');
INSERT INTO Instructor VALUES(27, 'Boxing Fitness Trainer,Boxing Fitness Institute (BFI)');
INSERT INTO Instructor VALUES(28,'Zumba Specialty Certification');

INSERT INTO Instructor VALUES(29, 'Yoga Alliance,British Wheel of Yoga' );
INSERT INTO Instructor VALUES(30,'BASI Pilates,Pilates Method Alliance (PMA)');
INSERT INTO Instructor VALUES(31,'ISSA (International Sports Sciences Association)');
INSERT INTO Instructor VALUES(32,'Boxing Fitness Trainer,International Fitness Association (IFA)');
INSERT INTO Instructor VALUES(33,'Zumba Specialty Certification');

INSERT INTO Instructor VALUES(34, 'International Association of Yoga Therapists (IAYT),Yoga Alliance' );
INSERT INTO Instructor VALUES(35, 'STOTT PILATES,Pilates Method Alliance (PMA)');
INSERT INTO Instructor VALUES(36,'ISSA (International Sports Sciences Association)');
INSERT INTO Instructor VALUES(37,'Boxing Fitness Institute (BFI),International Fitness Association (IFA)');
INSERT INTO Instructor VALUES(38,'Zumba Specialty Certification');

INSERT INTO Staff VALUES(39,'Customer service, Computer Skills');
INSERT INTO Staff VALUES(40,'Safety awareness, Hygienic cleaning');
INSERT INTO Staff VALUES(41,'Nutrition meals');
INSERT INTO Staff VALUES(42,'Massage therapy, Emergency first aid');

INSERT INTO Staff VALUES(43,'Customer service, Computer Skills');
INSERT INTO Staff VALUES(44,'Safety awareness, Hygienic cleaning');
INSERT INTO Staff VALUES(45,'Massage therapy, Emergency first aid');
INSERT INTO Staff VALUES(46,'Nutrition meals');

INSERT INTO Staff VALUES(47,'Customer service, Computer Skills');
INSERT INTO Staff VALUES(48,'Safety awareness, Hygienic cleaning');
INSERT INTO Staff VALUES(49,'Massage therapy, Emergency first aid');
INSERT INTO Staff VALUES(50,'Nutrition meals,Communication Skills');













 
