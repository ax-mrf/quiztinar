# Quiztinar
Generate Quizzes from Teaching Slides/Syllabus Material using GPT-4o

This Python script allows you to generate quizzes from PDF files using OpenAI's GPT-4o model. It extracts learning objectives from the PDF and generates multiple-choice questions based on those objectives. Simulating a two-step Chain of Thought pipeline, it aims to generate higher quality quizzes only through methods of prompting.

The output is saved as both PDF and CSV files for readability and easy integration with other platforms.

## Recommendations
- **Stick to One Chapter per file**: It works best with only one main topic per file.
- **Provide enough content**: If you're planning on producing a large number of quiz questions, make sure the chapter given to the model has sufficient content.
- **Beware of billing charges**: Quiztinar features loops of requests to OpenAI API and can hit your usage limit. Familiarize yourself with OpenAI's billing and usage limits.
- **Review output**: AI generated output can be faulty. Do not feature the output in a gradable exam environment without proper review.
- **Randomize the output choice order**: AI generated content does (very) heavily favor placing the correct answer at choices C and B. If you are going to use the material in an exam environment, consider shuffling the order of choices.
## Features

- **Extract Learning Objectives**: Automatically extracts learning objectives from a PDF file.
- **Modify Learning Objectives**: Allows you to modify the learning objectives extracted before the Quizzes are created.
- **Generate Quizzes**: Creates multiple-choice quizzes based on the extracted learning objectives.
- **Multiple Inputs**: Allows you to select several PDF files, will then process them sequentially.
- **Up to 50 Questions per PDF**: Allows you to specify the number of quiz questions you want to generate in multiples of 5 up until 50 questions.
- **Built-in PDF Splitter**: Divides your PDF into chapters and will work on all of them sequentially.
- **Output Formats**: Generates the learning objectives and quizzes in PDF files, and generates a CSV featuring the Quiz Question items separated for use and modifications before getting featured or presented to students. Output is saved in the same directory as input.

## Prerequisites

- Python 3.8 or higher
- OpenAI API key

## Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/ax-mrf/quiztinar
   cd quiztinar
   ```

2. **Set Up a Virtual Environment**:
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
   ```

3. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Set Up the `.env` File**:
   - Create a `.env` file in the root directory of your project.
   - Add your OpenAI API key to the `.env` file:
     ```plaintext
     API_KEY=your_openai_api_key_here
     ```
   - Replace `your_openai_api_key_here` with your actual OpenAI API key.

## Usage

1. **Run the Script**:
   ```bash
   python3 Quiztinar.py
   ```

2. **Using the GUI**:
   - **Select PDF Files**: Click the "Browse" button to select one or more PDF files.
   - **Number of Quizzes**: Specify the number of quizzes you want to generate per file. Each quiz contains 5 questions.
   - **Split PDF into Chapters**: If your PDF contains multiple chapters, you can split it into chapters by specifying page ranges.
   - **Confirm and Modify Learning Objectives**: Optionally, you can review and modify the learning objectives before generating the quiz.
   - **Run Script**: Click the "Run Script" button to start the quiz generation process.

3. **Output**:
   - The script will generate PDF and CSV files containing the quizzes and learning objectives.
   - The output files will be saved in the same directory as the input PDF files.

## Example Directory Structure

```plaintext
quiztinar/
│
├── Quiztinar.py
├── requirements.txt
├── .env
├── venv/
│   └── (virtual environment files)

```

## Dependencies

- **openai**: The OpenAI Python client library for interacting with the OpenAI API.
- **python-dotenv**: A library to load environment variables from a `.env` file.
- **PyPDF2**: A library to extract text from PDF files.
- **tiktoken**: A library to count tokens in text, used to ensure the text fits within OpenAI's token limits.
- **markdown**: A library to convert Markdown text to HTML.
- **weasyprint**: A library to convert HTML to PDF.
- **pandas**: A library for data manipulation, used to process quiz output into CSV.
- **tkinter**: The standard Python interface to the Tk GUI toolkit, used for the GUI.

## Notes

- **OpenAI API Key**: Ensure that you have a valid OpenAI API key. You can obtain one from the [OpenAI website](https://platform.openai.com/).
- **Virtual Environment**: Using a virtual environment is recommended to avoid conflicts with other Python projects.
- **File Size Limitations**: Be aware of OpenAI's token limits when processing large PDF files. If the text exceeds the token limit, you may need to split the PDF into smaller sections.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.


---
