# `index.html` Connection Code Snippet

This section provides a code snippet for index or the product page
``
### Note look for .html json
```
{
    "Flask Index Template": {
        "prefix": "index",
        "body": [
            "<!-- Inside index.html -->",
            "{% extends 'layout.html' %}",
            "",
            "{% block content %}",
            "<div class=\"container mt-4\">",
            "    <div class=\"row\">",
            "        {% for product in products %}",
            "        <div class=\"col-lg-3 col-md-4 col-sm-6 col-xs-12 mb-4\">",
            "            <div class=\"card h-100\">",
            "                 <img src=\"{{url_for('static',filename = product[4])}}\" class=\"card-img-top product-image\" alt=\"{{ product[1] }}\" data-bs-toggle=\"modal\" data-bs-target=\"#imageModal\" onclick=\"showImageinModal(this.src)\">",
            "                <div class=\"card-body\">",
            "                    <h5 class=\"card-title\">{{ product[1]}}</h5>",
            "                    <p class=\"card-text\">Price: {{ product[3] }} per {{ product[2] }}</p>",
            "                    <button type=\"button\" class=\"btn btn-primary add-item\" onclick=\"addItemToCart('{{ product[3] }}')\">Add Item</button>",
            "                    <!-- Other button elements -->",
            "                </div>",
            "            </div>",
            "        </div>",
            "        {% endfor %}",
            "    </div>",
            "    {% include 'modals/image_modal.html' %}",
            "    <!-- Total Cost Display -->",
            "    <div class=\"text-end mt-4\">",
            "        <h3>Total Cost: <span id=\"totalCost\">0</span> Pesos</h3>",
            "    </div>",
            "</div>",
            "{% endblock %}"
        ],
        "description": "Flask template for the index page with product listing and modals"
    }
}
```
# `routes.py` Connection Code Snippet

This section provides a code snippet for index.html that is link to your first route

### Note look for .python json
```
{
    "Flask Route for Index Page": {
        "prefix": "indexroute",
        "body": [
            "@app.route('/')",
            "def index():",
            "    cursor = mysql.connection.cursor()",
            "    cursor.execute(\"SELECT * FROM products\"),
            "    products = cursor.fetchall()",
            "    print(products)",
            "    cursor.close()",
            "    return render_template('index.html', products=products)"
        ],
        "description": "Flask route for displaying products on the index page"
    }
}
```
# `image_modal.html` Template Snippet

This section provides a code snippet for the `image_modal.html` template, which is used in conjunction with the `index.html` page in a Flask application. This modal is designed to display the image of each product when clicked.

### Snippet for Image Modal

### Note look for .html json
```

    "Image Modal HTML Template": {
        "prefix": "imagemodal",
        "body": [
            "<!-- Inside modals/image_modal.html -->",
            "<div class=\"modal fade\" id=\"imageModal\" tabindex=\"-1\" aria-labelledby=\"imageModalLabel\" aria-hidden=\"true\">",
            "    <div class=\"modal-dialog modal-lg\">",
            "        <div class=\"modal-content\">",
            "            <div class=\"modal-header\">",
            "                <h5 class=\"modal-title\" id=\"imageModalLabel\">Product Image</h5>",
            "                <button type=\"button\" class=\"btn-close\" data-bs-dismiss=\"modal\" aria-label=\"Close\"></button>",
            "            </div>",
            "            <div class=\"modal-body\">",
            "                <img id=\"modalImage\" src=\"\" class=\"img-fluid\" alt=\"Product Image\">",
            "            </div>",
            "        </div>",
            "    </div>",
            "</div>"
        ],
        "description": "HTML template for an image modal in a Flask application"
}
```
# `static/js/script.js` Functionality Snippet

This section provides a JavaScript code snippet for `script.js`. This script includes functionalities for adding items to a shopping cart and displaying product images in a modal.

### JavaScript Snippet for Cart Addition and Image Modal

```json
{
    "Add Item and Image Modal JS": {
        "prefix": "js",
        "body": [
            "// Inside script.js",
            "// Add item functionality",
            "let totalCost = 0;",
            "",
            "function updateTotalCostDisplay() {",
            "    const totalCostDisplay = document.getElementById('totalCost');",
            "    totalCostDisplay.innerText = totalCost.toFixed(2);",
            "}",
            "",
            "function addItemToCart(price) {",
            "    totalCost += parseFloat(price);",
            "    updateTotalCostDisplay();",
            "}",
            "// Modal for image",
            "function showImageinModal(imageUrl) {",
            "    document.getElementById('modalImage').src = imageUrl;",
            "}"
        ],
        "description": "JavaScript functions for adding items to cart and showing images in a modal"
    }
}
