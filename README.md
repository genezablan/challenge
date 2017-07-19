
# Technical Challenge

## Purpose: To evaluate applicant's basic knowledge in NodeJS and SQL

### Tasks

Given a list of users' data in an array of objects. 

```
   const userArr = [
    { first_name: 'Gene', points: 30, gender: 'male' },
    { first_name: 'Diane', points: 15, gender: 'female' },
    { first_name: 'Tatsaya', points: null, gender: 'female' },
    { first_name: 'Danyong', points: 20, gender: 'male' },
    { first_name: 'Elland', points: 15, gender: 'female' },
  ] 
```
1. Create a function that has a parameter of gender of the user, if the parameter is male the function would return an array of all male users. The array is sorted by the number of points from the lowest to the highest point.

2. Create a function that will convert the returned array to comma separated string.
for e.i. [a,b,c] ==> a,b,c


3. Consider the following example of a 'callback hell'.

  ```
   User.findOne({ id: id }, (user) => {
    Comments.findOne({ user_id: user.id }, (user) => {
     Links.find({ user_id: user.id }, (link) => {
      console.log('user comment link', link);
    });
   }); 
  });
  ```
  
  a) Convert this to more readable code. Hence you can use Promise.
  
  
 4. 
  ```
  Table: customer_points
  id: integer PRIMARY KEY,
  type: string,
  points: integer,
  created_at: timestamp
  
  Table: customers
  id: interger PRIMARY KEY,
  first_name: string,
  last_name: string,
  user_id: integer,
  last_name: string
  
  Table: user
  id: interger PRIMARY KEY,
  username: string,
  password: integer,
  created_at: timestamp
  
  Table: settings
  id: interger PRIMARY KEY,
  earn_frequency: integer
  ```
  - Each user has many customer point and customer belongs to user
  
  a. Write a query that gets all total points per day of the user with customer point type 'scan_earns'.
    The requery result should include these fields (first_name, last_name, total_points, Date).
    
  b. Write a query that gets all user who earn points more than the earn_frequency in the settings. 
    The query result sould include these fields (first_name, last_name, user_id).
  [Bonus]
  c. Write a query that gets all the user along with their points with the column last_scan_delay that is the delay on seconds from the last record 
    The query result sould include these fields (first_name, last_name, user_id, last_scan_delay)
