# find-files-of-variable-fileType
find files of variable fileType
The script will search your machine for files with the specified file type and save the results in a CSV file named by timestamp and file type under /Users/Shared directory.

Keep in mind that searching the entire file system may take a long time, depending on the number of files on your machine. You can limit the search to specific directories by changing the starting path in the "find" command. For example, to search only in the user's home directory, replace the / in find / -type f with the path to the desired directory, like find /Users/username -type f.
