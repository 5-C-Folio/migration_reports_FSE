# Things solved with this migration
* Further alignment with the [FC mapping document](https://github.com/5-C-Folio/Inventory/blob/main/FC%20Marc-to-Instance_Nov20.xlsx). For remaining issues, see below.
* Give Aron breakdown of the unmapped loan types
* 019, 730 were not mapped, 
* Count number of actual identifiers and other ref data occcurences
* Implement item material type (and order type) mappings from https://docs.google.com/spreadsheets/d/1uT6sQ-dyY77BfEDOzC4U4UohnOWcbuXEJ6cHL0SaAXQ/edit#gid=703283660 The Z30 exports should have the code
* Implement Loan type mapping. Example: The Z30 item status for circulation is only unique when accounting for the sublibrary+ the item status ID.  for example. SubLibrary SCNLS and Item status 01 map to "Standard Loan" https://docs.google.com/spreadsheets/d/118rzzMuOQunI4mhUOnYu8bgedmDjM75n2nNZ-EcAErc/edit#gid=489348141

# Things to solve with this migration
* If an item does not have a material type that maps, it can be assigned "unspecified"
# Issues remaining or surfaced as part of this migration
* Records with 583 http://eastlibraries.org/retained-materials url are being duplicated. Discuss, dedupe or move to another level (Holdings, Item)
* Item map not updated with latest work on Item mapping
* 657 Local classification? 
* 
* Count unspecified Material Types
* Discuss item status at separate meeting ...process_stataus (count and discuss)
* ~~Can we use HRID with the 998$b.   For those that have mutilple 998  the first (or last) 998 would be fine.~~
* 77X etc, check the community (leave 776 be) - [Add support for otherRelatedTitles (77X)](https://github.com/FOLIO-FSE/MARC21-To-FOLIO/issues/7)
* [Handle 880 - Alternate Graphic Representation](https://github.com/FOLIO-FSE/MARC21-To-FOLIO/issues/9)
* [Add support for otherRelatedTitles](https://github.com/FOLIO-FSE/MARC21-To-FOLIO/issues/7)
* [Handle 337$a - 338$a mapping when there is no 2-character 338$b set](https://github.com/FOLIO-FSE/MARC21-To-FOLIO/issues/10). This could be handled with adding 338$bs
* [Add support for other 338$2 than rdacarrier](https://github.com/FOLIO-FSE/MARC21-To-FOLIO/issues/11). The script is checking for wether or not this is an issue.