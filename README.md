# CSV to SQL Pivot Table Viewer

#### Video Demo:  <[(https://youtu.be/80lF3LPRFQQ)]>


#### Description:
This is a final project submission for CS50 introduction to computer science course.
This project is a web-based application built using Flask that allows users to upload CSV files, store them as SQL tables, and dynamically generate pivot table-like views of the data. The application offers basic functionality to filter columns and apply simple SQL aggregations (such as sum, count, and average) on the data.

### Motivation:
I chose this project because I wanted to better understand how data can be manipulated and visualized in a web environment. Working on this project has helped me improve my skills in handling CSV data and performing SQL queries. Additionally, I wanted to learn more about the process of rendering dynamic data in a web application and creating simple data visualizations. 

While developing this project, I used ChatGPT to troubleshoot buggy code. Importantly, I made sure to understand why certain parts of the code weren't working, and I actively applied the solutions learned. I also consulted ChatGPT for suggestions on improving the CSS used for the website's appearance. ChatGPT has also been used to improve the readability of this README file.

### Project Structure:
Here is the structure of the project files, as shown in the website folder:

website/
│
├── instance/
│   └── database.db              # SQLite database storing uploaded CSV data
├── static/
│   ├── extended_numeric_data.csv # Sample CSV files for testing
│   ├── numeric_data.csv          # Another sample CSV file, more complex than the 1st
│   ├── style.css                 # Stylesheet for the website
├── templates/
│   ├── apology.html              # Error page template
│   ├── home.html                 # Homepage for CSV uploads
│   ├── layout.html               # Base template layout
│   └── Pivot.html                # Pivot table view and query form
├── app.py                        # Main Flask application
├── droptables.py                 # Helper script to drop tables in the database, just a clean up tool
└── database.db                   # SQLite database file

### How to Run the Project:

1. **Set Up Environment**:
   - Install dependencies:
     ```bash
     pip install flask flask_sqlalchemy pandas sqlalchemy
     ```

2. **Run the Application**:
   - Execute the Flask application:
     ```bash
     flask run --debug
     ```
I've used the flask run --debug command to run my code, as it allows me to see real time changes to my code.

3. **Navigate to**: `http://127.0.0.1:5000` in your web browser.
   - Upload a CSV file and name it.
   - Make sure there isn't another an existing table with the same name. If there is, the web app will return an error page.
   - Make sure the file uploaded is a CSV file. If it isn't, the web app will return an error page.
   - Once uploaded succesfully, you will be redirected to the pivot page, in which you can select which table you want to visualise. 
   - You can now decide whether to go back to the Home page and upload another CSV, or remain to the Pivot page and visualise the data on the tables already loaded. 
   - To visualise the data of the loaded tables, select the table you want to see from the dropdown list and press the button "View".
   - A list of the column names for the table selected will appear, you can select one or multiple using ctrl + left click, or up/down arrows while pressing shift.
   - Select the type of calculation you want to apply to the columns selected, and press "Add column"
   - The data will appear in a table underneath the selection boxes

### Dependencies:
- **Flask**: A lightweight WSGI web application framework.
- **Flask-SQLAlchemy**: SQLAlchemy integration for Flask to handle database interactions.
- **Pandas**: Used for reading and manipulating the CSV files.
- **SQLite**: A lightweight relational database used to store the CSV data.
- **Jinja2**: Template engine for rendering dynamic HTML pages.

### Notes on design choices
As this project was meant to allow me to acquire a basic understanding on data manipulation and visualisation, I've decided to not implement a log in/out and user management system. I do understand the website as it is, allows every user to see each other user tables. I've spent quite a lot of time deciding on how to implement the dynamic SQL query to retrieve information. My first instict was to manipulate plain text within the query itself. However, by googling I've discovered that SQLAlchemy can perform this using methods, which is way more clean and easy to implement.

### Conclusion:
This project offers a basic yet flexible framework for uploading, storing, and querying CSV data in a web environment. It allows users to interact with their data easily, viewing it in a table format and performing simple pivot operations using SQL functions.
This project could be improved by:
   Improving the website aesthetic
   Introduce a user management system (log in/out) and segregate the uploaded data only to those users who did upload it
   introduce more option to manipulate the table
   
