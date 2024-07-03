# awk_cheat_sheet
# it is scripting language
it is a awk cheat sheet for me

# awk command structure
awk 'BEGIN {..befor script..} /pattern/ {...action...} END {..after script..}' input file address

BEGIN {....} -----> it uses for define variables and initial 

/pattern/ {...action} -----> its the main of awk command 

END {.....} ----> it use for last result operation 

# print list of pid 
![image](https://github.com/ehsanDadashi/awk_cheat_sheet/assets/29996315/bc738888-54db-401a-afa9-9a814c56fad3)

 ps | awk '{print $1}'  

 ![image](https://github.com/ehsanDadashi/awk_cheat_sheet/assets/29996315/6c3cb757-7fd3-493d-9eb8-624b47686633)

# search and replace with awk
consider this example

we have csv file like this 

![image](https://github.com/ehsanDadashi/awk_cheat_sheet/assets/29996315/f5f0ad40-0cb9-401d-9f7c-1295f6157bc6)

we want to replace example.com with sample.com

awk -F, '{gsub(/example.com/,"sample.com",$2); print}' OFS=, email.txt >> sample.txt

now the sample.txt file is like

![image](https://github.com/ehsanDadashi/awk_cheat_sheet/assets/29996315/667ca8f0-7e68-46da-86fd-d09a832e31fe)

# Analyze command awk in search and replace 
# awk -F, '{gsub(/example.com/,"sample.com",$2); print}' OFS=, email.txt >> sample.txt

-F, ----> by default awk use space as delimiter and if you want to change the delimitar to special charecter use -F switch

gsub ---> it's substitution function that replace all pattern selection 

/example.com/ ----> it's a pattern ton search in file

"sample.com" -----> it's a pattern to replace 

$2 ----> it's target field to search and replace in file . in this case first filed is john and second field is john@example.com and ...

print ----> to print output

OFS=, -----> the output delimiter is set to ',' to don't change the output file format .
