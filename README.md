# migration_five_colleges

# Item migration data manipulation steps
## Convert to utf-8
for i in *;do iconv -t UTF-8//IGNORE "$i" -o "$i".utf;done

## remove subfield indicators ($$) in calnumbers 
find . -name '*.tsv' -exec sed -ri 's/\$\$[a-z]//g' {} \;
