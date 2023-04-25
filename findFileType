#!/bin/bash

# Set the variable fileType to the desired file extension (e.g., txt, jpg, pdf)
variable_fileType="txt"

# Get the current timestamp
timestamp=$(date +%Y%m%d%H%M%S)

# Define the output CSV file path
output_file="/Users/Shared/${timestamp}_${variable_fileType}.csv"

# Add the CSV headers
echo "File Name,File Size,File Creation Date,File Modification Date,Path" > "$output_file"

# Find files and save their information to the CSV file
find / -type f -iname "*.${variable_fileType}" -exec stat -f '%N,%z,%SB,%Sm,%p' -t "%Y-%m-%d %H:%M:%S" {} \; | awk -F/ -v OFS=',' '{
    file_name=$NF
    file_path=""
    for (i=1; i<NF; i++) {
        file_path=file_path"/"$i
    }
    print file_name, $0, file_path
}' >> "$output_file"
