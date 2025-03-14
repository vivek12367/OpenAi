# Code Generation with CodeGen Model - Streamlit App

![APP](https://private-user-images.githubusercontent.com/101359606/422608062-cf1e18eb-389a-47d0-a554-3eb884a42dbe.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NDE5MTk1MTYsIm5iZiI6MTc0MTkxOTIxNiwicGF0aCI6Ii8xMDEzNTk2MDYvNDIyNjA4MDYyLWNmMWUxOGViLTM4OWEtNDdkMC1hNTU0LTNlYjg4NGE0MmRiZS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwMzE0JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDMxNFQwMjI2NTZaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1kYjRhYzM4Yjg5NDM5NTA1ZWYyNTg2YzllMzJiM2RkYWRiZTFiODA1ZmQ2YzM1YjRmNGNkODFhMzRiM2Q2Mzk0JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.AfdhaOzhVl5xUu4VjgOLWTEFlM_J87GOhlkhl19Zbww)

## Business Objective
The primary goal of this project is to create a user-friendly web application using Streamlit that leverages a pre-trained **CodeGen model** from Salesforce to generate Python code based on user input. The application is designed to help developers, data scientists, and engineers quickly prototype code snippets, functions, or even complete programs by simply providing a textual prompt. The app also includes features to validate the generated code for syntax errors, allowing users to download their code for further use.

### Key Objectives:
- **Automated Code Generation:** Generate Python code based on user-provided prompts.
- **Syntax Validation:** Ensure the generated code is free from syntax errors.
- **Real-Time Interaction:** Provide instant feedback to the user, such as syntax error alerts and code quality checks.
- **Downloadable Code:** Allow users to download the generated Python code for later use or integration into their projects.

---

## Approach

### 1. **Model Selection:**
The model used in this app is **Salesforce's CodeGen-350M-mono**, which is a pre-trained causal language model fine-tuned for code generation tasks. The model has been chosen for its ability to generate relevant and functional code based on prompts that may vary in complexity.

### 2. **Streamlit Interface:**
Streamlit is used to create a simple and interactive web interface. The app allows users to input a code prompt and adjust various parameters for code generation, such as:
- **Max Length:** Controls the length of the generated code.
- **Temperature:** Adjusts the randomness of the output (higher temperature = more randomness).
- **Top-p (Nucleus Sampling):** A probabilistic method to limit the choices from the model.
- **Top-k Sampling:** Limits the number of token choices the model considers.

### 3. **Code Generation Process:**
- The user inputs a textual prompt into the app.
- The app tokenizes the input and sends it to the CodeGen model for processing.
- The model generates Python code based on the input prompt, using the parameters set by the user (e.g., max length, temperature).
- The app decodes and displays the generated code with syntax highlighting and checks it for errors.
- If there are no errors, the app provides the option to download the generated code as a `.py` file.

### 4. **Error Detection:**
To ensure the generated code is functional, the app uses Python's `compile()` function to check for syntax errors. If errors are found, the app displays them to the user; otherwise, it confirms that the code is error-free.

---

## Recommendations

### 1. **Model Customization:**
For specific use cases, fine-tuning the CodeGen model on a more domain-specific dataset (e.g., data science-related prompts) could improve the quality of the generated code. This would ensure the model is better aligned with particular coding styles or libraries.

### 2. **Extend to Other Languages:**
Currently, the app generates Python code. However, expanding the model to support other languages such as JavaScript, Java, or C++ could significantly broaden the application’s use cases.

### 3. **Enhanced Code Quality Check:**
Although syntax validation is in place, integrating more advanced static code analysis tools could help assess the quality of the generated code (e.g., checking for performance optimization or security vulnerabilities).

### 4. **User Feedback and Improvement:**
Adding a feedback mechanism to the app would allow users to report the accuracy and usefulness of the generated code. This feedback could be used to further fine-tune the model and improve its outputs.

### 5. **Deployment to Production:**
For wider use, consider deploying this app on cloud platforms (such as Heroku, AWS, or GCP) to make it accessible to a larger audience without the need for local setup.

---

## How to Run the App

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yourusername/codegen-streamlit-app.git
   ```

2. **Install the Dependencies:**
   Navigate to the project folder and install the required Python packages:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Streamlit App:**
   Start the app by running:
   ```bash
   streamlit run app.py
   ```

4. **Access the App:**
   After running the command, open a browser and go to `http://localhost:8501` to interact with the app.

---

## Technologies Used

- **Streamlit:** For creating the interactive web app interface.
- **Transformers (Hugging Face):** For utilizing the pre-trained CodeGen model.
- **PyTorch:** For model processing and inference.
- **Base64:** For generating downloadable links for code files.

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Feel free to modify or expand this README based on any specific features or additional functionality in your app!
