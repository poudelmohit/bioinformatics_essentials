
A dataset example_data.txt is already present in the current working folder.

It looks like:

|         |          |       |             |
|---------|----------|-------|-------------|
| apple   | 10       | 1.2   | USA         |
| banana  | 20       | 0.5   | Mexico      |
| orange  | 30       | 0.8   | Brazil      |
| mango   | 15       | 1.5   | India       |
| kiwi    | 25       | 1.0   | New Zealand |
| grape   | 50       | 2.2   | France      |
| berry   | 40       | 1.8   | USA         |
| papaya  | 12       | 1.3   | India       |
| melon   | 35       | 0.9   | Mexico      |
| pear    | 22       | 1.7   | USA         |


As you can see, this dataset contains fruits name (column 1), quantity in stock(column 2), price per unit (column 3) and country of origin (column 4).

In this tutorial, we will be using this example data, to learn essential awk commands.


### 1. Print the first and second columns (fruit name and quantity)
    awk '{ print $1, $2 }' example_data.txt

### 2. Print the fruit name and country of origin
    awk '{ print $1, $4 }' example_data.txt

### 3. Print the entire line along with the line number
    awk '{ print NR, $0 }' example_data.txt

### 4. Print lines where the fruit comes from the USA
    awk '$4 == "USA"' example_data.txt

### 5. Print lines containing the string "India"
    awk '/India/' example_data.txt

### 6. Multiply the quantity (column 2) by the price (column 3)
    awk '{ print $2 * $3 }' example_data.txt

### 7. Sum up all the quantities (column 2)
    awk '{ sum += $2 } END { print sum }' example_data.txt

### 8. Calculate the average quantity (column 2)
    awk '{ sum += $2; count++ } END { print sum / count }' example_data.txt

### 9. Find the maximum value in column 2 (quantity)
    awk '{ if ($2 > max) max = $2 } END { print max }' example_data.txt

### 10. Find the minimum value in column 2 (quantity)
    awk '{ if ($2 < min || NR == 1) min = $2 } END { print min }' example_data.txt

### 11. Print fruit names with quantity greater than 30
    awk '{ if ($2 > 30) print $1 }' example_data.txt

### 12. Print lines where quantity is greater than 20 and price is less than 2.0
    awk '$2 > 20 && $3 < 2.0' example_data.txt

### 13. Print only the 3rd line
    awk 'NR == 3' example_data.txt

### 14. Skip the first line and print the rest
    awk 'NR > 1' example_data.txt

### 15. Specify a custom field separator (space by default)
    awk -F" " '{ print $1, $4 }' example_data.txt

### 16. Print fields separated by " | "
    awk 'BEGIN { OFS=" | " } { print $1, $2, $3 }' example_data.txt

### 17. Count how many fruits come from the USA
    awk '/USA/ { count++ } END { print count }' example_data.txt

### 18. Count the total number of lines
    awk 'END { print NR }' example_data.txt

### 19. Print even-numbered lines
    awk 'NR % 2 == 0' example_data.txt

### 20. Print odd-numbered lines
    awk 'NR % 2 == 1' example_data.txt

### 21. Replace "USA" with "United States" globally
    awk '{ gsub(/USA/, "United States"); print }' example_data.txt

### 22. Print the length of each fruit name (column 1)
    awk '{ print length($1) }' example_data.txt

### 23. Print lines where the fruit name is longer than 5 characters
    awk 'length($1) > 5' example_data.txt

### 24. Print lines between "banana" and "kiwi"
    awk '/banana/,/kiwi/' example_data.txt

### 25. Perform a case-insensitive search for "india"
    awk 'BEGIN { IGNORECASE=1 } /india/' example_data.txt

### 26. Print the last column (country of origin)
    awk '{ print $NF }' example_data.txt

### 27. Print the last two columns (price and country of origin)
    awk '{ print $(NF-1), $NF }' example_data.txt

### 28. Remove blank lines from the file
    awk 'NF > 0' example_data.txt

### 29. Print lines where the quantity (column 2) is numeric
    awk '$2 ~ /^[0-9]+$/' example_data.txt

### 30. Use a custom variable (min_qty) to filter lines by quantity
    awk -v min_qty=20 '$2 >= min_qty' example_data.txt

### 31. Increment the quantity by 1 for each fruit
    awk '{ $2++; print }' example_data.txt

### 32. Join two files line by line (e.g., data.txt and anotherfile.txt)
    awk 'FNR==NR { a[NR]=$0; next } { print a[FNR], $0 }' example_data.txt anotherfile.txt

### 33. Print lines matching both "USA" and "mango"
    awk '/USA/ && /mango/' example_data.txt

### 34. Remove duplicate lines
    awk '!seen[$0]++' example_data.txt

### 35. Replace "USA" with "United States" only in the 4th column
    awk '{ if ($4 == "USA") $4 = "United States"; print }' example_data.txt

### 36. Count how many fruits come from each country
    awk '{ a[$4]++ } END { for (i in a) print i, a[i] }' example_data.txt

### 37. Align columns nicely with tab-separated fields
    awk '{ printf "%-10s %-10s\n", $1, $2 }' example_data.txt

### 38. Split fields into multiple columns (if column 4 had hyphen-separated values)
    awk '{ n=split($4, arr, "-"); print arr[1], arr[2] }' example_data.txt

### 39. Calculate the running total of the quantity
    awk '{ sum += $2; print sum }' example_data.txt

### 40. Print lines with a specific number of fields (e.g., 4 fields)
    awk 'NF == 4' example_data.txt


