CAPSTONE 3 
LINUX SHELL SCRIPTING
In this project, I created a bash script that generates a multiplication table for a number entered by the user.

TASK.
1. I created a file on my terminal using the command vim shell
2. I then added the Shebang line: #!/bin/bash. It tells the system that this script should be executed by the Bash shell.  It ensures that the script is interpreted correctly by the appropriate shell.
3. Prompt user for input: read -p "Enter a number for which you want to generate the multiplication table: " number". This line prompts the user to input a number and stores it in the variable number. The -p option is used with the read command to display a prompt message. 
I used the “if” statement as follows

if ! [[ $number =~ ^[0-9]+$ ]]; then
    echo "Error: Invalid input. Please enter a valid number."
    exit 1
Fi

5. This code checks if the input stored in the variable number is a valid number. It uses a regular expression (^[0-9]+$) to ensure that the input consists only of digits (0-9). If the input is not a valid number, it displays an error message and exits the script with a status code of 1.
6.
 
start=1
end=10
These lines define the range of the multiplication table, from 1 to 10. The variables start and end hold the starting and ending values of the range, respectively.

7. echo "Multiplication table for $number:"
echo "---------------------------------"
for (( i=start; i<=end; i++ )); do
    result=$((number * i))
    echo "$number x $i = $result"
done

8. This  code generates the multiplication table for the input number. It prints a header indicating the number for which the table is being generated. Then, it iterates through the range defined by start and end, multiplying each number in the range by the input number ($number). It calculates the result and prints each multiplication operation in the format number x i = result.
9. I then gave the added execution to the file using the chmod command i.e. chmod +x shell
10. I executed the file using the command ./shell
11. The result is as follows
 12. Enter a number for which you want to generate the multiplication table: 5

Multiplication table for 5:

---------------------------------

5 x 1 = 5

5 x 2 = 10

5 x 3 = 15

5 x 4 = 20

5 x 5 = 25

5 x 6 = 30

5 x 7 = 35

5 x 8 = 40

5 x 9 = 45

5 x 10 = 50

13. The complete code for this project is as follows
14.  #!/bin/bash
. # Prompt user to input a number

read -p "Enter a number for which you want to generate the multiplication table: " number

# Check if the input is a valid number

if ! [[ $number =~ ^[0-9]+$ ]]; then

    echo "Error: Invalid input. Please enter a valid number."

    exit 1

fi

# Define the range (from 1 to 10)

start=1

end=10

echo "Multiplication table for $number:"

echo "---------------------------------"


# Loop through the range and print multiplication

for (( i=start; i<=end; i++ )); do

    result=$((number * i))

    echo "$number x $i = $result"

done
