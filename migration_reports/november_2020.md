- [Things solved with this migration](#things-solved-with-this-migration)
- [Things to solve with this migration](#things-to-solve-with-this-migration)
- [Issues remaining or surfaced as part of this migration](#issues-remaining-or-surfaced-as-part-of-this-migration)
  * [Bibliographic records transformation counters](#bibliographic-records-transformation-counters)
  * [Record status (leader pos 5) - 21 things](#record-status--leader-pos-5----21-things)
  * [Mapped Instance types - 2 things](#mapped-instance-types---2-things)
  * [Mapped identifier types - 13 things](#mapped-identifier-types---13-things)
  * [Incomplete entity mapping (a code issue) - 24 things](#incomplete-entity-mapping--a-code-issue----24-things)
  * [Mapped Contributor name types - 3 things](#mapped-contributor-name-types---3-things)
  * [Mapped contributor types - 132 things](#mapped-contributor-types---132-things)
  * [Instance formats - 48 things](#instance-formats---48-things)
  * [Mapped note types - 53 things](#mapped-note-types---53-things)
  * [Instance format ids handling (337 + 338) - 23 things](#instance-format-ids-handling--337---338----23-things)
  * [Matched Modes of issuance code - 4 things](#matched-modes-of-issuance-code---4-things)
  * [Mapped Alternative title types - 4 things](#mapped-alternative-title-types---4-things)
  * [Mapped electronic access relationships types - 4 things](#mapped-electronic-access-relationships-types---4-things)
  * [Unrecognized language codes in records - 1666 things](#unrecognized-language-codes-in-records---1666-things)
  * [Bib records that failed to parse. - - 16 things](#bib-records-that-failed-to-parse-----16-things)
  * [Records failed to migrate due to Value errors found in Transformation - 186 things](#records-failed-to-migrate-due-to-value-errors-found-in-transformation---186-things)
  * [unspecified Modes of issuance code - 5 things](#unspecified-modes-of-issuance-code---5-things)
  * [Mapped FOLIO fields](#mapped-folio-fields)
  * [Mapped Legacy fields](#mapped-legacy-fields)
- [MFHD records transformation results](#mfhd-records-transformation-results)
  * [MFHD records transformation counters](#mfhd-records-transformation-counters)
  * [Record status (leader pos 5) - 3 things](#record-status--leader-pos-5----3-things)
  * [Leader 06 (Holdings type) - 3 things](#leader-06--holdings-type----3-things)
  * [Undhandled condition defined in mapping rules - 3 things](#undhandled-condition-defined-in-mapping-rules---3-things)
  * [Legacy location codes - 439 things](#legacy-location-codes---439-things)
  * [Mapped Locations - 377 things](#mapped-locations---377-things)
  * [Incomplete entity mapping (a code issue) - 4 things](#incomplete-entity-mapping--a-code-issue----4-things)
  * [Locations - Unmapped legacy codes - 63 things](#locations---unmapped-legacy-codes---63-things)
  * [Mapped electronic access relationships types - 4 things](#mapped-electronic-access-relationships-types---4-things-1)
  * [Mapped note types - 1 things](#mapped-note-types---1-things)
  * [Mapped FOLIO fields](#mapped-folio-fields-1)
  * [Mapped Legacy fields](#mapped-legacy-fields-1)
- [Item records transformation results](#item-records-transformation-results)
  * [Item records transformation counters](#item-records-transformation-counters)
  * [Mapped loan types - 132 things](#mapped-loan-types---132-things)
  * [Mapped Material Types - 41 things](#mapped-material-types---41-things)
  * [Legacy item status - Not mapped - 41 things](#legacy-item-status---not-mapped---41-things)
  * [Field Contents - Z30_ITEM_STATUS - 41 things](#field-contents---z30-item-status---41-things)
  * [Missing location codes - 53 things](#missing-location-codes---53-things)
  * [Circulation notes - 1 things](#circulation-notes---1-things)
  * [Unapped Material Types - 13 things](#unapped-material-types---13-things)
  * [Unmapped loan types - 106 things](#unmapped-loan-types---106-things)
  * [Mapped FOLIO fields](#mapped-folio-fields-2)
  * [Mapped Legacy fields](#mapped-legacy-fields-2)

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
* Map Instance type ids properly.
* 
* Count unspecified Material Types
* Discuss item status at separate meeting ...process_stataus (count and discuss)
* ~~Can we use HRID with the 998$b.   For those that have mutilple 998  the first (or last) 998 would be fine.~~
* 77X etc, check the community (leave 776 be) - [Add support for otherRelatedTitles (77X)](https://github.com/FOLIO-FSE/MARC21-To-FOLIO/issues/7)
* [Handle 880 - Alternate Graphic Representation](https://github.com/FOLIO-FSE/MARC21-To-FOLIO/issues/9)
* [Add support for otherRelatedTitles](https://github.com/FOLIO-FSE/MARC21-To-FOLIO/issues/7)
* [Handle 337$a - 338$a mapping when there is no 2-character 338$b set](https://github.com/FOLIO-FSE/MARC21-To-FOLIO/issues/10). This could be handled with adding 338$bs
* [Add support for other 338$2 than rdacarrier](https://github.com/FOLIO-FSE/MARC21-To-FOLIO/issues/11). The script is checking for wether or not this is an issue.# Bibliographic records transformation results   
Time Run: 2020-11-22T23:04:55.757017   
## Bibliographic records transformation counters   
  Measure   | Count   
   --- | ---:   
Bib records that faile transformation | 186   
Legacy id and 001 not found. Failing record  | 2   
MARC21 Records successfully parsed | 6,262,661   
MARC21 Records with encoding errors - parsing failed | 16   
MARC21 records in file before parsing | 6,262,677   
Number of Instances in map | 7,483,010   
Number of records in file(s) | 6,262,661   
Records without HRID from rules. Created HRID | 6,262,628   
Successfully transformed bibs | 6,262,475   
Total number of Tags processed | 171,319,295   
Value Errors (records that failed transformation | 186   
   
## Record status (leader pos 5) - 21 things   
Measure | Count   
--- | ---:   
  | 12251   
/ | 1   
0 | 1   
1 | 1   
3 | 1   
5 | 1   
8 | 1   
I | 3   
K | 1   
a | 34542   
c | 2816938   
e | 38   
g | 6   
m | 439   
n | 3075135   
o | 5   
p | 278324   
q | 1   
r | 5   
s | 316   
u | 44650   
   
## Mapped Instance types - 2 things   
Measure | Count   
--- | ---:   
text | 71148   
unspecified | 11410184   
   
## Mapped identifier types - 13 things   
Measure | Count   
--- | ---:   
Cancelled GPO item number | 115   
Cancelled System control number | 1407062   
GPO item number | 670072   
ISBN | 3276366   
ISSN | 50001   
Invalid ISBN | 911692   
Invalid ISSN | 13901   
LCCN | 2165204   
Linking ISSN | 9855   
OCLC | 4774160   
Other standard identifier | 2113894   
Publisher or distributor number | 390162   
System control number | 3491883   
   
## Incomplete entity mapping (a code issue) - 24 things   
Measure | Count   
--- | ---:   
020 | 4347895   
028 | 1   
100 | 45   
110 | 8   
130 | 5   
246 | 108   
500 | 45   
504 | 3   
505 | 53   
508 | 1   
511 | 1   
520 | 298   
536 | 371   
538 | 4   
540 | 2   
545 | 1   
546 | 3   
555 | 1   
586 | 1   
590 | 22062   
700 | 21   
710 | 13   
730 | 94   
740 | 2   
   
## Mapped Contributor name types - 3 things   
Measure | Count   
--- | ---:   
Corporate name | 3606854   
Meeting name | 82592   
Personal name | 8628537   
   
## Mapped contributor types - 132 things   
Measure | Count   
--- | ---:   
Actor | 4518   
Adapter | 49   
Addressee | 1   
Animator | 21   
Annotator | 1   
Architect | 2   
Arranger | 4093   
Art director | 6   
Artist | 15   
Artistic director | 33   
Associated name | 15   
Attributed name | 1   
Author | 67269   
Author of afterword, colophon, etc. | 1   
Author of dialog | 1   
Author of introduction, etc. | 48   
Autographer | 8   
Bibliographic antecedent | 32   
Binder | 11   
Binding designer | 7   
Book designer | 27   
Book producer | 6   
Bookjacket designer | 2   
Bookseller | 1   
Broadcaster | 1   
Calligrapher | 4   
Choreographer | 574   
Cinematographer | 271   
Collection registrar | 1   
Collector | 12   
Commentator | 62   
Commentator for written text | 1   
Compiler | 22   
Composer | 22159   
Compositor | 4   
Conceptor | 3   
Conductor | 2195   
Consultant | 11   
Contributor | 12014342   
Copyright holder | 6   
Correspondent | 2   
Costume designer | 189   
Creator | 42   
Curator | 4   
Dancer | 100   
Dedicatee | 2   
Degree supervisor | 1   
Designer | 77   
Director | 3740   
Distributor | 27232   
Donor | 3   
Editor | 138123   
Editor of compilation | 9   
Editor of moving image work | 14   
Electrotyper | 13   
Engraver | 15   
Etcher | 1   
Expert | 2   
Field director | 2   
Film director | 20   
Film distributor | 6   
Film editor | 216   
Film producer | 10   
Filmmaker | 2   
Former owner | 26   
Honoree | 8   
Host | 30   
Host institution | 79   
Illustrator | 182   
Instrumentalist | 1088   
Interviewee | 708   
Interviewer | 279   
Issuing body | 16   
Librettist | 2393   
Lighting designer | 146   
Lithographer | 5   
Lyricist | 539   
Moderator | 1   
Monitor | 4   
Music copyist | 2   
Musical director | 9   
Musician | 32   
Narrator | 870   
Originator | 10   
Other | 76   
Papermaker | 2   
Performer | 13519   
Photographer | 22   
Presenter | 7   
Printer | 120   
Producer | 4610   
Production company | 628   
Production designer | 6   
Production manager | 1   
Production personnel | 48   
Proofreader | 2   
Publisher | 443   
Publishing director | 3   
Puppeteer | 2   
Recording engineer | 35   
Redaktor | 1   
Reporter | 14   
Researcher | 63   
Restager | 2   
Reviewer | 145   
Scenarist | 8   
Screenwriter | 1345   
Set designer | 105   
Signer | 1   
Singer | 758   
Sound designer | 11   
Speaker | 1217   
Sponsor | 23   
Stage director | 2   
Stage manager | 10   
Stereotyper | 5   
Teacher | 12   
Technical director | 37   
Television director | 1   
Television producer | 1   
Transcriber | 73   
Translator | 400   
Typographer | 14   
Videographer | 7   
Voice actor | 455   
Wood engraver | 2   
Writer of accompanying material | 28   
Writer of added commentary | 584   
Writer of added text | 1   
Writer of introduction | 406   
Writer of preface | 148   
Writer of supplementary textual content | 492   
   
## Instance formats - 48 things   
Measure | Count   
--- | ---:   
338$b value CD not found in FOLIO | 1   
338$b value bd not found in FOLIO | 1   
338$b value c not found in FOLIO | 111   
338$b value crc not found in FOLIO | 75   
338$b value n not found in FOLIO | 7   
338$b value nd not found in FOLIO | 2   
338$b value ntc not found in FOLIO | 1   
338$b value rdacarrier not found in FOLIO | 8   
338$b value sg not found in FOLIO | 2   
338$b value v not found in FOLIO | 1   
audio -- audio cartridge set by mapping rules | 87807   
audio -- audio cylinder set by mapping rules | 2   
audio -- audio roll set by mapping rules | 1   
audio -- audiocassette set by mapping rules | 972   
audio -- audiotape reel set by mapping rules | 15   
audio --other set by mapping rules | 11131   
computer -- computer chip cartridge set by mapping rules | 63   
computer -- computer disc cartridge set by mapping rules | 39   
computer -- computer disc set by mapping rules | 3111   
computer -- computer tape reel set by mapping rules | 1   
computer -- online resource set by mapping rules | 1738337   
computer -- other set by mapping rules | 27   
microform -- aperture card set by mapping rules | 3   
microform -- microfiche cassette set by mapping rules | 3   
microform -- microfiche set by mapping rules | 139142   
microform -- microfilm cartridge set by mapping rules | 58   
microform -- microfilm cassette set by mapping rules | 40   
microform -- microfilm reel set by mapping rules | 89827   
microform -- microopaque set by mapping rules | 1221   
projected image -- film cartridge set by mapping rules | 1   
projected image -- film reel set by mapping rules | 420   
projected image -- filmstrip set by mapping rules | 2   
projected image -- other set by mapping rules | 1   
projected image -- overhead transparency set by mapping rules | 1   
projected image -- slide set by mapping rules | 32   
stereographic -- stereograph disc set by mapping rules | 2   
unmediated -- card set by mapping rules | 106   
unmediated -- object set by mapping rules | 407   
unmediated -- other set by mapping rules | 322   
unmediated -- roll set by mapping rules | 3   
unmediated -- sheet set by mapping rules | 16636   
unmediated -- volume set by mapping rules | 3007894   
unspecified -- unspecified set by mapping rules | 4353   
video -- other set by mapping rules | 6275   
video -- video cartridge set by mapping rules | 48   
video -- videocassette set by mapping rules | 13932   
video -- videodisc set by mapping rules | 37496   
video -- videotape reel set by mapping rules | 2   
   
## Mapped note types - 53 things   
Measure | Count   
--- | ---:   
Accessibility note | 1252   
Accumulation and Frequency of Use note | 90   
Action note | 1933266   
Additional Physical Form Available note | 265749   
Awards note | 10775   
Bibliography note | 2285064   
Binding Information note | 159   
Biographical or Historical Data | 4597   
Cartographic Mathematical Data | 13373   
Case File Characteristics note | 1   
Citation / References note | 521507   
Copy and Version Identification note | 85   
Creation / Production Credits note | 56326   
Cumulative Index / Finding Aides notes | 9981   
Data quality note | 10   
Date / time and place of an event note | 191296   
Dissertation note | 114681   
Entity and Attribute Information note | 1   
Exhibitions note | 291   
Formatted Contents Note | 1102451   
Former Title Complexity note | 131   
Funding Information Note | 21844   
General note | 6129186   
Geographic Coverage note | 63   
Immediate Source of Acquisition note | 15826   
Information About Documentation note | 56   
Information related to Copyright Status | 253723   
Issuing Body note | 75093   
Language note | 273235   
Linking Entry Complexity note | 27295   
Local notes | 254191   
Location of Originals / Duplicates note | 200996   
Location of Other Archival Materials note | 511   
Methodology note | 12   
Numbering peculiarities note | 40906   
Original Version note | 202213   
Ownership and Custodial History note | 317   
Participant or Performer note | 280860   
Preferred Citation of Described Materials note | 587   
Publications About Described Materials note | 13   
Reproduction note | 1566830   
Restrictions on Access note | 59969   
Scale note for graphic material | 7   
Source of Description note | 604856   
Study Program Information note | 2084   
Summary | 984065   
Supplement note | 5619   
System Details note | 593202   
Target Audience note | 32391   
Terms Governing Use and Reproduction note | 360264   
Type of computer file or data note | 12910   
Type of report and period covered note | 10593   
With note | 12042   
   
## Instance format ids handling (337 + 338) - 23 things   
Measure | Count   
--- | ---:   
Source ($2) is set to Not set | 94   
Source ($2) is set to a rdacarrier | 1   
Source ($2) is set to carrier | 2491   
Source ($2) is set to dacarrier | 1   
Source ($2) is set to isbdmedia | 1   
Source ($2) is set to local | 2   
Source ($2) is set to obdrager | 1   
Source ($2) is set to rda carrier | 3   
Source ($2) is set to rdacarrie | 2   
Source ($2) is set to rdacarrier | 5228426   
Source ($2) is set to rdacarrier' | 1   
Source ($2) is set to rdacarrier, | 1   
Source ($2) is set to rdacarrier. | 384   
Source ($2) is set to rdacarrier/dan | 3   
Source ($2) is set to rdacarrier/dut | 55   
Source ($2) is set to rdacarrier/eng | 4   
Source ($2) is set to rdacarrier/fre | 16   
Source ($2) is set to rdacarrier/ger | 80   
Source ($2) is set to rdacarrier/spa | 15   
Source ($2) is set to rdacarrier3 | 2   
Source ($2) is set to rdacontent | 104   
Source ($2) is set to rdact | 3   
Source ($2) is set to rdamedia | 64   
   
## Matched Modes of issuance code - 4 things   
Measure | Count   
--- | ---:   
0345dbb6-2c22-40ca-b556-a52a3104d402 - single unit | 6109575   
4f53775c-8a4b-4176-9989-0cbcd18a59a5 - integrating resource | 14105   
612bbd3d-c16b-4bfb-8517-2afafc60204a - unspecified | 24   
926ff973-ee50-4fb6-9e59-80947f5aca69 - serial | 138924   
   
## Mapped Alternative title types - 4 things   
Measure | Count   
--- | ---:   
Former title | 3903   
Other title | 503906   
Uniform title | 1094358   
Variant title | 704773   
   
## Mapped electronic access relationships types - 4 things   
Measure | Count   
--- | ---:   
No information provided | 9476   
Related resource | 96361   
Resource | 335224   
Version of resource | 79577   
   
## Unrecognized language codes in records - 1666 things   
Measure | Count   
--- | ---:   
  | not recognized for ['015190069'] | 2   
  | not recognized for ['015190876'] | 2   
  | not recognized for ['015192514'] | 2   
 fr not recognized for ['001659769'] | 1   
 |  not recognized for ['015188688'] | 2   
 |  not recognized for ['015189465'] | 2   
 |  not recognized for ['015189729'] | 2   
 |  not recognized for ['015189882'] | 2   
 |  not recognized for ['015189914'] | 2   
 |  not recognized for ['015189917'] | 2   
 |  not recognized for ['015190166'] | 2   
 |  not recognized for ['015190196'] | 2   
 |  not recognized for ['015190239'] | 2   
 |  not recognized for ['015190291'] | 2   
 |  not recognized for ['015190329'] | 2   
 |  not recognized for ['015190866'] | 2   
 |  not recognized for ['015190874'] | 2   
 |  not recognized for ['015190956'] | 2   
 |  not recognized for ['015191054'] | 2   
 |  not recognized for ['015191057'] | 2   
 |  not recognized for ['015191059'] | 2   
 |  not recognized for ['015191061'] | 2   
 |  not recognized for ['015191064'] | 2   
 |  not recognized for ['015191068'] | 2   
 |  not recognized for ['015191076'] | 2   
 |  not recognized for ['015191101'] | 2   
 |  not recognized for ['015191104'] | 2   
 |  not recognized for ['015191110'] | 2   
 |  not recognized for ['015191111'] | 2   
 |  not recognized for ['015191151'] | 2   
 |  not recognized for ['015191156'] | 2   
 |  not recognized for ['015191171'] | 2   
 |  not recognized for ['015191186'] | 2   
 |  not recognized for ['015191211'] | 2   
 |  not recognized for ['015191219'] | 2   
 |  not recognized for ['015191331'] | 2   
 |  not recognized for ['015191519'] | 2   
 |  not recognized for ['015191577'] | 2   
 |  not recognized for ['015191644'] | 2   
 |  not recognized for ['015191716'] | 2   
 |  not recognized for ['015191738'] | 2   
 |  not recognized for ['015191774'] | 2   
 |  not recognized for ['015191785'] | 2   
 |  not recognized for ['015191787'] | 2   
 |  not recognized for ['015191800'] | 2   
 |  not recognized for ['015191805'] | 2   
 |  not recognized for ['015191917'] | 2   
 |  not recognized for ['015192217'] | 2   
 |  not recognized for ['015192255'] | 2   
 |  not recognized for ['015192290'] | 2   
 |  not recognized for ['015192313'] | 2   
 |  not recognized for ['015192330'] | 2   
 |  not recognized for ['015192345'] | 2   
 |  not recognized for ['015192384'] | 2   
 |  not recognized for ['015192402'] | 2   
 |  not recognized for ['015192403'] | 2   
 |  not recognized for ['015192414'] | 2   
 |  not recognized for ['015192425'] | 2   
 |  not recognized for ['015192439'] | 2   
 |  not recognized for ['015192446'] | 2   
 |  not recognized for ['015192509'] | 2   
 |  not recognized for ['015192525'] | 2   
 |  not recognized for ['015192612'] | 2   
 |  not recognized for ['015192625'] | 2   
 |  not recognized for ['015192741'] | 2   
 |  not recognized for ['015192772'] | 2   
 |  not recognized for ['015192788'] | 2   
 |  not recognized for ['015192789'] | 2   
 |  not recognized for ['015192790'] | 2   
 |  not recognized for ['015192793'] | 2   
 |  not recognized for ['015192795'] | 2   
 |  not recognized for ['015192796'] | 2   
 |  not recognized for ['015192797'] | 2   
 |  not recognized for ['015192798'] | 2   
 |  not recognized for ['015192799'] | 2   
 |  not recognized for ['015192801'] | 2   
 |  not recognized for ['015192803'] | 2   
 |  not recognized for ['015192807'] | 2   
 |  not recognized for ['015192808'] | 2   
 |  not recognized for ['015192809'] | 2   
 |  not recognized for ['015192813'] | 2   
 |  not recognized for ['015192814'] | 2   
 |  not recognized for ['015192828'] | 2   
 |  not recognized for ['015192829'] | 2   
 |  not recognized for ['015192833'] | 2   
 |  not recognized for ['015192840'] | 2   
 |  not recognized for ['015192841'] | 2   
 |  not recognized for ['015192842'] | 2   
 |  not recognized for ['015192843'] | 2   
 |  not recognized for ['015192844'] | 2   
 |  not recognized for ['015192848'] | 2   
 |  not recognized for ['015192861'] | 2   
 |  not recognized for ['015192867'] | 2   
 |  not recognized for ['015192870'] | 2   
 |  not recognized for ['015192872'] | 2   
 |  not recognized for ['015192894'] | 2   
 |  not recognized for ['015192910'] | 2   
 |  not recognized for ['015192938'] | 2   
 |  not recognized for ['015192957'] | 2   
 |  not recognized for ['015192963'] | 2   
 |  not recognized for ['015192972'] | 2   
 |  not recognized for ['015192997'] | 2   
 |  not recognized for ['015193005'] | 2   
 |  not recognized for ['015193011'] | 2   
 |  not recognized for ['015193036'] | 2   
 |  not recognized for ['015193039'] | 2   
 |  not recognized for ['015193054'] | 2   
 |  not recognized for ['015193061'] | 2   
 |  not recognized for ['015193065'] | 2   
 |  not recognized for ['015193067'] | 2   
 |  not recognized for ['015193070'] | 2   
 |  not recognized for ['015193082'] | 2   
 |  not recognized for ['015193083'] | 2   
 |  not recognized for ['015193084'] | 2   
 |  not recognized for ['015193085'] | 2   
 |  not recognized for ['015193086'] | 2   
 |  not recognized for ['015193091'] | 2   
 |  not recognized for ['015193094'] | 2   
 |  not recognized for ['015193095'] | 2   
 |  not recognized for ['015193107'] | 2   
 |  not recognized for ['015193113'] | 2   
 |  not recognized for ['015193118'] | 2   
 |  not recognized for ['015193181'] | 2   
 |  not recognized for ['015193190'] | 2   
 |  not recognized for ['015195882'] | 2   
 |  not recognized for ['015199087'] | 2   
 |  not recognized for ['015199557'] | 2   
 |  not recognized for ['015199564'] | 2   
 |  not recognized for ['015200057'] | 2   
 |  not recognized for ['015200086'] | 2   
 |  not recognized for ['015200386'] | 2   
 |  not recognized for ['015200387'] | 2   
 |0 not recognized for ['015191562'] | 2   
 |0 not recognized for ['015200576'] | 2   
'un not recognized for ['001755580', '000282997'] | 1   
--- not recognized for ['002376157'] | 1   
--- not recognized for ['015614620'] | 1   
-gx not recognized for ['015614620'] | 1   
.k6 not recognized for ['000186983', '001642312'] | 1   
.n3 not recognized for ['002636608'] | 1   
.t6 not recognized for ['001800374'] | 1   
0   not recognized for ['015199529'] | 2   
0   not recognized for ['015199538'] | 2   
0   not recognized for ['015199575'] | 2   
0 0 not recognized for ['015200093'] | 2   
0 e not recognized for ['001444126'] | 2   
0 e not recognized for ['002881004'] | 2   
0 e not recognized for ['015199867'] | 1   
0 y not recognized for ['015199197'] | 2   
0 y not recognized for ['015199202'] | 2   
0 y not recognized for ['015199211'] | 2   
0 y not recognized for ['015199216'] | 2   
0 y not recognized for ['015199261'] | 2   
0 y not recognized for ['015199292'] | 2   
0 y not recognized for ['015199302'] | 2   
0 y not recognized for ['015199442'] | 2   
0 y not recognized for ['015199558'] | 2   
0 y not recognized for ['015199678'] | 2   
0 y not recognized for ['015199680'] | 1   
0 y not recognized for ['015199714'] | 2   
0 y not recognized for ['015199759'] | 1   
0 y not recognized for ['015200037'] | 2   
0 y not recognized for ['015200416'] | 2   
0 | not recognized for ['015188949'] | 2   
0 | not recognized for ['015190101'] | 2   
0 | not recognized for ['015190343'] | 2   
0 | not recognized for ['015191469'] | 2   
0 | not recognized for ['015191560'] | 2   
0 | not recognized for ['015192331'] | 2   
0 | not recognized for ['015192343'] | 2   
0 | not recognized for ['015192357'] | 2   
0 | not recognized for ['015192677'] | 2   
0 | not recognized for ['015192943'] | 2   
0 | not recognized for ['015192979'] | 2   
0 | not recognized for ['015192986'] | 2   
0 | not recognized for ['015199081'] | 2   
0 | not recognized for ['015199090'] | 2   
0 | not recognized for ['015199095'] | 1   
0 | not recognized for ['015199120'] | 2   
0 | not recognized for ['015199131'] | 1   
0 | not recognized for ['015199973'] | 2   
00  not recognized for ['015199077'] | 1   
00  not recognized for ['015199181'] | 2   
00  not recognized for ['015199296'] | 2   
00  not recognized for ['015199392'] | 2   
001 not recognized for ['015199540'] | 2   
006 not recognized for ['000726955'] | 1   
033 not recognized for ['004423277'] | 1   
0ay not recognized for ['015199515'] | 2   
0dy not recognized for ['015191639'] | 2   
0dy not recognized for ['015191730'] | 2   
0dy not recognized for ['015192184'] | 2   
0dy not recognized for ['015192506'] | 2   
0dy not recognized for ['015192871'] | 2   
0en not recognized for ['000015501'] | 2   
0en not recognized for ['000024096'] | 2   
0en not recognized for ['000031780'] | 2   
0en not recognized for ['000032481'] | 2   
0en not recognized for ['000032592'] | 2   
0en not recognized for ['000068803'] | 2   
0en not recognized for ['000073778'] | 1   
0en not recognized for ['000083638'] | 2   
0en not recognized for ['000112266'] | 2   
0en not recognized for ['000112267'] | 2   
0en not recognized for ['000139917', '001582341'] | 2   
0en not recognized for ['000142006', '001584866'] | 2   
0en not recognized for ['000174801'] | 2   
0en not recognized for ['000197015'] | 2   
0en not recognized for ['000207513'] | 2   
0en not recognized for ['000208084'] | 2   
0en not recognized for ['000217716'] | 2   
0en not recognized for ['000228096'] | 2   
0en not recognized for ['000315579'] | 2   
0en not recognized for ['000366032'] | 2   
0en not recognized for ['000369286'] | 2   
0en not recognized for ['000369295'] | 2   
0en not recognized for ['000386671'] | 2   
0en not recognized for ['000430142', '000799495'] | 2   
0en not recognized for ['000729189'] | 2   
0en not recognized for ['000741835'] | 1   
0en not recognized for ['000751240', '010164250'] | 2   
0en not recognized for ['000803725'] | 2   
0en not recognized for ['000866625', '001436046'] | 2   
0en not recognized for ['001185519', '001920342'] | 2   
0en not recognized for ['001440572'] | 2   
0en not recognized for ['001450513'] | 2   
0en not recognized for ['001450731'] | 2   
0en not recognized for ['001450784'] | 2   
0en not recognized for ['001450843'] | 2   
0en not recognized for ['001450866'] | 2   
0en not recognized for ['001522917'] | 2   
0en not recognized for ['001525621', '000090519'] | 2   
0en not recognized for ['001542983'] | 2   
0en not recognized for ['001559876'] | 2   
0en not recognized for ['001561255'] | 1   
0en not recognized for ['001561792', '000122811'] | 2   
0en not recognized for ['001564213'] | 2   
0en not recognized for ['001565962'] | 2   
0en not recognized for ['001572150'] | 2   
0en not recognized for ['001587376'] | 2   
0en not recognized for ['001598158'] | 2   
0en not recognized for ['001600379'] | 2   
0en not recognized for ['001604525'] | 2   
0en not recognized for ['001629041'] | 2   
0en not recognized for ['001633404'] | 2   
0en not recognized for ['001633410'] | 2   
0en not recognized for ['001633871'] | 2   
0en not recognized for ['001634034'] | 2   
0en not recognized for ['001639749'] | 2   
0en not recognized for ['001640363'] | 2   
0en not recognized for ['001659851'] | 2   
0en not recognized for ['001669926', '002325124'] | 2   
0en not recognized for ['001684457'] | 2   
0en not recognized for ['001703260'] | 2   
0en not recognized for ['001833765'] | 2   
0en not recognized for ['001839635'] | 2   
0en not recognized for ['001875952'] | 2   
0en not recognized for ['001885585'] | 2   
0en not recognized for ['001888862'] | 2   
0en not recognized for ['001904482'] | 2   
0en not recognized for ['001909627'] | 2   
0en not recognized for ['001910016'] | 2   
0en not recognized for ['001925263'] | 1   
0en not recognized for ['001928293', '002878308'] | 2   
0en not recognized for ['001928860', '000799363', '004862038'] | 2   
0en not recognized for ['001929993'] | 2   
0en not recognized for ['001930063', '002896397', '000799487'] | 2   
0en not recognized for ['001946992'] | 2   
0en not recognized for ['001947414'] | 2   
0en not recognized for ['001947947'] | 2   
0en not recognized for ['002246591'] | 2   
0en not recognized for ['002359090'] | 1   
0en not recognized for ['002384844'] | 2   
0en not recognized for ['002390089', '011253231'] | 2   
0en not recognized for ['002653318'] | 2   
0en not recognized for ['002693206'] | 2   
0en not recognized for ['002882074'] | 2   
0en not recognized for ['003165554'] | 2   
0en not recognized for ['003181009'] | 1   
0en not recognized for ['003261309'] | 2   
0en not recognized for ['003264296'] | 2   
0en not recognized for ['003268872'] | 2   
0en not recognized for ['003303578'] | 2   
0en not recognized for ['004860636'] | 2   
0en not recognized for ['004860669'] | 2   
0en not recognized for ['004861275'] | 2   
0en not recognized for ['004861335'] | 2   
0en not recognized for ['004861621'] | 2   
0en not recognized for ['004996143'] | 2   
0en not recognized for ['010340390'] | 2   
0en not recognized for ['010561301', '001926944'] | 2   
0en not recognized for ['010815898'] | 2   
0en not recognized for ['010816618'] | 2   
0en not recognized for ['011178065'] | 2   
0en not recognized for ['011316877'] | 2   
0en not recognized for ['011404747'] | 1   
0en not recognized for ['011405511'] | 2   
0en not recognized for ['011405512'] | 2   
0en not recognized for ['011405538'] | 2   
0en not recognized for ['012463920'] | 2   
0en not recognized for ['015199542'] | 2   
0en not recognized for ['016198321', '001442678'] | 2   
0mu not recognized for ['015199539'] | 1   
0yi not recognized for ['015199402'] | 2   
0yi not recognized for ['015200081'] | 2   
0yi not recognized for ['015200092'] | 2   
0yi not recognized for ['015200095'] | 1   
0yi not recognized for ['015200103'] | 2   
0yi not recognized for ['015200127'] | 1   
0yi not recognized for ['015200145'] | 2   
1 y not recognized for ['015199174'] | 2   
1 y not recognized for ['015199180'] | 2   
1 y not recognized for ['015199288'] | 2   
1 y not recognized for ['015199372'] | 2   
1 y not recognized for ['015199831'] | 1   
1 y not recognized for ['015200117'] | 2   
1 | not recognized for ['015189584'] | 2   
1 | not recognized for ['015189750'] | 2   
1 | not recognized for ['015189878'] | 2   
1 | not recognized for ['015190268'] | 2   
1 | not recognized for ['015191208'] | 2   
1 | not recognized for ['015192385'] | 2   
1 | not recognized for ['015192821'] | 2   
1 | not recognized for ['015192838'] | 2   
1 | not recognized for ['015193125'] | 2   
1 | not recognized for ['015199079'] | 2   
1 | not recognized for ['015199091'] | 2   
1 | not recognized for ['015199094'] | 2   
1 | not recognized for ['015199320'] | 2   
115 not recognized for ['000160477'] | 1   
1at not recognized for ['001511251'] | 1   
1en not recognized for ['000429798'] | 2   
231 not recognized for ['004423277'] | 1   
319 not recognized for ['000160477'] | 1   
3ng not recognized for ['003963994', '001308601', '002107159'] | 1   
445 not recognized for ['000186983', '001642312'] | 1   
519 not recognized for ['002636608'] | 1   
55a not recognized for ['002636608'] | 1   
701 not recognized for ['000160477'] | 1   
aba not recognized for ['003631611'] | 1   
aba not recognized for ['014827287'] | 1   
acr not recognized for ['000476805'] | 1   
adu not recognized for ['011094034'] | 2   
aen not recognized for ['011090357'] | 2   
aen not recognized for ['011090447'] | 2   
aen not recognized for ['011090846'] | 2   
aen not recognized for ['011091056'] | 2   
aen not recognized for ['011091057'] | 2   
aen not recognized for ['011091154'] | 2   
aen not recognized for ['011091296'] | 2   
aen not recognized for ['011091581'] | 2   
aen not recognized for ['011091715'] | 1   
aen not recognized for ['011091832'] | 2   
aen not recognized for ['011091957'] | 2   
aen not recognized for ['011092321'] | 2   
aen not recognized for ['011092538'] | 2   
aen not recognized for ['011092581'] | 2   
age not recognized for ['011091568'] | 2   
age not recognized for ['011093239'] | 2   
age not recognized for ['011093350'] | 2   
age not recognized for ['011093738'] | 2   
agm not recognized for ['002536856'] | 1   
ahm not recognized for ['000690895'] | 1   
ahm not recognized for ['000690896'] | 1   
ahm not recognized for ['000690899'] | 1   
ait not recognized for ['002158102'] | 1   
anc not recognized for ['016037592'] | 1   
ani not recognized for ['000952329'] | 1   
aoa not recognized for ['002542357'] | 1   
arb not recognized for ['000679229'] | 1   
arb not recognized for ['001177155'] | 1   
arb not recognized for ['002869059', '000022060'] | 1   
are not recognized for ['002293008'] | 1   
are not recognized for ['014323359'] | 1   
are not recognized for ['014631949'] | 1   
asa not recognized for ['000624839'] | 1   
ass not recognized for ['001035599'] | 1   
ass not recognized for ['017240964'] | 1   
ayi not recognized for ['015199285'] | 2   
ayi not recognized for ['015200191'] | 2   
ayi not recognized for ['015200674'] | 2   
azh not recognized for ['000472587'] | 1   
azh not recognized for ['001226393'] | 1   
bab not recognized for ['003716143'] | 1   
bag not recognized for ['002693560'] | 1   
bag not recognized for ['017243379'] | 2   
bco not recognized for ['017438686'] | 1   
bda not recognized for ['011093207'] | 2   
bdu not recognized for ['011090390'] | 2   
bdu not recognized for ['011090719'] | 2   
bdu not recognized for ['011090742'] | 2   
bdu not recognized for ['011090936'] | 2   
bdu not recognized for ['011091102'] | 2   
bdu not recognized for ['011091213'] | 2   
bdu not recognized for ['011092153'] | 2   
bdu not recognized for ['011092506'] | 2   
bdu not recognized for ['011092591'] | 2   
bdu not recognized for ['011092871'] | 2   
bdu not recognized for ['011093224'] | 2   
bdu not recognized for ['011093848'] | 2   
bfr not recognized for ['011090774'] | 2   
bfr not recognized for ['011090776'] | 2   
bfr not recognized for ['011090792'] | 2   
bfr not recognized for ['011090892'] | 2   
bfr not recognized for ['011091074'] | 2   
bfr not recognized for ['011091365'] | 2   
bfr not recognized for ['011091402'] | 2   
bfr not recognized for ['011091432'] | 2   
bfr not recognized for ['011091439'] | 2   
bfr not recognized for ['011091648'] | 2   
bfr not recognized for ['011091649'] | 2   
bfr not recognized for ['011091803'] | 2   
bfr not recognized for ['011091951'] | 2   
bfr not recognized for ['011092109'] | 2   
bfr not recognized for ['011092420'] | 2   
bfr not recognized for ['011092732'] | 2   
bfr not recognized for ['011093586'] | 2   
bfr not recognized for ['011093714'] | 2   
bfr not recognized for ['011093717'] | 2   
bfr not recognized for ['011093718'] | 2   
bfr not recognized for ['011093823'] | 2   
bge not recognized for ['011090942'] | 2   
bge not recognized for ['011091726'] | 1   
bge not recognized for ['011091822'] | 2   
bge not recognized for ['011093290'] | 2   
bge not recognized for ['011093420'] | 2   
bge not recognized for ['011093540'] | 2   
bil not recognized for ['017302457'] | 2   
bio not recognized for ['017346840'] | 2   
bit not recognized for ['011091941'] | 2   
bl1 not recognized for ['000186983', '001642312'] | 1   
bsw not recognized for ['011093561'] | 2   
but not recognized for ['017243383'] | 2   
byi not recognized for ['015189511'] | 1   
byi not recognized for ['015191733'] | 2   
byi not recognized for ['015195871'] | 2   
byi not recognized for ['015197183'] | 2   
byi not recognized for ['015199255'] | 1   
byi not recognized for ['015199670'] | 2   
byi not recognized for ['015199870'] | 2   
byi not recognized for ['015200002'] | 2   
byi not recognized for ['015200097'] | 2   
byi not recognized for ['015200395'] | 2   
cae not recognized for ['001501510'] | 1   
can not recognized for ['000660435'] | 1   
can not recognized for ['004309254'] | 1   
can not recognized for ['011052964'] | 1   
cay not recognized for ['000656860', '002162574'] | 1   
cca not recognized for ['003047784'] | 2   
cce not recognized for ['002098367'] | 1   
cdu not recognized for ['011090563'] | 2   
cdu not recognized for ['011092611'] | 2   
cdu not recognized for ['011093319'] | 2   
cdu not recognized for ['011094030'] | 2   
cen not recognized for ['011090343'] | 2   
cen not recognized for ['011090405'] | 2   
cen not recognized for ['011090407'] | 2   
cen not recognized for ['011090538'] | 2   
cen not recognized for ['011090564'] | 2   
cen not recognized for ['011090631'] | 2   
cen not recognized for ['011090632'] | 2   
cen not recognized for ['011090657'] | 2   
cen not recognized for ['011090660'] | 2   
cen not recognized for ['011090973'] | 2   
cen not recognized for ['011090999'] | 2   
cen not recognized for ['011091031'] | 2   
cen not recognized for ['011091034'] | 2   
cen not recognized for ['011091047'] | 2   
cen not recognized for ['011091096'] | 2   
cen not recognized for ['011091181'] | 2   
cen not recognized for ['011091240'] | 1   
cen not recognized for ['011091467'] | 2   
cen not recognized for ['011091481'] | 2   
cen not recognized for ['011091500'] | 2   
cen not recognized for ['011091654'] | 2   
cen not recognized for ['011092162'] | 2   
cen not recognized for ['011092232'] | 2   
cen not recognized for ['011092250'] | 2   
cen not recognized for ['011092299'] | 2   
cen not recognized for ['011092342'] | 2   
cen not recognized for ['011092456'] | 2   
cen not recognized for ['011092469'] | 2   
cen not recognized for ['011092648'] | 2   
cen not recognized for ['011092704'] | 2   
cen not recognized for ['011092834'] | 2   
cen not recognized for ['011093150'] | 2   
cen not recognized for ['011093329'] | 2   
cen not recognized for ['011093510'] | 2   
cen not recognized for ['011093537'] | 2   
cen not recognized for ['011093594'] | 2   
cen not recognized for ['011093605'] | 2   
cen not recognized for ['011093642'] | 2   
cen not recognized for ['011093664'] | 2   
cen not recognized for ['011093759'] | 2   
cen not recognized for ['011093776'] | 2   
cen not recognized for ['011093866'] | 2   
cen not recognized for ['011093927'] | 2   
cen not recognized for ['011094008'] | 2   
cen not recognized for ['011094019'] | 2   
cen not recognized for ['011094037'] | 2   
cen not recognized for ['011094061'] | 2   
cep not recognized for ['000715807'] | 1   
cfr not recognized for ['011090598'] | 2   
cfr not recognized for ['011090729'] | 2   
cfr not recognized for ['011090762'] | 2   
cfr not recognized for ['011090827'] | 2   
cfr not recognized for ['011090902'] | 2   
cfr not recognized for ['011090914'] | 2   
cfr not recognized for ['011091205'] | 2   
cfr not recognized for ['011091233'] | 2   
cfr not recognized for ['011091236'] | 2   
cfr not recognized for ['011091364'] | 2   
cfr not recognized for ['011091438'] | 2   
cfr not recognized for ['011091689'] | 2   
cfr not recognized for ['011091694'] | 2   
cfr not recognized for ['011091802'] | 2   
cfr not recognized for ['011091838'] | 2   
cfr not recognized for ['011092424'] | 2   
cfr not recognized for ['011092425'] | 2   
cfr not recognized for ['011093119'] | 2   
cfr not recognized for ['011093398'] | 2   
cfr not recognized for ['011093975'] | 2   
cge not recognized for ['011090332'] | 2   
cge not recognized for ['011090392'] | 2   
cge not recognized for ['011090781'] | 2   
cge not recognized for ['011090782'] | 2   
cge not recognized for ['011090851'] | 2   
cge not recognized for ['011090857'] | 2   
cge not recognized for ['011091221'] | 2   
cge not recognized for ['011091348'] | 2   
cge not recognized for ['011091424'] | 2   
cge not recognized for ['011091429'] | 2   
cge not recognized for ['011091540'] | 2   
cge not recognized for ['011091567'] | 2   
cge not recognized for ['011091570'] | 2   
cge not recognized for ['011091821'] | 2   
cge not recognized for ['011091855'] | 2   
cge not recognized for ['011091863'] | 2   
cge not recognized for ['011091873'] | 2   
cge not recognized for ['011092002'] | 2   
cge not recognized for ['011092017'] | 2   
cge not recognized for ['011092028'] | 2   
cge not recognized for ['011092055'] | 2   
cge not recognized for ['011092423'] | 2   
cge not recognized for ['011092532'] | 2   
cge not recognized for ['011092550'] | 2   
cge not recognized for ['011092604'] | 2   
cge not recognized for ['011092669'] | 2   
cge not recognized for ['011093023'] | 2   
cge not recognized for ['011093038'] | 2   
cge not recognized for ['011093082'] | 2   
cge not recognized for ['011093846'] | 2   
cge not recognized for ['011094010'] | 2   
chz not recognized for ['000117883'] | 1   
cla not recognized for ['011092348'] | 2   
cmn not recognized for ['013472350'] | 1   
cmn not recognized for ['013472361'] | 1   
cna not recognized for ['001811716'] | 2   
coh not recognized for ['017503400'] | 1   
có not recognized for ['004268177'] | 1   
cpa not recognized for ['002299672'] | 2   
crf not recognized for ['000502846'] | 1   
crf not recognized for ['000810839'] | 1   
crf not recognized for ['002003079'] | 1   
cro not recognized for ['000009017'] | 1   
cro not recognized for ['000013558', '001428087'] | 1   
cro not recognized for ['000017380'] | 1   
cro not recognized for ['000017381'] | 1   
cro not recognized for ['000018090'] | 1   
cro not recognized for ['000035458'] | 1   
cro not recognized for ['000132850'] | 1   
cro not recognized for ['000169233'] | 1   
cro not recognized for ['000190287'] | 1   
cro not recognized for ['000229817'] | 1   
cro not recognized for ['000232964', '002757571'] | 1   
cro not recognized for ['000238058'] | 2   
cro not recognized for ['000253749'] | 1   
cro not recognized for ['000255356', '002924097', '001043937'] | 1   
cro not recognized for ['000257024', '003279528', '001727686'] | 1   
cro not recognized for ['000264743', '002956413'] | 1   
cro not recognized for ['000265724'] | 1   
cro not recognized for ['000277011', '002984811'] | 1   
cro not recognized for ['000294692', '003046615'] | 1   
cro not recognized for ['000326731', '003094418', '000781588', '001102492'] | 1   
cro not recognized for ['000420019'] | 1   
cro not recognized for ['000443903', '001945850', '003122113'] | 1   
cro not recognized for ['000533811'] | 1   
cro not recognized for ['000663205'] | 1   
cro not recognized for ['000720723'] | 1   
cro not recognized for ['000811009'] | 1   
cro not recognized for ['001014484'] | 2   
cro not recognized for ['001063081'] | 1   
cro not recognized for ['001069299', '001757495', '000284761', '000772635', '003024306'] | 1   
cro not recognized for ['001073225'] | 1   
cro not recognized for ['001075878', '000292722', '003042785'] | 1   
cro not recognized for ['001090520', '003079507'] | 1   
cro not recognized for ['001140638', '002992610', '001859117'] | 1   
cro not recognized for ['001232596', '000481584'] | 1   
cro not recognized for ['001232644'] | 1   
cro not recognized for ['001232645'] | 1   
cro not recognized for ['001232646'] | 1   
cro not recognized for ['001419907'] | 1   
cro not recognized for ['001438625', '002869866'] | 1   
cro not recognized for ['001441781', '000870560', '002876603', '004874003'] | 1   
cro not recognized for ['001450067'] | 1   
cro not recognized for ['001683435'] | 1   
cro not recognized for ['001791730'] | 1   
cro not recognized for ['001811696'] | 1   
cro not recognized for ['001932148', '001195878'] | 1   
cro not recognized for ['002409149'] | 1   
cro not recognized for ['002579172'] | 1   
cro not recognized for ['002607409'] | 1   
cro not recognized for ['002618660'] | 1   
cro not recognized for ['002681627'] | 1   
cro not recognized for ['002693736'] | 1   
cro not recognized for ['002714221'] | 1   
cro not recognized for ['002733637'] | 1   
cro not recognized for ['002743638'] | 1   
cro not recognized for ['002749757'] | 1   
cro not recognized for ['002755858'] | 1   
cro not recognized for ['002758481'] | 1   
cro not recognized for ['002773101', '000810687'] | 1   
cro not recognized for ['002782568'] | 1   
cro not recognized for ['002784472'] | 1   
cro not recognized for ['002784628'] | 1   
cro not recognized for ['002788018'] | 1   
cro not recognized for ['002788721'] | 1   
cro not recognized for ['002791107'] | 1   
cro not recognized for ['002793683'] | 1   
cro not recognized for ['002795228'] | 1   
cro not recognized for ['002805052'] | 1   
cro not recognized for ['002822119'] | 1   
cro not recognized for ['002843837', '000866639'] | 1   
cro not recognized for ['002844696'] | 1   
cro not recognized for ['002869440'] | 1   
cro not recognized for ['002874986'] | 1   
cro not recognized for ['002891694'] | 1   
cro not recognized for ['002896000'] | 1   
cro not recognized for ['002899843'] | 1   
cro not recognized for ['002909894'] | 1   
cro not recognized for ['002913870'] | 1   
cro not recognized for ['002915244'] | 1   
cro not recognized for ['002922467'] | 1   
cro not recognized for ['002923232'] | 1   
cro not recognized for ['002924976'] | 1   
cro not recognized for ['002926772'] | 1   
cro not recognized for ['002928270', '000506288'] | 1   
cro not recognized for ['002928274'] | 1   
cro not recognized for ['002935085'] | 1   
cro not recognized for ['002950458'] | 1   
cro not recognized for ['002950994'] | 1   
cro not recognized for ['002954282'] | 1   
cro not recognized for ['002957170'] | 1   
cro not recognized for ['002965201', '001739781'] | 1   
cro not recognized for ['002971571'] | 1   
cro not recognized for ['002971599'] | 1   
cro not recognized for ['002984973'] | 1   
cro not recognized for ['002986963', '001137867'] | 1   
cro not recognized for ['002995184'] | 1   
cro not recognized for ['002998239'] | 1   
cro not recognized for ['003004102'] | 1   
cro not recognized for ['003031179'] | 1   
cro not recognized for ['003037109'] | 1   
cro not recognized for ['003037346'] | 1   
cro not recognized for ['003040763'] | 1   
cro not recognized for ['003041000'] | 1   
cro not recognized for ['003049050'] | 1   
cro not recognized for ['003049913'] | 1   
cro not recognized for ['003063290'] | 1   
cro not recognized for ['003071615'] | 1   
cro not recognized for ['003094914'] | 1   
cro not recognized for ['003105675'] | 1   
cro not recognized for ['003105680'] | 1   
cro not recognized for ['003106347'] | 1   
cro not recognized for ['003115390'] | 1   
cro not recognized for ['003118142'] | 1   
cro not recognized for ['003126050'] | 1   
cro not recognized for ['003265137'] | 1   
cro not recognized for ['003276440'] | 1   
cro not recognized for ['003278831'] | 1   
cro not recognized for ['003291243'] | 1   
cro not recognized for ['003294437', '001086415', '000305097'] | 1   
cro not recognized for ['003326880'] | 2   
cro not recognized for ['003673410'] | 1   
cro not recognized for ['003680197'] | 1   
cro not recognized for ['003826022'] | 1   
cro not recognized for ['003826025'] | 1   
cro not recognized for ['004874289'] | 1   
cro not recognized for ['004955595'] | 1   
cro not recognized for ['016195508', '000487683'] | 1   
cro not recognized for ['016198283'] | 1   
cro not recognized for ['016200586'] | 1   
cro not recognized for ['016201010'] | 1   
cro not recognized for ['016202355'] | 1   
cro not recognized for ['016202422'] | 1   
cse not recognized for ['001476025'] | 1   
csz not recognized for ['001594164', '002588644'] | 1   
cty not recognized for ['015197043'] | 1   
cyi not recognized for ['015199430'] | 2   
cyr not recognized for ['000505529'] | 1   
cyr not recognized for ['015006476'] | 1   
cyr not recognized for ['015074975', '014967084'] | 1   
d | not recognized for ['015190279'] | 2   
d | not recognized for ['015191053'] | 2   
d | not recognized for ['015192964'] | 2   
dag not recognized for ['002162466'] | 1   
dam not recognized for ['002154479'] | 1   
dau not recognized for ['003198224'] | 1   
dca not recognized for ['002143898'] | 2   
dcg not recognized for ['000387123'] | 2   
dcg not recognized for ['000793116'] | 2   
dcg not recognized for ['003585621'] | 2   
dcj not recognized for ['000738771'] | 2   
ddu not recognized for ['017303482'] | 1   
dge not recognized for ['011092060'] | 2   
dge not recognized for ['012510466'] | 1   
dna not recognized for ['001539351'] | 1   
dna not recognized for ['001542421'] | 2   
dna not recognized for ['002098710'] | 2   
dnc not recognized for ['002155911'] | 1   
dng not recognized for ['001992192'] | 1   
dng not recognized for ['002053392'] | 1   
dng not recognized for ['002115127'] | 1   
don not recognized for ['002518785'] | 1   
duc not recognized for ['002588226'] | 1   
dur not recognized for ['000616664'] | 1   
dur not recognized for ['000808702'] | 1   
dur not recognized for ['001990017'] | 1   
dur not recognized for ['003998778'] | 1   
dyi not recognized for ['015189900'] | 2   
dyi not recognized for ['015192936'] | 2   
dyi not recognized for ['015197329'] | 2   
dyi not recognized for ['015199190'] | 2   
dyi not recognized for ['015199192'] | 1   
dyi not recognized for ['015199193'] | 2   
dyi not recognized for ['015199281'] | 2   
dyi not recognized for ['015199305'] | 2   
dyi not recognized for ['015199330'] | 2   
dyi not recognized for ['015199351'] | 2   
dyi not recognized for ['015199595'] | 2   
dyi not recognized for ['015199640'] | 2   
dyi not recognized for ['015199672'] | 2   
dyi not recognized for ['015199825'] | 2   
dyi not recognized for ['015200104'] | 2   
dyi not recognized for ['015200149'] | 2   
dyi not recognized for ['015200154'] | 2   
dyi not recognized for ['015200210'] | 2   
dyi not recognized for ['015200272'] | 2   
e-f not recognized for ['000033086'] | 1   
e-f not recognized for ['002595533'] | 1   
e-g not recognized for ['002406222'] | 1   
ebg not recognized for ['000131168'] | 1   
ebg not recognized for ['000507821'] | 1   
ebg not recognized for ['000811619'] | 1   
ebg not recognized for ['000824608'] | 1   
ebg not recognized for ['002008261'] | 1   
ebg not recognized for ['002100892'] | 1   
ebg not recognized for ['003400159'] | 1   
ebs not recognized for ['017503400'] | 1   
efa not recognized for ['003251773'] | 1   
egg not recognized for ['000212916'] | 1   
egn not recognized for ['000555167'] | 1   
egn not recognized for ['001867673', '001147235', '000381678'] | 1   
egn not recognized for ['002211472'] | 1   
egn not recognized for ['003999612'] | 1   
egr not recognized for ['003183640'] | 1   
ehg not recognized for ['002228435'] | 1   
ekr not recognized for ['002543202'] | 1   
emg not recognized for ['000555687'] | 1   
emg not recognized for ['000603874'] | 1   
emg not recognized for ['000719558'] | 1   
emg not recognized for ['000936915'] | 1   
emg not recognized for ['001543615'] | 1   
emg not recognized for ['001550805'] | 1   
emg not recognized for ['001576020'] | 1   
emg not recognized for ['001667031'] | 1   
emg not recognized for ['001692156'] | 1   
emg not recognized for ['001893764'] | 1   
emg not recognized for ['002048168'] | 1   
emg not recognized for ['002056767'] | 1   
emg not recognized for ['002101100'] | 1   
emg not recognized for ['002156686'] | 1   
emg not recognized for ['002216645'] | 1   
emg not recognized for ['004008434'] | 1   
emg not recognized for ['004447925'] | 1   
emg not recognized for ['010858848'] | 1   
emg not recognized for ['013217267'] | 1   
emn not recognized for ['001970487', '000468917'] | 1   
emn not recognized for ['002663959', '000414183', '001176606', '001910727'] | 1   
enb not recognized for ['003965497'] | 1   
end not recognized for ['000401465'] | 1   
end not recognized for ['000462967', '001963977'] | 1   
end not recognized for ['000533363'] | 1   
end not recognized for ['000550801'] | 1   
end not recognized for ['000583966'] | 1   
end not recognized for ['000690660'] | 1   
end not recognized for ['000703202'] | 1   
end not recognized for ['001154959'] | 1   
end not recognized for ['001723349'] | 1   
end not recognized for ['001731452', '002943259'] | 1   
end not recognized for ['002014235'] | 1   
end not recognized for ['002034299'] | 1   
end not recognized for ['002103031'] | 1   
end not recognized for ['002618233'] | 1   
end not recognized for ['002619214'] | 1   
end not recognized for ['002906828'] | 1   
end not recognized for ['003684034'] | 1   
end not recognized for ['003922951'] | 1   
end not recognized for ['010631148'] | 1   
end not recognized for ['012758831'] | 1   
end not recognized for ['014665433'] | 1   
end not recognized for ['017009155'] | 2   
ene not recognized for ['000542292'] | 1   
enf not recognized for ['000151622'] | 1   
enf not recognized for ['000229365'] | 1   
enf not recognized for ['000367572'] | 1   
enf not recognized for ['000407052', '001902104'] | 1   
enf not recognized for ['000598822'] | 1   
enf not recognized for ['000636940', '004089867', '002139183'] | 1   
enf not recognized for ['000639093'] | 1   
enf not recognized for ['001301202'] | 1   
enf not recognized for ['001327646'] | 1   
enf not recognized for ['001408449'] | 1   
enf not recognized for ['001716659'] | 1   
enf not recognized for ['001797945'] | 1   
enf not recognized for ['001862961'] | 1   
enf not recognized for ['002117968', '004009803'] | 1   
enf not recognized for ['002679749'] | 1   
enf not recognized for ['002864676'] | 1   
enf not recognized for ['002966625'] | 1   
enf not recognized for ['003361084'] | 1   
enf not recognized for ['003844511'] | 1   
enf not recognized for ['003864123'] | 1   
enf not recognized for ['003878718'] | 1   
enf not recognized for ['003998913'] | 1   
enf not recognized for ['003999507'] | 1   
enf not recognized for ['016372801'] | 1   
enf not recognized for ['016960737'] | 1   
enh not recognized for ['004436812', '004318973', '004321947'] | 1   
enh not recognized for ['004940404', '004973596'] | 1   
enh not recognized for ['010473009'] | 1   
enh not recognized for ['010660306'] | 1   
enk not recognized for ['000120405'] | 1   
enk not recognized for ['000556154'] | 1   
enk not recognized for ['000921066'] | 1   
enk not recognized for ['001407404'] | 1   
enk not recognized for ['001559065'] | 1   
enk not recognized for ['002221901', '004269727', '000708763', '001375273'] | 1   
enk not recognized for ['002660840'] | 1   
enk not recognized for ['004225838'] | 1   
enk not recognized for ['004462793'] | 1   
enk not recognized for ['012112614'] | 2   
enk not recognized for ['012295447', '012299502', '012315846'] | 1   
enk not recognized for ['017346755'] | 2   
enl not recognized for ['016285199'] | 1   
enn not recognized for ['001683600', '016479145'] | 1   
eno not recognized for ['016182105'] | 1   
enr not recognized for ['000213983'] | 1   
enr not recognized for ['003673572'] | 1   
ens not recognized for ['002536097'] | 1   
ent not recognized for ['000695709', '001367854'] | 1   
ent not recognized for ['002120610'] | 1   
ent not recognized for ['002147612'] | 1   
ent not recognized for ['002153882'] | 1   
eny not recognized for ['003290445'] | 1   
epa not recognized for ['000761275', '001716502', '000247380'] | 1   
eun not recognized for ['013767082'] | 1   
fen not recognized for ['016998614'] | 2   
fen not recognized for ['017009225'] | 2   
fer not recognized for ['000316620'] | 1   
fer not recognized for ['000661917'] | 1   
fer not recognized for ['000834241'] | 1   
fer not recognized for ['001276583'] | 1   
fer not recognized for ['001408493'] | 1   
fer not recognized for ['001442768', '000025835'] | 1   
fer not recognized for ['002119807'] | 1   
fer not recognized for ['002159774'] | 1   
fer not recognized for ['002169105'] | 1   
fer not recognized for ['003202382'] | 1   
fer not recognized for ['003882739'] | 1   
fer not recognized for ['011251413'] | 1   
fes not recognized for ['017241873'] | 2   
fes not recognized for ['017241874'] | 2   
fes not recognized for ['017241875'] | 2   
fes not recognized for ['017241876'] | 2   
fes not recognized for ['017241877'] | 2   
fes not recognized for ['017241878'] | 2   
fes not recognized for ['017241881'] | 2   
fes not recognized for ['017241886'] | 2   
fes not recognized for ['017241887'] | 2   
fes not recognized for ['017241891'] | 2   
fes not recognized for ['017241892'] | 2   
ffr not recognized for ['001578495'] | 1   
fle not recognized for ['000018191'] | 1   
fle not recognized for ['000164599'] | 1   
fle not recognized for ['000292090'] | 1   
fle not recognized for ['000330594', '001105664'] | 1   
fle not recognized for ['000441988'] | 1   
fle not recognized for ['000501120'] | 1   
fle not recognized for ['000511304'] | 1   
fle not recognized for ['000516966'] | 1   
fle not recognized for ['001014477', '000217223'] | 1   
fle not recognized for ['001272975'] | 1   
fle not recognized for ['001425967', '000011651'] | 1   
fle not recognized for ['001434724'] | 1   
fle not recognized for ['001438989'] | 1   
fle not recognized for ['001446416'] | 1   
fle not recognized for ['001448321', '002889604'] | 1   
fle not recognized for ['001452947'] | 1   
fle not recognized for ['001459855'] | 1   
fle not recognized for ['001487530'] | 1   
fle not recognized for ['001630024', '002654715'] | 1   
fle not recognized for ['001650522'] | 1   
fle not recognized for ['001652484'] | 1   
fle not recognized for ['001678702'] | 1   
fle not recognized for ['001709995'] | 1   
fle not recognized for ['001780200'] | 1   
fle not recognized for ['001810473'] | 2   
fle not recognized for ['001817819'] | 1   
fle not recognized for ['001820662'] | 1   
fle not recognized for ['001843975'] | 1   
fle not recognized for ['001914035'] | 1   
fle not recognized for ['001917498'] | 1   
fle not recognized for ['002166915'] | 1   
fle not recognized for ['002166917'] | 1   
fle not recognized for ['002681445'] | 1   
fle not recognized for ['002691739'] | 1   
fle not recognized for ['002742043'] | 1   
fle not recognized for ['002742248'] | 1   
fle not recognized for ['002742253'] | 1   
fle not recognized for ['002748277'] | 1   
fle not recognized for ['002785401'] | 1   
fle not recognized for ['002809683'] | 1   
fle not recognized for ['002819904'] | 1   
fle not recognized for ['002828879'] | 1   
fle not recognized for ['002835833'] | 1   
fle not recognized for ['002839855'] | 1   
fle not recognized for ['002870548'] | 1   
fle not recognized for ['002896392'] | 1   
fle not recognized for ['002926355'] | 1   
fle not recognized for ['002997584'] | 1   
fle not recognized for ['003003369'] | 1   
fle not recognized for ['003040204'] | 1   
fle not recognized for ['003053540'] | 1   
fle not recognized for ['003066488'] | 1   
fle not recognized for ['003100085'] | 1   
fle not recognized for ['003111345'] | 1   
fle not recognized for ['003113521'] | 1   
fle not recognized for ['003236137'] | 1   
fle not recognized for ['003254723'] | 1   
fle not recognized for ['003332890'] | 1   
fle not recognized for ['003609228'] | 1   
fle not recognized for ['003747338'] | 1   
fle not recognized for ['004094701'] | 1   
fle not recognized for ['010813661'] | 1   
fle not recognized for ['016199671'] | 1   
fle not recognized for ['017300350'] | 1   
fle not recognized for ['017368068'] | 2   
for not recognized for ['000500952'] | 1   
for not recognized for ['000511178'] | 1   
for not recognized for ['002001469'] | 1   
for not recognized for ['002012060'] | 1   
for not recognized for ['002649987'] | 1   
frc not recognized for ['000628049'] | 1   
frc not recognized for ['001271321'] | 1   
frc not recognized for ['001978406'] | 1   
frd not recognized for ['015858720'] | 2   
frn not recognized for ['003957493'] | 1   
fun not recognized for ['017241869'] | 2   
fun not recognized for ['017241922'] | 2   
fun not recognized for ['017241923'] | 2   
g.r not recognized for ['000437725'] | 1   
gas not recognized for ['003122957'] | 1   
gen not recognized for ['001547566'] | 1   
gen not recognized for ['001581853'] | 1   
gen not recognized for ['001684756'] | 1   
gew not recognized for ['000661345'] | 1   
ghm not recognized for ['001905804'] | 1   
ghm not recognized for ['002020852'] | 1   
ghm not recognized for ['015887290'] | 2   
gid not recognized for ['015198276'] | 1   
gke not recognized for ['001864556', '000378748', '001144990', '003002324'] | 1   
gmb not recognized for ['000251645'] | 1   
gri not recognized for ['002793227'] | 1   
grk not recognized for ['000113086', '003780059', '001551790'] | 1   
grk not recognized for ['000145009'] | 1   
grk not recognized for ['000406865', '001169002'] | 1   
grk not recognized for ['000567587'] | 1   
grk not recognized for ['000838847'] | 1   
grk not recognized for ['001194189'] | 1   
grk not recognized for ['001559708'] | 1   
grk not recognized for ['002027693'] | 1   
grk not recognized for ['002126860'] | 1   
grk not recognized for ['003830600'] | 1   
grk not recognized for ['003892396'] | 1   
grk not recognized for ['011246825'] | 1   
grk not recognized for ['012284744', '011268513'] | 1   
grk not recognized for ['014390068'] | 1   
grm not recognized for ['001356717'] | 1   
gue not recognized for ['002379760'] | 1   
guw not recognized for ['015694846'] | 1   
h0y not recognized for ['015199401'] | 2   
hab not recognized for ['015187689'] | 1   
hbe not recognized for ['017504675'] | 1   
hed not recognized for ['000115119'] | 1   
hed not recognized for ['000739792'] | 1   
hed not recognized for ['000938851'] | 1   
hed not recognized for ['001553195'] | 1   
hed not recognized for ['003863234'] | 1   
heg not recognized for ['000625693'] | 1   
hew not recognized for ['000062166'] | 1   
hew not recognized for ['010818052', '011049072'] | 1   
hiu not recognized for ['002222522'] | 1   
hiu not recognized for ['004421140'] | 1   
hkr not recognized for ['002920891'] | 1   
hop not recognized for ['000657192'] | 1   
hop not recognized for ['002162914'] | 1   
hua not recognized for ['015134680'] | 1   
hug not recognized for ['001996495'] | 1   
ico not recognized for ['000437725'] | 1   
ico not recognized for ['001886979', '002340856'] | 1   
ico not recognized for ['010619181'] | 1   
igb not recognized for ['000534329'] | 1   
ijn not recognized for ['011250723', '011252052', '011877323'] | 1   
ila not recognized for ['004239940'] | 1   
ill not recognized for ['003912873'] | 1   
ing not recognized for ['000095583'] | 1   
inu not recognized for ['017153035'] | 2   
ire not recognized for ['000043399'] | 1   
ire not recognized for ['000217304'] | 1   
ire not recognized for ['002763172'] | 1   
isl not recognized for ['017310366'] | 1   
ite not recognized for ['001977075'] | 1   
ite not recognized for ['004224169'] | 1   
iti not recognized for ['001545532'] | 1   
iti not recognized for ['004224169'] | 1   
itl not recognized for ['000233776', '001027901'] | 1   
itl not recognized for ['003172916', '000893407', '000055298'] | 1   
itn not recognized for ['000116697'] | 1   
itr not recognized for ['002121165'] | 1   
jan not recognized for ['000744631'] | 1   
jeb not recognized for ['000633104'] | 1   
jen not recognized for ['004416069'] | 1   
jnp not recognized for ['000589932'] | 1   
jnp not recognized for ['003820647'] | 1   
jpa not recognized for ['000394360'] | 1   
jpa not recognized for ['000670224'] | 1   
jpa not recognized for ['000708737'] | 1   
jpa not recognized for ['000827159'] | 1   
jpa not recognized for ['001995238'] | 1   
jpa not recognized for ['003765037', '002048761', '000547848'] | 1   
jpa not recognized for ['004891772', '000662892'] | 1   
jpg not recognized for ['015705053'] | 1   
jpm not recognized for ['001495557'] | 1   
jrc not recognized for ['002401827', '001484613', '000896214'] | 1   
jun not recognized for ['000159120'] | 1   
kaq not recognized for ['017241490'] | 2   
kaq not recognized for ['017241492'] | 2   
kaq not recognized for ['017241494'] | 2   
kaq not recognized for ['017241496'] | 2   
kpg not recognized for ['017469350'] | 1   
l2. not recognized for ['017472251'] | 1   
l6. not recognized for ['017472251'] | 1   
lag not recognized for ['000228942'] | 1   
lag not recognized for ['000461617'] | 1   
lag not recognized for ['001023729'] | 1   
lag not recognized for ['001219232'] | 1   
lag not recognized for ['001694038'] | 1   
lag not recognized for ['001962762'] | 1   
lag not recognized for ['002068582'] | 1   
lak not recognized for ['017192959'] | 1   
lak not recognized for ['017192960'] | 1   
lak not recognized for ['017192961'] | 1   
lak not recognized for ['017192962'] | 1   
lak not recognized for ['017192963'] | 1   
lak not recognized for ['017192964'] | 1   
lak not recognized for ['017192965'] | 1   
lak not recognized for ['017192966'] | 1   
lak not recognized for ['017192967'] | 1   
lak not recognized for ['017192968'] | 1   
lak not recognized for ['017192969'] | 1   
lak not recognized for ['017192970'] | 1   
lak not recognized for ['017192971'] | 1   
lak not recognized for ['017192972'] | 1   
lak not recognized for ['017192973'] | 1   
lak not recognized for ['017192974'] | 1   
lak not recognized for ['017192975'] | 1   
lak not recognized for ['017192976'] | 1   
lak not recognized for ['017192978'] | 1   
lak not recognized for ['017192979'] | 1   
lak not recognized for ['017192980'] | 1   
lak not recognized for ['017192981'] | 1   
lak not recognized for ['017192982'] | 1   
lak not recognized for ['017192983'] | 1   
lak not recognized for ['017192984'] | 1   
lak not recognized for ['017192985'] | 1   
lak not recognized for ['017192986'] | 1   
lak not recognized for ['017192987'] | 1   
lak not recognized for ['017192988'] | 1   
lar not recognized for ['002473049'] | 1   
lar not recognized for ['015859501'] | 2   
lbe not recognized for ['016276561', '017117478'] | 1   
let not recognized for ['001869258'] | 1   
let not recognized for ['002377417'] | 1   
lis not recognized for ['017476629'] | 1   
lml not recognized for ['014795479'] | 1   
lsk not recognized for ['003328256'] | 1   
lta not recognized for ['014619832'] | 1   
lvt not recognized for ['000570259'] | 1   
mex not recognized for ['011793967'] | 1   
mhe not recognized for ['016949921'] | 1   
mhg not recognized for ['001509479'] | 1   
mhg not recognized for ['001987652'] | 1   
mia not recognized for ['003912873'] | 1   
mnu not recognized for ['015617135'] | 1   
mor not recognized for ['002689295'] | 1   
msh not recognized for ['015186722'] | 1   
msh not recognized for ['015197043'] | 1   
msh not recognized for ['015197049'] | 1   
mym not recognized for ['003194090'] | 1   
n-m not recognized for ['017505475'] | 1   
n-u not recognized for ['001118044', '000345539'] | 1   
n-u not recognized for ['003135048'] | 1   
ned not recognized for ['014322483'] | 1   
neg not recognized for ['000752014'] | 1   
nem not recognized for ['002542500'] | 1   
ng  not recognized for ['002875393'] | 2   
ng  not recognized for ['003110349'] | 2   
ngd not recognized for ['003008312'] | 2   
ngm not recognized for ['002474057'] | 2   
ngm not recognized for ['002594807'] | 2   
ngm not recognized for ['002807462'] | 2   
ngm not recognized for ['002807671'] | 2   
ngm not recognized for ['002877799'] | 2   
ngm not recognized for ['002971865'] | 2   
ngm not recognized for ['002996513'] | 2   
ngm not recognized for ['003067009'] | 2   
ngm not recognized for ['003125238'] | 2   
ngm not recognized for ['016201508'] | 2   
nig not recognized for ['002252592'] | 1   
nkr not recognized for ['002659113'] | 1   
now not recognized for ['014884668'] | 1   
nyb not recognized for ['015186722'] | 1   
nyb not recognized for ['015197043'] | 1   
nyb not recognized for ['015197049'] | 1   
obj not recognized for ['002899091'] | 1   
occ not recognized for ['013451627'] | 1   
occ not recognized for ['013453799'] | 1   
occ not recognized for ['015202241'] | 1   
occ not recognized for ['015202444'] | 1   
och not recognized for ['004981040'] | 1   
ohi not recognized for ['000190035'] | 1   
oli not recognized for ['000167566'] | 1   
ong not recognized for ['000112735'] | 1   
ost not recognized for ['017503400'] | 1   
oth not recognized for ['012462482'] | 1   
oth not recognized for ['014959104'] | 1   
p | not recognized for ['015192231'] | 2   
p | not recognized for ['015192445'] | 2   
p | not recognized for ['015192474'] | 2   
p | not recognized for ['015192850'] | 2   
p | not recognized for ['015192939'] | 2   
pah not recognized for ['000079777'] | 1   
pah not recognized for ['003916177'] | 1   
pah not recognized for ['003948141'] | 1   
pcc not recognized for ['003864540'] | 1   
pcc not recognized for ['011190088'] | 1   
pcc not recognized for ['012186597'] | 2   
pcc not recognized for ['012381976', '012353357'] | 1   
pcc not recognized for ['012488413', '012295431'] | 1   
pcc not recognized for ['016693711'] | 1   
pen not recognized for ['001892108'] | 1   
pen not recognized for ['016998503'] | 2   
pji not recognized for ['011566230'] | 1   
pre not recognized for ['001657920'] | 1   
pre not recognized for ['002057563'] | 1   
pri not recognized for ['017346768'] | 2   
psa not recognized for ['001518340', '000914741'] | 1   
pun not recognized for ['002166445'] | 1   
pun not recognized for ['002183578'] | 1   
pur not recognized for ['002797563'] | 1   
qui not recognized for ['003675373'] | 1   
rak not recognized for ['002777664'] | 1   
rda not recognized for ['015844322'] | 1   
rdi not recognized for ['000437725'] | 1   
reg not recognized for ['001797945'] | 1   
rel not recognized for ['017241861'] | 2   
rel not recognized for ['017241882'] | 2   
rel not recognized for ['017241883'] | 2   
rel not recognized for ['017241888'] | 2   
rel not recognized for ['017241899'] | 2   
rel not recognized for ['017241913'] | 2   
rel not recognized for ['017241916'] | 2   
rel not recognized for ['017241918'] | 2   
res not recognized for ['016187457'] | 1   
ris not recognized for ['001953069'] | 1   
rou not recognized for ['000225431'] | 1   
rua not recognized for ['011126605'] | 1   
rur not recognized for ['000163177', '000973948'] | 1   
rur not recognized for ['000397052'] | 1   
rur not recognized for ['000532872'] | 1   
rur not recognized for ['000614093'] | 1   
rur not recognized for ['000664846'] | 1   
rur not recognized for ['000909059'] | 1   
rur not recognized for ['000982441', '001626841'] | 1   
rur not recognized for ['001508366'] | 1   
rur not recognized for ['001556892'] | 1   
rur not recognized for ['001671802'] | 1   
rur not recognized for ['001992415'] | 1   
rur not recognized for ['002033860'] | 1   
rur not recognized for ['002290247'] | 1   
rur not recognized for ['002400837'] | 1   
rur not recognized for ['002405803'] | 1   
rur not recognized for ['002524436'] | 1   
rur not recognized for ['002655916', '001630622', '000177667', '000984574'] | 1   
rur not recognized for ['003268171'] | 1   
rur not recognized for ['003681884'] | 1   
rur not recognized for ['003694138'] | 1   
rur not recognized for ['004927115', '001157526'] | 1   
rur not recognized for ['013749117'] | 1   
s4r not recognized for ['000913104'] | 1   
sap not recognized for ['000542998'] | 1   
sap not recognized for ['001710468'] | 1   
sca not recognized for ['001544079', '003652532', '000105228'] | 1   
scf not recognized for ['013456944'] | 1   
sen not recognized for ['000490603'] | 1   
ser not recognized for ['000001899', '002806480'] | 1   
ser not recognized for ['000003103'] | 1   
ser not recognized for ['000020639'] | 1   
ser not recognized for ['000157890'] | 1   
ser not recognized for ['000192044'] | 1   
ser not recognized for ['000220382', '002750343'] | 1   
ser not recognized for ['000248621', '016196208'] | 1   
ser not recognized for ['000254166'] | 1   
ser not recognized for ['000255657'] | 1   
ser not recognized for ['000271395'] | 1   
ser not recognized for ['000271689'] | 1   
ser not recognized for ['000339326'] | 1   
ser not recognized for ['000403042'] | 1   
ser not recognized for ['000423196', '001921885'] | 1   
ser not recognized for ['000452103'] | 1   
ser not recognized for ['000495296', '002950753'] | 1   
ser not recognized for ['000510161'] | 1   
ser not recognized for ['000524470'] | 1   
ser not recognized for ['000720723'] | 1   
ser not recognized for ['000728346'] | 1   
ser not recognized for ['000751382'] | 1   
ser not recognized for ['000810681'] | 1   
ser not recognized for ['000872182'] | 1   
ser not recognized for ['000960935'] | 1   
ser not recognized for ['001027363'] | 1   
ser not recognized for ['001034453', '002779346'] | 1   
ser not recognized for ['001049245', '000765560', '000261547', '002946261'] | 1   
ser not recognized for ['001087296'] | 1   
ser not recognized for ['001145679'] | 1   
ser not recognized for ['001186343'] | 1   
ser not recognized for ['001195054'] | 1   
ser not recognized for ['001199421', '001936357', '003004015'] | 1   
ser not recognized for ['001424384'] | 1   
ser not recognized for ['001427737'] | 1   
ser not recognized for ['001683435'] | 2   
ser not recognized for ['001685112'] | 1   
ser not recognized for ['001761015'] | 1   
ser not recognized for ['001773568', '003056934'] | 1   
ser not recognized for ['001811530'] | 1   
ser not recognized for ['001941336', '000439944'] | 1   
ser not recognized for ['002018267'] | 1   
ser not recognized for ['002097853'] | 1   
ser not recognized for ['002524029'] | 1   
ser not recognized for ['002550526'] | 1   
ser not recognized for ['002597858'] | 1   
ser not recognized for ['002734753'] | 1   
ser not recognized for ['002742694'] | 1   
ser not recognized for ['002752876'] | 1   
ser not recognized for ['002753963'] | 1   
ser not recognized for ['002755593'] | 1   
ser not recognized for ['002757897'] | 1   
ser not recognized for ['002757919'] | 1   
ser not recognized for ['002771582', '000238926'] | 1   
ser not recognized for ['002778280', '000242027'] | 1   
ser not recognized for ['002778500'] | 1   
ser not recognized for ['002778845'] | 1   
ser not recognized for ['002789873', '001717172'] | 1   
ser not recognized for ['002809538', '000003515'] | 1   
ser not recognized for ['002812400'] | 1   
ser not recognized for ['002829641'] | 1   
ser not recognized for ['002836006'] | 1   
ser not recognized for ['002911433', '000882117'] | 1   
ser not recognized for ['002915244'] | 1   
ser not recognized for ['002923117'] | 1   
ser not recognized for ['002924172'] | 1   
ser not recognized for ['002925652'] | 1   
ser not recognized for ['002926234'] | 1   
ser not recognized for ['002929983'] | 1   
ser not recognized for ['002939422'] | 1   
ser not recognized for ['002942336'] | 1   
ser not recognized for ['002943360'] | 1   
ser not recognized for ['002945140'] | 1   
ser not recognized for ['002950050'] | 1   
ser not recognized for ['002951347', '000521396'] | 1   
ser not recognized for ['002973713'] | 1   
ser not recognized for ['003001134', '001199121', '001936060'] | 1   
ser not recognized for ['003004014'] | 1   
ser not recognized for ['003004016'] | 1   
ser not recognized for ['003004102'] | 1   
ser not recognized for ['003010566'] | 1   
ser not recognized for ['003030573'] | 1   
ser not recognized for ['003038632'] | 1   
ser not recognized for ['003039489'] | 1   
ser not recognized for ['003039496', '001075276'] | 1   
ser not recognized for ['003039599'] | 1   
ser not recognized for ['003040421'] | 1   
ser not recognized for ['003041333'] | 1   
ser not recognized for ['003046942'] | 1   
ser not recognized for ['003070393', '001204530', '000440592'] | 1   
ser not recognized for ['003070398'] | 1   
ser not recognized for ['003106347'] | 1   
ser not recognized for ['003122169'] | 1   
ser not recognized for ['003122177'] | 1   
ser not recognized for ['003133827'] | 1   
ser not recognized for ['003136735'] | 1   
ser not recognized for ['003259101'] | 1   
ser not recognized for ['003278288', '000884187', '000042791', '000726169'] | 1   
ser not recognized for ['003278779'] | 1   
ser not recognized for ['003375563'] | 1   
ser not recognized for ['003685898'] | 1   
ser not recognized for ['003748658'] | 1   
ser not recognized for ['003748659'] | 1   
ser not recognized for ['003870565'] | 1   
ser not recognized for ['003963365'] | 1   
ser not recognized for ['003999350'] | 1   
ser not recognized for ['004106663'] | 1   
ser not recognized for ['004122085', '000649494', '002153751', '001334789'] | 1   
ser not recognized for ['004296380'] | 1   
ser not recognized for ['016196209'] | 1   
ser not recognized for ['016196975'] | 1   
ser not recognized for ['016196976'] | 1   
ser not recognized for ['016197504'] | 1   
ser not recognized for ['016202127'] | 1   
ser not recognized for ['016206619'] | 2   
ser not recognized for ['017309051'] | 1   
ser not recognized for ['017309055'] | 1   
ser not recognized for ['017309062'] | 1   
ser not recognized for ['017309265'] | 1   
ser not recognized for ['017309266'] | 1   
ser not recognized for ['017309269'] | 1   
ser not recognized for ['017309273'] | 1   
ser not recognized for ['017309275'] | 1   
ser not recognized for ['017309277'] | 1   
sev not recognized for ['017346711'] | 2   
shi not recognized for ['002359462'] | 1   
sia not recognized for ['002522639'] | 1   
sia not recognized for ['002683409'] | 1   
sil not recognized for ['000621540'] | 1   
sil not recognized for ['002121523'] | 1   
sil not recognized for ['011249361'] | 1   
sil not recognized for ['011249368'] | 1   
sil not recognized for ['011249370'] | 1   
sil not recognized for ['011293819'] | 1   
sil not recognized for ['011314625'] | 1   
sil not recognized for ['011335506'] | 1   
sil not recognized for ['011336930'] | 1   
sil not recognized for ['011336932'] | 1   
skv not recognized for ['003962844'] | 1   
snn not recognized for ['002001468'] | 1   
soa not recognized for ['003400159'] | 1   
soa not recognized for ['015825683'] | 1   
spd not recognized for ['003439571'] | 1   
spe not recognized for ['001983405', '000483093'] | 1   
spe not recognized for ['002394818'] | 1   
spe not recognized for ['002906508'] | 1   
spe not recognized for ['004933481'] | 1   
spn not recognized for ['000701791'] | 1   
spn not recognized for ['002601194', '000967671'] | 1   
spq not recognized for ['000905589'] | 1   
sqo not recognized for ['004106294'] | 1   
srb not recognized for ['012465139'] | 1   
src not recognized for ['000061278'] | 1   
src not recognized for ['000975586', '000748966'] | 1   
src not recognized for ['003866964'] | 1   
src not recognized for ['004011758'] | 1   
sre not recognized for ['004106263'] | 1   
ssc not recognized for ['002470696'] | 1   
stk not recognized for ['002194339'] | 1   
sue not recognized for ['002181265'] | 1   
sum not recognized for ['003316078'] | 1   
suo not recognized for ['017292744'] | 2   
swi not recognized for ['017343593'] | 2   
sze not recognized for ['002384256'] | 1   
tau not recognized for ['017243367'] | 2   
the not recognized for ['017241871'] | 2   
the not recognized for ['017241872'] | 2   
thi not recognized for ['000519579', '000813254', '003681023', '001255428'] | 1   
tid not recognized for ['015192224'] | 2   
tot not recognized for ['002143332'] | 1   
tpn not recognized for ['002614639'] | 1   
tro not recognized for ['000162275'] | 1   
tuv not recognized for ['002079428'] | 1   
tz' not recognized for ['017240954'] | 1   
tz' not recognized for ['017240955'] | 1   
tz' not recognized for ['017240956'] | 1   
tz' not recognized for ['017240957'] | 1   
tz' not recognized for ['017240958'] | 1   
u   not recognized for ['003326070'] | 2   
uca not recognized for ['000776302'] | 2   
udt not recognized for ['013982484'] | 1   
udt not recognized for ['013982488'] | 1   
udt not recognized for ['013982491'] | 1   
uka not recognized for ['003629999'] | 1   
ukn not recognized for ['000604393'] | 1   
ung not recognized for ['001445168'] | 1   
ung not recognized for ['003679311'] | 1   
unk not recognized for ['000153854'] | 1   
unk not recognized for ['000549081'] | 1   
unk not recognized for ['000569050'] | 1   
unk not recognized for ['000646304'] | 1   
unk not recognized for ['000788558', '002985079', '000369443', '001136969'] | 1   
unk not recognized for ['001064607'] | 1   
unk not recognized for ['001232647'] | 1   
unk not recognized for ['001776845', '001084853', '003063116'] | 1   
unk not recognized for ['001837245'] | 1   
unk not recognized for ['002435110'] | 1   
unk not recognized for ['002435555'] | 1   
unk not recognized for ['004423387'] | 1   
unk not recognized for ['004977787'] | 1   
unk not recognized for ['010803174'] | 1   
unk not recognized for ['010885180'] | 1   
unk not recognized for ['014211858'] | 1   
unk not recognized for ['014229690'] | 1   
unr not recognized for ['001480551', '000056023', '002393147'] | 1   
unr not recognized for ['002495857'] | 1   
upn not recognized for ['000383756'] | 1   
urk not recognized for ['000697206'] | 1   
urs not recognized for ['002542352'] | 1   
uru not recognized for ['004307725'] | 1   
uru not recognized for ['012949711'] | 1   
v7a not recognized for ['016276561', '017117478'] | 1   
val not recognized for ['002061453'] | 1   
vas not recognized for ['002729939'] | 1   
vit not recognized for ['002007853', '003664800', '001248077', '000507596'] | 1   
wan not recognized for ['003366512'] | 1   
wed not recognized for ['017241860'] | 2   
wed not recognized for ['017241862'] | 2   
wed not recognized for ['017241870'] | 2   
wed not recognized for ['017241907'] | 2   
wit not recognized for ['017346843'] | 2   
wng not recognized for ['001523964'] | 1   
x-- not recognized for ['017505475'] | 1   
yah not recognized for ['016206315'] | 1   
yue not recognized for ['016324336'] | 1   
yug not recognized for ['002734727'] | 1   
zho not recognized for ['013472361'] | 1   
zlm not recognized for ['016949921'] | 1   
zzx not recognized for ['001510427'] | 1   
|   not recognized for ['015189906'] | 2   
|   not recognized for ['015198697'] | 2   
|   not recognized for ['015199761'] | 2   
|   not recognized for ['015199827'] | 2   
|   not recognized for ['015199848'] | 2   
|   not recognized for ['015200389'] | 2   
|   not recognized for ['015200419'] | 2   
|   not recognized for ['015200423'] | 2   
|   not recognized for ['015200443'] | 2   
|   not recognized for ['015200569'] | 2   
|   not recognized for ['015200570'] | 2   
|   not recognized for ['015200586'] | 2   
|   not recognized for ['015200611'] | 2   
|   not recognized for ['015200618'] | 1   
| 0 not recognized for ['015192117'] | 2   
| 0 not recognized for ['015192362'] | 2   
| 0 not recognized for ['015192937'] | 2   
| 0 not recognized for ['015199838'] | 2   
| 1 not recognized for ['015200641'] | 2   
| | not recognized for ['015189319'] | 2   
| | not recognized for ['015191142'] | 2   
| | not recognized for ['015191191'] | 2   
| | not recognized for ['015191220'] | 2   
| | not recognized for ['015191408'] | 2   
| | not recognized for ['015191425'] | 2   
| | not recognized for ['015191567'] | 2   
| | not recognized for ['015191605'] | 2   
| | not recognized for ['015191618'] | 2   
| | not recognized for ['015191636'] | 2   
| | not recognized for ['015191637'] | 2   
| | not recognized for ['015191641'] | 2   
| | not recognized for ['015191655'] | 2   
| | not recognized for ['015191686'] | 2   
| | not recognized for ['015191704'] | 2   
| | not recognized for ['015191737'] | 2   
| | not recognized for ['015191911'] | 2   
| | not recognized for ['015192252'] | 2   
| | not recognized for ['015192279'] | 2   
| | not recognized for ['015192361'] | 2   
| | not recognized for ['015192782'] | 2   
| | not recognized for ['015192810'] | 2   
| | not recognized for ['015192815'] | 2   
| | not recognized for ['015192845'] | 2   
| | not recognized for ['015192901'] | 2   
| | not recognized for ['015192947'] | 2   
| | not recognized for ['015192966'] | 2   
| | not recognized for ['015192967'] | 2   
| | not recognized for ['015192983'] | 2   
| | not recognized for ['015193056'] | 2   
| | not recognized for ['015193080'] | 2   
| | not recognized for ['015193114'] | 2   
| | not recognized for ['015196581'] | 2   
| | not recognized for ['015196587'] | 2   
| | not recognized for ['015196807'] | 2   
| | not recognized for ['015196825'] | 2   
| | not recognized for ['015196952'] | 2   
| | not recognized for ['015197866'] | 2   
| | not recognized for ['015197981'] | 2   
| | not recognized for ['015199098'] | 2   
| | not recognized for ['015199121'] | 2   
| | not recognized for ['015199133'] | 2   
| | not recognized for ['015199241'] | 2   
| | not recognized for ['015199242'] | 2   
| | not recognized for ['015200124'] | 2   
| | not recognized for ['015200385'] | 2   
|0  not recognized for ['015199167'] | 2   
|0  not recognized for ['015199588'] | 2   
|0  not recognized for ['015200035'] | 2   
|00 not recognized for ['015200271'] | 2   
|0d not recognized for ['015200260'] | 2   
|1  not recognized for ['015199758'] | 2   
|by not recognized for ['015200361'] | 2   
|yi not recognized for ['015191371'] | 2   
|yi not recognized for ['015199857'] | 2   
ōle not recognized for ['017191820'] | 2   
ōle not recognized for ['017191821'] | 2   
ōle not recognized for ['017191822'] | 2   
ōle not recognized for ['017191823'] | 2   
ōle not recognized for ['017191824'] | 2   
ōle not recognized for ['017191825'] | 2   
ōle not recognized for ['017191826'] | 2   
ōle not recognized for ['017191827'] | 2   
ōle not recognized for ['017191828'] | 2   
ōle not recognized for ['017191829'] | 2   
ōle not recognized for ['017191830'] | 2   
ōle not recognized for ['017191831'] | 2   
ōle not recognized for ['017191832'] | 2   
ōle not recognized for ['017191833'] | 2   
ōle not recognized for ['017191834'] | 2   
ōle not recognized for ['017191835'] | 2   
ōle not recognized for ['017191836'] | 2   
ōle not recognized for ['017191837'] | 2   
ōle not recognized for ['017191838'] | 2   
ōle not recognized for ['017191839'] | 2   
ōle not recognized for ['017191840'] | 2   
ōle not recognized for ['017191841'] | 2   
ōle not recognized for ['017191842'] | 2   
ōle not recognized for ['017191843'] | 2   
ōle not recognized for ['017191844'] | 2   
ōle not recognized for ['017191845'] | 2   
ōle not recognized for ['017191846'] | 2   
ōle not recognized for ['017191847'] | 2   
ōle not recognized for ['017191848'] | 2   
ōle not recognized for ['017191849'] | 2   
ōle not recognized for ['017191850'] | 2   
ōle not recognized for ['017191851'] | 2   
ōle not recognized for ['017191852'] | 2   
ōle not recognized for ['017191853'] | 2   
ōle not recognized for ['017191854'] | 2   
ōle not recognized for ['017191855'] | 2   
ōle not recognized for ['017191856'] | 2   
ōle not recognized for ['017191857'] | 2   
ōle not recognized for ['017191858'] | 2   
ōle not recognized for ['017191859'] | 2   
ōle not recognized for ['017191860'] | 2   
ōle not recognized for ['017191861'] | 2   
ōle not recognized for ['017191862'] | 2   
ōle not recognized for ['017191863'] | 2   
ōle not recognized for ['017191864'] | 2   
ōle not recognized for ['017191865'] | 2   
ōle not recognized for ['017191866'] | 2   
ōle not recognized for ['017191867'] | 2   
ōle not recognized for ['017191868'] | 2   
ōle not recognized for ['017191869'] | 2   
ōle not recognized for ['017191870'] | 2   
ōle not recognized for ['017191871'] | 2   
ōle not recognized for ['017191872'] | 2   
ōle not recognized for ['017191873'] | 2   
ōle not recognized for ['017191874'] | 2   
ōle not recognized for ['017191875'] | 2   
ōle not recognized for ['017191876'] | 2   
ōle not recognized for ['017191877'] | 2   
ōle not recognized for ['017191878'] | 2   
ōle not recognized for ['017191879'] | 2   
ōle not recognized for ['017191880'] | 2   
ōle not recognized for ['017191881'] | 2   
ōle not recognized for ['017191882'] | 2   
ōle not recognized for ['017191883'] | 2   
ōle not recognized for ['017191884'] | 2   
ōle not recognized for ['017191885'] | 2   
ōle not recognized for ['017191886'] | 2   
ōle not recognized for ['017191887'] | 2   
ōle not recognized for ['017191888'] | 2   
ōle not recognized for ['017191889'] | 2   
ōle not recognized for ['017191890'] | 2   
ōle not recognized for ['017191891'] | 2   
ōle not recognized for ['017191892'] | 2   
ōle not recognized for ['017191893'] | 2   
ōle not recognized for ['017191894'] | 2   
ōle not recognized for ['017191895'] | 2   
ōle not recognized for ['017191896'] | 2   
ōle not recognized for ['017191897'] | 2   
ōle not recognized for ['017191898'] | 2   
ōle not recognized for ['017191899'] | 2   
ōle not recognized for ['017191900'] | 2   
ōle not recognized for ['017191901'] | 2   
ōle not recognized for ['017191902'] | 2   
ōle not recognized for ['017191903'] | 2   
ōle not recognized for ['017191904'] | 2   
ōle not recognized for ['017191905'] | 2   
ōle not recognized for ['017191906'] | 2   
ōle not recognized for ['017191907'] | 2   
ōle not recognized for ['017191908'] | 2   
ōle not recognized for ['017191909'] | 2   
ōle not recognized for ['017191910'] | 2   
ōle not recognized for ['017191911'] | 2   
ōle not recognized for ['017191912'] | 2   
ōle not recognized for ['017191913'] | 2   
ōle not recognized for ['017191914'] | 2   
ōle not recognized for ['017191915'] | 2   
ōle not recognized for ['017191916'] | 2   
ōle not recognized for ['017191917'] | 2   
ōle not recognized for ['017191918'] | 2   
ōle not recognized for ['017191919'] | 2   
ōle not recognized for ['017191920'] | 2   
ōle not recognized for ['017191921'] | 2   
ōle not recognized for ['017191922'] | 2   
ōle not recognized for ['017191923'] | 2   
ōle not recognized for ['017191924'] | 2   
ōle not recognized for ['017191925'] | 2   
ōle not recognized for ['017191926'] | 2   
ōle not recognized for ['017191927'] | 2   
ōle not recognized for ['017191928'] | 2   
ōle not recognized for ['017191929'] | 2   
ōle not recognized for ['017191930'] | 2   
ōle not recognized for ['017191931'] | 2   
ōle not recognized for ['017191932'] | 2   
ōle not recognized for ['017191933'] | 2   
ōle not recognized for ['017191934'] | 2   
ōle not recognized for ['017191935'] | 2   
ōle not recognized for ['017191936'] | 2   
ōle not recognized for ['017191937'] | 2   
ōle not recognized for ['017191938'] | 2   
ōle not recognized for ['017191939'] | 2   
ōle not recognized for ['017191940'] | 2   
ōle not recognized for ['017191941'] | 2   
ōle not recognized for ['017191942'] | 2   
ōle not recognized for ['017191943'] | 2   
ōle not recognized for ['017191944'] | 2   
ōle not recognized for ['017191945'] | 2   
ōle not recognized for ['017191946'] | 2   
ōle not recognized for ['017191947'] | 2   
ōle not recognized for ['017191948'] | 2   
ōle not recognized for ['017191949'] | 2   
ōle not recognized for ['017191950'] | 2   
ōle not recognized for ['017191951'] | 2   
ōle not recognized for ['017191952'] | 2   
ōle not recognized for ['017191953'] | 2   
ōle not recognized for ['017191954'] | 2   
ōle not recognized for ['017191955'] | 2   
ōle not recognized for ['017191956'] | 2   
ℓat not recognized for ['001658908'] | 1   
   
## Bib records that failed to parse. - - 16 things   
Measure | Count   
--- | ---:   
'ascii' codec can't decode byte 0xcc in position 0: ordinal not in range(128) b"04495cgm a2200829Ia 4500005001700000007001000017008004100027028004300068035002000111040012700131041002300258043001200281050002400293245021800317246003900535246003500574264006000609300005700669336005000726337002300776338003000799546005700829511005000886508010500936520069501041500011301736600003901849650004901888650004901937650003601986650002402022650004002046650005302086650005302139650004302192651004402235655002602279655002602305655003302331655003602364655002602400655003702426655004502463655004502508655004802553700002802601700002902629700003502658700003402693700002802727700003502755700003302790700002402823710002002847710005002867710003202917880020002949880006403149880004603213880008403259880002403343880002403367880003103391880003103422880002403453880003103477880003103508880002403539880005103563880003303614998001803647\x1e20200424081037.0\x1evd cvaizq\x1e041013s2004    ko 115            vlkor d\x1e41\x1faBDVD-030\x1fbP\xc5\xadrimi\xc5\x8f Ent'\xc5\x8ft'einm\xc5\x8fnt\xc5\xad\x1e  \x1fa(OCoLC)56957349\x1e  \x1faCOO\x1fbeng\x1fcCOO\x1fdWAU\x1fdOCL\x1fdOCLCA\x1fdOCLCQ\x1fdOCLCA\x1fdOCLCQ\x1fdWAU\x1fdOCLCQ\x1fdOCLCO\x1fdWAU\x1fdOCLCA\x1fdOCLCO\x1fdOCLCQ\x1fdOCLCO\x1fdRCE\x1fdOCLCF\x1fdOCLCO\x1e1 \x1fakor\x1fjeng\x1fjkor\x1fgkor\x1e  \x1faa-ko---\x1e 4\x1faPN1997.2\x1fb.I54 2004\x1e00\x1f6880-01\x1faIn\xc5\x8f kongju /\x1fcchegong, Unikorea ; chejak, Nau P'ill\xc5\xadm ; kih\xc5\x8fek/chejak, Yi Chun-dong ; w\xc5\x8fnan, Kw\xc5\x8fn Hye-w\xc5\x8fn ; sinario, Pak H\xc5\xadng-sik, Song Hye-jin ; p'\xc5\xadrodyus\xc5\x8f, Chin H\xc5\xadi-mun ; kamdok, Pak H\xc5\xadng-sik.\x1e1 \x1fiAlso known as:\x1faMy mother, Mermaid\x1e1 \x1fiAlso known as:\x1faLittle mermaid\x1e\xcc\x86\x1f6880-02\x1fa[S\xc5\x8ful] :\x1fbP\xc5\xadrimi\xc5\x8f Ent'\xc5\x8ft'einm\xc5\x8fnt\xc5\xad,\x1fc2004.\x1e  \x1fa2 videodiscs (115 min.) :\x1fbsound, color ;\x1fc4 3/4 in.\x1e  \x1fatwo-dimensional moving image\x1fbtdi\x1f2rdacontent\x1e  \x1favideo\x1fbv\x1f2rdamedia\x1e  \x1favideodisc\x1fbvd\x1f2rdacarrier\x1e  \x1faIn Korean with optional Korean or English subtitles.\x1e1 \x1f6880-03\x1faCh\xc5\x8fn To-y\xc5\x8fn, Pak Hae-il, Ko Tu-sim.\x1e  \x1f6880-04\x1faCh'wary\xc5\x8fng kamdok, Ch'oe Y\xc5\x8fng-t'aek ; p'y\xc5\x8fnjip, Kim Yang-il ; \xc5\xadmak, Cho S\xc5\x8fng-u (M & F).\x1e  \x1faNa-y\xc5\x8fng works at a post office and is sick and tired of being around her shamefully unyielding mother and her pushover father. The only thing that she can look forward to is her trip abroad in a few days. But one day, her father leaves home without any notice. Her mother doesn't care what happens to him and doesn't care to look for him. Na-y\xc5\x8fng has no choice but to give up her dream trip abroad and to search for her father instead. Once she arrives at her parents' hometown, Na-y\xc5\x8fng falls into the time and place her mother lived in 30 years ago. After falling into this mysterious world, Na-y\xc5\x8fng gets tangled up in the middle of the love that unfolds between her mother and father.\x1e  \x1faSpecial features (not subtitled) on disc 2 include: behind-the-scenes footage, outtakes, and deleted scenes.\x1e10\x1faKw\xc5\x8fn, Hye-w\xc5\x8fn\x1fvFilm adaptations.\x1e 0\x1faMothers and daughters\x1fzKorea (South)\x1fvDrama.\x1e 0\x1faFathers and daughters\x1fzKorea (South)\x1fvDrama.\x1e 0\x1faFamilies\x1fzKorea (South)\x1fvDrama.\x1e 0\x1faTime travel\x1fvDrama.\x1e 7\x1faFamilies.\x1f2fast\x1f0(OCoLC)fst01728849\x1e 7\x1faFathers and daughters.\x1f2fast\x1f0(OCoLC)fst00921890\x1e 7\x1faMothers and daughters.\x1f2fast\x1f0(OCoLC)fst01026997\x1e 7\x1faTime travel.\x1f2fast\x1f0(OCoLC)fst01151176\x1e 7\x1faKorea (South)\x1f2fast\x1f0(OCoLC)fst01206791\x1e 7\x1faFiction films.\x1f2lcgft\x1e 7\x1faFeature films.\x1f2lcgft\x1e 4\x1faFeature films\x1fzKorea (South)\x1e 4\x1faForeign language films\x1fxKorean.\x1e 7\x1faFeature films.\x1f2gsafd\x1e 7\x1faDrama.\x1f2fast\x1f0(OCoLC)fst01423879\x1e 7\x1faFeature films.\x1f2fast\x1f0(OCoLC)fst01710384\x1e 7\x1faFiction films.\x1f2fast\x1f0(OCoLC)fst01710264\x1e 7\x1faFilm adaptations.\x1f2fast\x1f0(OCoLC)fst01710491\x1e1 \x1f6880-05\x1faLee, Joon-dong.\x1e1 \x1f6880-06\x1faKw\xc5\x8fn, Hye-w\xc5\x8fn.\x1e1 \x1f6880-07\x1faPak, H\xc5\xadng-sik,\x1fd1962-\x1e1 \x1f6880-08\x1faSong, Hye-jin,\x1fd1974-\x1e1 \x1f6880-09\x1faChin, H\xc5\xadi-mun.\x1e1 \x1f6880-10\x1faCh\xc5\x8fn, To-y\xc5\x8fn,\x1fd1973-\x1e1 \x1f6880-11\x1faPark, Hae-il,\x1fd1977-\x1e1 \x1f6880-12\x1faKo, Tu-sim.\x1e2 \x1faUniKorea (Firm)\x1e2 \x1f6880-13\x1faP'\xc5\xadrimi\xc5\x8f Ent'\xc5\x8ft'einm\xc5\x8fnt'\xc5\xad (Firm)\x1e2 \x1f6880-14\x1faNau P\xca\xbbill\xc5\xadm (Chu)\x1e00\x1f6245-01/\x1fa\xec\x9d\xb8\xec\x96\xb4\xea\xb3\xb5\xec\xa3\xbc /\x1fc\xec\xa0\x9c\xea\xb3\xb5, Unikorea ; \xec\xa0\x9c\xec\x9e\x91, \xeb\x82\x98\xec\x9a\xb0\xed\x95\x84\xeb\xa6\x84 ; \xea\xb8\xb0\xed\x9a\x8d/\xec\xa0\x9c\xec\x9e\x91, \xec\x9d\xb4\xec\xa4\x80\xeb\x8f\x99 ; \xec\x9b\x90\xec\x95\x88, \xea\xb6\x8c\xed\x98\x9c\xec\x9b\x90 ; \xec\x8b\x9c\xeb\x82\x98\xeb\xa6\xac\xec\x98\xa4, \xeb\xb0\x95\xed\x9d\xa5\xec\x8b\x9d, \xec\x86\xa1\xed\x98\x9c\xec\xa7\x84 ; \xed\x94\x84\xeb\xa1\x9c\xeb\x93\x80\xec\x84\x9c, \xec\xa7\x84\xed\x9d\xac\xeb\xac\xb8 ; \xea\xb0\x90\xeb\x8f\x85, \xeb\xb0\x95\xed\x9d\xa5\xec\x8b\x9d.\x1e 1\x1f6264-02/\x1fa[\xec\x84\x9c\xec\x9a\xb8] :\x1fb\xed\x94\x84\xeb\xa6\xac\xeb\xaf\xb8\xec\x96\xb4\xec\x97\x94\xed\x84\xb0\xed\x85\x8c\xec\x9d\xb8\xeb\xa8\xbc\xed\x8a\xb8,\x1fc2004.\x1e1 \x1f6511-03/\x1fa\xec\xa0\x84\xeb\x8f\x84\xec\x97\xb0, \xeb\xb0\x95\xed\x95\xb4\xec\x9d\xbc, \xea\xb3\xa0\xeb\x91\x90\xec\x8b\xac.\x1e  \x1f6508-04/\x1fa\xec\xb4\xac\xec\x98\x81\xea\xb0\x90\xeb\x8f\x85, \xec\xb5\x9c\xec\x98\x81\xed\x83\x9d ; \xed\x8e\xb8\xec\xa7\x91, \xea\xb9\x80\xec\x96\x91\xec\x9d\xbc ; \xec\x9d\x8c\xec\x95\x85, \xec\xa1\xb0\xec\x84\xb1\xec\x9a\xb0 (M&F).\x1e1 \x1f6700-05/\x1fa\xec\x9d\xb4\xec\xa4\x80\xeb\x8f\x99.\x1e1 \x1f6700-06/\x1fa\xea\xb6\x8c\xed\x98\x9c\xec\x9b\x90.\x1e1 \x1f6700-07/\x1fa\xeb\xb0\x95\xed\x9d\xa5\xec\x8b\x9d,\x1fd1962-\x1e1 \x1f6700-08/\x1fa\xec\x86\xa1\xed\x98\x9c\xec\xa7\x84,\x1fd1974-\x1e1 \x1f6700-09/\x1fa\xec\xa7\x84\xed\x9d\xac\xeb\xac\xb8.\x1e1 \x1f6700-10/\x1fa\xec\xa0\x84\xeb\x8f\x84\xec\x97\xb0,\x1fd1973-\x1e1 \x1f6700-11/\x1fa\xeb\xb0\x95\xed\x95\xb4\xec\x9d\xbc,\x1fd1977-\x1e1 \x1f6700-12/\x1fa\xea\xb3\xa0\xeb\x91\x90\xec\x8b\xac.\x1e2 \x1f6710-13/\x1fa\xed\x94\x84\xeb\xa6\xac\xeb\xaf\xb8\xec\x96\xb4\xec\x97\x94\xed\x84\xb0\xed\x85\x8c\xec\x9d\xb8\xeb\xa8\xbc\xed\x8a\xb8 (Firm)\x1e2 \x1f6710-14/\x1fa\xeb\x82\x98\xec\x9a\xb0\xed\x95\x84\xeb\xa6\x84 (Firm)\x1e  \x1faSM\x1fb004450943\x1e\x1d" | 1   
'ascii' codec can't decode byte 0xcc in position 70: ordinal not in range(128) b'03824cam a2200541Ii 4500005001700000008004100017Es 056800058016002300626020002600649020002300675024001800698035002400716040008000740041001300820050002800833072001300861072001300874100005000887240002600937245003700963264003701000300004501037336002601082336003301108337002801141338002701169520110001196520018202296650005202478650003502530651006602565651004902631651005002680651003302730650005202763650005502815651004102870655003402911655002702945655003902972655005603011655005303067655003903120655004603159655003903205998002403244928001403268\x1e20190919141941.0\x1e171215s2017    gw a     6    000 1 ger d\x1ebeginnt mit einer Bahnfahrt durch die Vororte Hamburgs. Doch an den Ra\xcc\x88ndern der Dinge, die der Protagonistin Nacha begegnen, stehen Verweise auf tiefergehende Informationen. In den Fu\xc3\x9fnoten liegt die Basis fu\xcc\x88r das Hier und Jetzt. Deutsche und argentinische Wirklichkeiten und Vergangenheiten u\xcc\x88berlagern sich. Eine Erza\xcc\x88hlerin auf der Spurensuche nach ihrer argentinischen Familie, die unter der Milita\xcc\x88rdiktatur der Siebzigerjahre gelitten hat. Ein ungewo\xcc\x88hnliches Debu\xcc\x88t!" (Deutschlandfunk, Die besten 7 Bu\xcc\x88cher fu\xcc\x88r junge Leser im Monat November 2017).\x1e7 \x1fa1131273370\x1f2GyFmDB\x1e  \x1fa9783945034675\x1fq(pbk.)\x1e  \x1fa3945034671\x1fq(pbk.)\x1e3 \x1fa9783945034675\x1e  \x1fa(OCoLC)on1017094215\x1e  \x1faOHX\x1fbeng\x1ferda\x1fcOHX\x1fdNDD\x1fdWTU\x1fdOCLCO\x1fdKZS\x1fdOCLCO\x1fdOCLCF\x1fdEYM\x1fdOCLCO\x1fdUtOrBLW\x1e1 \x1fager\x1fhspa\x1e 4\x1faPN6790.A73\x1fbV65615 2017\x1e 7\x1faPN\x1f2lcco\x1e 7\x1faNC\x1f2lcco\x1e1 \x1faVollenweider, Nacha,\x1fd1983-\x1feartist,\x1feauthor.\x1e10\x1faNotas al pie.\x1flGerman\x1e10\x1faFussnoten /\x1fcNacha Vollenweider.\x1e 1\x1faBerlin :\x1fbAvant-Verlag,\x1fc[2017].\x1e  \x1fa205 pages :\x1fball illustrations ;\x1fc23 cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1fastill image\x1fbsti\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e  \x1faFu\xc3\x9fnoten beginnt mit einer Bahnfahrt durch die Vororte Hamburgs, einer Situation, wie sie allta\xcc\x88glicher nicht sein ko\xcc\x88nnte. Doch an den Ra\xcc\x88ndern der Dinge, die die Protagonistin Nacha dabei erlebt, stehen kleine Zahlen, als Verweise auf tiefergehende Informationen. Hier unten, im Reich der Fu\xc3\x9fnoten, spielen sich die Dinge ab, auf denen das, was im Jetzt statt findet, gru\xcc\x88ndet. Deutsche und argentinische Wirklichkeiten und Vergangenheiten u\xcc\x88berlagern sich - so wie die Grundrisspla\xcc\x88ne argentinischer Sta\xcc\x88dte und das Muster der Sitzbezu\xcc\x88ge der Bahn. Der Leser begleitet die Erza\xcc\x88hlerin auf einer Spurensuche nach ihrer argentinischen Familie, die unter der Milita\xcc\x88rdiktatur der Siebzigerjahre gelitten hat. Das wechselvolle Schicksal ihrer Vorfahren ist eng verknu\xcc\x88pft mit ihrem Leben als junge Frau in einer deutschen Gro\xc3\x9fstadt. Nacha Vollenweider entwickelt in ihrem Debu\xcc\x88t eine ungewo\xcc\x88hnliche, faszinierende Art des Erza\xcc\x88hlens: stilistisch ruhig und nu\xcc\x88chtern, aber inhaltlich gro\xc3\x9f und tiefgru\xcc\x88ndig - und verwendet nebenbei - voila\xcc\x80 - ein neues Genre: den Comic-Essay. \x1e  \x1faThe reader accompanies Nacha in pursuit of his Argentinean family, which suffered under the military dictatorship of the 1970s. German and Argentine realities and pasts overlap.\x1e 0\x1faFamily reunification\x1fxComic books, strips, etc.\x1e 0\x1faFamily reunification\x1fxFiction.\x1e 0\x1faArgentina\x1fxPolitics and government\x1fvComic books, strips, etc.\x1e 0\x1faArgentina\x1fxPolitics and government\x1fvFiction.\x1e 0\x1faArgentina\x1fxHistory\x1fvComic books, strips, etc.\x1e 0\x1faArgentina\x1fxHistory\x1fvFiction.\x1e 7\x1faFamily reunification.\x1f2fast\x1f0(OCoLC)fst01893695\x1e 7\x1faPolitics and government.\x1f2fast\x1f0(OCoLC)fst01919741\x1e 7\x1faArgentina.\x1f2fast\x1f0(OCoLC)fst01205614\x1e 7\x1faComics (Graphic works)\x1f2lcgft\x1e 7\x1faGraphic novels.\x1f2lcgft\x1e 4\x1faComics (Graphic works)\x1fzArgentina.\x1e 7\x1faComic books, strips, etc.\x1f2fast\x1f0(OCoLC)fst01423722\x1e 7\x1faComics (Graphic works)\x1f2fast\x1f0(OCoLC)fst01921613\x1e 7\x1faFiction.\x1f2fast\x1f0(OCoLC)fst01423787\x1e 7\x1faGraphic novels.\x1f2fast\x1f0(OCoLC)fst01726630\x1e 7\x1faHistory.\x1f2fast\x1f0(OCoLC)fst01411628\x1e  \x1faUM\x1fb017070238\x1fcBSLW\x1e  \x1faAUTHORITY\x1e\x1d' | 1   
'ascii' codec can't decode byte 0xcc in position 73: ordinal not in range(128) b'03922cam a2200421Ii 4500005001700000008004100017Anb018000058Anb002700238Lat113700265019001501402020001801417020001501435035002401450040005701474050002101531090002201552100003401574245009401608264004501702264001101747300003101758336002601789337002801815338002701843490011201870500009001982504005902072520004202131520033002173520069902503650004303202650004303245650005303288650002903341830009203370998002403462928001403486\x1e20200803112702.0\x1e200624s20202020gw       b    000 0 ger d\x1eetung" heutzutage vor allem mit Bezug auf die eucharistische Anbetung pra\xcc\x88sent. Doch reicht es viel tiefer. Die Schultheologie des Hochmittelalters reflektiert den Themenbereich \x1eetung und Verehrung" bzw. \x1erie und Dulie" in grundsa\xcc\x88tzlicher Weise, indem sie u\xcc\x88ber das Wesen, die verschiedenen Adressaten und die zugrundeliegende Tugend der Verehrung nachdenkt. Diese Debatten werden in der vorliegenden Arbeit nach dogmengeschichtlicher Methode analysiert. Dabei wird der Schwerpunkt auf ausgewa\xcc\x88hlte Autoren und deren thematisch einschla\xcc\x88gige Abhandlungen gelegt (Summa Halensis, Albertus Magnus, Bonaventura, Thomas von Aquin). Zu deren angemessener Kontextualisierung werden nicht nur Autoren wie Roland von Cremona, Richard Fishacre und Robert Kilwardby vergleichend herangezogen, sondern auch die vorausgehenden anbetungstheologischen Entwicklungen der Fru\xcc\x88hscholastik sowie der U\xcc\x88bergangsphase zur Hochscholastik (u.a. bei Wilhelm von Auxerre, Philipp dem Kanzler und Alexander von Hales) beru\xcc\x88cksichtigt. Aus der Erhebung der oftmals nur mikroanalytisch voneinander abzugrenzenden Schritte des Denkweges ergibt sich ein repra\xcc\x88sentatives und facettenreiches Bild der scholastischen Anbetungstheologie, die - trotz mancher eigener Schwa\xcc\x88chen - den heutigen Zugang zum Thema in vielfa\xcc\x88ltiger Weise bereichern kann." --back cover\x1e  \x1fa1156774147\x1e  \x1fa9783402103012\x1e  \x1fa340210301X\x1e  \x1fa(OCoLC)on1159720506\x1e  \x1faUV0\x1fbeng\x1ferda\x1fcUV0\x1fdUV0\x1fdISB\x1fdYDX\x1fdISB\x1fdSNN\x1fdUtOrBLW\x1e 4\x1faBR253\x1fb.O88 2020\x1e  \x1faB720\x1fb.B4 n.f. 85\x1e1 \x1faOtter, Josef,\x1fd1996-\x1feauthor.\x1e10\x1faAdoratio :\x1fbTheologie der Anbetung in der Scholastik des 13. Jahrhunderts /\x1fcJosef Otter.\x1e 1\x1faMu\xcc\x88nster :\x1fbAschendorff Verlag,\x1fc[2020]\x1e 4\x1fc\xc2\xa92020\x1e  \x1faxviii, 581 pages ;\x1fc23 cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e1 \x1faBeitra\xcc\x88ge zur Geschichte der Philosophie und Theologie des Mittelalters,\x1fx0067-5024 ;\x1fvNeue Folge, Band 85\x1e  \x1faOriginally presented as the author\'s thesis (doctoral)--Universita\xcc\x88t Augsburg, 2018.\x1e  \x1faIncludes bibliographical references (pages [567]-581).\x1e  \x1fa"Im kirchlichen Umfeld ist das Thema \x1e3 \x1faThe Society of Oriental Liturgy (SOL) is an international academic society dedicated to the scholarly study of the various Eastern Christian liturgical traditions and related fields in all its aspects and phases, including allied disciplines, and its multiple methodologies. By this it unites scholars from all denominations.\x1e3 \x1faThis volume comprises sixteen selected papers from the Seventh Congress held in July 2018 in Presov, Slovakia, on very diverse traditions: Armenian, Byzantine, Coptic, Ethiopian, Georgian, and Syriac, across a wide range of countries and cultures. The authors study inter alia the texts of liturgical services, the genesis of liturgical books, their translations and adaptations, liturgical theology, architecture, liturgical history, and allusions to liturgy in popular literature. The papers discuss both the historical practice of diverse Eastern Churches and the current situation. Thus, the present collection of articles shows clearly the progress made in an attractive field of research.\x1e 0\x1faChurch history\x1fyMiddle Ages, 600-1500.\x1e 0\x1faEastern churches\x1fxLiturgy\x1fxCongresses.\x1e 0\x1faOriental Orthodox churches\x1fxLiturgy\x1fxCongresses.\x1e 0\x1faPublic worship\x1fxHistory.\x1e 0\x1faBeitra\xcc\x88ge zur Geschichte der Philosophie und Theologie des Mittelalters\x1fvn.F., Bd. 85.\x1e  \x1faSM\x1fb017475728\x1fcBSLW\x1e  \x1faAUTHORITY\x1e\x1d' | 1   
'utf-8' codec can't decode byte 0x91 in position 39: invalid start byte b'01122nam a2200313I  4500005001700000008004100017010001300058019001100071035002000082040003300102043001200135050001600147099001700163099002000180100002900200245011200229264007100341300003400412336002600446337002800472338002700500490008300527650003300610830006900643998002400712998002400736998002400760998002400784\x1e20140804160157.0\x1e770511s1924    nyud          001 0 engm \x1e  \x1fa25000705\x1e  \x1fa241790\x1e  \x1fa(OCoLC)02954525\x1e  \x1faDLC\x1fcPZI\x1fdm.c.\x1fdHAM\x1fdUtOrBLW\x1e  \x1fan-us---\x1e00\x1faHD6508\x1fb.W6\x1e  \x1fa331.3\x1faW836g\x1e  \x1fa338.073\x1faN21\x1fa6\x1e1 \x1faWolman, Leo,\x1fd1890-1961.\x1e14\x1faThe growth of American trade unions, 1880-1923 /\x1fcby Leo Wolman ;... with a foreword by Wesley C. Mitchell.\x1e 1\x1faNew York :\x1fbNational Bureau of Economic Research, i\x91D\x91DInc,\x1fc1924.\x1e  \x1fa170 pages :\x1fbcharts ;\x1fc24 cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e1 \x1faPublications of the National Bureau of Economic Research, Incorporated,\x1fvno. 6\x1e 0\x1faLabor unions\x1fzUnited States.\x1e 0\x1faPublications of the National Bureau of Economic Research\x1fvno. 6.\x1e  \x1faAM\x1fb000422990\x1fcBSLW\x1e  \x1faHA\x1fb000798726\x1fcBSLW\x1e  \x1faMH\x1fb001186833\x1fcBSLW\x1e  \x1faSM\x1fb001921646\x1fcBSLW\x1e\x1d' | 1   
'utf-8' codec can't decode byte 0x91 in position 41: invalid start byte b'01677cam a2200361   4500005001700000008004100017010001300058020001500071035002000086040003800106043001200144050001700156100003400173245013600207264006100343300004500404336002600449337002800475338002700503490007500530504004100605583013800646583013300784583012900917650002601046650003801072700005101110710004201161830004001203998002401243998002401267998002401291\x1e20140804131636.0\x1e700807s1970    nyua     bs   001 0 eng  \x1e  \x1fa78085410\x1e  \x1fa0870142100\x1e  \x1fa(OCoLC)00089067\x1e  \x1faDLC\x1fcDLC\x1fdm.c.\x1fdOCL\x1fdHAM\x1fdUtOrBLW\x1e  \x1fan-us---\x1e00\x1faHG538\x1fb.F863\x1e1 \x1faFriedman, Milton,\x1fd1912-2006.\x1e10\x1faMonetary statistics of the United States;\x91D :\x1fbestimates \x91D, sources, methods /\x1fc[by] Milton Friedman [and] Anna Jacobson Schwartz.\x1e 1\x1faNew York :\x1fbNational Bureau of Economic Research,\x1fc1970.\x1e  \x1faxx, 629 pages :\x1fbillustrations ;\x1fc24 cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e1 \x1faNational Bureau of Economic Research.\x1ftStudies in business cycles,\x1fv20\x1e  \x1faIncludes bibliographical references.\x1e1 \x1facommitted to retain\x1fc20160630\x1fd20310630\x1ffEAST\x1fuhttp://eastlibraries.org/retained-materials\x1fzAmherst College copy: EAST commitment\x1f5MA\x1e1 \x1facommitted to retain\x1fc20160630\x1fd20310630\x1ffEAST\x1fuhttp://eastlibraries.org/retained-materials\x1fzHampshire copy: EAST commitment\x1f5MAH\x1e1 \x1facommitted to retain\x1fc20160630\x1fd20310630\x1ffEAST\x1fuhttp://eastlibraries.org/retained-materials\x1fzSmith copy: EAST commitment\x1f5MNS\x1e 0\x1faMoney\x1fzUnited States.\x1e 0\x1faMoney\x1fzUnited States\x1fvStatistics.\x1e1 \x1faSchwartz, Anna J.\x1fq(Anna Jacobson),\x1fd1915-2012\x1e2 \x1faNational Bureau of Economic Research.\x1e 0\x1faStudies in business cycles\x1fvno. 20.\x1e  \x1faAM\x1fb000259678\x1fcBSLW\x1e  \x1faHA\x1fb000764625\x1fcBSLW\x1e  \x1faSM\x1fb001730471\x1fcBSLW\x1e\x1d' | 1   
'utf-8' codec can't decode byte 0xef in position 39: unexpected end of data b"01050cam a2200265I  4500005001700000008004100017035002000058040003200078090001600110099001700126110005700143245006900200264007400269300002700343336002600370337002800396338002700424490007600451650005200527650004500579650004600624830007500670998001800745098002100763\x1e20140805000332.0\x1e750305119088 \xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2          \xcc\xb2\xef\x1e  \x1fa(OCoLC)01200959\x1e  \x1fcIAU\x1fdOCL\x1fdm/c\x1fdSNN\x1fdUtOrBLW\x1e  \x1faLB2334\x1fb.C3\x1e  \x1fa371\x1faC21b\x1fa2\x1e2 \x1faCarnegie Foundation for the Advancement of Teaching.\x1e14\x1faThe financial status of the professor in America and in Germany.\x1e 1\x1faNew York City :\x1fb[Knickerbocker Press (G. P. Putnam's Sons)],\x1fc[1908]\x1e  \x1fax, 101 pages ;\x1fc26 cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e1 \x1faBulletin (Carnegie Foundation for the Advancement of Teaching) ;\x1fvno. 2\x1e 0\x1faCollege teachers\x1fzUnited States\x1fxSalaries, etc.\x1e 0\x1faCollege teachers\x1fzCanada\x1fxSalaries, etc.\x1e 0\x1faCollege teachers\x1fzGermany\x1fxSalaries, etc.\x1e 0\x1faBulletin (Carnegie Foundation for the Advancement of Teaching)\x1fvno. 2.\x1e  \x1faSM\x1fb001429492\x1e11\x1faIXAPT\x1faC2b no. 2\x1e\x1d" | 1   
'utf-8' codec can't decode byte 0xef in position 39: unexpected end of data b'00930nam a2200265I  4500005001700000008004100017035002000058040002200078090001600100099002000116100002600136245010700162264005100269300002300320336002600343337002800369338002700397490005000424504002800474650003100502650003400533830005100567998001800618098002800636\x1e20140805062956.0\x1e730216119300 \xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2          \xcc\xb2\xef\x1e  \x1fa(OCoLC)00560311\x1e  \x1fcYNG\x1fdSNN\x1fdUtOrBLW\x1e  \x1faPC4261\x1fb.B8\x1e  \x1fa378.73M6915\x1faJ4\x1e1 \x1faBuffum, Mary Evaline.\x1e14\x1faThe construction of object pronouns in the works of modern Spanish writers, /\x1fcby Mary Evaline Buffum.\x1e 1\x1faColumbia :\x1fbThe University of Missouri,\x1fc1930.\x1e  \x1fa46 pages ;\x1fc27 cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e1 \x1faUniversity of Missouri studies ;\x1fvv. 5, no. 3\x1e  \x1faBibliography: p. 42-46.\x1e 0\x1faSpanish language\x1fxPronoun.\x1e 0\x1faSpanish language\x1fxWord order.\x1e 0\x1faUniversity of Missouri studies ;\x1fvv. 5, no. 3.\x1e  \x1faSM\x1fb001777730\x1e11\x1faIx83Mis\x1fa+M6u v.5, no.3\x1e\x1d' | 1   
'utf-8' codec can't decode byte 0xef in position 39: unexpected end of data b'00964nam a2200253I  4500005001700000008004100017010001300058035002000071040002800091099002300119100003300142245006600175264004300241300001900284336002600303337002800329338002700357490006600384504009600450650003700546650002600583810008300609998001800692\x1e20140805063817.0\x1e730601118900 \xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2          \xcc\xb2\xef\x1e  \x1fa05036537\x1e  \x1fa(OCoLC)00635151\x1e  \x1fcHIR\x1fdm.c.\x1fdSNN\x1fdUtOrBLW\x1e  \x1fa379.73\x1faUn3c\x1fa1890\x1e1 \x1faCajori, Florian,\x1fd1859-1930.\x1e14\x1faThe teaching and history of mathematics in the United States.\x1e 1\x1faWashington :\x1fbGovt. Print. Off,\x1fc1890.\x1e  \x1fa400p. ;\x1fc24cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e1 \x1faU.S. Bureau of education. Circular of information, 1890. no.3\x1e  \x1fa"Bibliography of fluxions and calculus. Textbooks printed in the United States": p.395-400.\x1e 0\x1faMathematics\x1fxStudy and teaching.\x1e 0\x1faMathematics\x1fxHistory.\x1e1 \x1faUnited States.\x1fbBureau of Education.\x1ftCirculars of information ;\x1fv1890, no. 3.\x1e  \x1faSM\x1fb001784944\x1e\x1d' | 1   
'utf-8' codec can't decode byte 0xef in position 39: unexpected end of data b'01049nam a2200265I  4500005001700000008004100017035002000058040002700078090002300105100003600128245010700164250010900271264004300380300003000423336002600453337002800479338002700507490004600534500004600580650002300626700004700649740002100696830004800717998001800765\x1e20140805191703.0\x1e750325119666 \xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2          \xcc\xb2\xef\x1e  \x1fa(OCoLC)01237183\x1e  \x1fcBOS\x1fdm/c\x1fdSNN\x1fdUtOrBLW\x1e  \x1faPQ6183\x1fb.B04 1966M\x1e1 \x1faCasta\xc3\xb1a, Hier\xc3\xb3nimo Francisco.\x1e10\x1faPrimera parte de los romances nuevos. /\x1fccompuestos por Hieronimo Francisco Casta\xc3\xb1a (Zaragoza, 1604).\x1e  \x1faReimpresos por vez primera del ejemplar \xc3\xbanico, con un estudio preliminar de Antonio Rodr\xc3\xadguez-Mo\xc3\xb1ino.\x1e 1\x1faValencia :\x1fbEditorial castalia,\x1fc1966.\x1e  \x1faxxxi, 113 pages ;\x1fc18 cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e1 \x1faFloresta; joyas po\xc3\xa9ticas espa\xc3\xb1olas,\x1fv10\x1e  \x1faPart of the pages are numbered as leaves.\x1e 0\x1faRomances, Spanish.\x1e1 \x1faRodr\xc3\xadguez Mo\xc3\xb1ino, Antonio R.,\x1fd1910-1970\x1e0 \x1faRomances nuevos.\x1e 0\x1faFloresta; joyas po\xc3\xa9ticas espa\xc3\xb1olas ;\x1fv10.\x1e  \x1faRC\x1fb004469932\x1e\x1d' | 1   
'utf-8' codec can't decode byte 0xef in position 39: unexpected end of data b'01059cam a2200289I  4500005001700000008004100017010001300058035002000071040002700091050002000118099001600138099001000154100002900164245007900193264009900272264001100371300004700382336002600429337002800455338002700483490004800510500006800558655001900626700005700645830004900702998001800751\x1e20140804145805.0\x1e750521119422 \xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2          \xcc\xb2\xef\x1e  \x1fa42022257\x1e  \x1fa(OCoLC)01347971\x1e  \x1fcRBN\x1fdOCL\x1fdSNN\x1fdUtOrBLW\x1e 0\x1faPS3503.O365\x1fbT5\x1e  \x1fa825\x1faB6393t\x1e  \x1faPlays\x1e1 \x1faBolton, Guy,\x1fd1884-1979.\x1e10\x1faTheatre, :\x1fba comedy in three acts, /\x1fcby Guy Bolton and Somerset Maugham.\x1e 1\x1faNew York, N.Y., Los Angeles, Calif. :\x1fbS. French; [etc., etc.],\x1fc[i.e. between 1940 and 1949?]\x1e 4\x1fc\xc2\xa91942\x1e  \x1fa124 pages :\x1fb2 diagram on 1 leaf ;\x1fc19 cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e1 \x1faOn cover: French\'s standard library edition\x1e  \x1fa"Copyright, 1937 (in novel form), by William Somerset Maugham."\x1e 7\x1faPlays.\x1f2rbgenr\x1e1 \x1faMaugham, W. Somerset\x1fq(William Somerset),\x1fd1874-1965\x1e 0\x1faOn cover: French\'s standard library edition.\x1e  \x1faAM\x1fb000359903\x1e\x1d' | 1   
'utf-8' codec can't decode byte 0xef in position 39: unexpected end of data b'01087cam a2200301I  4500005001700000008004100017010001300058035002000071040002200091050001500113099002600128100005800154245014300212264004700355300004600402336002600448337002800474338002700502490005100529504003100580650002300611650001600634650001400650740002200664830005200686998001800738098002900756\x1e20140805001127.0\x1e750506119388 \xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2          \xcc\xb2\xef\x1e  \x1fa38028387\x1e  \x1fa(OCoLC)01314827\x1e  \x1fcGAT\x1fdSNN\x1fdUtOrBLW\x1e00\x1faQA689\x1fb.B5\x1e  \x1fa378.73M6915\x1faJ4\x1fa13:2\x1e1 \x1faBlumenthal, Leonard M.\x1fq(Leonard Mascot),\x1fd1901-1984.\x1e10\x1faDistance geometries; :\x1fba study of the development of abstract metrics /\x1fc[by] Leonard M. Blumenthal. With an introduction by Karl Menger.\x1e 1\x1faColumbia :\x1fbUniversity of Missouri,\x1fc1938.\x1e  \x1fa2 preliminary leaves, 145 pages ;\x1fc27 cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e1 \x1faUniversity of Missouri studies ;\x1fvv. 13, no. 2\x1e  \x1faBibliography; p.[138]-142.\x1e 0\x1faDistance geometry.\x1e 0\x1faSet theory.\x1e 0\x1faTopology.\x1e0 \x1faAbstract metrics.\x1e 0\x1faUniversity of Missouri studies ;\x1fvv. 13, no. 2.\x1e  \x1faSM\x1fb001437235\x1e11\x1faIx83Mis\x1fa+M6u v.13, no.2\x1e\x1d' | 1   
'utf-8' codec can't decode byte 0xef in position 39: unexpected end of data b'01087nam a2200289I  4500005001700000008004100017010001300058035002000071040002800091050001500119099001600134100004900150245003600199264005600235300003000291336002600321337002800347338002700375490010400402502005200506504003000558600003100588830009200619830005300711998001800764098001500782\x1e20140805070309.0\x1e731109119033 \xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2          \xcc\xb2\xef\x1e  \x1fa05033558\x1e  \x1fa(OCoLC)00739117\x1e  \x1fcTFW\x1fdm.c.\x1fdSNN\x1fdUtOrBLW\x1e 0\x1faB2347\x1fb.B8\x1e  \x1fa406\x1faW75\x1fa2\x1e1 \x1faBrauer, Herman G. A.\x1fq(Herman Gustav Adolph)\x1e14\x1faThe philosophy of Ernest Renan.\x1e 1\x1faMadison, Wis. :\x1fb[publisher not identified],\x1fc1903.\x1e  \x1fapages [205]-379. ;\x1fc24cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e1 \x1faBulletin of the University of Wisconsin. no. 55. Philology and literature series, v. 2, no. 3, 1903\x1e  \x1faThesis (Ph.D.) - University of Wisconsin, 1902.\x1e  \x1faBibliography: p. 372-377.\x1e10\x1faRenan, Ernest,\x1fd1823-1892.\x1e 0\x1faBulletin of the University of Wisconsin.\x1fpPhilology and literature series\x1fvv. 2, no. 3.\x1e 0\x1faBulletin of the University of Wisconsin\x1fvno. 55.\x1e  \x1faSM\x1fb001805961\x1e11\x1faBE39\x1faR2zb\x1e\x1d' | 1   
'utf-8' codec can't decode byte 0xef in position 39: unexpected end of data b'01158nam a2200277I  4500005001700000008004100017010001300058035002000071040002700091050002300118099001500141100003300156245003400189264004900223300002200272336002600294337002800320338002700348500001100375500017900386500016000565700005000725700004400775700004300819998001800862\x1e20140805080215.0\x1e720322119288 \xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2          \xcc\xb2\xef\x1e  \x1fa28019609\x1e  \x1fa(OCoLC)00268895\x1e  \x1fcOUN\x1fdOCL\x1fdSNN\x1fdUtOrBLW\x1e 0\x1faPR6003.L8\x1fbR4 1928\x1e  \x1fa825\x1faB627r\x1e1 \x1faBlunden, Edmund,\x1fd1896-1974.\x1e10\x1faRetreat /\x1fcby Edmund Blunden.\x1e 1\x1fa[London] :\x1fbRichard Cobden-Sanderson,\x1fc1928.\x1e  \x1fa70 pages ;\x1fc23 cm\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e  \x1faPoems.\x1e  \x1faAmherst College Special Collections copy 1 is in dust jacket; copy 2 is accompanied by a letter from Blunden to G.E. de B. Wilmot (in file; envelope tipped into volume).\x1f5MA.\x1e  \x1faSC/RBR: In dust jacket; bookplate on front pastedown: Lamont House Library, Smith College. From the Library of Florence Corliss Lamont, class of 1893.\x1f5MNS\x1e1 \x1faLamont, Florence Corliss,\x1feformer owner.\x1f5MNS\x1e1 \x1faWilmot, G. E. de B.,\x1feformer owner.\x1f5MA\x1e1 \x1faCobden-Sanderson, Richard,\x1fepublisher.\x1e  \x1faSM\x1fb001857476\x1e\x1d' | 1   
'utf-8' codec can't decode byte 0xef in position 39: unexpected end of data b'01166nam a2200289I  4500005001700000008004100017035002000058040002800078090002900106099002400135100003900159245008300198264011300281300004400394336002600438337002800464338002700492490009300519500001700612504002700629650003800656650002800694650002300722700002100745830009200766998001800858\x1e20140805011257.0\x1e730508s1963    inua     b    000 0 engu\xef\x1e  \x1fa(OCoLC)00617255\x1e  \x1fcCWR\x1fdm.c.\x1fdSNN\x1fdUtOrBLW\x1e  \x1faLB1103\x1fb.S6 v.28, no.1-7\x1e  \x1fa158.52\x1faSol3m\x1fa28:5\x1e1 \x1faBirch, Herbert George,\x1fd1918-1973.\x1e10\x1faIntersensory development in children [by] Herbert G. Birch and Arthur Lefford.\x1e 1\x1fa[Lafayette, Ind.] :\x1fbChild Development publications of the Society for Research in Child Development,\x1fc1963.\x1e  \x1fa48 pages :\x1fbdiagrams, tables. ;\x1fc23 cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e1 \x1faMonographs of the Society for Research in Child Development ;\x1fvv.28, no. 5, serial no.89\x1e  \x1faCover title.\x1e  \x1faBibliography: p.47-48.\x1e 0\x1faSenses and sensation in children.\x1e 0\x1faPerception in children.\x1e 0\x1faChild development.\x1e1 \x1faLefford, Arthur.\x1e 0\x1faMonographs of the Society for Research in Child Development\x1fvv.28, no. 5, serial no.89.\x1e  \x1faMH\x1fb001089582\x1e\x1d' | 1   
'utf-8' codec can't decode byte 0xef in position 39: unexpected end of data b'01300nam a2200277I  4500005001700000008004100017010001300058035002000071040002200091050002200113099001800135100003400153245008700187264003700274300002800311336002600339337002800365338002700393490007100420501030300491504003000794630005900824630004700883830007400930998001801004\x1e20170922070756.0\x1e750411119344 \xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2          \xcc\xb2\xef\x1e  \x1fa34023296\x1e  \x1fa(OCoLC)01268657\x1e  \x1fcBPS\x1fdSNN\x1fdUtOrBLW\x1e00\x1faBS410\x1fb.Z5 vol.65\x1e  \x1fa205\x1faZ34b\x1fa65\x1e1 \x1faCaspari, Wilhelm,\x1fd1876-1947.\x1e10\x1faLieder und Gottesspr\xc3\xbcche der r\xc3\xbcckwanderer (Jesaja 40-55) /\x1fcvon Wilhelm Caspari.\x1e 1\x1faGiessen :\x1fbA. T\xc3\xb6pelmann,\x1fc1934.\x1e  \x1favi, 264 pages ;\x1fc24 cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e1 \x1faZeitschrift f\xc3\xbcr die alttestamentliche wissenschaft ;\x1fvBeihefte 65\x1e  \x1faBound with: Ezechielprobleme -- Die altorientalische Weisheit in ihrer israelitisch-j\xc3\xbcdischen Auspr\xc3\xa4gung : eine studie zur Nationalisierung der Weisheit in Israel -- Der Elohist als erz\xc3\xa4hler ein irrweg der Pentateuchkritik? : an der Genesis erl\xc3\xa4utert -- Name und Wort Gottes im Alten Testament.\x1e  \x1faBibliography: p. 262-263.\x1e00\x1faBible.\x1fpIsaiah, XL-LV\x1fxCriticism, interpretation, etc.\x1e00\x1faBible.\x1fpIsaiah, XL-LV\x1fxCriticism, Textual.\x1e 0\x1faBeihefte zur Zeitschrift f\xc3\xbcr die alttestamentliche Wissenschaft\x1fv65.\x1e  \x1faSM\x1fb001434261\x1e\x1d' | 1   
'utf-8' codec can't decode byte 0xef in position 39: unexpected end of data b'01321nam a2200301I  4500005001700000008004100017010001300058035002000071040002200091050002700113099002100140100005000161245012000211264006200331300006400393336002600457337002800483338002700511490005000538490005500588583012900643600003100772600004700803700004600850830004900896830005600945998001801001\x1e20140805075454.0\x1e750723119288 \xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2          \xcc\xb2\xef\x1e  \x1fa28026606\x1e  \x1fa(OCoLC)01468115\x1e  \x1fcFUG\x1fdSNN\x1fdUtOrBLW\x1e 0\x1faQ11\x1fb.S7 vol. 81, no.4\x1e  \x1fa506\x1faSm69m\x1fa81:4\x1e1 \x1faBushnell, David I.\x1fq(David Ives),\x1fd1875-1941.\x1e10\x1faDrawing by Jacques Lemoyne de Morgues of Saturioua, :\x1fba Timucua chief in Florida, 1564 /\x1fcby David I. Bushnell,jr.\x1e 1\x1faCity of Washington :\x1fbThe Smithsonian institution,\x1fc1928.\x1e  \x1fa1 page leaves, 9 pages :\x1fb1 illustration, portrait ;\x1fc25cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e1 \x1faPublication (Smithsonian Institution) ;\x1fv2972\x1e1 \x1faSmithsonian miscellaneous collections. v.81, no. 4\x1e1 \x1facommitted to retain\x1fc20160630\x1fd20310630\x1ffEAST\x1fuhttp://eastlibraries.org/retained-materials\x1fzSmith copy: EAST commitment\x1f5MNS\x1e00\x1faSaturioua,\x1fcTimucua chief.\x1e10\x1faLe Moyne de Morgues, Jacques,\x1fd1533?-1588.\x1e1 \x1faLe Moyne de Morgues, Jacques,\x1fd1533?-1588\x1e 0\x1faPublication (Smithsonian Institution)\x1fv2972.\x1e 0\x1faSmithsonian miscellaneous collections. v.81, no. 4.\x1e  \x1faSM\x1fb001850894\x1e\x1d' | 1   
   
## Records failed to migrate due to Value errors found in Transformation - 186 things   
Measure | Count   
--- | ---:   
Legacy id and 001 not found. Failing record  for ['unknown']  | 1   
No Instance type ID for ['000650511']  | 1   
No Instance type ID for ['000802798']  | 1   
No Instance type ID for ['000802836']  | 1   
No Instance type ID for ['000802847']  | 1   
No Instance type ID for ['000802848']  | 1   
No Instance type ID for ['000802849']  | 1   
No Instance type ID for ['000802850']  | 1   
No Instance type ID for ['000802852']  | 1   
No Instance type ID for ['000805538']  | 1   
No Instance type ID for ['000805663']  | 1   
No Instance type ID for ['000805784']  | 1   
No Instance type ID for ['000806390']  | 1   
No Instance type ID for ['000806426']  | 1   
No Instance type ID for ['000807014']  | 1   
No Instance type ID for ['000807716']  | 1   
No Instance type ID for ['000807873']  | 1   
No Instance type ID for ['000807932']  | 1   
No Instance type ID for ['000813277']  | 1   
No Instance type ID for ['000815856']  | 1   
No Instance type ID for ['000817585']  | 1   
No Instance type ID for ['001227696']  | 1   
No Instance type ID for ['003339883']  | 1   
No Instance type ID for ['003677979']  | 1   
No Instance type ID for ['004094273']  | 1   
No Instance type ID for ['004098772']  | 1   
No Instance type ID for ['004452910']  | 1   
No Instance type ID for ['010502761']  | 1   
No Instance type ID for ['013976641']  | 1   
No Instance type ID for ['014082940']  | 1   
No Instance type ID for ['014543777']  | 1   
No Instance type ID for ['016328621']  | 1   
No Instance type ID for ['017393803']  | 1   
No title for ['000072332'] for ['000072332']  | 1   
No title for ['000077982'] for ['000077982']  | 1   
No title for ['000122725'] for ['000122725']  | 1   
No title for ['000170293'] for ['000170293']  | 1   
No title for ['000198627'] for ['000198627']  | 1   
No title for ['000330496'] for ['000330496']  | 1   
No title for ['000348853'] for ['000348853']  | 1   
No title for ['000447897'] for ['000447897']  | 1   
No title for ['000559535'] for ['000559535']  | 1   
No title for ['000809211'] for ['000809211']  | 1   
No title for ['000905630'] for ['000905630']  | 1   
No title for ['000914521'] for ['000914521']  | 1   
No title for ['001061285'] for ['001061285']  | 1   
No title for ['001621513'] for ['001621513']  | 1   
No title for ['001656459'] for ['001656459']  | 1   
No title for ['001807895'] for ['001807895']  | 1   
No title for ['001843746'] for ['001843746']  | 1   
No title for ['001852236'] for ['001852236']  | 1   
No title for ['001979294', '016526144'] for ['001979294', '016526144']  | 1   
No title for ['002062130'] for ['002062130']  | 1   
No title for ['002155884'] for ['002155884']  | 1   
No title for ['003167139'] for ['003167139']  | 1   
No title for ['003388703'] for ['003388703']  | 1   
No title for ['003389316'] for ['003389316']  | 1   
No title for ['003394063'] for ['003394063']  | 1   
No title for ['003401932'] for ['003401932']  | 1   
No title for ['003403439'] for ['003403439']  | 1   
No title for ['003403519'] for ['003403519']  | 1   
No title for ['003406376'] for ['003406376']  | 1   
No title for ['003409645'] for ['003409645']  | 1   
No title for ['003413362'] for ['003413362']  | 1   
No title for ['003415006'] for ['003415006']  | 1   
No title for ['003415017'] for ['003415017']  | 1   
No title for ['003421066'] for ['003421066']  | 1   
No title for ['003431696'] for ['003431696']  | 1   
No title for ['003580878'] for ['003580878']  | 1   
No title for ['004898130'] for ['004898130']  | 1   
No title for ['004939587'] for ['004939587']  | 1   
No title for ['004982939'] for ['004982939']  | 1   
No title for ['004986967'] for ['004986967']  | 1   
No title for ['010492390'] for ['010492390']  | 1   
No title for ['010551627'] for ['010551627']  | 1   
No title for ['010551754'] for ['010551754']  | 1   
No title for ['011205046'] for ['011205046']  | 1   
No title for ['011228895'] for ['011228895']  | 1   
No title for ['011228913'] for ['011228913']  | 1   
No title for ['011228920'] for ['011228920']  | 1   
No title for ['011244781'] for ['011244781']  | 1   
No title for ['012155226'] for ['012155226']  | 1   
No title for ['012155272'] for ['012155272']  | 1   
No title for ['012155319'] for ['012155319']  | 1   
No title for ['012155397'] for ['012155397']  | 1   
No title for ['012285151'] for ['012285151']  | 1   
No title for ['012408984'] for ['012408984']  | 1   
No title for ['012457733'] for ['012457733']  | 1   
No title for ['012565625'] for ['012565625']  | 1   
No title for ['013700849'] for ['013700849']  | 1   
No title for ['014012320'] for ['014012320']  | 1   
No title for ['014031253'] for ['014031253']  | 1   
No title for ['014074131'] for ['014074131']  | 1   
No title for ['014169027'] for ['014169027']  | 1   
No title for ['014596426'] for ['014596426']  | 1   
No title for ['014602200'] for ['014602200']  | 1   
No title for ['014717766'] for ['014717766']  | 1   
No title for ['014903868'] for ['014903868']  | 1   
No title for ['014935567'] for ['014935567']  | 1   
No title for ['014935576'] for ['014935576']  | 1   
No title for ['014935603'] for ['014935603']  | 1   
No title for ['014935614'] for ['014935614']  | 1   
No title for ['014935650'] for ['014935650']  | 1   
No title for ['014935663'] for ['014935663']  | 1   
No title for ['014935666'] for ['014935666']  | 1   
No title for ['014938796'] for ['014938796']  | 1   
No title for ['014940775'] for ['014940775']  | 1   
No title for ['014940799'] for ['014940799']  | 1   
No title for ['014942710'] for ['014942710']  | 1   
No title for ['014943015'] for ['014943015']  | 1   
No title for ['014943028'] for ['014943028']  | 1   
No title for ['014944219'] for ['014944219']  | 1   
No title for ['014944443'] for ['014944443']  | 1   
No title for ['014944463'] for ['014944463']  | 1   
No title for ['014944466'] for ['014944466']  | 1   
No title for ['014944478'] for ['014944478']  | 1   
No title for ['014944481'] for ['014944481']  | 1   
No title for ['014944495'] for ['014944495']  | 1   
No title for ['014944509'] for ['014944509']  | 1   
No title for ['014944583'] for ['014944583']  | 1   
No title for ['014944622'] for ['014944622']  | 1   
No title for ['014944763'] for ['014944763']  | 1   
No title for ['014944782'] for ['014944782']  | 1   
No title for ['014944801'] for ['014944801']  | 1   
No title for ['014944813'] for ['014944813']  | 1   
No title for ['014944837'] for ['014944837']  | 1   
No title for ['014944838'] for ['014944838']  | 1   
No title for ['014944881'] for ['014944881']  | 1   
No title for ['014944916'] for ['014944916']  | 1   
No title for ['014944948'] for ['014944948']  | 1   
No title for ['014944951'] for ['014944951']  | 1   
No title for ['014944953'] for ['014944953']  | 1   
No title for ['014944986'] for ['014944986']  | 1   
No title for ['014945037'] for ['014945037']  | 1   
No title for ['014945049'] for ['014945049']  | 1   
No title for ['014945095'] for ['014945095']  | 1   
No title for ['014945125'] for ['014945125']  | 1   
No title for ['014945132'] for ['014945132']  | 1   
No title for ['014945142'] for ['014945142']  | 1   
No title for ['014945160'] for ['014945160']  | 1   
No title for ['014945184'] for ['014945184']  | 1   
No title for ['014945235'] for ['014945235']  | 1   
No title for ['014945243'] for ['014945243']  | 1   
No title for ['014945289'] for ['014945289']  | 1   
No title for ['014945303'] for ['014945303']  | 1   
No title for ['014945329'] for ['014945329']  | 1   
No title for ['014945332'] for ['014945332']  | 1   
No title for ['014946640'] for ['014946640']  | 1   
No title for ['014946653'] for ['014946653']  | 1   
No title for ['014946731'] for ['014946731']  | 1   
No title for ['014946962'] for ['014946962']  | 1   
No title for ['014947066'] for ['014947066']  | 1   
No title for ['014947071'] for ['014947071']  | 1   
No title for ['014947099'] for ['014947099']  | 1   
No title for ['015188870'] for ['015188870']  | 1   
No title for ['015189356'] for ['015189356']  | 1   
No title for ['015194745'] for ['015194745']  | 1   
No title for ['015194830'] for ['015194830']  | 1   
No title for ['015195369'] for ['015195369']  | 1   
No title for ['015195437'] for ['015195437']  | 1   
No title for ['015195517'] for ['015195517']  | 1   
No title for ['015196533'] for ['015196533']  | 1   
No title for ['015198826'] for ['015198826']  | 1   
No title for ['015199072'] for ['015199072']  | 1   
No title for ['015199094'] for ['015199094']  | 1   
No title for ['015631668'] for ['015631668']  | 1   
No title for ['015632228'] for ['015632228']  | 1   
No title for ['016033898'] for ['016033898']  | 1   
No title for ['016287157'] for ['016287157']  | 1   
No title for ['016453904'] for ['016453904']  | 1   
No title for ['016476444', '001753533', '003017648'] for ['016476444', '001753533', '003017648']  | 1   
No title for ['016706270'] for ['016706270']  | 1   
No title for ['016945518'] for ['016945518']  | 1   
No title for ['016947374'] for ['016947374']  | 1   
No title for ['016989191'] for ['016989191']  | 1   
No title for ['016991702'] for ['016991702']  | 1   
No title for ['016992006'] for ['016992006']  | 1   
No title for ['016992038'] for ['016992038']  | 1   
No title for ['016994239'] for ['016994239']  | 1   
No title for ['017090053'] for ['017090053']  | 1   
No title for ['017118246'] for ['017118246']  | 1   
No title for ['017118275'] for ['017118275']  | 1   
No title for ['017123417'] for ['017123417']  | 1   
No title for ['017129634'] for ['017129634']  | 1   
No title for ['017502875'] for ['017502875']  | 1   
No title for ['017505225'] for ['017505225']  | 1   
   
## unspecified Modes of issuance code - 5 things   
Measure | Count   
--- | ---:   
  | 18   
I | 1   
g | 1   
r | 1   
u | 3   

## Mapped FOLIO fields   
FOLIO Field | Mapped | Empty | Unmapped  
--- | --- | --- | ---:  
@context | 0 (0%) | 0 | 6262661  
alternativeTitles | 1723078 (28%) | 0 | 4539583  
catalogedDate | 0 (0%) | 0 | 6262661  
childInstances | 0 (0%) | 0 | 6262661  
classifications | 0 (0%) | 0 | 6262661  
contributors | 6148717 (98%) | 0 | 113944  
discoverySuppress | 6262475 (100%) | 0 | 186  
editions | 718021 (11%) | 0 | 5544640  
electronicAccess | 281198 (4%) | 0 | 5981463  
hrid | 6262475 (100%) | 0 | 186  
id | 6262475 (100%) | 0 | 186  
identifiers | 6138802 (98%) | 0 | 123859  
indexTitle | 6262475 (100%) | 0 | 186  
instanceFormatIds | 6262475 (100%) | 0 | 186  
instanceTypeId | 6262475 (100%) | 0 | 186  
languages | 6262475 (100%) | 0 | 186  
links | 0 (0%) | 0 | 6262661  
matchKey | 0 (0%) | 0 | 6262661  
metadata | 6262475 (100%) | 0 | 186  
modeOfIssuanceId | 6262475 (100%) | 0 | 186  
natureOfContentTermIds | 0 (0%) | 0 | 6262661  
notes | 6041867 (96%) | 0 | 220794  
parentInstances | 0 (0%) | 0 | 6262661  
physicalDescriptions | 6181516 (99%) | 0 | 81145  
precedingTitles | 0 (0%) | 0 | 6262661  
previouslyHeld | 0 (0%) | 0 | 6262661  
publication | 6243425 (100%) | 0 | 19236  
publicationFrequency | 107496 (2%) | 0 | 6155165  
publicationRange | 122598 (2%) | 0 | 6140063  
series | 2720818 (43%) | 0 | 3541843  
source | 6262475 (100%) | 0 | 186  
sourceRecordFormat | 0 (0%) | 0 | 6262661  
staffSuppress | 6262475 (100%) | 0 | 186  
statisticalCodeIds | 0 (0%) | 0 | 6262661  
statusId | 0 (0%) | 0 | 6262661  
statusUpdatedDate | 0 (0%) | 0 | 6262661  
subjects | 5696038 (91%) | 0 | 566623  
succeedingTitles | 0 (0%) | 0 | 6262661  
tags | 0 (0%) | 0 | 6262661  
title | 6262475 (100%) | 0 | 186  

## Mapped Legacy fields  
Legacy Field | Present | Mapped | Empty | Unmapped  
--- | --- | --- | --- | ---:  
001 | 1 (0.0%) | 0 (0%) | 0 | 1  
003 | 2481656 (39.6%) | 0 (0%) | 0 | 2481656  
005 | 6262660 (100.0%) | 0 (0%) | 0 | 6262660  
006 | 2119300 (33.8%) | 0 (0%) | 0 | 2119300  
007 | 3238884 (51.7%) | 0 (0%) | 0 | 3238884  
008 | 6261628 (100.0%) | 6261628 (100%) | 6261628 | 0  
010 | 2279979 (36.4%) | 2279979 (36%) | 2279979 | 0  
012 | 7398 (0.1%) | 0 (0%) | 0 | 7398  
013 | 1 (0.0%) | 0 (0%) | 0 | 1  
015 | 225155 (3.6%) | 0 (0%) | 0 | 225155  
016 | 186436 (3.0%) | 0 (0%) | 0 | 186436  
017 | 196 (0.0%) | 0 (0%) | 0 | 196  
018 | 7 (0.0%) | 0 (0%) | 0 | 7  
019 | 474232 (7.6%) | 474232 (8%) | 474232 | 0  
020 | 4267804 (68.1%) | 4267804 (68%) | 4267804 | 0  
022 | 55647 (0.9%) | 55647 (1%) | 55647 | 0  
024 | 2113894 (33.8%) | 2113894 (34%) | 2113894 | 0  
025 | 1496 (0.0%) | 0 (0%) | 0 | 1496  
026 | 20 (0.0%) | 0 (0%) | 0 | 20  
027 | 8476 (0.1%) | 0 (0%) | 0 | 8476  
028 | 390162 (6.2%) | 390162 (6%) | 390162 | 0  
030 | 8752 (0.1%) | 0 (0%) | 0 | 8752  
031 | 102 (0.0%) | 0 (0%) | 0 | 102  
032 | 1143 (0.0%) | 0 (0%) | 0 | 1143  
033 | 108872 (1.7%) | 0 (0%) | 0 | 108872  
034 | 12812 (0.2%) | 0 (0%) | 0 | 12812  
035 | 8365388 (133.6%) | 8365388 (134%) | 8365388 | 0  
036 | 194 (0.0%) | 0 (0%) | 0 | 194  
037 | 361399 (5.8%) | 0 (0%) | 0 | 361399  
039 | 15342 (0.2%) | 0 (0%) | 0 | 15342  
040 | 5958473 (95.1%) | 0 (0%) | 0 | 5958473  
041 | 475254 (7.6%) | 475254 (8%) | 475254 | 0  
042 | 612970 (9.8%) | 0 (0%) | 0 | 612970  
043 | 1733162 (27.7%) | 0 (0%) | 0 | 1733162  
044 | 1612 (0.0%) | 0 (0%) | 0 | 1612  
045 | 123619 (2.0%) | 0 (0%) | 0 | 123619  
046 | 6735 (0.1%) | 0 (0%) | 0 | 6735  
047 | 61707 (1.0%) | 0 (0%) | 0 | 61707  
048 | 163361 (2.6%) | 0 (0%) | 0 | 163361  
050 | 2967122 (47.4%) | 0 (0%) | 0 | 2967122  
051 | 12352 (0.2%) | 0 (0%) | 0 | 12352  
052 | 13539 (0.2%) | 0 (0%) | 0 | 13539  
055 | 23653 (0.4%) | 0 (0%) | 0 | 23653  
060 | 40074 (0.6%) | 0 (0%) | 0 | 40074  
065 | 1 (0.0%) | 0 (0%) | 0 | 1  
066 | 54399 (0.9%) | 0 (0%) | 0 | 54399  
069 | 4 (0.0%) | 0 (0%) | 0 | 4  
070 | 19889 (0.3%) | 0 (0%) | 0 | 19889  
072 | 1004845 (16.0%) | 0 (0%) | 0 | 1004845  
074 | 670050 (10.7%) | 670050 (11%) | 670050 | 0  
080 | 2234 (0.0%) | 0 (0%) | 0 | 2234  
082 | 1054572 (16.8%) | 0 (0%) | 0 | 1054572  
083 | 322 (0.0%) | 0 (0%) | 0 | 322  
084 | 151557 (2.4%) | 0 (0%) | 0 | 151557  
085 | 106 (0.0%) | 0 (0%) | 0 | 106  
086 | 727184 (11.6%) | 0 (0%) | 0 | 727184  
088 | 148770 (2.4%) | 0 (0%) | 0 | 148770  
090 | 2002631 (32.0%) | 0 (0%) | 0 | 2002631  
091 | 1 (0.0%) | 0 (0%) | 0 | 1  
092 | 59704 (1.0%) | 0 (0%) | 0 | 59704  
093 | 1 (0.0%) | 0 (0%) | 0 | 1  
096 | 2643 (0.0%) | 0 (0%) | 0 | 2643  
098 | 89225 (1.4%) | 0 (0%) | 0 | 89225  
099 | 889093 (14.2%) | 0 (0%) | 0 | 889093  
100 | 3658244 (58.4%) | 3658244 (58%) | 3658244 | 0  
110 | 1175381 (18.8%) | 1175381 (19%) | 1175381 | 0  
111 | 55198 (0.9%) | 55198 (1%) | 55198 | 0  
130 | 67899 (1.1%) | 67899 (1%) | 67899 | 0  
164 | 1 (0.0%) | 0 (0%) | 0 | 1  
210 | 26272 (0.4%) | 0 (0%) | 0 | 26272  
222 | 42073 (0.7%) | 0 (0%) | 0 | 42073  
240 | 374215 (6.0%) | 374215 (6%) | 374215 | 0  
242 | 197 (0.0%) | 0 (0%) | 0 | 197  
243 | 54 (0.0%) | 0 (0%) | 0 | 54  
245 | 6264185 (100.0%) | 6264185 (100%) | 6264185 | 0  
246 | 704773 (11.3%) | 704773 (11%) | 704773 | 0  
247 | 3903 (0.1%) | 3903 (0%) | 3903 | 0  
250 | 718429 (11.5%) | 718429 (11%) | 718429 | 0  
254 | 4058 (0.1%) | 0 (0%) | 0 | 4058  
255 | 13373 (0.2%) | 13373 (0%) | 13373 | 0  
256 | 10660 (0.2%) | 0 (0%) | 0 | 10660  
257 | 6010 (0.1%) | 0 (0%) | 0 | 6010  
258 | 2 (0.0%) | 0 (0%) | 0 | 2  
260 | 1252071 (20.0%) | 1252071 (20%) | 1252071 | 0  
261 | 101 (0.0%) | 0 (0%) | 0 | 101  
263 | 16587 (0.3%) | 0 (0%) | 0 | 16587  
264 | 6334823 (101.2%) | 6334823 (101%) | 6334823 | 0  
270 | 79 (0.0%) | 0 (0%) | 0 | 79  
300 | 6184445 (98.8%) | 6184445 (99%) | 6184445 | 0  
306 | 123923 (2.0%) | 0 (0%) | 0 | 123923  
307 | 3 (0.0%) | 0 (0%) | 0 | 3  
310 | 107652 (1.7%) | 107652 (2%) | 107652 | 0  
321 | 17661 (0.3%) | 0 (0%) | 0 | 17661  
336 | 10439408 (166.7%) | 5219704 (83%) | 5219704 | 5219704  
337 | 5245048 (83.8%) | 0 (0%) | 0 | 5245048  
338 | 5231754 (83.5%) | 5231754 (84%) | 5231754 | 0  
340 | 6295 (0.1%) | 0 (0%) | 0 | 6295  
341 | 38 (0.0%) | 0 (0%) | 0 | 38  
342 | 5 (0.0%) | 0 (0%) | 0 | 5  
343 | 3 (0.0%) | 0 (0%) | 0 | 3  
344 | 80660 (1.3%) | 0 (0%) | 0 | 80660  
345 | 1076 (0.0%) | 0 (0%) | 0 | 1076  
346 | 5069 (0.1%) | 0 (0%) | 0 | 5069  
347 | 435391 (7.0%) | 0 (0%) | 0 | 435391  
348 | 5961 (0.1%) | 0 (0%) | 0 | 5961  
351 | 655 (0.0%) | 0 (0%) | 0 | 655  
352 | 14 (0.0%) | 0 (0%) | 0 | 14  
361 | 1 (0.0%) | 0 (0%) | 0 | 1  
362 | 130587 (2.1%) | 130587 (2%) | 130587 | 0  
363 | 7 (0.0%) | 0 (0%) | 0 | 7  
365 | 45365 (0.7%) | 0 (0%) | 0 | 45365  
366 | 67 (0.0%) | 0 (0%) | 0 | 67  
370 | 162 (0.0%) | 0 (0%) | 0 | 162  
377 | 1 (0.0%) | 0 (0%) | 0 | 1  
380 | 8788 (0.1%) | 0 (0%) | 0 | 8788  
381 | 24 (0.0%) | 0 (0%) | 0 | 24  
382 | 36049 (0.6%) | 0 (0%) | 0 | 36049  
383 | 2804 (0.0%) | 0 (0%) | 0 | 2804  
384 | 1017 (0.0%) | 0 (0%) | 0 | 1017  
385 | 629 (0.0%) | 0 (0%) | 0 | 629  
386 | 2165 (0.0%) | 0 (0%) | 0 | 2165  
388 | 60 (0.0%) | 0 (0%) | 0 | 60  
440 | 391444 (6.3%) | 0 (0%) | 0 | 391444  
490 | 2483924 (39.7%) | 0 (0%) | 0 | 2483924  
500 | 6129186 (97.9%) | 6129186 (98%) | 6129186 | 0  
501 | 12042 (0.2%) | 12042 (0%) | 12042 | 0  
502 | 114681 (1.8%) | 114681 (2%) | 114681 | 0  
504 | 2285064 (36.5%) | 2285064 (36%) | 2285064 | 0  
505 | 1102451 (17.6%) | 1102451 (18%) | 1102451 | 0  
506 | 59969 (1.0%) | 59969 (1%) | 59969 | 0  
507 | 7 (0.0%) | 7 (0%) | 7 | 0  
508 | 56326 (0.9%) | 56326 (1%) | 56326 | 0  
510 | 521507 (8.3%) | 521507 (8%) | 521507 | 0  
511 | 280860 (4.5%) | 280860 (4%) | 280860 | 0  
513 | 10593 (0.2%) | 10593 (0%) | 10593 | 0  
514 | 10 (0.0%) | 10 (0%) | 10 | 0  
515 | 40906 (0.7%) | 40906 (1%) | 40906 | 0  
516 | 12910 (0.2%) | 12910 (0%) | 12910 | 0  
518 | 191296 (3.1%) | 191296 (3%) | 191296 | 0  
520 | 984065 (15.7%) | 984065 (16%) | 984065 | 0  
521 | 32391 (0.5%) | 32391 (1%) | 32391 | 0  
522 | 63 (0.0%) | 63 (0%) | 63 | 0  
524 | 587 (0.0%) | 587 (0%) | 587 | 0  
525 | 5619 (0.1%) | 5619 (0%) | 5619 | 0  
526 | 2084 (0.0%) | 2084 (0%) | 2084 | 0  
530 | 265749 (4.2%) | 265749 (4%) | 265749 | 0  
532 | 1252 (0.0%) | 1252 (0%) | 1252 | 0  
533 | 1566830 (25.0%) | 1566830 (25%) | 1566830 | 0  
534 | 202213 (3.2%) | 202213 (3%) | 202213 | 0  
535 | 200996 (3.2%) | 200996 (3%) | 200996 | 0  
536 | 21844 (0.3%) | 21844 (0%) | 21844 | 0  
538 | 593202 (9.5%) | 593202 (9%) | 593202 | 0  
539 | 500 (0.0%) | 0 (0%) | 0 | 500  
540 | 360264 (5.8%) | 360264 (6%) | 360264 | 0  
541 | 15826 (0.3%) | 15826 (0%) | 15826 | 0  
542 | 253723 (4.1%) | 253723 (4%) | 253723 | 0  
544 | 511 (0.0%) | 511 (0%) | 511 | 0  
545 | 4597 (0.1%) | 4597 (0%) | 4597 | 0  
546 | 273235 (4.4%) | 273235 (4%) | 273235 | 0  
547 | 131 (0.0%) | 131 (0%) | 131 | 0  
550 | 75093 (1.2%) | 75093 (1%) | 75093 | 0  
552 | 1 (0.0%) | 1 (0%) | 1 | 0  
555 | 9981 (0.2%) | 9981 (0%) | 9981 | 0  
556 | 56 (0.0%) | 56 (0%) | 56 | 0  
558 | 2 (0.0%) | 0 (0%) | 0 | 2  
561 | 317 (0.0%) | 317 (0%) | 317 | 0  
562 | 85 (0.0%) | 85 (0%) | 85 | 0  
563 | 159 (0.0%) | 159 (0%) | 159 | 0  
565 | 1 (0.0%) | 1 (0%) | 1 | 0  
567 | 12 (0.0%) | 12 (0%) | 12 | 0  
580 | 27295 (0.4%) | 27295 (0%) | 27295 | 0  
581 | 13 (0.0%) | 13 (0%) | 13 | 0  
583 | 1933266 (30.9%) | 1933266 (31%) | 1933266 | 0  
584 | 90 (0.0%) | 90 (0%) | 90 | 0  
585 | 291 (0.0%) | 291 (0%) | 291 | 0  
586 | 10775 (0.2%) | 10775 (0%) | 10775 | 0  
588 | 604856 (9.7%) | 604856 (10%) | 604856 | 0  
590 | 254191 (4.1%) | 254191 (4%) | 254191 | 0  
591 | 2 (0.0%) | 0 (0%) | 0 | 2  
600 | 1282903 (20.5%) | 1282903 (20%) | 1282903 | 0  
610 | 901433 (14.4%) | 901433 (14%) | 901433 | 0  
611 | 29077 (0.5%) | 29077 (0%) | 29077 | 0  
630 | 239731 (3.8%) | 239731 (4%) | 239731 | 0  
647 | 1581 (0.0%) | 1581 (0%) | 1581 | 0  
648 | 82212 (1.3%) | 82212 (1%) | 82212 | 0  
650 | 14939718 (238.6%) | 14939718 (239%) | 14939718 | 0  
651 | 2065106 (33.0%) | 2065106 (33%) | 2065106 | 0  
653 | 2087275 (33.3%) | 0 (0%) | 0 | 2087275  
654 | 120 (0.0%) | 0 (0%) | 0 | 120  
655 | 2641698 (42.2%) | 2641698 (42%) | 2641698 | 0  
656 | 19 (0.0%) | 0 (0%) | 0 | 19  
657 | 335404 (5.4%) | 0 (0%) | 0 | 335404  
658 | 23 (0.0%) | 0 (0%) | 0 | 23  
662 | 3 (0.0%) | 0 (0%) | 0 | 3  
690 | 118725 (1.9%) | 0 (0%) | 0 | 118725  
691 | 391 (0.0%) | 0 (0%) | 0 | 391  
699 | 51 (0.0%) | 0 (0%) | 0 | 51  
700 | 4970293 (79.4%) | 4970293 (79%) | 4970293 | 0  
710 | 2431473 (38.8%) | 2431473 (39%) | 2431473 | 0  
711 | 27394 (0.4%) | 27394 (0%) | 27394 | 0  
712 | 1 (0.0%) | 0 (0%) | 0 | 1  
720 | 848 (0.0%) | 0 (0%) | 0 | 848  
730 | 652244 (10.4%) | 652244 (10%) | 652244 | 0  
740 | 503906 (8.0%) | 503906 (8%) | 503906 | 0  
751 | 107 (0.0%) | 0 (0%) | 0 | 107  
752 | 322961 (5.2%) | 0 (0%) | 0 | 322961  
753 | 403 (0.0%) | 0 (0%) | 0 | 403  
755 | 13 (0.0%) | 0 (0%) | 0 | 13  
758 | 66 (0.0%) | 0 (0%) | 0 | 66  
760 | 3791 (0.1%) | 0 (0%) | 0 | 3791  
762 | 102 (0.0%) | 0 (0%) | 0 | 102  
765 | 751 (0.0%) | 0 (0%) | 0 | 751  
767 | 209 (0.0%) | 0 (0%) | 0 | 209  
770 | 3198 (0.1%) | 0 (0%) | 0 | 3198  
772 | 2093 (0.0%) | 0 (0%) | 0 | 2093  
773 | 357378 (5.7%) | 0 (0%) | 0 | 357378  
774 | 140 (0.0%) | 0 (0%) | 0 | 140  
775 | 7170 (0.1%) | 0 (0%) | 0 | 7170  
776 | 1525758 (24.4%) | 0 (0%) | 0 | 1525758  
777 | 1056 (0.0%) | 0 (0%) | 0 | 1056  
780 | 54494 (0.9%) | 0 (0%) | 0 | 54494  
785 | 46832 (0.7%) | 0 (0%) | 0 | 46832  
786 | 24 (0.0%) | 0 (0%) | 0 | 24  
787 | 11796 (0.2%) | 0 (0%) | 0 | 11796  
793 | 23340 (0.4%) | 0 (0%) | 0 | 23340  
796 | 4122 (0.1%) | 0 (0%) | 0 | 4122  
797 | 69594 (1.1%) | 0 (0%) | 0 | 69594  
800 | 33841 (0.5%) | 33841 (1%) | 33841 | 0  
810 | 362813 (5.8%) | 362813 (6%) | 362813 | 0  
811 | 945 (0.0%) | 945 (0%) | 945 | 0  
830 | 2623220 (41.9%) | 2623220 (42%) | 2623220 | 0  
850 | 13697 (0.2%) | 0 (0%) | 0 | 13697  
851 | 1 (0.0%) | 0 (0%) | 0 | 1  
852 | 6950 (0.1%) | 0 (0%) | 0 | 6950  
853 | 18 (0.0%) | 0 (0%) | 0 | 18  
854 | 2 (0.0%) | 0 (0%) | 0 | 2  
856 | 520638 (8.3%) | 520638 (8%) | 520638 | 0  
859 | 5 (0.0%) | 0 (0%) | 0 | 5  
863 | 13 (0.0%) | 0 (0%) | 0 | 13  
865 | 1 (0.0%) | 0 (0%) | 0 | 1  
866 | 372 (0.0%) | 0 (0%) | 0 | 372  
880 | 407465 (6.5%) | 0 (0%) | 0 | 407465  
883 | 32 (0.0%) | 0 (0%) | 0 | 32  
884 | 14 (0.0%) | 0 (0%) | 0 | 14  
886 | 1212 (0.0%) | 0 (0%) | 0 | 1212  
887 | 31113 (0.5%) | 0 (0%) | 0 | 31113  
928 | 719310 (11.5%) | 0 (0%) | 0 | 719310  
998 | 7489880 (119.6%) | 0 (0%) | 0 | 7489880  
# MFHD records transformation results   
Time Finished: 2020-11-24T11:30:56.882623   
## MFHD records transformation counters   
  Measure   | Count   
   
--- | ---:   
Failed records | 221   
Holdings records written to disk | 7,498,518   
Number of records in file(s) | 7,498,739   
Total number of Tags processed | 62,603,465   
Value errors | 221   
bib id not in map | 221   
   
## Record status (leader pos 5) - 3 things   
Measure | Count   
--- | ---:   
4 | 1   
c | 311   
n | 7498427   
   
## Leader 06 (Holdings type) - 3 things   
Measure | Count   
--- | ---:   
v | 13   
x | 19965968   
y | 4522   
   
## Undhandled condition defined in mapping rules - 3 things   
Measure | Count   
--- | ---:   
remo | 7498228   
set_call_number_type_by_indicator | 7498397   
set_electronic_if_serv | 7498228   
   
## Legacy location codes - 439 things   
Measure | Count   
--- | ---:   
ACDEP | 1230   
ACDPM | 103975   
AFAS | 49941   
AFASD | 34   
AFASF | 1139   
AFASH | 199   
AFASL | 10811   
AFASO | 941   
AFASR | 210   
AFAST | 12434   
AFASTT | 1   
AFASV | 51   
AFASW | 964   
AFAV | 26   
AFBLU | 226   
AFCAS | 4   
AFDRM | 32   
AFDVD | 11578   
AFIN | 2505   
AFMAP | 273   
AFMIC | 482   
AFPER | 3811   
AFRAL | 285   
AFREF | 8954   
AFREP | 38   
AFRES | 6   
AFRFD | 925   
AFRFL | 232   
AFRI | 255   
AFRIV | 177   
AFRJP | 41   
AFRKU | 29   
AFRLA | 165   
AFROM | 168   
AFRSA | 36   
AFRST | 615810   
AFRTA | 1584   
AFRUC | 9001   
AFRUF | 183   
AFRUR | 1128   
AFRUS | 618   
AFVHS | 5390   
AGEOW | 176   
AMRES | 98   
AMRST | 37   
AMSCO | 13994   
AMSD | 23722   
AMSTO | 346   
AMUS | 1379   
AMUSP | 21   
AMUSR | 2042   
ASCIR | 65   
ASCIV | 3   
ASLV | 111   
B392 1-6 | 1   
CAMB | 547   
CHCRC | 251   
CSCRC | 74   
DEPOSITORY: 1 (1963)-29 (2008) 11.07.13 | 1   
DEPOSITORY: 1 (1984)-2 (1985); WITHDRAWN: 3 (1986)-24 (2007) 02.04.14; WITHDRAWN: 25 (2008)-27 (2010) 11.29.16 | 1   
DEPOSITORY: 1 (1990), 3 (1992)-4 (1993), 6 (1995)-11 (1999) 10.17.12; DEPOSITORY: 23 (2011); WITHDRAWN: 12 (2000)-22 (2010) 04.12.13; DEPOSITORY: 27 (2014)-28 (2015); WITHDRAWN: 24 (2012)-26 (2013) 11.20.17 | 1   
DEPOSITORY: 4 (2005)-6 (2007) 05.31.13 | 1   
DEPOSITORY: 44 (1949)-45 (1949); WITHDRAWN: 2 (1918)-43 (1948), 46 (1950)-65 (1959) 09.30.13 | 1   
EBEBL | 412   
EVANS | 37370   
FCANI | 36898   
FCCLM | 7959   
FCCNX | 110593   
FCDPM | 74077   
FCDPS | 18353   
FCDWC | 44   
FCDWJ | 1   
FCDWS | 248573   
FCEBR | 198424   
FCFRE | 1017   
FCJSD | 74646   
FCJSO | 6483   
FCJSP | 5519   
FCKNU | 1510   
FCOTL | 330   
FCPMB | 7   
FD2BN | 190   
FD2SP | 88667   
FE2AA | 197   
FE2JK | 871   
FF2IM | 1271   
FG2DL | 428   
FG2EU | 67409   
FG2MW | 63932   
FG2NU | 181   
FJ2MW | 45   
FK2CS | 14886   
FM3CH | 83   
FM3KP | 23020   
FM3LD | 368   
FM3N5 | 17129   
FM3N9 | 20935   
FR3WS | 1290   
FS3WL | 455   
FT3JP | 34   
FT3WI | 1108   
FV4CH | 320   
FX4CS | 24371   
FY4N1 | 13624   
FZ4V1 | 589   
HARCH | 45   
HASFX | 491   
HCEBL | 106   
HDART | 13   
HDIV | 2691   
HGALE | 11327   
HGAME | 470   
HMED | 249   
HMEDF | 649   
HMEDV | 2706   
HMICR | 29   
HMOSE | 5   
HMVHS | 1073   
HNET | 11387   
HPER | 42   
HRECC | 4962   
HRECS | 227   
HREF | 386   
HRESV | 36   
HSEYD | 2686   
HSKAE | 1912   
HSPEC | 389   
HSTAC | 114937   
HWRIG | 1511   
MASRF | 10   
MCSV1 | 8784   
MCSV2 | 3368   
MCSV3 | 9329   
MCSV4 | 4087   
MDARC | 1202   
MDFAL | 666   
MDHON | 5814   
MDLBC | 716   
MDMST | 975   
MEACO | 22   
MEBOX | 50   
MEENA | 179   
MERES | 235   
MHCCM | 77   
MHCHO | 2   
MHEBL | 375   
MHEBP | 28   
MHEHP | 128   
MHIOP | 125   
MLEIB | 286   
MLEIF | 1194   
MLRC | 12   
MLRCF | 2   
MLRCR | 25   
MMAIN | 443941   
MMAUC | 35   
MMAUS | 8   
MMBFG | 1252   
MMCUT | 110298   
MMEBP | 80   
MMFAC | 256   
MMIC | 1289   
MMNSP | 12   
MMPER | 3003   
MMREF | 6754   
MMRSV | 13   
MMSTM | 202   
MMTCU | 1814   
MMTDA | 289   
MMTJU | 1840   
MMTLC | 5777   
MMTXT | 289   
MMVID | 5722   
MORSA | 44842   
MPEQU | 2   
MPMCD | 39   
MPOSC | 218   
MPPER | 52   
MPRAT | 17223   
MPRCD | 2516   
MPREF | 490   
MPRSV | 2   
MPVID | 349   
MQEQU | 5   
MSKMU | 734   
MSP11 | 4671   
MSP12 | 4808   
MSP13 | 6028   
MSP14 | 6576   
MSP15 | 6721   
MSP16 | 9558   
MSP17 | 9464   
MSP18 | 10155   
MSP19 | 9777   
MSP20 | 5265   
MSP51 | 21057   
RCCD | 538   
RCCDR | 24   
RCDB | 17   
RCDV | 5   
RCDVD | 184   
RCFAC | 684   
RCFIN | 2   
RCGEN | 22198   
RCHEX | 124   
RCKIN | 154   
RCMOR | 21   
RCMT | 9   
RCMTP | 7   
RCOS | 24   
RCRAR | 1179   
RCVHS | 168   
SACDR | 223   
SALS | 1202   
SALSO | 569   
SAMED | 26   
SAMIC | 990   
SAOVP | 1   
SAOVR | 615   
SAPER | 1609   
SAREF | 1067   
SARES | 5   
SARFO | 108   
SASB | 529   
SASTK | 73055   
SASTR | 12000   
SATHE | 212   
SATHEO | 2   
SAVD | 172   
SCA | 792   
SCDRN | 3   
SCINT | 997311   
SCINTL | 1   
SCINTx | 1   
SCMOA | 294   
SCPOP | 45   
SCSSC | 1858   
SDEAF | 1   
SHAW | 38094   
SJCDR | 48   
SJCR | 710   
SJMIC | 130   
SJO | 682   
SJPER | 118   
SJR78 | 4   
SJRB | 492   
SJREC | 10717   
SJRES | 1   
SJRF | 3866   
SJRFQ | 35   
SJRFT | 138   
SJRR | 6   
SJSB | 34535   
SJSB  | 867   
SJSFB | 2316   
SJSFF | 27   
SJSFS | 446   
SJSLP | 1842   
SJSMS | 1868   
SJSS | 23272   
SJTR | 6642   
SJTRF | 33   
SJTU | 24   
SJVD | 1038   
SJVDV | 2462   
SJVLD | 1   
SJXCD | 15161   
SJXCF | 198   
SJXCS | 190   
SNAUD | 174   
SNBRO | 5   
SNBUR | 642   
SNCAV | 329   
SNCDD | 1   
SNCDR | 6   
SNCDS | 3   
SNDVD | 7601   
SNEAL | 1238   
SNEAS | 16   
SNFRR | 3   
SNHBK | 1967   
SNKAN | 2   
SNMAR | 1   
SNMFC | 2   
SNMFL | 1   
SNOT | 2   
SNOVR | 7   
SNPAP | 2   
SNPER | 11   
SNPRL | 7   
SNPRM | 190   
SNPRO | 6   
SNRCD | 1   
SNREF | 101   
SNRES | 71   
SNSTK | 18   
SNTHE | 103   
SNUNK | 2   
SNVA | 1   
SNVD | 1   
SNVID | 1   
SNWFI | 279   
SPBRO | 714   
SRBR | 32418   
SRBRF | 685   
SSCDD | 186   
SSCDE | 9   
SSCMA | 111   
SSCSK | 4   
SSNCD | 20   
SSNFC | 3   
SSNFL | 4   
SSNMA | 72   
SSRVI | 3   
SSSSS | 1   
STNFL | 6   
SXSTK | 749385   
SXSTKS | 1   
SXSTL | 15707   
SXTHE | 10918   
UAAA | 60   
UARC | 1331   
UCD | 515   
UCDEV | 15   
UCOL | 59   
UCOLB | 13   
UDAVI | 893   
UDBKS | 5   
UDCDC | 50   
UDGEN | 8083   
UDMAS | 6678   
UDMF | 147201   
UEA | 24053   
UEARC | 930   
UEARF | 804   
UEARJ | 1042   
UEARK | 195   
UGEN | 1414120   
UGEN  | 31   
UICUR | 138   
UIJUV | 1637   
UILL | 1   
UIREG | 14476   
UIRES | 50   
UJUV | 5070   
ULAS | 136   
ULCDK | 3   
ULIBO | 1   
UMAAA | 8   
UMANX | 27154   
UMAP | 98   
UMCD | 260   
UMCR | 979   
UMCVP | 434   
UMDIG | 117   
UMDVD | 8812   
UMED | 30   
UMFF | 35826   
UMFIL | 577   
UMFM | 14890   
UMFP | 154   
UMFS | 73276   
UMLBW | 3088   
UMLDS | 45   
UMMCD | 15685   
UMMDV | 209   
UMMED | 44   
UMMFF | 27697   
UMMFG | 492   
UMMLP | 9865   
UMMON | 4776   
UMMTP | 182   
UMMVD | 269   
UMPA | 1   
UMPRF | 1   
UMREP | 12   
UMTPA | 2   
UMTXK | 523   
UMTXT | 1057   
UMVD | 3634   
UNASA | 4   
UNEA | 2376   
UNEWP | 25   
UPER | 8312   
UPERC | 63   
UPTRC | 123   
URES | 2   
URF | 1522   
URFD | 7   
URFM | 338   
URFS | 1   
URUD | 8936   
USCOS | 1   
USEED | 86   
USMF | 6   
USPC | 16402   
USPCX | 18789   
USPRF | 79   
USTOL | 110   
USTOY | 6316   
UTHES | 23995   
UWACS | 1381   
UWART | 1657   
UWBFL | 139   
UWBUR | 1057   
UWCES | 399   
UWCIA | 83   
UWCVE | 706   
UWDRO | 1166   
UWDSK | 45   
UWEAP | 5547   
UWEBD | 1   
UWEBL | 1356   
UWELS | 669   
UWETD | 7775   
UWFPL | 364   
UWGES | 601   
UWGRN | 553   
UWGVR | 1187   
UWIOP | 95   
UWLAS | 566   
UWLGB | 1824   
UWLLT | 10384   
UWMUS | 352   
UWNCC | 2248   
UWOCA | 7710   
UWOHO | 131   
UWPQC | 256689   
UWSAF | 47002   
UWSIA | 567   
UWSKQ | 3471   
UWSPR | 21093   
UWSYN | 983   
UWVCI | 245   
UWWSL | 335   
UWWW | 59753   
UWWWD | 5843   
UWWWR | 244   
YSTCK | 29789   
   
## Mapped Locations - 377 things   
Measure | Count   
--- | ---:   
19th Century UK Periodicals | 181   
AC & SC Springer eBooks | 88667   
AC & UM Japan Knowledge eResources | 871   
AC African Writers eBooks | 255   
AC American Slavery Collection | 111   
AC Archives & Special Collections | 49941   
AC Archives & Special Collections Depository | 34   
AC Cambridge Companions eBooks | 547   
AC Center for Russian Culture | 9001   
AC Center for Russian Culture Allen Collection | 285   
AC Center for Russian Culture Alma Law Theater Collection | 165   
AC Center for Russian Culture Art Collection | 1128   
AC Center for Russian Culture Fleishman Collection | 232   
AC Center for Russian Culture Ivas | 177   
AC Center for Russian Culture Kuzminsky Collection | 29   
AC Center for Russian Culture Reference | 183   
AC Center for Russian Culture Russian Jewish Periodicals | 41   
AC Center for Russian Culture Satirical Periodicals | 36   
AC Center for Russian Culture Special Collection | 618   
AC Center for Russian Culture Tara | 1584   
AC EBL ebooks | 412   
AC Early American Imprints I | 37370   
AC Early American Imprints II | 38094   
AC Frost Media CD-ROM | 168   
AC Frost Media VHS tape | 5390   
AC Frost Stacks - AFRST | 615810   
AC Frost reference desk | 925   
AC GeoScienceWorld ebooks | 176   
AC Music books | 1379   
AC Music periodicals | 21   
AC Music reference | 2042   
AC Music reserves | 98   
AC Music restricted | 37   
AC Music scores | 13994   
AC Music sound recordings | 23722   
AC Music storage | 346   
AC Science reference | 65   
AC Science reserves | 3   
ASP Classical Music Online | 7959   
ASP Classical Scores v1 | 24371   
ASP Classical Scores v3 | 14886   
ASP Dance in Video (volume 1) | 589   
ASP N American Immigrant Letters, Diaries... | 1271   
ASP N American Women's Letters & Diaries | 455   
ASP Women & Social Movement International | 1108   
ASP Women & Social Movements in US Scholars | 1290   
British Library Newspapers | 190   
Cambridge Histories Online - FM3CH | 83   
Cambridge Histories Online - FV4CH | 320   
Dict. of Literary Biography | 428   
Early European Books Online 1-14 | 67409   
FC E-Resources - FCDWC | 44   
FC E-Resources - FCDWJ | 1   
FC E-Resources - FCDWS | 248573   
FC E-Resources - FCEBR | 198424   
FC E-Resources - FCKNU | 1510   
FC Free E-Resources | 1017   
Five College Annex | 36898   
Five College Depository - FCDPM | 74077   
Five College Depository - FCDPS | 18353   
Five College Depository - UTHES | 23995   
HC Archives - HHARCH | 45   
HC Barry Moser Collection | 5   
HC CDisc | 4962   
HC Career Options | 251   
HC Current Periodicals | 42   
HC DART Program | 13   
HC Division III Archives | 2691   
HC Game Library | 470   
HC Internet - HASFX | 491   
HC Internet - HCEBL | 106   
HC Internet - HGALE | 11327   
HC Internet - HNET | 11387   
HC Kael Collection | 1912   
HC Media | 249   
HC Media Film Storage | 649   
HC Media Storage | 2706   
HC Microform | 29   
HC Reference | 386   
HC Reserves | 36   
HC Seydel Collection | 2686   
HC Special Collections | 389   
HC Spoken Word | 227   
HC VHS Tapes | 1073   
HC Women's Lives Collection | 1511   
Japanese Graded Readers | 34   
Kanopy Streaming Videos | 23020   
Loeb Classical Library | 368   
MH ASP Classical Scores Library - MCSV1 | 8784   
MH ASP Classical Scores Library - MCSV2 | 3368   
MH ASP Classical Scores Library - MCSV3 | 9329   
MH ASP Classical Scores Library - MCSV4 | 4087   
MH ASP Early Encounters in N America | 179   
MH Archives & Special Collections Reference | 10   
MH Archives - MDARC | 1202   
MH Archives - MDFAL | 666   
MH Cambridge Histories Online | 2   
MH Circulation Equipment | 5   
MH Cutter Collection | 110298   
MH EBL eBooks | 375   
MH EBSCOhost eBook Perpetual | 128   
MH Faculty Display | 256   
MH Honors Theses | 5814   
MH IOP eBooks | 125   
MH LRC | 12   
MH LRC Leisre Films | 2   
MH LRC Reserve | 25   
MH Leisure Films | 1194   
MH Leisure Reading | 286   
MH Master Theses | 975   
MH Media Video/DVD | 5722   
MH Media/CD-ROM | 35   
MH Media/Sound CD | 8   
MH Microforms | 1289   
MH Newspapers | 12   
MH O'Reilly Safari Books Online | 44842   
MH Oxford eBook Perpetual | 50   
MH Periodical Stacks | 3003   
MH Pratt Audio CD | 2516   
MH Pratt CD-ROM | 39   
MH Pratt Circulation Equipment | 2   
MH Pratt Orchestra Scores | 218   
MH Pratt Periodicals | 52   
MH Pratt Reference | 490   
MH Pratt Reserve | 2   
MH Pratt Stacks | 17223   
MH Pratt Video/DVD | 349   
MH Reference | 6754   
MH Reserve | 13   
MH Skinner Museum | 734   
MH Special Collections | 5777   
MH Special Collections/Books for Girls (in Cutter) | 1252   
MH Special Collections/Cutter Collection | 1814   
MH Special Collections/Dante Collection | 289   
MH Special Collections/Juvenile Collection | 1840   
MH Special Collections/Lady Borton Collection | 716   
MH Special Collections/Seminary Textbooks | 289   
MH Springer eBooks - MSP11 | 4671   
MH Springer eBooks - MSP12 | 4808   
MH Springer eBooks - MSP13 | 6028   
MH Springer eBooks - MSP14 | 6576   
MH Springer eBooks - MSP15 | 6721   
MH Springer eBooks - MSP16 | 9558   
MH Springer eBooks - MSP17 | 9464   
MH Springer eBooks - MSP18 | 10155   
MH Springer eBooks - MSP19 | 9777   
MH Springer eBooks - MSP20 | 5265   
MH Springer eBooks - MSP51 | 21057   
MH Stacks | 443941   
MH Stimson Room - Poetry | 202   
MH ebrary Perpetual | 28   
Making of the Modern World | 63932   
Manuscript Women's Letters and Diaries | 45   
NCCO Archives 1-4 | 13624   
NCCO Archives 5-8 | 17129   
NCCO Archives 9-12 | 20935   
Naxos Music Library | 110593   
Open Textbook Library | 330   
Project Muse OA eBooks | 7   
RC CD-ROM | 24   
RC Compact Disk | 538   
RC DVD | 184   
RC Docent's Bookshelf | 17   
RC Donahue | 5   
RC Facsimiles | 684   
RC Fine Books | 2   
RC Gen | 22198   
RC Hexter | 124   
RC Kinney | 154   
RC More | 21   
RC Music Tape - RCMT | 9   
RC Music Tape - RCMTP | 7   
RC Oversize | 24   
RC Rare Books | 1179   
RC VHS | 168   
SC Annex Stacks - SXSTK | 749385   
SC Annex Stacks - SXSTL | 15707   
SC Annex Theses | 10918   
SC Art | 73055   
SC Art CD Restricted | 223   
SC Art Locked Stack - SALS | 1202   
SC Art Locked Stack - SALSO | 569   
SC Art Microforms | 990   
SC Art Oversize | 615   
SC Art Oversized Periodicals | 1   
SC Art Periodical | 1609   
SC Art Reference | 1067   
SC Art Reference Oversize | 108   
SC Art Reserve | 5   
SC Art Restricted Circ | 12000   
SC Art Small Books | 529   
SC Art Theses | 212   
SC Art Video | 172   
SC Career Development Office | 74   
SC College Archives | 792   
SC Conway Center | 279   
SC House Book | 1967   
SC Internet | 997311   
SC Josten Book | 34535   
SC Josten CD Folio | 198   
SC Josten CD-ROM | 48   
SC Josten Cassette | 190   
SC Josten Choral Ref | 710   
SC Josten Compact Disc | 15161   
SC Josten DVD | 2462   
SC Josten Folio Book | 2316   
SC Josten Folio Score | 446   
SC Josten LP | 10717   
SC Josten Laserdisc | 1   
SC Josten Loan LP | 1842   
SC Josten Microform | 130   
SC Josten Mini Score | 1868   
SC Josten Orchestra | 682   
SC Josten Periodical | 118   
SC Josten Quick Ref | 35   
SC Josten RR Tape | 6   
SC Josten Rare Book | 492   
SC Josten Recording 78 | 4   
SC Josten Reference | 3866   
SC Josten Reserve | 1   
SC Josten Score | 23272   
SC Josten Thesis | 138   
SC Josten Treasure | 6642   
SC Josten Treasure Folio | 33   
SC Josten Tunnel | 24   
SC Josten Video | 1038   
SC Josten XFolio Score | 27   
SC Nielson UNK - HNSTAC | 114937   
SC Nielson UNK - SCDRN | 3   
SC Nielson UNK - SDEAF | 1   
SC Nielson UNK - SNBRO | 5   
SC Nielson UNK - SNCDD | 1   
SC Nielson UNK - SNCDR | 6   
SC Nielson UNK - SNCDS | 3   
SC Nielson UNK - SNFRR | 3   
SC Nielson UNK - SNKAN | 2   
SC Nielson UNK - SNMAR | 1   
SC Nielson UNK - SNMFC | 2   
SC Nielson UNK - SNOT | 2   
SC Nielson UNK - SNPAP | 2   
SC Nielson UNK - SNPRO | 6   
SC Nielson UNK - SNRCD | 1   
SC Nielson UNK - SNSTK | 18   
SC Nielson UNK - SNTHE | 103   
SC Nielson UNK - SNUNK | 2   
SC Nielson UNK - SNVD | 1   
SC Nielson UNK - SNYEAS | 16   
SC Nielson UNK - SNYOVR | 7   
SC Nielson UNK - SNYVID | 1   
SC Pop-Up Exhibit | 45   
SC Rare Book Room Ref | 685   
SC Rare Book Room Stacks | 32418   
SC Smith Museum | 294   
SC Sophia Smith Collection | 1858   
SC Special Collections browsing | 714   
SC Storage Film | 6   
SC Young Audio | 174   
SC Young Burack | 642   
SC Young Caverno | 329   
SC Young DVD | 7601   
SC Young East Asian Language | 1238   
SC Young Periodicals | 11   
SC Young Reference | 101   
SC Young Reserve | 71   
SC Young Reserve - Laptop | 7   
SC Young Reserve Permanent | 190   
Technical-Migration | 275683   
UM Audiocassette STORAGE | 182   
UM Collection Development | 15   
UM Collection Services - UAAA | 60   
UM Collection Services - UCOL | 59   
UM Current News & Mags-Lower Level Reading Area - UNEWP | 25   
UM Current News & Mags-Lower Level Reading Area - UPERC | 63   
UM Davis Collection | 893   
UM Digital Media Lab- 3rd Floor | 117   
UM Doc e-resource | 5843   
UM Du Bois Map Collection Atlases | 1   
UM Du Bois Map Collection Reference | 1   
UM Du Bois Reserves - UMREP | 12   
UM Du Bois Reserves - URES | 2   
UM East Asian | 24053   
UM East Asian Ref. Room | 804   
UM East Asian Ref. Room Read Chinese | 930   
UM East Asian Ref. Room Read Japanese | 1042   
UM East Asian Ref. Room Read Korean | 195   
UM Electronic Cover Record | 706   
UM Faculty Commons | 3   
UM Gov. Docs. | 8083   
UM Gov. Docs. Office | 50   
UM Interent Gender Studies | 601   
UM Interent Greenleaf | 553   
UM Internet - UWART | 1657   
UM Internet - UWBFL | 139   
UM Internet - UWEBD | 1   
UM Internet - UWEBL | 1356   
UM Internet - UWELS | 669   
UM Internet - UWETD | 7775   
UM Internet - UWMUS | 352   
UM Internet - UWOCA | 7710   
UM Internet - UWPQC | 256689   
UM Internet - UWSKQ | 3471   
UM Internet - UWSPR | 21093   
UM Internet - UWSYN | 983   
UM Internet - UWVCI | 245   
UM Internet - UWWSL | 335   
UM Internet - UWWW | 59753   
UM Internet Docuseek2 | 45   
UM Internet Drama Online | 1166   
UM Internet Early Arabic | 5547   
UM Internet Film Platform | 364   
UM Internet Gale in Context Environment Studies | 399   
UM Internet LGBTQ Culture | 1824   
UM Internet Latin Studies | 566   
UM Internet Library of Latin Texts | 10384   
UM Internet Oxford Handbooks Online | 131   
UM Internet-ACS | 1381   
UM Internet-CIAO | 83   
UM Internet-IOP | 95   
UM Internet-SIAM | 567   
UM Internet-Safari | 47002   
UM Internet-UWBUR | 1057   
UM Internet-UWNCC | 2248   
UM Juvenile | 5070   
UM LP STORAGE | 9865   
UM Laserdisc STORAGE | 45   
UM Latin American STORAGE | 136   
UM Law Materials STORAGE | 110   
UM Lebow STORAGE | 3088   
UM Library Office | 1   
UM MT IDA Curriculum Collection | 138   
UM MT IDA Juvenile Collection | 1637   
UM MT IDA Reserve Collection | 50   
UM Mass Docs STORAGE | 6678   
UM Media - UDMCD | 260   
UM Media - UMED | 30   
UM Media DVD - UMMDVD | 8812   
UM Media STORAGE | 3634   
UM Microcard STORAGE | 979   
UM Microfiche STORAGE - UMDMF | 147201   
UM Microfiche STORAGE - UMMMFF | 27697   
UM Microfilm STORAGE - UMMFM | 14890   
UM Microform STORAGE - UMMFS | 73276   
UM Microforms Guides | 492   
UM Microprint STORAGE | 154   
UM Mt IDA Regular Collection | 14476   
UM Music Media | 44   
UM Music Media CD - UMMMCD | 15685   
UM Music Media DVD | 209   
UM Music Media Video STORAGE - UMMMVD | 269   
UM Music Monument | 4776   
UM Music Ref- 6th FL | 338   
UM Near Eastern | 2376   
UM Print Cover Record | 434   
UM Reference e-resource - UWGVR | 1187   
UM Reference e-resource - UWWWR | 244   
UM Reserve - Films | 577   
UM Rudman Childrens Literature Col. | 8936   
UM Scholar Works Services | 1   
UM Science - USGEN | 1414120   
UM Science - USPER | 8312   
UM Science CD Cabinet | 515   
UM Science Microfiche | 35826   
UM Science NASA Collection | 4   
UM Science PTRC Consult Room | 123   
UM Science Reference | 1522   
UM Science Reference Desk | 7   
UM Science SEED Collection | 86   
UM Special Collections - UARC | 1331   
UM Special Collections - USPC | 16402   
UM Special Collections Annex | 18789   
UM Special Collections Maps | 98   
UM Special Collections Microforms | 6   
UM Special Collections Reference | 79   
UM Textbook Annex K Storage | 523   
UM Textbook Annex Storage | 1057   
UM U.S. Gov Docs STORAGE | 6316   
YB Yiddish Book Center | 29789   
   
## Incomplete entity mapping (a code issue) - 4 things   
Measure | Count   
--- | ---:   
852 | 14983569   
866 | 118058   
867 | 190   
868 | 1594   
   
## Locations - Unmapped legacy codes - 63 things   
Measure | Count   
--- | ---:   
ACDEP | 1230   
ACDPM | 103975   
AFASF | 1139   
AFASH | 199   
AFASL | 10811   
AFASO | 941   
AFASR | 210   
AFAST | 12434   
AFASTT | 1   
AFASV | 51   
AFASW | 964   
AFAV | 26   
AFBLU | 226   
AFCAS | 4   
AFDRM | 32   
AFDVD | 11578   
AFIN | 2505   
AFMAP | 273   
AFMIC | 482   
AFPER | 3811   
AFREF | 8954   
AFREP | 38   
AFRES | 6   
B392 1-6 | 1   
DEPOSITORY: 1 (1963)-29 (2008) 11.07.13 | 1   
DEPOSITORY: 1 (1984)-2 (1985); WITHDRAWN: 3 (1986)-24 (2007) 02.04.14; WITHDRAWN: 25 (2008)-27 (2010) 11.29.16 | 1   
DEPOSITORY: 1 (1990), 3 (1992)-4 (1993), 6 (1995)-11 (1999) 10.17.12; DEPOSITORY: 23 (2011); WITHDRAWN: 12 (2000)-22 (2010) 04.12.13; DEPOSITORY: 27 (2014)-28 (2015); WITHDRAWN: 24 (2012)-26 (2013) 11.20.17 | 1   
DEPOSITORY: 4 (2005)-6 (2007) 05.31.13 | 1   
DEPOSITORY: 44 (1949)-45 (1949); WITHDRAWN: 2 (1918)-43 (1948), 46 (1950)-65 (1959) 09.30.13 | 1   
FCJSD | 74646   
FCJSO | 6483   
FCJSP | 5519   
FE2AA | 197   
MEACO | 22   
MERES | 235   
MHCCM | 77   
MMEBP | 80   
SAMED | 26   
SATHEO | 2   
SCINTL | 1   
SCINTx | 1   
SJSB  | 867   
SNMFL | 1   
SNVA | 1   
SSCDD | 186   
SSCDE | 9   
SSCMA | 111   
SSCSK | 4   
SSNCD | 20   
SSNFC | 3   
SSNFL | 4   
SSNMA | 72   
SSRVI | 3   
SSSSS | 1   
SXSTKS | 1   
UCOLB | 13   
UDBKS | 5   
UGEN  | 31   
UILL | 1   
UMAAA | 8   
UMANX | 27154   
UMTPA | 2   
URFS | 1   
   
## Mapped electronic access relationships types - 4 things   
Measure | Count   
--- | ---:   
No information provided | 396549   
Related resource | 3562   
Resource | 4265928   
Version of resource | 184621   
   
## Mapped note types - 1 things   
Measure | Count   
--- | ---:   
Note | 13257   

## Mapped FOLIO fields   
FOLIO Field | Mapped | Empty | Unmapped  
--- | --- | --- | ---:  
acquisitionFormat | 0 (0%) | 0 | 7498739  
acquisitionMethod | 0 (0%) | 0 | 7498739  
bareHoldingsItems | 0 (0%) | 0 | 7498739  
callNumber | 7498384 (100%) | 0 | 355  
callNumberPrefix | 7498384 (100%) | 0 | 355  
callNumberSuffix | 7498384 (100%) | 0 | 355  
callNumberTypeId | 7498518 (100%) | 0 | 221  
copyNumber | 0 (0%) | 0 | 7498739  
digitizationPolicy | 0 (0%) | 0 | 7498739  
discoverySuppress | 0 (0%) | 0 | 7498739  
electronicAccess | 3020239 (40%) | 0 | 4478500  
formerIds | 0 (0%) | 0 | 7498739  
holdingsInstance | 0 (0%) | 0 | 7498739  
holdingsItems | 0 (0%) | 0 | 7498739  
holdingsStatements | 875 (0%) | 0 | 7497864  
holdingsStatementsForIndexes | 192 (0%) | 0 | 7498547  
holdingsStatementsForSupplements | 2 (0%) | 0 | 7498737  
holdingsTypeId | 7498518 (100%) | 0 | 221  
hrid | 0 (0%) | 0 | 7498739  
id | 7498518 (100%) | 0 | 221  
illPolicy | 0 (0%) | 0 | 7498739  
illPolicyId | 0 (0%) | 0 | 7498739  
instanceId | 7498518 (100%) | 0 | 221  
metadata | 7498518 (100%) | 0 | 221  
notes | 12837 (0%) | 0 | 7485902  
numberOfItems | 0 (0%) | 0 | 7498739  
permanentLocation | 0 (0%) | 0 | 7498739  
permanentLocationId | 7498518 (100%) | 0 | 221  
receiptStatus | 0 (0%) | 0 | 7498739  
receivingHistory | 0 (0%) | 0 | 7498739  
retentionPolicy | 0 (0%) | 0 | 7498739  
shelvingTitle | 7498384 (100%) | 0 | 355  
sourceId | 0 (0%) | 0 | 7498739  
statisticalCodeIds | 0 (0%) | 0 | 7498739  
tags | 0 (0%) | 0 | 7498739  
temporaryLocationId | 0 (0%) | 0 | 7498739  

## Mapped Legacy fields  
Legacy Field | Present | Mapped | Empty | Unmapped  
--- | --- | --- | --- | ---:  
001 | 7498739 (100.0%) | 0 (0%) | 0 | 7498739  
004 | 4309196 (57.5%) | 0 (0%) | 0 | 4309196  
005 | 7498739 (100.0%) | 0 (0%) | 0 | 7498739  
008 | 7498734 (100.0%) | 0 (0%) | 0 | 7498734  
035 | 6 (0.0%) | 0 (0%) | 0 | 6  
049 | 1 (0.0%) | 0 (0%) | 0 | 1  
056 | 1 (0.0%) | 0 (0%) | 0 | 1  
085 | 2 (0.0%) | 0 (0%) | 0 | 2  
086 | 1 (0.0%) | 0 (0%) | 0 | 1  
092 | 1 (0.0%) | 0 (0%) | 0 | 1  
0WN | 44 (0.0%) | 0 (0%) | 0 | 44  
112 | 1 (0.0%) | 0 (0%) | 0 | 1  
310 | 1 (0.0%) | 0 (0%) | 0 | 1  
500 | 3 (0.0%) | 0 (0%) | 0 | 3  
515 | 1 (0.0%) | 0 (0%) | 0 | 1  
589 | 3 (0.0%) | 0 (0%) | 0 | 3  
590 | 10650 (0.1%) | 0 (0%) | 0 | 10650  
592 | 1 (0.0%) | 0 (0%) | 0 | 1  
664 | 1 (0.0%) | 0 (0%) | 0 | 1  
686 | 1 (0.0%) | 0 (0%) | 0 | 1  
830 | 1 (0.0%) | 0 (0%) | 0 | 1  
841 | 1 (0.0%) | 0 (0%) | 0 | 1  
852 | 7498397 (100.0%) | 7498397 (100%) | 7498397 | 0  
853 | 14064 (0.2%) | 0 (0%) | 0 | 14064  
854 | 48 (0.0%) | 0 (0%) | 0 | 48  
855 | 16 (0.0%) | 0 (0%) | 0 | 16  
856 | 4852663 (64.7%) | 4852663 (65%) | 4852663 | 0  
865 | 7 (0.0%) | 0 (0%) | 0 | 7  
866 | 118934 (1.6%) | 118934 (2%) | 118934 | 0  
867 | 192 (0.0%) | 192 (0%) | 192 | 0  
868 | 1786 (0.0%) | 1786 (0%) | 1786 | 0  
886 | 1 (0.0%) | 0 (0%) | 0 | 1  
910 | 105 (0.0%) | 0 (0%) | 0 | 105  
928 | 109 (0.0%) | 0 (0%) | 0 | 109  
930 | 105 (0.0%) | 0 (0%) | 0 | 105  
932 | 3 (0.0%) | 0 (0%) | 0 | 3  
950 | 1 (0.0%) | 0 (0%) | 0 | 1  
952 | 790603 (10.5%) | 0 (0%) | 0 | 790603  
954 | 1 (0.0%) | 0 (0%) | 0 | 1  
956 | 27 (0.0%) | 0 (0%) | 0 | 27  
958 | 2 (0.0%) | 0 (0%) | 0 | 2  
962 | 1 (0.0%) | 0 (0%) | 0 | 1  
965 | 1 (0.0%) | 0 (0%) | 0 | 1  
966 | 8 (0.0%) | 0 (0%) | 0 | 8  
985 | 1 (0.0%) | 0 (0%) | 0 | 1  
CAN | 1 (0.0%) | 0 (0%) | 0 | 1  
FMT | 7498739 (100.0%) | 0 (0%) | 0 | 7498739  
H37 | 1 (0.0%) | 0 (0%) | 0 | 1  
IWB | 1 (0.0%) | 0 (0%) | 0 | 1  
LKR | 7498531 (100.0%) | 7498531 (100%) | 7498531 | 0  
NO. | 1 (0.0%) | 0 (0%) | 0 | 1  
OEN | 10 (0.0%) | 0 (0%) | 0 | 10  
ONW | 13 (0.0%) | 0 (0%) | 0 | 13  
OQN | 2 (0.0%) | 0 (0%) | 0 | 2  
OWH | 1 (0.0%) | 0 (0%) | 0 | 1  
OWM | 10 (0.0%) | 0 (0%) | 0 | 10  
OWN | 7507261 (100.1%) | 0 (0%) | 0 | 7507261  
PWM | 12 (0.0%) | 0 (0%) | 0 | 12  
PWN | 1 (0.0%) | 0 (0%) | 0 | 1  
SPA | 1 (0.0%) | 0 (0%) | 0 | 1  
STA | 5451 (0.1%) | 0 (0%) | 0 | 5451  
WON | 2 (0.0%) | 0 (0%) | 0 | 2  
`08 | 1 (0.0%) | 0 (0%) | 0 | 1  
`WN | 2 (0.0%) | 0 (0%) | 0 | 2  

   

# Item records transformation results   
Time Finished: 2020-11-25T10:14:23.882881   
## Item records transformation counters   
  Measure   | Count   
   
--- | ---:   
Duplicate item ids | 596,023   
Holdings id not in map | 44,133   
Missing location codes, adding "None" | 390,661   
Missing required field(s): materialTypeId | 1   
Missing required field(s): permanentLoanTypeId | 163   
Number of Items written to disk | 9,620,370   
Number of records in file(s) | 9,664,667   
Sucessfully transformed items | 9,620,370   
Temp location code: N | 8,953,463   
Temp location code: Y | 667,071   
Total failed items with Value errors | 44,297   
   
## Mapped loan types - 132 things   
Measure | Count   
--- | ---:   
2 Week: MHLIB - 09 | 287   
2 Week: MHPSL - 19 | 2755   
4 Week: HCLIB - 10 | 5638   
4 Week: HCLIB - 19 | 176   
4 Week: HCMED - 10 | 3365   
4 Week: MHLIB - 10 | 121013   
4 Week: MHLIB - 14 | 146434   
4 Week: MHLIB - 16 | 22760   
4 Week: MHSKM - 14 | 918   
4 Week: SCANN - 10 | 15   
4 Week: SCNLS - 10 | 2   
4 Week: UMDUB - 06 | 27211   
4 Week: UMDUB - 20 | 313811   
4 Week: UMDUB - 22 | 15695   
4 Week: UMDUB - 25 | 51174   
4 Week: UMDUB - 27 | 16794   
4 Week: UMMDA - 20 | 278   
4 Week: UMMDA - 22 | 38   
4 Week: UMSCI - 06 | 1   
4 Week: UMSCI - 20 | 35826   
4 Week: UMSCI - 25 | 28   
Comm Catalog: UMDUB - 28 | 1088   
Equipment 1 Day: UMMDA - 56 | 67   
Equipment 3 Day: MHLIB - 08 | 8   
Equipment 3 Day: MHPSL - 15 | 21   
Equipment 3 Day: UMDML - 55 | 99   
Equipment 3 Day: UMDML - 57 | 208   
Equipment 3 Day: UMMDA - 54 | 57   
Equipment 3 Day: UMMDA - 55 | 13   
Equipment 3 Day: UMMDA - 57 | 80   
Equipment 4 Hour: UMDML - 52 | 6   
Equipment 4 Hour: UMDML - 58 | 51   
Internet: HCLIB - 04 | 23316   
Internet: MHLIB - 04 | 166553   
Internet: SCANN - 04 | 7   
Internet: SCJOS - 04 | 3   
Internet: SCNLS - 04 | 998588   
Internet: UMDUB - 04 | 444322   
Limited: SCANN - 11 | 124387   
Limited: SCANN - 12 | 42   
Limited: SCANN - 13 | 3437   
Limited: SCANN - 14 | 1   
Limited: SCJOS - 11 | 988   
Limited: SCJOS - 12 | 19530   
Limited: SCJOS - 13 | 3542   
Limited: SCJOS - 14 | 16155   
Limited: SCNLS - 11 | 16   
Limited: SCNLS - 13 | 26   
Limited: SCYOU - 11 | 14   
Limited: SCYOU - 12 | 1   
Limited: UMDUB - 07 | 7501   
Non-Circulating: ACASP - 01 | 7   
Non-Circulating: ACASP - 02 | 120069   
Non-Circulating: ACDEP - 02 | 9   
Non-Circulating: ACFST - 02 | 17701   
Non-Circulating: ACMUS - 02 | 3018   
Non-Circulating: ACSCI - 02 | 206   
Non-Circulating: HCASC - 02 | 3730   
Non-Circulating: HCLIB - 02 | 2996   
Non-Circulating: HCMED - 02 | 886   
Non-Circulating: MHASC - 02 | 17715   
Non-Circulating: MHLIB - 02 | 11503   
Non-Circulating: MHPSL - 02 | 949   
Non-Circulating: SCANN - 02 | 1192   
Non-Circulating: SCANN - 03 | 19   
Non-Circulating: SCHIL - 02 | 7065   
Non-Circulating: SCHIL - 03 | 280   
Non-Circulating: SCJOS - 02 | 7948   
Non-Circulating: SCJOS - 03 | 6   
Non-Circulating: SCNLS - 02 | 26   
Non-Circulating: SCNLS - 03 | 2037   
Non-Circulating: SCSPC - 02 | 39854   
Non-Circulating: SCSPC - 03 | 311   
Non-Circulating: SCWST - 02 | 163   
Non-Circulating: SCYOU - 02 | 135   
Non-Circulating: UMDUB - 02 | 2070   
Non-Circulating: UMDUB - 03 | 26720   
Non-Circulating: UMDUB - 13 | 1628   
Non-Circulating: UMIMA - 02 | 19   
Non-Circulating: UMMDA - 52 | 2   
Non-Circulating: UMSCA - 02 | 44911   
Non-Circulating: UMSCA - 13 | 128   
Non-Circulating: UMSCI - 02 | 8   
Non-Circulating: UMSCI - 13 | 3142   
Reserve 1 Day : HCLIB - 13 | 2   
Reserve 1 Week : SCYOU - 25 | 6   
Reserve 3 Day: ACSCI - 24 | 1   
Reserve 4 Hour, due at closing: SCJOS - 21 | 240   
Reserve 4 Hour, due at closing: SCYOU - 21 | 11   
Reserve 4 Hour: ACFST - 22 | 479   
Reserve 4 Hour: ACMED - 22 | 7   
Reserve 4 Hour: ACMUS - 22 | 411   
Reserve 4 Hour: ACSCI - 22 | 286   
Reserve 4 Hour: HCLIB - 09 | 28   
Reserve 4 Hour: MHLIB - 11 | 36   
Reserve 4 Hour: MHLRC - 11 | 235   
Reserve 4 Hour: MHPSL - 11 | 13   
Reserve 4 Hour: SCANN - 20 | 3   
Reserve 4 Hour: SCJOS - 20 | 216   
Reserve 4 Hour: SCNLS - 20 | 790   
Reserve 4 Hour: SCNLS - 27 | 1   
Reserve 4 Hour: SCYOU - 20 | 788   
Reserve 4 Hour: UMDUB - 31 | 5   
Reserve 4 Hour: UMIDA - 31 | 73   
Reserve 4 Hour: UMMDA - 02 | 1699   
Reserve 4 Hour: UMMDA - 31 | 6656   
Semester: ACFST - 15 | 247   
Semester: SCYOU - 66 | 146   
Standard Loan: ACDEP - 01 | 123922   
Standard Loan: ACFST - 01 | 702223   
Standard Loan: ACFST - 16 | 342   
Standard Loan: ACMED - 01 | 2868   
Standard Loan: ACMUS - 01 | 22909   
Standard Loan: HCASC - 01 | 1   
Standard Loan: HCLIB - 01 | 157274   
Standard Loan: HCMED - 01 | 20   
Standard Loan: MHLIB - 01 | 526817   
Standard Loan: MHLRC - 01 | 2   
Standard Loan: MHPSL - 01 | 24078   
Standard Loan: MHPSL - 10 | 1675   
Standard Loan: SCANN - 01 | 943193   
Standard Loan: SCHIL - 01 | 77087   
Standard Loan: SCJOS - 01 | 69408   
Standard Loan: SCNLS - 01 | 802   
Standard Loan: SCSPC - 01 | 3764   
Standard Loan: SCWST - 01 | 5   
Standard Loan: SCYOU - 01 | 309   
Standard Loan: UMDML - 01 | 29   
Standard Loan: UMDUB - 01 | 1594936   
Standard Loan: UMIDA - 01 | 16969   
Standard Loan: UMMDA - 01 | 133   
Standard Loan: UMSCI - 01 | 162224   
   
## Mapped Material Types - 41 things   
Measure | Count   
--- | ---:   
ADMIN - ADMIN | 5181   
Analog Game - GAME | 464   
Archival Material - ARCH | 14560   
Artifact/Object - ARTI | 40   
Audio CD - AUDCD | 19757   
Audio CD - MUSCD | 33986   
Audio CD - SPOK | 933   
Audiocassette - ACASS | 688   
Book - BOOK | 4901641   
CD-ROM - CDROM | 2981   
Data File - DATA | 78   
Database - DATAB | 1014   
Database - ONRES | 11974   
E-Book - EBOOK | 2468110   
E-Book Package - EBKPK | 1   
E-Journal - EJOUR | 37463   
E-Journal Package - EJOUP | 1   
E-Score - EMUS | 25573   
E-Thesis/Dissertation - ETHES | 760   
E-Thesis/Dissertation - THES | 20275   
Equipment - CAMRA | 17   
Equipment - EQUIP | 7205   
Equipment - HDPHN | 9   
Equipment - KEY | 120   
Equipment - LAPTP | 65   
Film - FILM | 1624   
Government Publication - GPUB | 983   
Journal - ISSBD | 1351700   
Journal - ISSUE | 105607   
LP Phonorecord - LP | 31762   
Map - MAP | 3157   
Microform - MFILM | 62   
Microform - MICR | 232206   
Microform - MICRO | 49   
Newspaper - NEWS | 225   
Score - MUSIC | 109574   
Streaming Audio - EAUDI | 118657   
Streaming Audio - STRA | 2   
Streaming Video - STRV | 7747   
Supplement - SUPP | 129   
Videocassette - VCASS | 19273   
   
## Legacy item status - Not mapped - 40 things   
Measure | Count   
--- | ---:   
01 | 4685711   
02 | 369451   
03 | 29432   
04 | 2710138   
05 | 2462   
06 | 29954   
07 | 8742   
08 | 8   
09 | 315   
10 | 191690   
11 | 740937   
12 | 56366   
13 | 130972   
14 | 163528   
15 | 374   
16 | 23560   
17 | 25580   
18 | 28008   
19 | 2931   
20 | 353356   
21 | 305   
22 | 16972   
23 | 14   
24 | 15043   
25 | 53070   
27 | 16907   
28 | 1088   
31 | 6734   
32 | 3   
35 | 1   
36 | 1   
52 | 8   
54 | 57   
55 | 112   
56 | 67   
57 | 288   
58 | 51   
66 | 347   
76 | 1   
77 | 6   
   
## Field Contents - Z30_ITEM_STATUS - 41 things   
Measure | Count   
--- | ---:   
 | 77   
01 | 4685711   
02 | 369451   
03 | 29432   
04 | 2710138   
05 | 2462   
06 | 29954   
07 | 8742   
08 | 8   
09 | 315   
10 | 191690   
11 | 740937   
12 | 56366   
13 | 130972   
14 | 163528   
15 | 374   
16 | 23560   
17 | 25580   
18 | 28008   
19 | 2931   
20 | 353356   
21 | 305   
22 | 16972   
23 | 14   
24 | 15043   
25 | 53070   
27 | 16907   
28 | 1088   
31 | 6734   
32 | 3   
35 | 1   
36 | 1   
52 | 8   
54 | 57   
55 | 112   
56 | 67   
57 | 288   
58 | 51   
66 | 347   
76 | 1   
77 | 6   
   
## Missing location codes - 52 things   
Measure | Count   
--- | ---:   
ACDEP | 24165   
ACDPM | 123931   
AFASF | 1527   
AFASH | 871   
AFASL | 13974   
AFASO | 1332   
AFASR | 247   
AFAST | 12482   
AFASV | 59   
AFASW | 1254   
AFAV | 73   
AFBLU | 234   
AFCAS | 5   
AFCHI | 20   
AFDRM | 37   
AFDVD | 13780   
AFIN | 2508   
AFMAP | 567   
AFMIC | 5444   
AFPER | 37366   
AFREF | 16636   
AFREP | 102   
AFRES | 565   
FCJSD | 74646   
FCJSO | 6483   
FCJSP | 5519   
FE2AA | 194   
MEACO | 22   
MERES | 235   
MHCCM | 77   
MMEBP | 80   
NOCOD | 1   
SAMED | 26   
SSCDD | 308   
SSCMA | 137   
SSCRE | 17   
SSCSK | 16   
SSNCD | 31   
SSNFC | 2   
SSNFL | 1   
SSNMA | 93   
SSNPE | 1   
SSRPR | 5   
SSRPS | 725   
SSRRE | 35   
SSRVI | 3   
SSTXT | 146   
UDBKS | 5   
UDPER | 1   
UILL | 1   
UMANX | 44671   
URFS | 1   
   
## Circulation notes - 1 things   
Measure | Count   
--- | ---:   
Circ note | 196659   
   
## Unapped Material Types - 12 things   
Measure | Count   
--- | ---:   
unspecified - AUDIO | 16198   
unspecified - ENEWS | 21   
unspecified - ERES | 3837   
unspecified - EVIDE | 30495   
unspecified - KIT | 18   
unspecified - LASER | 1   
unspecified - LSRDC | 45   
unspecified - NOMAP | 59   
unspecified - NONPR | 14   
unspecified - PERBD | 31654   
unspecified - VDVD | 46062   
unspecified - WSITE | 532   
   
## Unmapped loan types - 106 things   
Measure | Count   
--- | ---:   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - ACASP - 10 | 5   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - ACDEP - 10 | 24165   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - ACFST - 04 | 79475   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - ACFST - 05 | 1   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - ACFST - 10 | 34758   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - ACFST - 18 | 26492   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - ACFST - 21 | 1   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - ACMUS - 10 | 125   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - ACMUS - 17 | 24706   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - ACMUS - 21 | 2   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - ACMUS - 23 | 7   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - ACRUS - 01 | 1   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - ACRUS - 02 | 23522   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - ACRUS - 03 | 8   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - ACSCI - 21 | 1   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - ACSCI - 23 | 2   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - FCANN - 01 | 38013   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - FCANN - 02 | 3   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - FCANN - 11 | 138499   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - FCANN - 12 | 1   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - FCANN - 13 | 1260   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - FCANN - 25 | 2   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - FCDPT - 01 | 196396   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - FCDPT - 02 | 24259   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - FCDPT - 11 | 252243   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - FCDPT - 12 | 91   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - FCDPT - 13 | 108400   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - FCWWW - 04 | 997874   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - HCFP  - 01 | 67   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - HCLIB - 05 | 1   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - HCLIB - 06 | 2662   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - HCLIB - 07 | 1239   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - HCLIB - 16 | 32   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - HCLIB - 18 | 305   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - HCLIB - 21 | 25   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - HCLIB - 77 | 3   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - MHASC - 01 | 80   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - MHASC - 14 | 3   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - MHLIB - 07 | 2   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - MHLIB - 18 | 1202   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - MHLRC - 15 | 92   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - MHLRC - 18 | 3   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - MHPSL - 16 | 417   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - REN   - 02 | 25965   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCANN - 18 | 3   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCANN - null | 41   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCHIL - 10 | 27   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCHIL - 11 | 17203   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCHIL - 12 | 17965   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCHIL - 13 | 240   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCHIL - 20 | 95   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCHIL - 21 | 9   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCHIL - null | 5   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCJOS - 05 | 2345   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCJOS - 18 | 3   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCJOS - 24 | 122   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCJOS - null | 17   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCNLS - 05 | 4   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCNLS - 22 | 1   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCNLS - 24 | 3   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCNLS - null | 14   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCSPC - 11 | 345   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCSPC - 12 | 1   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCSPC - 20 | 39   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCTYO - 01 | 3505   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCTYO - 02 | 372   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCTYO - 03 | 51   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCTYO - 10 | 902   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCTYO - 11 | 18   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCTYO - 13 | 9161   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCTYO - 20 | 1510   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCTYO - 22 | 52   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCTYO - 23 | 5   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCTYO - 24 | 7   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCTYO - 25 | 40   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCTYO - 27 | 112   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCTYO - 66 | 201   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCWST - 13 | 6   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCYOU - 05 | 110   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - SCYOU - 22 | 3   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - UMDPT - 02 | 5   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - UMDPT - 11 | 1   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - UMDUB - 05 | 1   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - UMDUB - 11 | 122378   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - UMDUB - 12 | 15419   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - UMDUB - 14 | 1   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - UMDUB - 21 | 16   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - UMDUB - 24 | 14910   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - UMIDA - 25 | 28   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - UMMDA - 06 | 80   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - UMMDA - 15 | 14   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - UMMDA - 16 | 8   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - UMMDA - 25 | 1   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - UMMDA - 32 | 3   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - UMMDA - 35 | 1   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - UMMDA - 36 | 1   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - UMSCA - 25 | 1791   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - UMSCA - 76 | 1   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - UMSCI - 11 | 84561   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - UMSCI - 12 | 3316   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - UMSCI - 14 | 16   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - UMSCI - 16 | 1   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - UMSCI - 17 | 874   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - UMSCI - 77 | 3   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - YMAIN - 01 | 16156   
('aafef5d1-fd94-4194-8908-27ca373c1191', 'Migration-technical') - YMAIN - 02 | 11453   

## Mapped FOLIO fields   
FOLIO Field | Mapped | Empty | Unmapped  
--- | --- | --- | ---:  
accessionNumber | 5198185 (54%) | 4466482 | 0  
barcode | 9664666 (100%) | 1 | 0  
chronology | 10992930 (114%) | 8292271 | -9620534  
circulationNotes | 196659 (2%) | 9468008 | 0  
copyNumber | 5641616 (58%) | 4023051 | 0  
descriptionOfPieces | 2269300 (23%) | 7395367 | 0  
discoverySuppress | 0 (0%) | 0 | 9664667  
effectiveCallNumberComponents | 0 (0%) | 0 | 9664667  
effectiveLocationId | 0 (0%) | 0 | 9664667  
electronicAccess | 0 (0%) | 0 | 9664667  
enumeration | 2530369 (26%) | 74433903 | -67299605  
formerIds | 9664667 (100%) | 0 | 0  
holdingsRecord2 | 0 (0%) | 0 | 9664667  
holdingsRecordId | 9664667 (100%) | 0 | 0  
hrid | 0 (0%) | 0 | 9664667  
id | 9664667 (100%) | 0 | 0  
inTransitDestinationServicePointId | 0 (0%) | 0 | 9664667  
itemDamagedStatusDate | 0 (0%) | 0 | 9664667  
itemDamagedStatusId | 0 (0%) | 0 | 9664667  
itemIdentifier | 0 (0%) | 0 | 9664667  
itemLevelCallNumber | 8898469 (92%) | 766198 | 0  
itemLevelCallNumberPrefix | 0 (0%) | 0 | 9664667  
itemLevelCallNumberSuffix | 0 (0%) | 0 | 9664667  
itemLevelCallNumberTypeId | 0 (0%) | 0 | 9664667  
lastCheckIn | 0 (0%) | 0 | 9664667  
materialType | 0 (0%) | 0 | 9664667  
materialTypeId | 9664589 (100%) | 78 | 0  
metaData | 9664667 (100%) | 0 | 0  
missingPieces | 0 (0%) | 0 | 9664667  
missingPiecesDate | 0 (0%) | 0 | 9664667  
notes | 5559906 (58%) | 33098762 | -28994001  
numberOfMissingPieces | 0 (0%) | 0 | 9664667  
numberOfPieces | 0 (0%) | 0 | 9664667  
permanentLoanTypeId | 9662154 (100%) | 2513 | 0  
permanentLocation | 0 (0%) | 0 | 9664667  
permanentLocationId | 9662083 (100%) | 2584 | 0  
purchaseOrderLineIdentifier | 0 (0%) | 0 | 9664667  
statisticalCodeIds | 172343 (2%) | 9492324 | 0  
status | 9664667 (100%) | 0 | 0  
status.name | 9664590 (100%) | 77 | 0  
tags | 0 (0%) | 0 | 9664667  
temporaryLoanTypeId | 0 (0%) | 0 | 9664667  
temporaryLocation | 0 (0%) | 0 | 9664667  
temporaryLocationId | 9620534 (100%) | 0 | 44133  
volume | 0 (0%) | 0 | 9664667  
yearCaption | 0 (0%) | 0 | 9664667  

## Mapped Legacy fields  
Legacy Field | Present | Mapped | Empty | Unmapped  
--- | --- | --- | --- | ---:  
Z30_85X_TYPE | 9620534 (99.5%) | 0 (0%) | 0 | 9620534  
Z30_ALPHA | 9664667 (100.0%) | 0 (0%) | 0 | 9664667  
Z30_ARRIVAL_DATE | 9664667 (100.0%) | 0 (0%) | 0 | 9664667  
Z30_BARCODE | 9664667 (100.0%) | 9664667 (100%) | 9664667 | 0  
Z30_CALL_NO | 9664667 (100.0%) | 9664667 (100%) | 9664667 | 0  
Z30_CALL_NO_2 | 9664667 (100.0%) | 0 (0%) | 0 | 9664667  
Z30_CALL_NO_2_KEY | 9664667 (100.0%) | 0 (0%) | 0 | 9664667  
Z30_CALL_NO_2_TYPE | 9664667 (100.0%) | 0 (0%) | 0 | 9664667  
Z30_CALL_NO_KEY | 9664667 (100.0%) | 0 (0%) | 0 | 9664667  
Z30_CALL_NO_TYPE | 9664667 (100.0%) | 0 (0%) | 0 | 9664667  
Z30_CATALOGER | 9664667 (100.0%) | 0 (0%) | 0 | 9664667  
Z30_CHRONOLOGICAL_I | 9620534 (99.5%) | 9620534 (100%) | 9620534 | 0  
Z30_CHRONOLOGICAL_J | 9620534 (99.5%) | 0 (0%) | 0 | 9620534  
Z30_CHRONOLOGICAL_K | 9620534 (99.5%) | 0 (0%) | 0 | 9620534  
Z30_CHRONOLOGICAL_L | 9620534 (99.5%) | 0 (0%) | 0 | 9620534  
Z30_CHRONOLOGICAL_M | 9620534 (99.5%) | 0 (0%) | 0 | 9620534  
Z30_COLLECTION | 9664667 (100.0%) | 9664667 (100%) | 9664667 | 0  
Z30_COPY_ID | 9664667 (100.0%) | 9664667 (100%) | 9664667 | 0  
Z30_DATE_LAST_RETURN | 9664667 (100.0%) | 0 (0%) | 0 | 9664667  
Z30_DEPOSITORY_ID | 9620534 (99.5%) | 0 (0%) | 0 | 9620534  
Z30_DESCRIPTION | 9664667 (100.0%) | 9664667 (100%) | 9664667 | 0  
Z30_ENUMERATION_A | 9620534 (99.5%) | 9620534 (100%) | 9620534 | 0  
Z30_ENUMERATION_B | 9620534 (99.5%) | 9620534 (100%) | 9620534 | 0  
Z30_ENUMERATION_C | 9620534 (99.5%) | 9620534 (100%) | 9620534 | 0  
Z30_ENUMERATION_D | 9620534 (99.5%) | 9620534 (100%) | 9620534 | 0  
Z30_ENUMERATION_E | 9620534 (99.5%) | 9620534 (100%) | 9620534 | 0  
Z30_ENUMERATION_F | 9620534 (99.5%) | 9620534 (100%) | 9620534 | 0  
Z30_ENUMERATION_G | 9620534 (99.5%) | 9620534 (100%) | 9620534 | 0  
Z30_ENUMERATION_H | 9620534 (99.5%) | 9620534 (100%) | 9620534 | 0  
Z30_EXPECTED_ARRIVAL_DATE | 9664667 (100.0%) | 0 (0%) | 0 | 9664667  
Z30_GAP_INDICATOR | 9620534 (99.5%) | 0 (0%) | 0 | 9620534  
Z30_HOL_DOC_NUMBER_X | 9664667 (100.0%) | 9664667 (100%) | 9664667 | 0  
Z30_HOUR_LAST_RETURN | 9664667 (100.0%) | 0 (0%) | 0 | 9664667  
Z30_INVENTORY_NUMBER | 9664667 (100.0%) | 9664667 (100%) | 9664667 | 0  
Z30_INVENTORY_NUMBER_DATE | 9664667 (100.0%) | 0 (0%) | 0 | 9664667  
Z30_IP_LAST_RETURN | 9664667 (100.0%) | 0 (0%) | 0 | 9664667  
Z30_IP_LAST_RETURN_V6 | 9620534 (99.5%) | 0 (0%) | 0 | 9620534  
Z30_ISSUE_DATE | 9664667 (100.0%) | 9664667 (100%) | 9664667 | 0  
Z30_ITEM_PROCESS_STATUS | 9664667 (100.0%) | 9664667 (100%) | 9664667 | 0  
Z30_ITEM_STATISTIC | 9664667 (100.0%) | 9664667 (100%) | 9664667 | 0  
Z30_ITEM_STATUS | 9664667 (100.0%) | 9664667 (100%) | 9664667 | 0  
Z30_LAST_SHELF_REPORT_DATE | 9664667 (100.0%) | 0 (0%) | 0 | 9664667  
Z30_LINKING_NUMBER | 9620534 (99.5%) | 0 (0%) | 0 | 9620534  
Z30_MAINTENANCE_COUNT | 9620534 (99.5%) | 0 (0%) | 0 | 9620534  
Z30_MATERIAL | 9664667 (100.0%) | 9664667 (100%) | 9664667 | 0  
Z30_NOTE_CIRCULATION | 9664667 (100.0%) | 9664667 (100%) | 9664667 | 0  
Z30_NOTE_INTERNAL | 9664667 (100.0%) | 9664667 (100%) | 9664667 | 0  
Z30_NOTE_OPAC | 9664667 (100.0%) | 9664667 (100%) | 9664667 | 0  
Z30_NO_LOANS | 9664667 (100.0%) | 0 (0%) | 0 | 9664667  
Z30_ON_SHELF_DATE | 9664667 (100.0%) | 0 (0%) | 0 | 9664667  
Z30_ON_SHELF_SEQ | 9664667 (100.0%) | 0 (0%) | 0 | 9664667  
Z30_OPEN_DATE | 9664667 (100.0%) | 0 (0%) | 0 | 9664667  
Z30_ORDER_NUMBER | 9664667 (100.0%) | 9664667 (100%) | 9664667 | 0  
Z30_PAGES | 9664667 (100.0%) | 0 (0%) | 0 | 9664667  
Z30_PRICE | 9664667 (100.0%) | 0 (0%) | 0 | 9664667  
Z30_PROCESS_STATUS_DATE | 9620534 (99.5%) | 0 (0%) | 0 | 9620534  
Z30_REC_KEY | 9664667 (100.0%) | 9664667 (100%) | 9664667 | 0  
Z30_REC_KEY_2 | 9664667 (100.0%) | 0 (0%) | 0 | 9664667  
Z30_REC_KEY_3 | 9664667 (100.0%) | 0 (0%) | 0 | 9664667  
Z30_SHELF_REPORT_NUMBER | 9664667 (100.0%) | 0 (0%) | 0 | 9664667  
Z30_SUB_LIBRARY | 9664667 (100.0%) | 9664667 (100%) | 9664667 | 0  
Z30_SUPP_INDEX_O | 9620534 (99.5%) | 0 (0%) | 0 | 9620534  
Z30_TEMP_LOCATION | 9620534 (99.5%) | 9620534 (100%) | 9620534 | 0  
Z30_UPDATE_DATE | 9664667 (100.0%) | 0 (0%) | 0 | 9664667  
Z30_UPD_TIME_STAMP | 9620534 (99.5%) | 0 (0%) | 0 | 9620534  
