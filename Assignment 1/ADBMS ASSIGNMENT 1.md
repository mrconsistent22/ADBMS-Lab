**ADBMS ASSIGNMENT 1**

**TE IT** 

**3081** 

**TEJAS SHINDE** 



Windows PowerShell

Copyright (C) Microsoft Corporation. All rights reserved.



Install the latest PowerShell for new features and improvements! https://aka.ms/PSWindows



PS C:\\Users\\ASUS\\Desktop> mongosh

Current Mongosh Log ID: 68ebd427767a48d0c0718dc3

Connecting to:          mongodb://127.0.0.1:27017/?directConnection=true\&serverSelectionTimeoutMS=2000\&appName=mongosh+2.5.5

Using MongoDB:          8.0.11

Using Mongosh:          2.5.5

mongosh 2.5.8 is available for download: https://www.mongodb.com/try/download/shell



For mongosh info see: https://www.mongodb.com/docs/mongodb-shell/



------

&nbsp;  The server generated these startup warnings when booting

&nbsp;  2025-10-01T10:22:48.059+05:30: Access control is not enabled for the database. Read and write access to data and configuration is unrestricted

------



test> use company

switched to db company

company> db.createCollection("employee")

{ ok: 1 }

company> db.employee.insertMany(\[

&nbsp;	{eid: 1, ename: "Tejas", designation: "Analyst", hiredate: "2015-07-01", salary: 12000, hobbies: \["Reading", "Cycling"], department: "Sales" },

&nbsp;	{eid: 2, ename: "Aryan", designation: "Manager", hiredate: "2014-01-15", salary: 15000, hobbies: \["Painting", "Swimming"], department: "HR"},

&nbsp;	{eid: 3, ename: "Aradhana", designation: "Salesman", hiredate: "2016-03-10", salary: 9000, hobbies: \["Traveling", "Reading"], department: "Sales" },

&nbsp;	{eid: 4, ename: "Tejas K", designation: "Analyst", hiredate: "2017-05-20", salary: 8000, hobbies: \["Music", "Cooking"], department: "IT"},

&nbsp;	{eid: 5, ename: "Kedar", designation: "Developer", hiredate: "2015-08-10", salary: 13000, hobbies: \["Reading", "Painting"], department: "Production"},	

&nbsp;	{eid: 6, ename: "Max", designation: "Tester", hiredate: "2015-09-30", salary: 7000, hobbies: \["Gaming", "Reading"], department: "Sales"},

&nbsp;	{eid: 7, ename: "Kane", designation: "Salesman", hiredate: "2014-11-10", salary: 11000, hobbies: \["Reading", "Writing"], department: "Sales" },

&nbsp;	{eid: 8, ename: "Bhuvi", designation: "Manager", hiredate: "2013-10-15", salary: 16000, hobbies: \["Painting", "Traveling"], department: "HR"},

&nbsp;	{eid: 9, ename: "Steyn", designation: "Developer", hiredate: "2015-07-15", salary: 14000, hobbies: \["Swimming", "Reading"], department: "Production"},

&nbsp;	{eid: 10, ename: "Williamson", designation: "Analyst", hiredate: "2016-12-25", salary: 10000, hobbies: \["Music", "Painting", "Gaming"], department: "IT"}])



{

&nbsp; acknowledged: true,

&nbsp; insertedIds: {

&nbsp;   '0': ObjectId('68ebd45c767a48d0c0718dc4'),

&nbsp;   '1': ObjectId('68ebd45c767a48d0c0718dc5'),

&nbsp;   '2': ObjectId('68ebd45c767a48d0c0718dc6'),

&nbsp;   '3': ObjectId('68ebd45c767a48d0c0718dc7'),

&nbsp;   '4': ObjectId('68ebd45c767a48d0c0718dc8'),

&nbsp;   '5': ObjectId('68ebd45c767a48d0c0718dc9'),

&nbsp;   '6': ObjectId('68ebd45c767a48d0c0718dca'),

&nbsp;   '7': ObjectId('68ebd45c767a48d0c0718dcb'),

&nbsp;   '8': ObjectId('68ebd45c767a48d0c0718dcc'),

&nbsp;   '9': ObjectId('68ebd45c767a48d0c0718dcd')

&nbsp; }

}





**a) List the names of analysts and salesmen.**



company> db.employee.find({ designation: {$in: \["Analyst", "Salesman"]}}, {ename: 1})

\[

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc4'), ename: 'Tejas' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc6'), ename: 'Aradhana' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc7'), ename: 'Tejas K' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dca'), ename: 'Kane' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dcd'), ename: 'Williamson' }

]





**b) List the eid,ename and salary from employee collection.**



company> db.employee.find({},{eid:1, ename:1,salary:1})

