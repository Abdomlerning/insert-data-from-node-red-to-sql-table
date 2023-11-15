Write Function in JavaScript to Insert Data from Node-RED to SQL Table
🗒️ Answer
To insert data from Node-RED to an SQL table using JavaScript, you can use the "Function" node along with the appropriate SQL node for database interaction. Below is a basic example of a JavaScript function in a Node-RED "Function" node that prepares and sends an SQL INSERT query:
// Example Function Node Code
var data = msg.payload;  // Assuming msg.payload contains the data to be inserted

// SQL INSERT Query
var sqlQuery = "INSERT INTO your_table_name (column1, column2, ...) VALUES (?, ?, ...)"; 

// Parameters for the SQL Query
var sqlParams = [data.value1, data.value2, ...];  // Replace with your actual column values

// Set up the SQL message
msg.topic = sqlQuery;
msg.payload = sqlParams;

// Send the SQL message to the SQL node for execution
return msg;
Ensure you replace your_table_name, column1, column2, etc., and data.value1, data.value2, etc., with your actual table name, column names, and corresponding values.

This code assumes that you have an SQL node properly configured in your Node-RED flow to execute SQL queries. The SQL node should be connected downstream from the "Function" node, allowing the generated SQL message to trigger the execution of the SQL query.
