# PDF to Excel Converter in Python :snake:

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/LadyKerr/pdf-to-excel)

This Python script uses the `tabula-py` and `pandas` libraries to convert a PDF file into an Excel file. Each table in the PDF file is written to a separate sheet in the Excel file.

## Running with GitHub Codespaces :rocket:

This repository is configured to use GitHub Codespaces, which provides a complete, configurable development environment in the cloud. Here's how to use it:

1. Click the Open in Codespaces button at the top of the repository, then click the green, Create Codespace buttn. This will open the repository in a new Codespace.

2. **Wait for the Codespace to be created.** GitHub will create a new Codespace for this repository and set it up according to the `devcontainer.json` file. This includes pulling the specified Docker image, running the `postCreateCommand` to install `tabula-py` and `pandas`, and installing the specified VS Code extensions. This process might take a few minutes.

3. **Add your PDF file.** Once the Codespace is ready, add your PDF file to the repository. You can do this by dragging and dropping the file into the file explorer on the left side of the screen.

4. **Add your empty Excel file.** Add an empty Excel file to the repository. You can do this by right-clicking on the file explorer and selecting New File. Name the file with the `.xlsx` extension.

5. **Run the Python script.** Once the Codespace is ready, run the following command in the terminal:

```bash
python pdf_to_excel.py
```

## Usage :computer:

The script defines a function `pdf_to_excel(pdf_file_path, excel_file_path)`, which reads a PDF file and writes its tables to an Excel file.

Here's how you can use this function:

```python
pdf_to_excel('path_to_pdf_file.pdf', 'path_to_excel_file.xlsx')
```

Replace `path_to_pdf_file.pdf`with the path to the PDF file you want to convert, and replace `path_to_excel_file.xlsx`` with the path where you want to save the Excel file.

## Dependencies :package:

- `tabula-py`: A simple wrapper for Tabula, which can read tables in a PDF.
- `pandas`: A powerful data manipulation library.

You can install these dependencies with pip:

```bash
pip3 install tabula-py pandas
```

## How It Works :wrench:

The `tabula.read_pdf` function reads the PDF file and returns a list of tables. Each table is a pandas DataFrame.

The `pd.ExcelWriter` context manager is used to write to the Excel file.

Inside the context manager, a for loop iterates over the list of tables. Each table is written to a separate sheet in the Excel file with the `DataFrame.to_excel` method provided by the pandas library.
