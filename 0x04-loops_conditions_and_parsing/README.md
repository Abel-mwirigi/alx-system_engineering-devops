0x04-loops_conditions_and_parsing
if [[ "$file" == *-* ]]; then

This is an if statement that checks whether the value of the file variable contains a dash "-" in its name. Here's what each part does:

[[ "$file" == *-* ]]: This is a conditional expression. It uses double square brackets [[ ... ]], which is a more powerful conditional construct than single square brackets [ ... ]. Inside the double square brackets, we have:

"$file": This is the value of the file variable, which represents the name of a file in the current directory.

==: This is the equality operator, used to compare the value of "$file" to the pattern *-*.

*-*: This pattern matches any string that contains at least one dash ("-") character. The asterisks (*) are wildcard characters that match zero or more characters, so *-* means "any string that has at least one dash."

If the condition is true (i.e., if the file name contains a dash), then the code block within the if statement is executed.

name_part=$(echo "$file" | cut -d '-' -f 2-)

Inside the if block, we are extracting the part of the file name after the first dash. Here's what each part does:

$(...): This is command substitution. It allows the output of a command (in this case, echo "$file" | cut -d '-' -f 2-) to be assigned to the variable name_part.

echo "$file": This part prints the value of the file variable to standard output.

|: This is a pipe symbol, used to redirect the output of the echo command to the input of the cut command.

cut -d '-' -f 2-: This part uses the cut command to split the input on the dash character (-) and extract the part of the name after the first dash.

-d '-': Specifies that the delimiter used for splitting is the dash character.
-f 2-: Specifies to start from the second field (the part after the first dash) and include all subsequent fields. The 2- indicates "from the second field to the end."
echo "$name_part"