# simple-jdbc
Using this library you can easily write persistency logic. This library provides a simple function to do CURD operations.

# Working with SimpleJdbcTemplate

public class Employee {
  private int empId;
  private String empName;
  
  public void setEmpId(int empId) {
    this.empId = empId;
  }
  public int getEmpId() {
    return this.empId;
  }
  public void setEmpName(String empName) {
    this.empName = empName;
  }
  public int getEmpName() {
    return this.empName;
  }
}

1. We have to create SimpleJdbcTemplate Object
    SimpleJdbcTemplate t = new SimpleJdbcTemplate("jdbc-driver-class-name","url","username","password");
    ex:-
      String driver = "com.mysql.jdbc.Driver";
      String url = "jdbc:mysql://localhost:3306/mydb";
      String username = "root";
      String password = "my-password";
      SimpleJdbcTemplate template = new SimpleJdbcTemplate(driver, url, username, password);
      
2. Create Query object using createQuery() function of SimpleJdbcTemplate object
    ex:-
      String sql = "SELECT * FROM emp WHERE eid=?
      Query query = template.createQuery(sql,10);
      
3. Now Execute The Query
    ex:-
      i) If it is NO-SELECT operation use update() function of Query object. It will return the integer (Number of rows effected).
          int count = query.update();
      
      ii) If query is select exact one row then use get() function of Query object. It will return T class object.
          Employee emp = query.get(new EmployeeRowMapper());
          
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
          