\[

&nbsp; {

&nbsp;   \_id: ObjectId('68ebd45c767a48d0c0718dc4'),

&nbsp;   eid: 1,

&nbsp;   ename: 'Tejas',

&nbsp;   salary: 12000

&nbsp; },

&nbsp; {

&nbsp;   \_id: ObjectId('68ebd45c767a48d0c0718dc5'),

&nbsp;   eid: 2,

&nbsp;   ename: 'Aryan',

&nbsp;   salary: 15000

&nbsp; },

&nbsp; {

&nbsp;   \_id: ObjectId('68ebd45c767a48d0c0718dc6'),

&nbsp;   eid: 3,

&nbsp;   ename: 'Aradhana',

&nbsp;   salary: 9000

&nbsp; },

&nbsp; {

&nbsp;   \_id: ObjectId('68ebd45c767a48d0c0718dc7'),

&nbsp;   eid: 4,

&nbsp;   ename: 'Tejas K',

&nbsp;   salary: 8000

&nbsp; },

&nbsp; {

&nbsp;   \_id: ObjectId('68ebd45c767a48d0c0718dc8'),

&nbsp;   eid: 5,

&nbsp;   ename: 'Kedar',

&nbsp;   salary: 13000

&nbsp; },

&nbsp; {

&nbsp;   \_id: ObjectId('68ebd45c767a48d0c0718dc9'),

&nbsp;   eid: 6,

&nbsp;   ename: 'Max',

&nbsp;   salary: 7000

&nbsp; },

&nbsp; {

&nbsp;   \_id: ObjectId('68ebd45c767a48d0c0718dca'),

&nbsp;   eid: 7,

&nbsp;   ename: 'Kane',

&nbsp;   salary: 11000

&nbsp; },

&nbsp; {

&nbsp;   \_id: ObjectId('68ebd45c767a48d0c0718dcb'),

&nbsp;   eid: 8,

&nbsp;   ename: 'Bhuvi',

&nbsp;   salary: 16000

&nbsp; },

&nbsp; {

&nbsp;   \_id: ObjectId('68ebd45c767a48d0c0718dcc'),

&nbsp;   eid: 9,

&nbsp;   ename: 'Steyn',

&nbsp;   salary: 14000

&nbsp; },

&nbsp; {

&nbsp;   \_id: ObjectId('68ebd45c767a48d0c0718dcd'),

&nbsp;   eid: 10,

&nbsp;   ename: 'Williamson',

&nbsp;   salary: 10000

&nbsp; }

]





**c) List names of employees who are not managers.**





company> db.employee.find({designation:{$ne:"Manager"}},{ename:1})

\[

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc4'), ename: 'Tejas' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc6'), ename: 'Aradhana' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc7'), ename: 'Tejas K' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc8'), ename: 'Kedar' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc9'), ename: 'Max' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dca'), ename: 'Kane' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dcc'), ename: 'Steyn' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dcd'), ename: 'Williamson' }

]





**d) List the names of employees whose employee numbers are 1,3,7,9.**



company> db.employee.find({eid:{$in:\[1,3,7,9]}},{ename:1})

\[

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc4'), ename: 'Tejas' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc6'), ename: 'Aradhana' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dca'), ename: 'Kane' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dcc'), ename: 'Steyn' }

]





**e) List the names of all employees those having reading as a secound hobby.**



company> db.employee.find({hobbies:{$elemMatch:{$eq:"Reading"}}}, {ename:1})

\[

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc4'), ename: 'Tejas' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc6'), ename: 'Aradhana' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc8'), ename: 'Kedar' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc9'), ename: 'Max' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dca'), ename: 'Kane' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dcc'), ename: 'Steyn' }

]





**f) List employee names for those who have joined between 30 June and 31 Dec 2015.**



company> db.employee.find({hiredate:{$gte:"2015-06-30",$lte:"2015-12-31"}},{ename:1})

\[

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc4'), ename: 'Tejas' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc8'), ename: 'Kedar' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc9'), ename: 'Max' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dcc'), ename: 'Steyn' }

]





**g) List the different designations in the company.**



company> db.employee.distinct("designation")

\[ 'Analyst', 'Developer', 'Manager', 'Salesman', 'Tester' ]





**h) List the eid,ename,salary of all employees whose salary is less than 10000.**



company> db.employee.find({salary:{$lt:10000}},{eid:1,ename:1,salary:1})

\[

&nbsp; {

&nbsp;   \_id: ObjectId('68ebd45c767a48d0c0718dc6'),

&nbsp;   eid: 3,

&nbsp;   ename: 'Aradhana',

&nbsp;   salary: 9000

&nbsp; },

&nbsp; {

&nbsp;   \_id: ObjectId('68ebd45c767a48d0c0718dc7'),

&nbsp;   eid: 4,

&nbsp;   ename: 'Tejas K',

&nbsp;   salary: 8000

&nbsp; },

&nbsp; {

&nbsp;   \_id: ObjectId('68ebd45c767a48d0c0718dc9'),

&nbsp;   eid: 6,

&nbsp;   ename: 'Max',

&nbsp;   salary: 7000

&nbsp; }

]





**i) List the name and designation of the employee who works in production department.**



company> db.employee.find({department:"Production"},{ename:1, designation:1})

