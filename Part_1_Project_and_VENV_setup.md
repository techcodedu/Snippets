 **# Setting Up Your Kiosk Project**


**Note: ***Assuming you don't have an internet connection** ***

**Here are the steps to set up your project directory and activate the virtual environment**
**1. Create and Activate with a Snippet:**

- Open a terminal and create a new snippet with the following content:

```json

  "setup": {
    "prefix": "setup",
    "body": [
      "# Create project directory",
      "mkdir project_name",

      "# Navigate to project directory",
      "cd $1_kiosk",

      "# Open project in VS Code",
      "code ."
  
      "# Locate a venv folder from your old project and paste in your new",
      "",

      "# Activate virtual environment",
      "copiedvenv\Scripts\activate",

      "# Open project in VS Code",
      "code ."
    ],
    "description": "Sets up project directory, copies virtual environment, activates it, and opens VS Code"
  }
```


**3. Saving and Testing:**

1. Save the snippets file.
2. in a .html file type the prefix keyword "setup"


