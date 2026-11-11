# Step 1: Create the file
touch notes.txt
- Creates an empty file if it doesnot exist

# Step 2: Write the first line using >
echo "1. Linux is an operating system." > notes.txt
echo - prints text
> - Writes to a file, repl;acing existing content
>> - Appends text without deleting existing content

# Step 3: Append lines using >>
echo "2. pwd displays the current directory." >> notes.txt
echo "3. ls lists files and directories." >> notes.txt

# Step 4: Add six more lines
printf '%s\n' \
"4. cd changes the current directory." \
"5. mkdir creates a directory." \
"6. touch creates an empty file." \
"7. cat displays a whole file." \
"8. head shows the first lines." \
"9. tail shows the last lines." >> notes.txt

printf - Prints formatted text


# Step 5: Use tee to display and append the final line
echo "10. tee writes to a file and displays the text." | tee -a notes.txt

tee -a - Displays text and appends it to a file


# Step 6: Read the entire file
cat notes.txt
cat - Displays the entire file

# Step 7: Read the first 2 lines
head -n 2 notes.txt
head - Displays the first 2 lines

# Step 8: Read the last 2 lines
tail -n 2 notes.txt
tail - Displays the last 2 lines

# Step 9: Verify the total number of lines
wc -l notes.txt
wc -l - Count the number of lines