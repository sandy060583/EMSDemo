# EMSDemo
Employee Management System - UI using ASP.NET MVC 5 and REST API using ASP.NET Core 2.0 WEB API



EMS.UI : https://github.com/sandy060583/EMS.UI

•	created using ASP.NET MVC5 and C# - Visual Studio 2017

EMS.Api : https://github.com/sandy060583/EMS.API

•	created using ASP.NET Core 2.0 and Dapper ORM. 
•	SQL Local database is used to store the employee and city data. Please run the script to create table if required. 
•	Swagger is used for documentation. Run this API project before running UI project.

EMS.Common : https://github.com/sandy060583/EMS.Common

•	Class library project created to store domain models, common classes.

 

Create New Database - DemoEMS and tables 

1. In Visual studio 2017 - open SQL Server Object Explorer.

2. Create new database DemoEMS under (localdb)\ProjectsV13


3. Create tables Employee and City using SQL scripts and insert some test data.

Right click on DemoEMS database and select New Query options

DROP TABLE [dbo].[City];

CREATE TABLE [dbo].[City]
(
    [CityId] INT NOT NULL PRIMARY KEY IDENTITY(1,1), 
    [CityName] NVARCHAR(50) NOT NULL
);

DROP TABLE [dbo].[Employee];

CREATE TABLE [dbo].[Employee]
(
    [EmployeeId] INT NOT NULL PRIMARY KEY IDENTITY(1,1), 
    [EmployeeName] NVARCHAR(50) NOT NULL, 
    [CityId] INT NOT NULL
);


Insert into [dbo].[City] (CityName) Values ('Pune');

Insert into [dbo].[City] (CityName) Values ('Mumbai');

Insert into [dbo].[City] (CityName) Values ('Delhi');

Insert into [dbo].[City] (CityName) Values ('Ahmadabad');

Insert into [dbo].[City] (CityName) Values ('Surat');


Insert into [dbo].[Employee] (EmployeeName, CityId) Values ('Sandeep',1);

Insert into [dbo].[Employee] (EmployeeName, CityId) Values ('Ravi',2);

Insert into [dbo].[Employee] (EmployeeName, CityId) Values ('Dharmik',3);

Insert into [dbo].[Employee] (EmployeeName, CityId) Values ('Jigesh',1);


 

4. Update Connection string - BaseRepository.cs 

Right click on DemoEMS database and select property - it will display connection string for database.
copy this connection string and update into BaseRepository.cs class 

5. Run the application

Run EMS.Api project – it should display swagger page

http://localhost:56208/swagger/

 
Launch EMS.UI project - Web.Config 

update key - "EMSWebApiBaseUrl" used to point API – change it if port get changed while you run the project.


 
