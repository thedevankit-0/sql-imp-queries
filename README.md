# sql-imp-queries
## create table 
```sql
create table GuestList(
[GueastId] int not null IDENTITY(1,1) PRIMARY KEY,
[Name] varchar (50) not null,
[Email] varchar (50) not null,
[Phone] int not null,
WillAttend bit

);
```
## Foreign key with unique id
```sql
create table Student (
ID uniqueidentifier primary key default NEWID()  not null,
[FirstName] nvarchar(50)  not null,
 [LastName] nvarchar(50)  not null, 
 [Address] nvarchar(50)  not null, 
 [Email] nvarchar(50)  not null, 
 [Contact] nvarchar(10) not null, 
 [Gender] char(1)  not null, 
 [PhdSubjectId] uniqueidentifier  not null, 
 [Year] char(4)  not null

 CONSTRAINT FKSUBJECTID FOREIGN KEY (PhdSubjectId)
REFERENCES PhdSubject (Id)	
	)

create table PhdSubject (
ID uniqueidentifier primary key default NEWID()  not null,
[Name] nvarchar(50)  not null,
 [Description] nvarchar(150)  not null
 )

```
## create table with unique ID 
```sql
create table Student (
ID uniqueidentifier primary key default NEWID()  not null,
[FirstName] nvarchar(50)  not null,
 [LastName] nvarchar(50)  not null, 
 [Address] nvarchar(50)  not null, 
 [Email] nvarchar(50)  not null, 
 [Contact] nvarchar(10), 
 [Gender] char(1)  not null, 
 [Subject] nvarchar(50)  not null, 
 [Year] char(4)  not null, 
 ProfilePhoton varchar(50)
	)
```
## create procedure
```sql
ALTER PROCEDURE [dbo].[UserDBOperation]
@Action varchar(50)=NULL,
@UserId INT=0,
@FirstName VARCHAR(30)=NULL,
@LastName VARCHAR(30)=NULL,
@Email VARCHAR(20)=NULL,
@DateOfBirth VARCHAR(30)=NULL,
@Gender VARCHAR(16)=NULL,
@education VARCHAR(30)=NULL,
@Country VARCHAR(30)=NULL,
@City VARCHAR(30)=NULL,
@UserName VARCHAR(10)=NULL,
@UserPassword DATE=NULL
As

BEGIN
 IF @Action = 'SELECT'
 BEGIN 
  SELECT  [FirstName]
		  ,[LastName]
		  ,[Email]
		  ,[DateOfBirth]
		  ,[Gender]
		  ,[Country]
		  ,[City]
		  ,[UserName]
		  ,[UserPassword]
		  ,[UserId]
  FROM UserData;
 END

 IF @Action = 'INSERT'
 BEGIN
  INSERT INTO UserData ([FirstName]
      ,[LastName]
      ,[Email]
      ,[DateOfBirth]
      ,[Gender]
      ,[Country]
      ,[City]
      ,[UserName]
      ,[UserPassword]) 
    VALUES
      (@FirstName
      ,@LastName
      ,@Email
      ,@DateOfBirth
      ,@Gender
      ,@Country
      ,@City
      ,@UserName
      ,@UserPassword);
 END

 IF @Action ='DELETE'
 BEGIN
  DELETE FROM UserData
  WHERE UserId=@UserId;
 END

 IF @Action ='UPDATE'
 BEGIN
  UPDATE UserData
  SET [Firstname]=@FirstName
   ,[Lastname]=@LastName
   ,[Email]=@Email
   ,[DateOfBirth]=@DateOfBirth
   ,[Gender]=@Gender
   ,[Country]=@Country
   ,[City]=@City
   ,[UserName]=@UserName
   ,[UserPassword]=@UserPassword
  WHERE UserId=@UserId; 
 END
END
```


 public int Patient_Id { get; set; }
        [Display(Name = "Full Name")]
        [Required(ErrorMessage = "First name cannot be empty")]
        [RegularExpression("^([a-zA-Z]{2,})$", ErrorMessage = "Name contains only alphabets")]
        public string Name { get; set; }

        [Required(ErrorMessage = "Please select a gender")]
        public string Gender { get; set; }

        [Display(Name = "Phone")]
        [Required(ErrorMessage = "Phone cannot be empty")]
        [RegularExpression(@"^\(?([0-9]{3})\)?([0-9]{3})?([0-9]{4})$", ErrorMessage = "Phone contains only numbers and 10 digits")]
        public string PhoneNumber { get; set; }

        [Required(ErrorMessage = "Email cannot be empty")]
        [RegularExpression(@"^([\w-\.]+@([\w-]+\.)+[\w-]{2,4})?$", ErrorMessage = "Email address should be in the format abc@abc.com")]
        public string Email { get; set; }

        [Required(ErrorMessage = "Password cannot be empty")]
        [DataType(DataType.Password, ErrorMessage = "Invalid password")]
        [RegularExpression("^(?=.*[a-z])(?=.*[A-Z])(?=.*[@#$%^&+=]).{8,16}$", ErrorMessage = "Password contains one special character, one uppercase, one lowercase, minimum 8 and maximum 16 characters")]
        public string Password { get; set; }

        [Required(ErrorMessage = "Address cannot be empty")]
        public string Address { get; set; }

        public bool UserType { get; set; }
        public System.DateTime RegistrationDate { get; set; }


```sql
SELECT *

  FROM [PatientManagement].[dbo].[AdviceDetails]


   Alter table [dbo].[AdviceDetails]
  Drop column AdviceId;

  Alter table [dbo].[AdviceDetails]
  Drop  Constraint PK_AdviceDetails;

  ALTER TABLE [dbo].[AdviceDetails]
DROP CO; 
  
Aletrtable colounm and add autu increment
    ALTER TABLE  [dbo].[AdviceDetails] Add AdviceId int NOT NULL IDENTITY (1,1) PRIMARY KEY

    
 [DataType(DataType.Date)]
        [Display(Name = "Appointment Date")]
        [DisplayFormat(DataFormatString = "{0:dd/MM/yyyy}", ApplyFormatInEditMode = true)]
        public System.DateTime AppointmentDate { get; set; }
```
	
Add And Drop column to add primary key with not null


```sql
ALTER TABLE Movies 
   Add PRIMARY KEY (Id);


   ALTER TABLE Movies ALTER COLUMN Id int NOT NULL;

```

Important links:

https://forums.asp.net/t/2133883.aspx?How+to+send+data+from+_Layout+to+controller+

https://codeburst.io/getting-started-with-angular-7-and-bootstrap-4-styling-6011b206080?source=search_post&gi=1d973c784052

https://medium.com/better-programming/the-differences-between-a-junior-mid-level-and-senior-developer-bb2cb2eb000d