\[

&nbsp; {

&nbsp;   \_id: ObjectId('68ebd45c767a48d0c0718dc8'),

&nbsp;   ename: 'Kedar',

&nbsp;   designation: 'Developer'

&nbsp; },

&nbsp; {

&nbsp;   \_id: ObjectId('68ebd45c767a48d0c0718dcc'),

&nbsp;   ename: 'Steyn',

&nbsp;   designation: 'Developer'

&nbsp; }

]





**j) List the all employees whose name start with "A" letter.**



company> db.employee.find({ename:{$regex:/^A/}},{ename:1})

\[

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc5'), ename: 'Aryan' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc6'), ename: 'Aradhana' }

]





**k) List the all employees whose name containing "sh" string.**



company> db.employee.find({ename:{$regex:/sh/i}},{ename:1})

\-





**l) List the all employees whose names either start or end with “S”.**



company> db.employee.find({ename:{$regex:/S|S$/}},{ename:1})

\[ { \_id: ObjectId('68ebd45c767a48d0c0718dcc'), ename: 'Steyn' } ]





**m) List the names of employees whose department is not HR.**



company> db.employee.find({department:{$ne:"HR"}}, {ename:1})

\[

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc4'), ename: 'Tejas' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc6'), ename: 'Aradhana' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc7'), ename: 'Tejas K' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc8'), ename: 'Kedar' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc9'), ename: 'Max' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dca'), ename: 'Kane' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dcc'), ename: 'Steyn' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dcd'), ename: 'Williamson' }

]





**n) List the number of employees working in sales department.**



company> db.employee.countDocuments({department:"Sales"})

4





**o) List the number of designations available in the EMP collections.**



company> db.employee.distinct("designation").length

5





**p) List the eid,ename,salary of all employees whose salary in between 10000 to 20000.**



company> db.employee.find({salary:{$gte:10000, $lte:20000}},{sid:1,ename:1,salary:1})

\[

&nbsp; {

&nbsp;   \_id: ObjectId('68ebd45c767a48d0c0718dc4'),

&nbsp;   ename: 'Tejas',

&nbsp;   salary: 12000

&nbsp; },

&nbsp; {

&nbsp;   \_id: ObjectId('68ebd45c767a48d0c0718dc5'),

&nbsp;   ename: 'Aryan',

&nbsp;   salary: 15000

&nbsp; },

&nbsp; {

&nbsp;   \_id: ObjectId('68ebd45c767a48d0c0718dc8'),

&nbsp;   ename: 'Kedar',

&nbsp;   salary: 13000

&nbsp; },

&nbsp; {

&nbsp;   \_id: ObjectId('68ebd45c767a48d0c0718dca'),

&nbsp;   ename: 'Kane',

&nbsp;   salary: 11000

&nbsp; },

&nbsp; {

&nbsp;   \_id: ObjectId('68ebd45c767a48d0c0718dcb'),

&nbsp;   ename: 'Bhuvi',

&nbsp;   salary: 16000

&nbsp; },

&nbsp; {

&nbsp;   \_id: ObjectId('68ebd45c767a48d0c0718dcc'),

&nbsp;   ename: 'Steyn',

&nbsp;   salary: 14000

&nbsp; },

&nbsp; {

&nbsp;   \_id: ObjectId('68ebd45c767a48d0c0718dcd'),

&nbsp;   ename: 'Williamson',

&nbsp;   salary: 10000

&nbsp; }

]





**q) List the eid,ename of all employees whose salary is greater than or equal to 15000.**



company> db.employee.find({salary:{$gte:15000}},{eid:1,ename:1})

\[

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc5'), eid: 2, ename: 'Aryan' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dcb'), eid: 8, ename: 'Bhuvi' }

]





**r) List details of employees whose department is Sales and salary is 10000.**



db.employee.find({department:"Sales", salary:10000})

\-





**s) List the names of employees those having reading and painting hobbies.**



&nbsp;db.employee.find({hobbies:{$all:\["Reading", "Painting"]}},{ename:1})

\[ { \_id: ObjectId('68ebd45c767a48d0c0718dc8'), ename: 'Kedar' } ]





**t) List the first hobby of all employees from the employee collection.**



&nbsp;db.employee.find({},{firstHobby:{$arrayElemAt:\["$hobbies",0]}})

\[

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc4'), firstHobby: 'Reading' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc5'), firstHobby: 'Painting' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc6'), firstHobby: 'Traveling' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc7'), firstHobby: 'Music' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc8'), firstHobby: 'Reading' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dc9'), firstHobby: 'Gaming' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dca'), firstHobby: 'Reading' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dcb'), firstHobby: 'Painting' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dcc'), firstHobby: 'Swimming' },

&nbsp; { \_id: ObjectId('68ebd45c767a48d0c0718dcd'), firstHobby: 'Music' }

]





**u) List the names of all employees those having three different hobbies.**



&nbsp;db.employee.find({$expr:{$eq:\[{$size:"$hobbies"},3]}},{ename:1})

\[ { \_id: ObjectId('68ebd45c767a48d0c0718dcd'), ename: 'Williamson' } ]





