# File Details Filter Script

The *File Details Filter Script* is a versatile Bash utility designed to help users filter, analyze, and display file details stored in CSV format. This script empowers users to extract valuable insights from file metadata based on various filters. Whether you need to search for files of specific sizes, within certain date ranges, or owned by particular users, this script simplifies the process.

## Table of Contents

- [Introduction](#introduction)
- [Usage](#usage)
 - [Options](#options)
 - [Examples](#examples)
- [Functions](#functions)
- [Dependencies](#dependencies)
- [Getting Started](#getting-started)
- [File Details](#file-details)
- [Saving Filtered Results](#saving-filtered-results)
- [Flowchart](#Flowchart)

## Introduction

Managing large datasets of files often requires sophisticated tools to extract useful information. The *File Details Filter Script* streamlines this process by allowing users to filter file information based on various attributes such as size, date, owner, and more. The script is built with flexibility in mind, allowing users to fine-tune their filters and customize their output.

### Usage

To use the script, run it in your terminal with the following syntax:

```bash
./file_details_filter.sh <file_abs_path> [options]
```

## Options

- -s, --size <size>: Show files with a size greater than or equal to the specified size. Sizes can be provided in formats like B, KB, MB, GB, TB (case insensitive).

- -d, --date <date>: Show files with a last modified date matching the specified date in the format YYYY-MM-DD.

- -o, --owner <owner>: Show files owned by the specified owner.

- -e, --extension: Display filenames without extensions.

- -l, --listing: Present file details as a comprehensive listing.

- -h, --help: Display the help message.

### Examples

***1.Display files larger than or equal to 1KB:***

- ```./file_details_filter.sh /path/to/file.csv -s 1KB```

**2.*Filter files with last modified date of '2023-07-15':***

- ```./file_details_filter.sh /path/to/file.csv -d 2023-07-15```

***3.Show files owned by 'user123':***

- ```./file_details_filter.sh /path/to/file.csv -o user123```

***4.Display filenames without extensions:***

- ```./file_details_filter.sh /path/to/file.csv -e```

***5.Generate a detailed file listing:***

- ```./file_details_filter.sh /path/to/file.csv -l```

***6.Display the help message:***

- ```/file_details_filter.sh -h```

### Functions

The script contains several essential functions:

#### `display_help`

- Displays comprehensive usage information and available options. This function is responsible for printing out the script's usage instructions and the description of all available options. It provides users with clear guidance on how to use the script effectively.

#### `human_readable_size_to_bytes`

- Converts human-readable size formats (e.g., 1KB) to bytes. This function takes a human-readable size input, such as "1KB", and converts it into its corresponding value in bytes. It ensures consistent and accurate size conversions, allowing the script to work with different units of size.

#### `bytes_to_human_readable_size`

- Converts bytes to human-readable size formats (e.g., KB, MB). This function performs the reverse of the previous function, taking a size in bytes and converting it into a human-readable format. It ensures that file sizes are presented in a user-friendly way, making them easier to interpret.

#### `filter_file_details`

- Extracts file details from a CSV file and applies filters based on the provided flags. Displays the filtered results. This function is the core of the script's functionality. It reads the file details from a CSV file, processes each entry, and applies the specified filters. It then displays the filtered results, including information like absolute path, filename, file size, last modified date, and owner. 

#### `save_results`

- Persists the filtered results into a timestamped CSV file. This function provides users with the option to save the filtered results to a CSV file. It generates a filename with a timestamp to ensure uniqueness and prevents overwriting existing files. Users can choose to save the filtered results for future reference or analysis.

- Each function contributes to the script's overall functionality, allowing users to efficiently filter and analyze file details according to their requirements.



### Dependencies

*The File Details Filter Script operates independently without any external dependencies. It solely relies on standard Bash capabilities, ensuring straightforward execution across various systems.*

#### Getting Started

- **Ensure the script has execution permissions:**

```chmod +x file_details_filter.sh```

- **2.Run the script with appropriate arguments as outlined in the examples.**

####  File Details

The script expects the CSV file to have the following columns, in order: "File Permissions", "File Owner", "File Size", "Filename", "Absolute Path", "Last Modified". The first row is treated as the header and will be skipped.

#### Saving Filtered Results

After filtering and viewing the results, the script offers the option to save the output to a timestamped CSV file. Users can confirm whether to save the results or not.

### Flowchart

![flowchart.drawio](C:\Users\MY HP\Downloads\flowchart.drawio.svg)





