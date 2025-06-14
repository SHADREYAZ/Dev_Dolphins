%md
# TransactionPatternProject

## Overview
The `TransactionPatternProject` is designed to detect specific patterns in transaction data. The project processes large transaction datasets, splits them into manageable chunks, and applies various pattern detection algorithms. The results are saved in batches for further analysis.

## Project Structure
- **Cell 1: Ingest Transactions**
  - Reads a large transactions CSV file.
  - Splits the data into chunks of 10,000 rows each.
  - Saves each chunk as a separate CSV file.

- **Cell 2: Patterns**
  - Contains functions to detect different patterns in the transaction data:
    - `process_pattern1`: Detects top 1% transactions by amount for each merchant.
    - `process_pattern2`: Detects customer-merchant pairs with specific transaction characteristics.
    - `process_pattern3`: Detects merchants with more male customers than female customers.

- **Cell 3: Save Detections**
  - Saves detection results in batches of 50 rows each.
  - Files are named with a timestamp and batch index.

- **Cell 4: Detect Patterns**
  - Continuously monitors a directory for new transaction data chunks.
  - Processes each chunk to detect patterns.
  - Moves the processed chunk to a different directory.

## Usage
1. **Ingest Transactions**: Run the `ingest_transactions` function to split the large transaction file into smaller chunks.
2. **Detect Patterns**: Run the `detect_patterns` function to process each chunk and detect patterns.
3. **Save Detections**: The `save_detections` function is called within the pattern detection functions to save the results.

## Dependencies
- Python
- Pandas
- PySpark
- Databricks

## Directory Structure
- `/Volumes/workspace/default/myprojectdata/transactions.csv`: Input transactions file.
- `/Volumes/workspace/default/myprojectdata/raw_chunks/`: Directory for storing transaction chunks.
- `/Volumes/workspace/default/myprojectdata/output_bucket/`: Directory for storing detection results.
- `/Volumes/workspace/default/myprojectdata/processed_file/`: Directory for storing processed chunks.
