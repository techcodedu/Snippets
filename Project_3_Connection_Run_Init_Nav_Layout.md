# SQL Schema for the Kiosk Project

Below is the SQL schema for the `yourname_kiosk` database. This schema includes tables for products, orders, and order items, along with the relationships between them.

### Note* look for .json SQL 
```
    "SQL Kiosk Database Schema": {
        "prefix": "kioskdb",
        "body": [
            "CREATE DATABASE yourname_kiosk;",
            "",
            "USE yourname_kiosk;",
            "",
            "CREATE TABLE products (",
            "    product_id INT AUTO_INCREMENT PRIMARY KEY,",
            "    name VARCHAR(255) NOT NULL,",
            "    unit VARCHAR(50),",
            "    price_per_unit DECIMAL(10, 2),",
            "    image_url VARCHAR(255)",
            ");",
            "",
            "CREATE TABLE orders (",
            "    order_id INT AUTO_INCREMENT PRIMARY KEY,",
            "    total_price DECIMAL(10, 2),",
            "    date_time DATETIME DEFAULT CURRENT_TIMESTAMP,",
            "    customer_contact VARCHAR(255)",
            ");",
            "",
            "CREATE TABLE order_items (",
            "    order_item_id INT AUTO_INCREMENT PRIMARY KEY,",
            "    order_id INT,",
            "    product_id INT,",
            "    quantity DECIMAL(10, 2),",
            "    price DECIMAL(10, 2),",
            "    FOREIGN KEY (order_id) REFERENCES orders(order_id),",
            "    FOREIGN KEY (product_id) REFERENCES products(product_id)",
            ");",
            "",
            "INSERT INTO `products` (`product_id`, `name`, `unit`, `price_per_unit`, `image_url`) VALUES",
            "(1, 'Cucumber', 'kg', 3.00, 'images/cucumber.jpg'),",
            "(2, 'Carrot', 'pc', 4.00, 'images/carrot.jpg');"
        ],
        "description": "Creates the necessary tables and relations for the Kiosk database"
    }
```


# `init.py` Connection Code Snippet

This section provides a code snippet for setting up a Flask application with a MySQL database, ideal for inclusion in `init.py`.

## Usage

This snippet initializes a Flask application and configures it to connect to a MySQL database. 
### Note* look for .json python 

### Snippet

```{
    "Init Flask with MySQL": {
        "prefix": "init",
        "body": [
            "from flask import Flask",
            "from flask_mysqldb import MySQL",
            "",
            "app = Flask(__name__)",
            "",
            "# Database connection",
            "app.config['MYSQL_HOST'] = 'localhost'",
            "app.config['MYSQL_USER'] = 'root'",
            "app.config['MYSQL_PASSWORD'] = ''",
            "app.config['MYSQL_DB'] = 'yourdatabase'",
            "",
            "mysql = MySQL(app)",
            "",
            "# Import routes",
            "from yourname_app import routes"
        ],
        "description": "Initialize Flask app with MySQL"
    }
}
```
# `run.py` Execution Code Snippet

The following code snippet is for the `run.py` file, which is used to run the Flask application in development mode with debug enabled.

### Note* look for .json python 

```
    "Run Flask App": {
        "prefix": "run",
        "body": [
            "from app_foldername import app",
            "",
            "if __name__ == \"__main__\":",
            "    app.run(debug=True)"
        ],
        "description": "Run the Flask application in development mode with debug enabled"
}
```
# `templates/layouts.html` Execution Code snippet

The following code snippet is for the layouts.html. 
### Note* look for .json html 
```

    "Flask Layout Template": {
        "prefix": "layout",
        "body": [
            "<!DOCTYPE html>",
            "<html lang=\"en\">",
            "  <head>",
            "    <meta charset=\"UTF-8\" />",
            "    <meta name=\"viewport\" content=\"width=device-width, initial-scale=1.0\" />",
            "    <title>MKNR Palengke Kiosk</title>",
            "    <!-- Bootstrap CSS Link -->",
            "    <link",
            "      rel=\"stylesheet\"",
            "      href=\"{{ url_for('static', filename='css/bootstrap.min.css') }}\"",
            "    />",
            "  </head>",
            "  <body>",
            "    <!-- Inside layout.html -->",
            "    <header>",
            "      <nav class=\"navbar navbar-expand-lg navbar-light bg-light\">",
            "        <div class=\"container\">",
            "          <a class=\"navbar-brand\" href=\"/\">Your Kiosk Name</a>",
            "          <div class=\"navbar-nav\">",
            "            <a class=\"nav-link\" href=\"/\">Home</a>",
            "            <a class=\"nav-link\" href=\"/orders\">Orders</a>",
            "            <!-- Placeholder -->",
            "          </div>",
            "        </div>",
            "      </nav>",
            "    </header>",
            "",
            "    <main class=\"container\">{% block content %}{% endblock %}</main>",
            "",
            "    <footer>",
            "      <!-- Footer Content Here -->",
            "    </footer>",
            "",
            "    <!-- Bootstrap JS Link -->",
            "    <script src=\"{{ url_for('static', filename='js/bootstrap.bundle.min.js') }}\"></script>",
            "     <script src=\"{{ url_for('static', filename='js/script.js') }}\"></script>",
            "  </body>",
            "</html>"
        ],
        "description": "Basic Flask layout template with Bootstrap"

}
```
