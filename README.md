# Project Costing Calculator

## Overview

This is a Project Costing Calculator that helps you calculate the total cost of a project, including staff costs, materials, taxes, and more. The project was originally a command-line application (main.py) and has been updated to include a modern web interface.

## Original Code (main.py) - Issues Identified

1. **Variable Scope Issue**: The `amount` variable used in line 138 was only defined in the loop scope for permanent staff, leading to potential errors.
2. **Overwritten Staff Details**: The `staff_details` list was overwritten twice (first for permanent staff, then for temporary staff), causing loss of permanent staff data.
3. **Incorrect Table Population**: When generating the Word document, it tried to access `num_of_days` from temporary staff (which don't have this field), causing errors.
4. **Missing Total Calculation**: The total of permanent and temporary staff costs was not being calculated for the direct cost.
5. **No Frontend**: The application was command-line only with no user-friendly interface.

## Updated Code - Improvements Made

### New Files Added:
- `app.py`: Main Flask application with all calculation logic and routes
- `requirements.txt`: List of dependencies needed to run the project
- `templates/index.html`: Main form interface for entering data
- `templates/result.html`: Results page displaying calculated costs
- `README.md`: This documentation file

### Key Fixes and Enhancements:
1. **Separate Staff Lists**: Now uses separate lists for permanent and temporary staff to avoid data loss
2. **Proper Cost Calculation**: Correctly sums both permanent and temporary staff costs for direct cost calculation
3. **Web Interface**: Added a modern, responsive frontend using Flask and HTML/CSS
4. **Improved Word Document**: Generates a more comprehensive Word document with separate tables for permanent and temporary staff
5. **Download Feature**: Allows downloading the cost summary as a Word document directly from the web interface
6. **Responsive Design**: The frontend works well on both desktop and mobile devices

## How to Run the Project

### Step 1: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 2: Run the Application
```bash
python app.py
```

### Step 3: Access the Application
Open your web browser and go to `http://localhost:5000`

## Features

- Enter details for permanent staff (with different rate slots)
- Enter details for temporary staff (with optional HRA)
- Input various other project costs (consumables, equipment, travel, etc.)
- Calculate total project cost including tax
- View detailed results in a user-friendly format
- Download the cost summary as a Word document

## Technologies Used

- **Backend**: Flask (Python)
- **Frontend**: HTML5, CSS3, JavaScript
- **Document Generation**: python-docx
