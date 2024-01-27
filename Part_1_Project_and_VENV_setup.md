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
      "mkdir $1_kiosk",

      "# Navigate to project directory",
      "cd $1_kiosk",

      "# Copy a venv from your old project and place it here in our new project directory",
      "",

      "# Activate virtual environment",
      "appvenv\Scripts\activate",

      "# Open project in VS Code",
      "code ."
    ],
    "description": "Sets up project directory, copies virtual environment, activates it, and opens VS Code"
  }
```

- Save the snippet. and the prefix keyword "setup"


