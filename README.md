# awk_cheat_sheet
# it is scripting language
it is a awk cheat sheet for me

# awk command structure
awk 'your command you want to do' file_addr

# print list of pid 
![image](https://github.com/ehsanDadashi/awk_cheat_sheet/assets/29996315/bc738888-54db-401a-afa9-9a814c56fad3)

 ps | awk '{print $1}'  

 ![image](https://github.com/ehsanDadashi/awk_cheat_sheet/assets/29996315/6c3cb757-7fd3-493d-9eb8-624b47686633)

# search and replace with awk
consider this example

we have csv file like this 

name,email,age
john,john@example.com,28
doe,doe@example.com,31

we want to replace example.com with sample.com

awk -F, '{gsub(/example.com/,"sample.com",$2); print}' OFS=, email.txt >> sample.txt

now the sample.txt file is like

name,email,age
john,john@sample.com,28
doe,doe@sample.com,31

# Analyze command awk in search and replace 
# awk -F, '{gsub(/example.com/,"sample.com",$2); print}' OFS=, email.txt >> sample.txt

-F, ----> by default awk use space as delimiter and if you want to change the delimitar to special charecter use -F switch

gsub ---> it's substitution function that replace all pattern selection 

/example.com/ ----> it's a pattern ton search in file

"sample.com" -----> it's a pattern to replace 

$2 ----> it's target field to search and replace in file . in this case first filed is john and second field is john@example.com and ...

print ----> to print output

OFS=, -----> the output delimiter is set to ',' to don't change the output file format .
