# Digital Brand Survey Tool

## Description

digital-brand-survey/
|-- backend/
|   |-- .env
|   |-- data_processing.py
|   |-- package.json
|   |-- server.js
|   |-- .gitignore
|-- frontend/
|   |-- public/
|   |   |-- index.html
|   |-- src/
|   |   |-- components/
|   |   |   |-- SurveyForm.js
|   |   |   |-- Question.js
|   |   |   |-- AdminPanel.js
|   |   |-- App.js
|   |   |-- index.js
|   |-- .env
|   |-- package.json
|   |-- .gitignore
|-- README.md


## Table of Contents


- [Digital Brand Survey Tool](#digital-brand-survey-tool)
  - [Description](#description)
  - [Table of Contents](#table-of-contents)
  - [Project Overview](#project-overview)
  - [Objectives](#objectives)
  - [Key Features](#key-features)
  - [Technologies Used](#technologies-used)
  - [Setup Instructions](#setup-instructions)
    - [Backend Setup](#backend-setup)
    - [Frontend Setup](#frontend-setup)
  - [Usage](#usage)
  - [Environment Variables](#environment-variables)
  - [Contributing](#contributing)
  - [License](#license)

## Project Overview

This project aims to develop a comprehensive digital brand survey tool designed to gather diverse responses from various vendors. The survey will include questions across multiple categories and employ various response formats, including multiple-choice, numerical, and both short and long text responses. The tool will feature code-free customizability for site administrators to update and modify questions as needed. Additionally, it will integrate with a backend system to feed collected data into a larger, separate dashboard for analysis and reporting.

## Objectives

1. Develop a Versatile Survey Tool: Create a digital survey tool that supports a wide range of question types and response formats.
2. Ensure Easy Customizability: Implement a user-friendly, code-free interface for site administrators to update and add questions.
3. Integrate with Backend Systems: Ensure seamless data integration with an existing dashboard for comprehensive data analysis and reporting.
4. Enhance Data Collection: Design the tool to capture detailed and varied data from vendors to inform sustainability analysis.

## Key Features

1. **Diverse Question Types:**
   - Multiple-choice questions
   - Numerical input fields
   - Short text responses
   - Long text responses
   - Ability to "add more" which would duplicate a set of questions (e.g., default of 3 materials per product)

2. **User-Friendly Customization Interface:**
   - Drag-and-drop functionality for adding or rearranging questions
   - Simple input fields for updating question text and response options
   - Preview mode to test survey updates before deployment

3. **Seamless Data Integration:**
   - Automated data export to a backend dashboard
   - Real-time data syncing
   - Compatibility with existing data analysis tools

4. **Admin Access and Permissions:**
   - Role-based access control to ensure only authorized personnel can modify the survey
   - Ability to add new admin and brand users
   - Audit logs to track changes made to the survey

5. **Responsive Design:**
   - Mobile-friendly interface to ensure accessibility across devices
   - Consistent user experience on both desktop and mobile platforms

## Technologies Used

- **Frontend:** React, Bootstrap
- **Backend:** Node.js, Express.js
- **Data Processing and Visualization:** Python (Pandas, Matplotlib, Seaborn)

## Setup Instructions

### Backend Setup

1. Clone the repository and navigate to the backend directory:

    ```bash
    git clone https://github.com/<USERNAME>/<REPO>.git
    cd <REPO>/backend
    ```

2. Create a `.env` file in the backend directory and add your environment variables:

    **backend/.env**

    ```plaintext
    # Add any environment variables here
    ```

3. Install the necessary Node.js packages:

    ```bash
    npm install
    ```

4. Install the necessary Python packages:

    ```bash
    pip install pandas matplotlib seaborn
    ```

5. Create the `data_processing.py` file in the backend directory with the following content:

    **backend/data_processing.py**

    ```python
    import pandas as pd
    import matplotlib.pyplot as plt
    import seaborn as sns

    # Load the CSV data
    data = pd.read_csv('survey_data.csv')

    # Data cleaning
    data = data.fillna('N/A')  # Replace NaN values with 'N/A'

    # Save the cleaned data back to CSV
    data.to_csv('cleaned_survey_data.csv', index=False)

    # Generate a simple visualization (e.g., a count plot of responses)
    plt.figure(figsize=(10, 6))
    sns.countplot(data=data, x='value')
    plt.title('Survey Responses Count')
    plt.xlabel('Response')
    plt.ylabel('Count')
    plt.xticks(rotation=45)
    plt.tight_layout()
    plt.savefig('survey_responses_visualization.png')

    print('Data cleaned and visualization created')
    ```

6. Start the backend server:

    ```bash
    npm start
    ```

### Frontend Setup

1. Navigate to the frontend directory:

    ```bash
    cd ../frontend
    ```

2. Create a `.env` file in the frontend directory and add your environment variables:

    **frontend/.env**

    ```plaintext
    REACT_APP_API_URL=http://localhost:5000
    ```

3. Install the necessary Node.js packages:

    ```bash
    npm install
    ```

4. Start the frontend development server:

    ```bash
    npm start
    ```

## Usage

1. Access the frontend at `http://localhost:3000`.
2. Fill out the survey form and submit it.
3. Check the backend server logs to see the data being processed.
4. View the generated visualization at `http://localhost:5000/survey_responses_visualization.png`.

## Environment Variables

- **Backend**: Create a `.env` file in the `backend` directory and add environment variables as needed.
- **Frontend**: Create a `.env` file in the `frontend` directory and add `REACT_APP_API_URL` with the backend URL.

## Contributing

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes.
4. Commit your changes (`git commit -am 'Add new feature'`).
5. Push to the branch (`git push origin feature-branch`).
6. Create a new Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
