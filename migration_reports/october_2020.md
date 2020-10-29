# Things to solve with this migration
*  if an item does not have a material type that maps, it can be assigned "unspecified"
*  implement item material type (and order type) mappings from https://docs.google.com/spreadsheets/d/1uT6sQ-dyY77BfEDOzC4U4UohnOWcbuXEJ6cHL0SaAXQ/edit#gid=703283660
The Z30 exports should have the code
* Implement Loan type mapping. Example: The Z30 item status for circulation is only unique when accounting for the sublibrary+ the item status ID.  for example.
SubLibrary SCNLS and Item status 01 map to "Standard Loan"
# Issues remaining or surfaced 
* Records with 583 http://eastlibraries.org/retained-materials url are being duplicated. Discuss, dedupe or move to another level (Holdings, Item)
* 
