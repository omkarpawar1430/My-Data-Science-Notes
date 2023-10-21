
Tags: #python 

------------------------------------------

# Flask API

---

- 🔗 Links
    
    [Welcome to Flask — Flask Documentation (2.2.x)](https://flask.palletsprojects.com/en/2.2.x/)
    
    [Template Designer Documentation — Jinja Documentation (3.1.x)](https://jinja.palletsprojects.com/en/3.1.x/templates/)
    
- Web Server Gateway Interface
    
    Flask is Web Server Gateway Interface, 
    
    Yes, Flask is a WSGI (Web Server Gateway Interface) framework for Python. WSGI is a specification for a universal interface between web servers and web applications or frameworks written in Python.
    
    In simpler terms, WSGI allows Python web applications like Flask to communicate with web servers like Apache or Nginx. WSGI acts as a bridge between the web server and the web application, handling requests from the web server and passing them on to the application, and then returning the response back to the web server.
    

- what is the static and templates folder?
    
    The **`static`** folder is used to store static files such as images, CSS files, and JavaScript files that are used by your Flask application. When a client requests a web page from your Flask application, any static files that are required by that page (e.g., CSS or JavaScript files) are served from the **`static`** folder. This helps to improve the performance of your application, as the static files can be cached by the client's web browser.
    
    The **`templates`** folder is used to store HTML templates that are used to render dynamic content in your Flask application. Flask uses the Jinja2 templating engine by default, which allows you to write templates that contain placeholders for dynamic content. When a Flask view function returns a response that includes a template, Flask will render the template with the dynamic content and return the resulting HTML to the client.
    
- Jinja2
    
    Jinja2 is the default templating engine used by Flask. Templates are used to render dynamic content, meaning content that changes based on user input or other factors. In simpler terms, templates allow you to create web pages that display different content based on the situation. For example, you can use templates to create a web page that displays a user's profile information, with different information displayed for each user.
    
    Jinja2 uses a special syntax that allows you to include dynamic content in your templates. For example, you can include variables, loops, and conditional statements in your templates to make them more flexible and powerful. When a Flask view function returns a response that includes a template, Flask will render the template with the dynamic content and return the resulting HTML to the client.
    
- get bootstrap
    
    [Introduction](https://getbootstrap.com/docs/5.0/getting-started/introduction/)
    
- container vs container-fluid
    
    A **`container`** is a class used in Bootstrap, a popular front-end framework, to create a fixed-width container. The width of the container remains constant, regardless of the screen size. This means that the content within the container will not expand to fill the entire width of the screen on larger devices.
    
    On the other hand, **`container-fluid`** is another class used in Bootstrap to create a full-width container that stretches to the edges of the screen. This means that the content within the container will expand to fill the entire width of the screen on larger devices.
    
    In general, it's best to use **`container-fluid`** if you want your content to stretch to the full width of the screen, and **`container`** if you want to limit the width of your content to a fixed size. It's important to consider the design of your website and the user experience you want to create when choosing between **`container`** and **`container-fluid`**.
    
- **pip install Flask-SQLAlchemy**
    
    Flask SQLAlchemy is a popular Python library that provides an Object-Relational Mapping (ORM) system for working with relational databases in Flask applications. Here are some reasons why you might consider using Flask SQLAlchemy:
    
    1. Simplicity: Flask SQLAlchemy provides a simple and intuitive interface for working with databases in Flask applications. It allows you to interact with the database using Python objects instead of SQL queries, which can simplify your code and reduce the potential for errors.
    2. Portability: Flask SQLAlchemy abstracts away the differences between different database management systems (such as MySQL, PostgreSQL, and SQLite) and provides a consistent interface for working with them. This makes it easier to switch between different databases or deploy your application on different platforms.
    3. Security: Flask SQLAlchemy provides built-in protections against SQL injection attacks and other security vulnerabilities, making it a more secure option for interacting with databases.
    4. Scalability: Flask SQLAlchemy is designed to work well with large, complex databases and can handle advanced features such as sharding and replication.
    
    Overall, Flask SQLAlchemy is a powerful tool for building Flask applications that interact with databases. If your Flask application needs to store and retrieve data, Flask SQLAlchemy can provide a robust and reliable solution that can help you build scalable, secure, and maintainable applications.
    
- `__repr__`  concept from OOP
    
    implementing the **`__repr__()`**
     the method can be helpful for debugging and testing purposes, as it provides a concise and informative way to represent objects of a class.
    
- How to activate the environment in the power shell ?
    
    ![[Pasted image 20230506082641.png]]
    
- GET vs POST method
    
    
- CRUD

---------------------
#### links:
[[]]
[[]]