# SQL Schema for the Kiosk Project

Below is the SQL schema for the `yourname_kiosk` database. This schema includes tables for products, orders, and order items, along with the relationships between them.


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
            "          <a class=\"navbar-brand\" href=\"/\">MKNR Palengke Kiosk</a>",
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
            "  </body>",
            "</html>"
        ],
        "description": "Basic Flask layout template with Bootstrap"

}
```
