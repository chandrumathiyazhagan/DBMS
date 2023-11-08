# Ex. No: 10 DATA BASE CONNECTIVITY USING  MYSQL AND JAVA
### DATE: 
### AIM: To create database connectivity and display the employee table 

### Steps:
1. Install mysql,visual studio,jdk, extensions of java pack.
2. Create a employee table and insert the data into employee table  
3. Create a new java project in visual studio.
4. write a java progarm to perform the following 1.create a connection 2. fetch data and store it in result set 3. Display table rows. 4. Close the connection
5. Deploy the jar file in lib folder 
6. Run the program

### Program:
```python
import java.sql.*;  
public class App
{  
public static void main(String args[])
{  
try
{  
    Class.forName("com.mysql.cj.jdbc.Driver");  
    Connection con=DriverManager.getConnection("jdbc:mysql://localhost:3306/d1","root","sasidevi@2005");  
//here sonoo is database name, root is username and password  
    Statement stmt=con.createStatement();  
    ResultSet rs=stmt.executeQuery("select * from first");  
    while(rs.next())  
        System.out.println(rs.getInt(1)+"  "+rs.getString(2)+"  "+rs.getString(3));  
    con.close();  
}
catch(Exception e)
{
     System.out.println(e);
}  
}  
}
```

### Output:
![image](https://github.com/chandrumathiyazhagan/DBMS/assets/119393023/9d7e32df-0eb0-499d-b1f3-fff167543336)

### Result:
Thust the database is connected and data displayed sucessfully.
