# CSV Data Cleaning Script

This Python script is designed to clean and preprocess CSV data. It includes functionality for handling missing values, validating email addresses, removing duplicates, and splitting the cleaned data into smaller chunks. The script also logs key actions and errors throughout the process.

## Features

- Prompts the user for an input CSV file and separator.
- Cleans the data by:
  - Removing non-ASCII characters.
  - Handling missing values by logging them and removing the corresponding records.
  - Validating email addresses.
  - Checking for duplicates based on `login_id` and `mail_address`.
- Modifies the `created_at` column to retain only the date (format: `yyyy-mm-dd`).
- Generates a garbage file containing invalid records with specified issues.
- Saves cleaned data to a new CSV file.
- Splits the cleaned output file into a specified number of chunks.
- Uses logging for tracking the script's progress and errors.

## Requirements

- Python 3.x
- pandas library

You can install the required libraries using pip:

```bash
pip install pandas
```

## Usage

1. Place the script in the same directory as your input CSV file.
2. Run the script using Python:

```bash
python revised_split_and_clean.py
```

3. Follow the prompts to enter:
   - The name of the input CSV file (including the file extension).
   - The separator used in the input CSV file.
   - The number of chunks to split the cleaned output file into.

## Input and Output

- **Input File:** A CSV file containing the data to be cleaned.
- **Garbage File:** A CSV file that logs records with missing values or duplicates. It will be named `<input_file>_garbage.csv`.
- **Cleaned Output File:** A CSV file that contains the cleaned and non-duplicate records. It will be named `<input_file>_nonduplicate.csv`.
- **Split Files:** The cleaned output file will be split into the specified number of chunks, named `<input_file>_nonduplicate_<n>.csv`, where `<n>` is the chunk number.

## Example

If your input file is named `china-2020.csv` and you choose a comma `,` as the separator, the output files will be:
- `china-2020_garbage.csv`
- `china-2020_nonduplicate.csv`
- `china-2020_nonduplicate_1.csv`
- `china-2020_nonduplicate_2.csv`
- ...

## Logging

The script logs key actions and errors to the console. You can modify the logging level in the script if needed.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
