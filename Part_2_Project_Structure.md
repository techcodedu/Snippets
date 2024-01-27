 **# Project Structure Guide**

**1. Accessing the Snippet HQ:**

To efficiently display the project structure, let's create a custom snippet in VS Code:

1. Open VS Code.
2. Navigate to **File > Preferences > Configure User Snippets**.
3. Choose **html** as the language for your snippet.

**2. Creating the Snippet:**

Paste the following snippet code into the opened file:

```json
"Project structure": {
  "prefix": "projects",
  "body": [
    "<pre>",
    "<code>",
    "FarmersMarketApp/",
    "├── app/",
    "│  ├── static/",
    "│  │  ├── css/",
    "│  │  │  └── styles.css",
    "│  │  ├── js/",
    "│  │  │  └── script.js",
    "│  │  └── images/",
    "│  │    └── [product images]",
    "│  ├── templates/",
    "│  │  ├── layout.html",
    "│  │  ├── index.html",
    "│  │  ├── product.html",
    "│  │  └── order_confirmation.html",
    "│  ├── __init__.py",
    "│  └── routes.py",
    "├── venv/",
    "├── requirements.txt",
    "└── run.py",
    "</code>",
    "</pre>"
  ],
  "description": "Displays the FarmersMarketApp project structure"
}
```

**3. Saving and Testing:**

1. Save the snippets file.
2. in a html file type the prefix keyword "html"
