# **CSV**

Some simple scripts to jog memory when CSV output is required.

# Writing a CSV file
```python
import csv

with open('csv_file.csv', 'w') as fout:
	writer = csv.writer(fout)
	writer.writerow(['Name','Job'])
	writer.writerow(['Satoshi','Saviour'])
	writer.writerow(['Bob','Singer'])
```

# Reading CSV files.
```python
import csv

with open('csv_file.csv', 'r') as fin:
	reader = csv.reader(fin)

	for row in reader:
		print(row)
```

This will read all the rows within that file.

# Reading a csv file and storing contents into python list.

```python
import csv

name = list()
job = list()
...so on...

with open('csv_file.csv', 'r') as fin:
	reader = csv.reader(fin)

	row_numbers = 0 # this is to omit the headers (can be commented out)

	if row_numbers >= 1:
		name.append(row[0]) # or whatever row is desired within the list
		job.append(row[1])

	row_numbers += 1 # this repeats process on next row
```

# These lists can be written, or appended to a new CSV file.

```python
def writes(row_one, row_two):
	with open('csv_file_updated.csv', 'w') as fout:
		writer = csv.writer(fout)
		writer.writerow(name)
		writer.writerow(job)

writes(name, job)
```

This example will now create a new file named `csv_file_updated.csv`. It will omit the headers and write only the data containing names and jobs.


## Operation Modes

*Modes: actions that can be applied to files.*

- `r`: Opens a file for reading only. The file pointer is placed at the beginning of the file. This is the default mode.
- `rb`: Opens a file for reading only in binary format. The file pointer is placed at the beginning of the file. This is the default mode.
- `r+`: Opens a file for both reading and writing. The file pointer will be at the beginning of the file.
- `rb+`: Opens a file for both reading and writing in binary format. The file pointer will be at the beginning of the file.
- `w`: Opens a file for writing only. Overwrites the file if the file exists. If the file does not exist, creates a new file for writing.
- `wb`: Opens a file for writing only in binary format. Overwrites the file if the file exists. If the file does not exist, creates a new file for writing.
- `w+`: Opens a file for both writing and reading. Overwrites the existing file if the file exists. If the file does not exist, creates a new file for reading and writing.
- `wb+`: Opens a file for both writing and reading in binary format. Overwrites the existing file if the file exists. If the file does not exist, creates a new file for reading and writing.
- `a`: Opens a file for appending. The file pointer is at the end of the file if the file exists. That is, the file is in the append mode. If the file does not exist, it creates a new file for writing.
- `ab`: Opens a file for appending in binary format. The file pointer is at the end of the file if the file exists. That is, the file is in the append mode. If the file does not exist, it creates a new file for writing.
- `a+`: Opens a file for both appending and reading. The file pointer is at the end of the file if the file exists. The file opens in the append mode. If the file does not exist, it creates a new file for reading and writing.
- `ab+`: Opens a file for both appending and reading in binary format. The file pointer is at the end of the file if the file exists. The file opens in the append mode. If the file does not exist, it creates a new file for reading and writing.

# Tips and Tricks

`newline= ` This will avoid getting extra newlines, and empty rows between two rows that contain data.

```python

with open('example.csv','a+', newline='') as csv_file):

```
