# CoreDataEngineers Linux and Git Project

## Project Overview

This project demonstrates basic Linux system administration, Bash scripting,
ETL processing, cron job scheduling, file management, and Git version control.

The project was completed using an Ubuntu Linux server hosted on Oracle Cloud
Infrastructure (OCI).

---

## Project Structure

```text
linux-git-project/
│
├── raw/
│   └── annual-enterprise-survey-2023-financial-year-provisional.csv
│
├── Transformed/
│   └── 2023_year_finance.csv
│
├── Gold/
│   └── 2023_year_finance.csv
│
├── json_and_CSV/
│   ├── test.csv
│   └── test.json
│
├── etl.sh
├── move_files.sh
├── etl.log
├── .gitignore
└── README.md
````

---

# Task 1: Bash ETL Process

The ETL process consists of three stages:

## Extract

The Bash script downloads the Annual Enterprise Survey CSV dataset from
Statistics New Zealand.

The URL is stored in an environment variable:

```bash
export CSV_URL="..."
```

The downloaded file is saved in the `raw` directory.

The script checks that the download was successful and confirms that the
file exists.

## Transform

The transformation is performed using Bash-compatible Linux command-line
tools.

The `Variable_code` column is renamed to:

```text
variable_code
```

The following columns are selected:

```text
year
Value
Units
variable_code
```

The transformed data is saved as:

```text
Transformed/2023_year_finance.csv
```

## Load

The transformed file is copied into the `Gold` directory:

```text
Gold/2023_year_finance.csv
```

The script confirms that the file has successfully been loaded.

---

# Task 2: Cron Job

The ETL script is scheduled to run every day at midnight.

The cron expression used is:

```text
0 0 * * *
```

The cron job executes:

```text
etl.sh
```

Output and errors are redirected to:

```text
etl.log
```

The cron configuration can be checked with:

```bash
crontab -l
```

---

# Task 3: CSV and JSON File Movement

The `move_files.sh` script searches a source directory for CSV and JSON
files and moves them into:

```text
json_and_CSV/
```

The script uses the Linux `find` command and can handle one or multiple
CSV and JSON files.

Example:

```text
raw/
├── file1.csv
├── file2.csv
├── data1.json
└── data2.json
```

After running the script:

```text
json_and_CSV/
├── file1.csv
├── file2.csv
├── data1.json
└── data2.json
```

---

# Task 4: Git Version Control

Git was used to version all project scripts and documentation.

The repository was initialized using:

```bash
git init
```

Files were staged using:

```bash
git add .
```

Changes were committed using:

```bash
git commit -m "Complete Linux and Git project"
```

The project was then pushed to GitHub.

---

# How to Run the ETL Script

Make the script executable:

```bash
chmod +x etl.sh
```

Run:

```bash
./etl.sh
```

---

# How to Run the File Movement Script

Make the script executable:

```bash
chmod +x move_files.sh
```

Run:

```bash
./move_files.sh
```

---

# Technologies and Tools

* Linux / Ubuntu
* Bash
* curl
* awk
* find
* cron
* Git
* GitHub
* Oracle Cloud Infrastructure

---

# Learning Outcomes

This project demonstrates practical experience with:

* Linux command-line operations
* Bash scripting
* ETL concepts
* File and directory management
* CSV processing
* Environment variables
* Cron scheduling
* Git version control
* GitHub repository management
* Basic cloud infrastructure

```
```
