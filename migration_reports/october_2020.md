Inventory migration report October 2020

- [Things to solve with this migration](#things-to-solve-with-this-migration)
- [Issues remaining or surfaced](#issues-remaining-or-surfaced)
- [Not Deduped Bibliographic records transformation results](#not-deduped-bibliographic-records-transformation-results)
  * [Bibliographic records transformation counters](#bibliographic-records-transformation-counters)
  * [Unmapped MARC tags](#unmapped-marc-tags)
  * [Mapped FOLIO fields](#mapped-folio-fields)
  * [Unmapped FOLIO fields](#unmapped-folio-fields)
  * [Unmapped conditions in rules](#unmapped-conditions-in-rules)
  * [Record status counts](#record-status-counts)
  * [Unrecognized language codes in records - 1609 things](#unrecognized-language-codes-in-records---1609-things)
  * [Records failed to migrate due to Value errors found in Transformation - 292 things](#records-failed-to-migrate-due-to-value-errors-found-in-transformation---292-things)
  * [Bib records that failed to parse. - - 12 things](#bib-records-that-failed-to-parse-----12-things)
- [DEDUPED Bibliographic records transformation results](#deduped-bibliographic-records-transformation-results)
  * [Bibliographic records transformation counters](#bibliographic-records-transformation-counters-1)
  * [Unmapped MARC tags](#unmapped-marc-tags-1)
  * [Mapped FOLIO fields](#mapped-folio-fields-1)
  * [Unmapped FOLIO fields](#unmapped-folio-fields-1)
  * [Unmapped conditions in rules](#unmapped-conditions-in-rules-1)
  * [Record status counts](#record-status-counts-1)
  * [Unrecognized language codes in records - 867 things](#unrecognized-language-codes-in-records---867-things)
  * [Records failed to migrate due to Value errors found in Transformation - 116 things](#records-failed-to-migrate-due-to-value-errors-found-in-transformation---116-things)
  * [Bib records that failed to parse. - - 2 things](#bib-records-that-failed-to-parse-----2-things)
- [Holdings transformation results](#holdings-transformation-results)
  * [Stats](#stats)
  * [Legacy locations](#legacy-locations)
  * [FOLIO locations](#folio-locations)
  * [Unmapped location codes](#unmapped-location-codes)
  * [Call number types (852 $2) values](#call-number-types--852--2--values)
  * [Unmapped FOLIO fields](#unmapped-folio-fields-2)
  * [Mapped FOLIO Fields](#mapped-folio-fields)
  * [Failed records that needs to get fixed](#failed-records-that-needs-to-get-fixed)
  * [Top missing holdings ids](#top-missing-holdings-ids)
  * [Top duplicate item ids](#top-duplicate-item-ids)
  * [Item transformation counters](#item-transformation-counters)
  * [Mapped loan types - 162 things](#mapped-loan-types---162-things)
  * [Mapped Material Types - 41 things](#mapped-material-types---41-things)
  * [Field Contents - Z30_ITEM_STATUS - 42 things](#field-contents---z30-item-status---42-things)
  * [Missing location codes - 48 things](#missing-location-codes---48-things)
  * [Unapped Material Types - 15 things](#unapped-material-types---15-things)
  * [Unmapped loan types - 112 things](#unmapped-loan-types---112-things)
  * [Mapped FOLIO fields](#mapped-folio-fields-2)
  * [Mapped Legacy fields](#mapped-legacy-fields)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>


# Things to solve with this migration
*  if an item does not have a material type that maps, it can be assigned "unspecified"
*  implement item material type (and order type) mappings from https://docs.google.com/spreadsheets/d/1uT6sQ-dyY77BfEDOzC4U4UohnOWcbuXEJ6cHL0SaAXQ/edit#gid=703283660
The Z30 exports should have the code
* Implement Loan type mapping. Example: The Z30 item status for circulation is only unique when accounting for the sublibrary+ the item status ID.  for example.
SubLibrary SCNLS and Item status 01 map to "Standard Loan" https://docs.google.com/spreadsheets/d/118rzzMuOQunI4mhUOnYu8bgedmDjM75n2nNZ-EcAErc/edit#gid=489348141
# Issues remaining or surfaced 
* Records with 583 http://eastlibraries.org/retained-materials url are being duplicated. Discuss, dedupe or move to another level (Holdings, Item)
* 337 not mapped (lloking at https://docs.google.com/spreadsheets/d/11lGBiPoetHuC3u-onVVLN4Mj5KtVHqJaQe4RqCxgGzo/edit#gid=1871391984, it seems like it has the same target as the 338. Will add this.
* Item map not updated with latest work on Item mapping
* 657 Local classification? 
* 019, 730 not mapped, 
* 77X etc, check the community (leace 776 be) 
* Count number of actual identifiers
* Count unspecifide Material Types
* Discuss item status at separate meeting ...process_stataus (count and discuss)
* Give Aron breakdown of the unmapped loan types
# Not Deduped Bibliographic records transformation results
Time Run: 2020-10-30T18:46:34.170350
## Bibliographic records transformation counters
  Measure   | Count
--- | ---:
Bib records that faile transformation | 292
Bibs processed | 3,110,819
Incomplete entity mapping - 060 | 1
Incomplete entity mapping - 082 | 2
Incomplete entity mapping - 090 | 4,995
Incomplete entity mapping - 100 | 44
Incomplete entity mapping - 110 | 8
Incomplete entity mapping - 130 | 3
Incomplete entity mapping - 246 | 46
Incomplete entity mapping - 260 | 393,753
Incomplete entity mapping - 264 | 491,488
Incomplete entity mapping - 500 | 33
Incomplete entity mapping - 504 | 1
Incomplete entity mapping - 505 | 49
Incomplete entity mapping - 508 | 1
Incomplete entity mapping - 520 | 275
Incomplete entity mapping - 538 | 4
Incomplete entity mapping - 540 | 2
Incomplete entity mapping - 545 | 1
Incomplete entity mapping - 546 | 2
Incomplete entity mapping - 555 | 1
Incomplete entity mapping - 586 | 1
Incomplete entity mapping - 590 | 12,348
Incomplete entity mapping - 700 | 17
Incomplete entity mapping - 710 | 13
Incomplete entity mapping - 740 | 1
MARC21 Records successfully parsed | 3,110,807
MARC21 Records with encoding errors - parsing failed | 12
MARC21 records in file before parsing | 3,110,819
Number of Instances in map | 3,110,515
Successfully transformed bibs | 3,110,515
Total number of Tags processed | 94,984,288
Value Errors | 292
## Unmapped MARC tags
A list of the records not covered by the mapping rules. These rules can be customized to cover more fields. The counts next to the field name is the number of records with this field.
Tag | Count
--- | ---:
003 | 2,027,511
005 | 3,110,807
006 | 2,052,462
007 | 2,944,973
012 | 1,918
018 | 4
019 | 175,346
026 | 19
031 | 12
033 | 107,838
034 | 9,788
036 | 2
037 | 253,461
039 | 15,342
040 | 2,805,598
042 | 210,650
043 | 681,781
044 | 1,364
045 | 67,525
046 | 6,311
047 | 56,474
048 | 111,360
051 | 2,778
052 | 12,786
065 | 1
066 | 21,930
069 | 1
070 | 6,458
072 | 947,226
083 | 170
084 | 65,575
085 | 59
088 | 86,821
092 | 19,806
093 | 1
096 | 698
098 | 6,507
099 | 475,417
164 | 1
210 | 4,720
242 | 75
243 | 48
256 | 10,081
257 | 6,006
258 | 1
261 | 101
263 | 2,169
270 | 65
306 | 118,974
307 | 1
321 | 5,898
337 | 2,203,977
340 | 5,635
341 | 38
342 | 3
343 | 2
344 | 80,533
345 | 1,074
346 | 5,055
347 | 426,960
348 | 3,700
351 | 652
352 | 10
361 | 1
363 | 6
365 | 45,345
366 | 54
370 | 124
377 | 1
380 | 8,264
381 | 11
382 | 30,208
383 | 704
384 | 140
385 | 67
386 | 618
388 | 23
539 | 102
591 | 1
647 | 1,282
648 | 38,025
654 | 29
656 | 13
657 | 334,787
658 | 3
662 | 3
690 | 85,734
691 | 8
699 | 12
712 | 1
730 | 597,436
751 | 4
752 | 318,132
753 | 359
755 | 6
758 | 60
760 | 303
762 | 9
765 | 90
767 | 35
770 | 869
772 | 467
773 | 351,086
774 | 116
775 | 3,279
776 | 1,373,327
777 | 296
780 | 17,416
785 | 14,480
786 | 23
787 | 6,288
793 | 15,661
796 | 4,122
797 | 69,594
850 | 5,322
851 | 1
852 | 6,921
853 | 12
854 | 1
859 | 5
863 | 12
865 | 1
866 | 16
880 | 181,936
883 | 12
884 | 14
886 | 198
887 | 31,079
928 | 231,388
## Mapped FOLIO fields
The number of times a certain FOLIO field was filled with information
Fielname | Count
--- | ---:
alternativeTitles | 685,055
classifications | 1,486,142
contributors | 3,046,011
discoverySuppress | 3,110,515
editions | 240,487
electronicAccess | 183,665
hrid | 1
id | 3,110,515
identifiers | 3,110,515
indexTitle | 3,110,438
instanceFormatIds | 2,172,305
instanceTypeId | 3,110,515
languages | 2,972,168
metadata | 3,110,515
notes | 3,036,797
physicalDescriptions | 3,041,417
publication | 2,640,196
publicationFrequency | 54,034
publicationRange | 46,938
series | 1,657,775
source | 3,110,515
staffSuppress | 3,110,515
subjects | 3,005,744
title | 3,110,515
## Unmapped FOLIO fields
The number of records missing certain FOLIO fields
Tag | Count
--- | ---:
alternativeTitles | 2,425,460
catalogedDate | 3,110,515
classifications | 1,624,373
contributors | 64,504
editions | 2,870,028
electronicAccess | 2,926,850
holdingsRecords2 | 3,110,515
hrid | 3,110,514
instanceFormatIds | 938,210
instanceFormats | 3,110,515
matchKey | 3,110,515
modeOfIssuanceId | 3,110,515
natureOfContentTermIds | 3,110,515
notes | 73,718
physicalDescriptions | 69,098
previouslyHeld | 3,110,515
publication | 470,319
publicationFrequency | 3,056,481
publicationRange | 3,063,577
series | 1,452,740
sourceRecordFormat | 3,110,515
statisticalCodeIds | 3,110,515
statusId | 3,110,515
statusUpdatedDate | 3,110,515
subjects | 104,771
tags | 3,110,515
## Unmapped conditions in rules
Conditions from the mapping-rules never covered by the transformation
Measure | Number
--- | ---:
## Record status counts
Record status in the records from Leader in position 05   Valid values are a - Increase in encoding level, c - Corrected or revised, d - Deleted, n - New, p - Increase in encoding level from prepublication
Measure | Number
--- | ---:
  | 12,227
I | 2
a | 686
c | 1,246,469
e | 38
g | 5
m | 438
n | 1,800,370
o | 3
p | 5,599
r | 5
s | 315
u | 44,650
## Unrecognized language codes in records - 1609 things
src not recognized for ['000061278']\
pah not recognized for ['000079777']\
ing not recognized for ['000095583']\
hed not recognized for ['000115119']\
itn not recognized for ['000116697']\
ebg not recognized for ['000131168']\
unk not recognized for ['000153854']\
cro not recognized for ['000190287']\
ser not recognized for ['000192044']\
egg not recognized for ['000212916']\
enf not recognized for ['000229365']\
fer not recognized for ['000316620']\
upn not recognized for ['000383756']\
jpa not recognized for ['000394360']\
end not recognized for ['000401465']\
lag not recognized for ['000461617']\
azh not recognized for ['000472587']\
sen not recognized for ['000490603']\
for not recognized for ['000500952']\
crf not recognized for ['000502846']\
cyr not recognized for ['000505529']\
ebg not recognized for ['000507821']\
for not recognized for ['000511178']\
rur not recognized for ['000532872']\
end not recognized for ['000533363']\
ene not recognized for ['000542292']\
sap not recognized for ['000542998']\
end not recognized for ['000550801']\
egn not recognized for ['000555167']\
emg not recognized for ['000555687']\
unk not recognized for ['000569050']\
enf not recognized for ['000598822']\
emg not recognized for ['000603874']\
ukn not recognized for ['000604393']\
rur not recognized for ['000614093']\
dur not recognized for ['000616664']\
sil not recognized for ['000621540']\
frc not recognized for ['000628049']\
enf not recognized for ['000639093']\
hop not recognized for ['000657192']\
can not recognized for ['000660435']\
fer not recognized for ['000661917']\
cro not recognized for ['000663205']\
rur not recognized for ['000664846']\
arb not recognized for ['000679229']\
ahm not recognized for ['000690895']\
ahm not recognized for ['000690896']\
ahm not recognized for ['000690899']\
urk not recognized for ['000697206']\
spn not recognized for ['000701791']\
end not recognized for ['000703202']\
jpa not recognized for ['000708737']\
cep not recognized for ['000715807']\
emg not recognized for ['000719558']\
ser not recognized for ['000728346']\
dcj not recognized for ['000738771']\
dcj not recognized for ['000738771']\
hed not recognized for ['000739792']\
dcg not recognized for ['000793116']\
dcg not recognized for ['000793116']\
dur not recognized for ['000808702']\
crf not recognized for ['000810839']\
ebg not recognized for ['000811619']\
ebg not recognized for ['000824608']\
fer not recognized for ['000834241']\
grk not recognized for ['000838847']\
emg not recognized for ['000936915']\
hed not recognized for ['000938851']\
lag not recognized for ['001023729']\
lag not recognized for ['001219232']\
azh not recognized for ['001226393']\
enf not recognized for ['001301202']\
enf not recognized for ['001327646']\
enk not recognized for ['001407404']\
enf not recognized for ['001408449']\
fer not recognized for ['001408493']\
cse not recognized for ['001476025']\
jpm not recognized for ['001495557']\
cae not recognized for ['001501510']\
zzx not recognized for ['001510427']\
emg not recognized for ['001543615']\
gen not recognized for ['001547566']\
emg not recognized for ['001550805']\
hed not recognized for ['001553195']\
gen not recognized for ['001581853']\
emg not recognized for ['001667031']\
end not recognized for ['001723349']\
enf not recognized for ['001797945']\
reg not recognized for ['001797945']\
lag not recognized for ['001962762']\
dur not recognized for ['001990017']\
snn not recognized for ['002001468']\
for not recognized for ['002001469']\
crf not recognized for ['002003079']\
ebg not recognized for ['002008261']\
for not recognized for ['002012060']\
ser not recognized for ['002018267']\
end not recognized for ['002034299']\
dng not recognized for ['002053392']\
emg not recognized for ['002056767']\
pre not recognized for ['002057563']\
tuv not recognized for ['002079428']\
ser not recognized for ['002097853']\
dna not recognized for ['002098710']\
dna not recognized for ['002098710']\
ebg not recognized for ['002100892']\
emg not recognized for ['002101100']\
end not recognized for ['002103031']\
ent not recognized for ['002120610']\
sil not recognized for ['002121523']\
hop not recognized for ['002162914']\
pun not recognized for ['002166445']\
fle not recognized for ['002166915']\
fer not recognized for ['002169105']\
pun not recognized for ['002183578']\
hiu not recognized for ['002222522']\
ngm not recognized for ['002877799']\
ngm not recognized for ['002877799']\
egr not recognized for ['003183640']\
fer not recognized for ['003202382']\
efa not recognized for ['003251773']\
u   not recognized for ['003326070']\
u   not recognized for ['003326070']\
aba not recognized for ['003631611']\
end not recognized for ['003684034']\
grk not recognized for ['003830600']\
enf not recognized for ['003844511']\
hed not recognized for ['003863234']\
enf not recognized for ['003864123']\
dur not recognized for ['003998778']\
enf not recognized for ['003998913']\
enf not recognized for ['003999507']\
egn not recognized for ['003999612']\
emg not recognized for ['004008434']\
fle not recognized for ['004094701']\
ila not recognized for ['004239940']\
ser not recognized for ['004296380']\
uru not recognized for ['004307725']\
can not recognized for ['004309254']\
hiu not recognized for ['004421140']\
emg not recognized for ['004447925']\
enk not recognized for ['004462793']\
spe not recognized for ['004933481']\
end not recognized for ['010631148']\
unk not recognized for ['010803174']\
emg not recognized for ['010858848']\
unk not recognized for ['010885180']\
can not recognized for ['011052964']\
cge not recognized for ['011090332']\
cge not recognized for ['011090332']\
cen not recognized for ['011090343']\
cen not recognized for ['011090343']\
aen not recognized for ['011090357']\
aen not recognized for ['011090357']\
bdu not recognized for ['011090390']\
bdu not recognized for ['011090390']\
cge not recognized for ['011090392']\
cge not recognized for ['011090392']\
cen not recognized for ['011090405']\
cen not recognized for ['011090405']\
cen not recognized for ['011090407']\
cen not recognized for ['011090407']\
aen not recognized for ['011090447']\
aen not recognized for ['011090447']\
cen not recognized for ['011090538']\
cen not recognized for ['011090538']\
cdu not recognized for ['011090563']\
cdu not recognized for ['011090563']\
cen not recognized for ['011090564']\
cen not recognized for ['011090564']\
cfr not recognized for ['011090598']\
cfr not recognized for ['011090598']\
cen not recognized for ['011090631']\
cen not recognized for ['011090631']\
cen not recognized for ['011090632']\
cen not recognized for ['011090632']\
cen not recognized for ['011090657']\
cen not recognized for ['011090657']\
cen not recognized for ['011090660']\
cen not recognized for ['011090660']\
bdu not recognized for ['011090719']\
bdu not recognized for ['011090719']\
cfr not recognized for ['011090729']\
cfr not recognized for ['011090729']\
bdu not recognized for ['011090742']\
bdu not recognized for ['011090742']\
cfr not recognized for ['011090762']\
cfr not recognized for ['011090762']\
bfr not recognized for ['011090774']\
bfr not recognized for ['011090774']\
bfr not recognized for ['011090776']\
bfr not recognized for ['011090776']\
cge not recognized for ['011090781']\
cge not recognized for ['011090781']\
cge not recognized for ['011090782']\
cge not recognized for ['011090782']\
bfr not recognized for ['011090792']\
bfr not recognized for ['011090792']\
cfr not recognized for ['011090827']\
cfr not recognized for ['011090827']\
aen not recognized for ['011090846']\
aen not recognized for ['011090846']\
cge not recognized for ['011090851']\
cge not recognized for ['011090851']\
cge not recognized for ['011090857']\
cge not recognized for ['011090857']\
bfr not recognized for ['011090892']\
bfr not recognized for ['011090892']\
cfr not recognized for ['011090902']\
cfr not recognized for ['011090902']\
cfr not recognized for ['011090914']\
cfr not recognized for ['011090914']\
bdu not recognized for ['011090936']\
bdu not recognized for ['011090936']\
bge not recognized for ['011090942']\
bge not recognized for ['011090942']\
cen not recognized for ['011090973']\
cen not recognized for ['011090973']\
cen not recognized for ['011090999']\
cen not recognized for ['011090999']\
cen not recognized for ['011091031']\
cen not recognized for ['011091031']\
cen not recognized for ['011091034']\
cen not recognized for ['011091034']\
cen not recognized for ['011091047']\
cen not recognized for ['011091047']\
aen not recognized for ['011091056']\
aen not recognized for ['011091056']\
aen not recognized for ['011091057']\
aen not recognized for ['011091057']\
bfr not recognized for ['011091074']\
bfr not recognized for ['011091074']\
cen not recognized for ['011091096']\
cen not recognized for ['011091096']\
bdu not recognized for ['011091102']\
bdu not recognized for ['011091102']\
aen not recognized for ['011091154']\
aen not recognized for ['011091154']\
cen not recognized for ['011091181']\
cen not recognized for ['011091181']\
cfr not recognized for ['011091205']\
cfr not recognized for ['011091205']\
bdu not recognized for ['011091213']\
bdu not recognized for ['011091213']\
cge not recognized for ['011091221']\
cge not recognized for ['011091221']\
cfr not recognized for ['011091233']\
cfr not recognized for ['011091233']\
cfr not recognized for ['011091236']\
cfr not recognized for ['011091236']\
cen not recognized for ['011091240']\
aen not recognized for ['011091296']\
aen not recognized for ['011091296']\
cge not recognized for ['011091348']\
cge not recognized for ['011091348']\
cfr not recognized for ['011091364']\
cfr not recognized for ['011091364']\
bfr not recognized for ['011091365']\
bfr not recognized for ['011091365']\
bfr not recognized for ['011091402']\
bfr not recognized for ['011091402']\
cge not recognized for ['011091424']\
cge not recognized for ['011091424']\
cge not recognized for ['011091429']\
cge not recognized for ['011091429']\
bfr not recognized for ['011091432']\
bfr not recognized for ['011091432']\
cfr not recognized for ['011091438']\
cfr not recognized for ['011091438']\
bfr not recognized for ['011091439']\
bfr not recognized for ['011091439']\
cen not recognized for ['011091467']\
cen not recognized for ['011091467']\
cen not recognized for ['011091481']\
cen not recognized for ['011091481']\
cen not recognized for ['011091500']\
cen not recognized for ['011091500']\
cge not recognized for ['011091540']\
cge not recognized for ['011091540']\
cge not recognized for ['011091567']\
cge not recognized for ['011091567']\
age not recognized for ['011091568']\
age not recognized for ['011091568']\
cge not recognized for ['011091570']\
cge not recognized for ['011091570']\
aen not recognized for ['011091581']\
aen not recognized for ['011091581']\
bfr not recognized for ['011091648']\
bfr not recognized for ['011091648']\
bfr not recognized for ['011091649']\
bfr not recognized for ['011091649']\
cen not recognized for ['011091654']\
cen not recognized for ['011091654']\
cfr not recognized for ['011091689']\
cfr not recognized for ['011091689']\
cfr not recognized for ['011091694']\
cfr not recognized for ['011091694']\
aen not recognized for ['011091715']\
bge not recognized for ['011091726']\
cfr not recognized for ['011091802']\
cfr not recognized for ['011091802']\
bfr not recognized for ['011091803']\
bfr not recognized for ['011091803']\
cge not recognized for ['011091821']\
cge not recognized for ['011091821']\
bge not recognized for ['011091822']\
bge not recognized for ['011091822']\
aen not recognized for ['011091832']\
aen not recognized for ['011091832']\
cfr not recognized for ['011091838']\
cfr not recognized for ['011091838']\
cge not recognized for ['011091855']\
cge not recognized for ['011091855']\
cge not recognized for ['011091863']\
cge not recognized for ['011091863']\
cge not recognized for ['011091873']\
cge not recognized for ['011091873']\
bit not recognized for ['011091941']\
bit not recognized for ['011091941']\
bfr not recognized for ['011091951']\
bfr not recognized for ['011091951']\
aen not recognized for ['011091957']\
aen not recognized for ['011091957']\
cge not recognized for ['011092002']\
cge not recognized for ['011092002']\
cge not recognized for ['011092017']\
cge not recognized for ['011092017']\
cge not recognized for ['011092028']\
cge not recognized for ['011092028']\
cge not recognized for ['011092055']\
cge not recognized for ['011092055']\
dge not recognized for ['011092060']\
dge not recognized for ['011092060']\
bfr not recognized for ['011092109']\
bfr not recognized for ['011092109']\
bdu not recognized for ['011092153']\
bdu not recognized for ['011092153']\
cen not recognized for ['011092162']\
cen not recognized for ['011092162']\
cen not recognized for ['011092232']\
cen not recognized for ['011092232']\
cen not recognized for ['011092250']\
cen not recognized for ['011092250']\
cen not recognized for ['011092299']\
cen not recognized for ['011092299']\
aen not recognized for ['011092321']\
aen not recognized for ['011092321']\
cen not recognized for ['011092342']\
cen not recognized for ['011092342']\
cla not recognized for ['011092348']\
cla not recognized for ['011092348']\
bfr not recognized for ['011092420']\
bfr not recognized for ['011092420']\
cge not recognized for ['011092423']\
cge not recognized for ['011092423']\
cfr not recognized for ['011092424']\
cfr not recognized for ['011092424']\
cfr not recognized for ['011092425']\
cfr not recognized for ['011092425']\
cen not recognized for ['011092456']\
cen not recognized for ['011092456']\
cen not recognized for ['011092469']\
cen not recognized for ['011092469']\
bdu not recognized for ['011092506']\
bdu not recognized for ['011092506']\
cge not recognized for ['011092532']\
cge not recognized for ['011092532']\
aen not recognized for ['011092538']\
aen not recognized for ['011092538']\
cge not recognized for ['011092550']\
cge not recognized for ['011092550']\
aen not recognized for ['011092581']\
aen not recognized for ['011092581']\
bdu not recognized for ['011092591']\
bdu not recognized for ['011092591']\
cge not recognized for ['011092604']\
cge not recognized for ['011092604']\
cdu not recognized for ['011092611']\
cdu not recognized for ['011092611']\
cen not recognized for ['011092648']\
cen not recognized for ['011092648']\
cge not recognized for ['011092669']\
cge not recognized for ['011092669']\
cen not recognized for ['011092704']\
cen not recognized for ['011092704']\
bfr not recognized for ['011092732']\
bfr not recognized for ['011092732']\
cen not recognized for ['011092834']\
cen not recognized for ['011092834']\
bdu not recognized for ['011092871']\
bdu not recognized for ['011092871']\
cge not recognized for ['011093023']\
cge not recognized for ['011093023']\
cge not recognized for ['011093038']\
cge not recognized for ['011093038']\
cge not recognized for ['011093082']\
cge not recognized for ['011093082']\
cfr not recognized for ['011093119']\
cfr not recognized for ['011093119']\
cen not recognized for ['011093150']\
cen not recognized for ['011093150']\
bda not recognized for ['011093207']\
bda not recognized for ['011093207']\
bdu not recognized for ['011093224']\
bdu not recognized for ['011093224']\
age not recognized for ['011093239']\
age not recognized for ['011093239']\
bge not recognized for ['011093290']\
bge not recognized for ['011093290']\
cdu not recognized for ['011093319']\
cdu not recognized for ['011093319']\
cen not recognized for ['011093329']\
cen not recognized for ['011093329']\
age not recognized for ['011093350']\
age not recognized for ['011093350']\
cfr not recognized for ['011093398']\
cfr not recognized for ['011093398']\
bge not recognized for ['011093420']\
bge not recognized for ['011093420']\
cen not recognized for ['011093510']\
cen not recognized for ['011093510']\
cen not recognized for ['011093537']\
cen not recognized for ['011093537']\
bge not recognized for ['011093540']\
bge not recognized for ['011093540']\
bsw not recognized for ['011093561']\
bsw not recognized for ['011093561']\
bfr not recognized for ['011093586']\
bfr not recognized for ['011093586']\
cen not recognized for ['011093594']\
cen not recognized for ['011093594']\
cen not recognized for ['011093605']\
cen not recognized for ['011093605']\
cen not recognized for ['011093642']\
cen not recognized for ['011093642']\
cen not recognized for ['011093664']\
cen not recognized for ['011093664']\
bfr not recognized for ['011093714']\
bfr not recognized for ['011093714']\
bfr not recognized for ['011093717']\
bfr not recognized for ['011093717']\
bfr not recognized for ['011093718']\
bfr not recognized for ['011093718']\
age not recognized for ['011093738']\
age not recognized for ['011093738']\
cen not recognized for ['011093759']\
cen not recognized for ['011093759']\
cen not recognized for ['011093776']\
cen not recognized for ['011093776']\
bfr not recognized for ['011093823']\
bfr not recognized for ['011093823']\
cge not recognized for ['011093846']\
cge not recognized for ['011093846']\
bdu not recognized for ['011093848']\
bdu not recognized for ['011093848']\
cen not recognized for ['011093866']\
cen not recognized for ['011093866']\
cen not recognized for ['011093927']\
cen not recognized for ['011093927']\
cfr not recognized for ['011093975']\
cfr not recognized for ['011093975']\
cen not recognized for ['011094008']\
cen not recognized for ['011094008']\
cge not recognized for ['011094010']\
cge not recognized for ['011094010']\
cen not recognized for ['011094019']\
cen not recognized for ['011094019']\
cdu not recognized for ['011094030']\
cdu not recognized for ['011094030']\
adu not recognized for ['011094034']\
adu not recognized for ['011094034']\
cen not recognized for ['011094037']\
cen not recognized for ['011094037']\
cen not recognized for ['011094061']\
cen not recognized for ['011094061']\
rua not recognized for ['011126605']\
sil not recognized for ['011249361']\
sil not recognized for ['011249368']\
sil not recognized for ['011249370']\
fer not recognized for ['011251413']\
sil not recognized for ['011293819']\
sil not recognized for ['011314625']\
sil not recognized for ['011335506']\
sil not recognized for ['011336930']\
sil not recognized for ['011336932']\
pji not recognized for ['011566230']\
mex not recognized for ['011793967']\
pcc not recognized for ['012186597']\
pcc not recognized for ['012186597']\
oth not recognized for ['012462482']\
dge not recognized for ['012510466']\
end not recognized for ['012758831']\
emg not recognized for ['013217267']\
occ not recognized for ['013451627']\
occ not recognized for ['013453799']\
scf not recognized for ['013456944']\
cmn not recognized for ['013472350']\
cmn not recognized for ['013472361']\
zho not recognized for ['013472361']\
rur not recognized for ['013749117']\
eun not recognized for ['013767082']\
udt not recognized for ['013982484']\
udt not recognized for ['013982488']\
udt not recognized for ['013982491']\
unk not recognized for ['014211858']\
unk not recognized for ['014229690']\
lta not recognized for ['014619832']\
lml not recognized for ['014795479']\
aba not recognized for ['014827287']\
now not recognized for ['014884668']\
oth not recognized for ['014959104']\
msh not recognized for ['015186722']\
nyb not recognized for ['015186722']\
hab not recognized for ['015187689']\
 |  not recognized for ['015188688']\
 |  not recognized for ['015188688']\
0 | not recognized for ['015188949']\
0 | not recognized for ['015188949']\
| | not recognized for ['015189319']\
| | not recognized for ['015189319']\
 |  not recognized for ['015189465']\
 |  not recognized for ['015189465']\
byi not recognized for ['015189511']\
1 | not recognized for ['015189584']\
1 | not recognized for ['015189584']\
 |  not recognized for ['015189729']\
 |  not recognized for ['015189729']\
1 | not recognized for ['015189750']\
1 | not recognized for ['015189750']\
1 | not recognized for ['015189878']\
1 | not recognized for ['015189878']\
 |  not recognized for ['015189882']\
 |  not recognized for ['015189882']\
dyi not recognized for ['015189900']\
dyi not recognized for ['015189900']\
|   not recognized for ['015189906']\
|   not recognized for ['015189906']\
 |  not recognized for ['015189914']\
 |  not recognized for ['015189914']\
 |  not recognized for ['015189917']\
 |  not recognized for ['015189917']\
  | not recognized for ['015190069']\
  | not recognized for ['015190069']\
0 | not recognized for ['015190101']\
0 | not recognized for ['015190101']\
 |  not recognized for ['015190166']\
 |  not recognized for ['015190166']\
 |  not recognized for ['015190196']\
 |  not recognized for ['015190196']\
 |  not recognized for ['015190239']\
 |  not recognized for ['015190239']\
1 | not recognized for ['015190268']\
1 | not recognized for ['015190268']\
d | not recognized for ['015190279']\
d | not recognized for ['015190279']\
 |  not recognized for ['015190291']\
 |  not recognized for ['015190291']\
 |  not recognized for ['015190329']\
 |  not recognized for ['015190329']\
0 | not recognized for ['015190343']\
0 | not recognized for ['015190343']\
 |  not recognized for ['015190866']\
 |  not recognized for ['015190866']\
 |  not recognized for ['015190874']\
 |  not recognized for ['015190874']\
  | not recognized for ['015190876']\
  | not recognized for ['015190876']\
 |  not recognized for ['015190956']\
 |  not recognized for ['015190956']\
d | not recognized for ['015191053']\
d | not recognized for ['015191053']\
 |  not recognized for ['015191054']\
 |  not recognized for ['015191054']\
 |  not recognized for ['015191057']\
 |  not recognized for ['015191057']\
 |  not recognized for ['015191059']\
 |  not recognized for ['015191059']\
 |  not recognized for ['015191061']\
 |  not recognized for ['015191061']\
 |  not recognized for ['015191064']\
 |  not recognized for ['015191064']\
 |  not recognized for ['015191068']\
 |  not recognized for ['015191068']\
 |  not recognized for ['015191076']\
 |  not recognized for ['015191076']\
 |  not recognized for ['015191101']\
 |  not recognized for ['015191101']\
 |  not recognized for ['015191104']\
 |  not recognized for ['015191104']\
 |  not recognized for ['015191110']\
 |  not recognized for ['015191110']\
 |  not recognized for ['015191111']\
 |  not recognized for ['015191111']\
| | not recognized for ['015191142']\
| | not recognized for ['015191142']\
 |  not recognized for ['015191151']\
 |  not recognized for ['015191151']\
 |  not recognized for ['015191156']\
 |  not recognized for ['015191156']\
 |  not recognized for ['015191171']\
 |  not recognized for ['015191171']\
 |  not recognized for ['015191186']\
 |  not recognized for ['015191186']\
| | not recognized for ['015191191']\
| | not recognized for ['015191191']\
1 | not recognized for ['015191208']\
1 | not recognized for ['015191208']\
 |  not recognized for ['015191211']\
 |  not recognized for ['015191211']\
 |  not recognized for ['015191219']\
 |  not recognized for ['015191219']\
| | not recognized for ['015191220']\
| | not recognized for ['015191220']\
 |  not recognized for ['015191331']\
 |  not recognized for ['015191331']\
|yi not recognized for ['015191371']\
|yi not recognized for ['015191371']\
| | not recognized for ['015191408']\
| | not recognized for ['015191408']\
| | not recognized for ['015191425']\
| | not recognized for ['015191425']\
0 | not recognized for ['015191469']\
0 | not recognized for ['015191469']\
 |  not recognized for ['015191519']\
 |  not recognized for ['015191519']\
0 | not recognized for ['015191560']\
0 | not recognized for ['015191560']\
 |0 not recognized for ['015191562']\
 |0 not recognized for ['015191562']\
| | not recognized for ['015191567']\
| | not recognized for ['015191567']\
 |  not recognized for ['015191577']\
 |  not recognized for ['015191577']\
| | not recognized for ['015191605']\
| | not recognized for ['015191605']\
| | not recognized for ['015191618']\
| | not recognized for ['015191618']\
| | not recognized for ['015191636']\
| | not recognized for ['015191636']\
| | not recognized for ['015191637']\
| | not recognized for ['015191637']\
0dy not recognized for ['015191639']\
0dy not recognized for ['015191639']\
| | not recognized for ['015191641']\
| | not recognized for ['015191641']\
 |  not recognized for ['015191644']\
 |  not recognized for ['015191644']\
| | not recognized for ['015191655']\
| | not recognized for ['015191655']\
| | not recognized for ['015191686']\
| | not recognized for ['015191686']\
| | not recognized for ['015191704']\
| | not recognized for ['015191704']\
 |  not recognized for ['015191716']\
 |  not recognized for ['015191716']\
0dy not recognized for ['015191730']\
0dy not recognized for ['015191730']\
byi not recognized for ['015191733']\
byi not recognized for ['015191733']\
| | not recognized for ['015191737']\
| | not recognized for ['015191737']\
 |  not recognized for ['015191738']\
 |  not recognized for ['015191738']\
 |  not recognized for ['015191774']\
 |  not recognized for ['015191774']\
 |  not recognized for ['015191785']\
 |  not recognized for ['015191785']\
 |  not recognized for ['015191787']\
 |  not recognized for ['015191787']\
 |  not recognized for ['015191800']\
 |  not recognized for ['015191800']\
 |  not recognized for ['015191805']\
 |  not recognized for ['015191805']\
| | not recognized for ['015191911']\
| | not recognized for ['015191911']\
 |  not recognized for ['015191917']\
 |  not recognized for ['015191917']\
| 0 not recognized for ['015192117']\
| 0 not recognized for ['015192117']\
0dy not recognized for ['015192184']\
0dy not recognized for ['015192184']\
 |  not recognized for ['015192217']\
 |  not recognized for ['015192217']\
tid not recognized for ['015192224']\
tid not recognized for ['015192224']\
p | not recognized for ['015192231']\
p | not recognized for ['015192231']\
| | not recognized for ['015192252']\
| | not recognized for ['015192252']\
 |  not recognized for ['015192255']\
 |  not recognized for ['015192255']\
| | not recognized for ['015192279']\
| | not recognized for ['015192279']\
 |  not recognized for ['015192290']\
 |  not recognized for ['015192290']\
 |  not recognized for ['015192313']\
 |  not recognized for ['015192313']\
 |  not recognized for ['015192330']\
 |  not recognized for ['015192330']\
0 | not recognized for ['015192331']\
0 | not recognized for ['015192331']\
0 | not recognized for ['015192343']\
0 | not recognized for ['015192343']\
 |  not recognized for ['015192345']\
 |  not recognized for ['015192345']\
0 | not recognized for ['015192357']\
0 | not recognized for ['015192357']\
| | not recognized for ['015192361']\
| | not recognized for ['015192361']\
| 0 not recognized for ['015192362']\
| 0 not recognized for ['015192362']\
 |  not recognized for ['015192384']\
 |  not recognized for ['015192384']\
1 | not recognized for ['015192385']\
1 | not recognized for ['015192385']\
 |  not recognized for ['015192402']\
 |  not recognized for ['015192402']\
 |  not recognized for ['015192403']\
 |  not recognized for ['015192403']\
 |  not recognized for ['015192414']\
 |  not recognized for ['015192414']\
 |  not recognized for ['015192425']\
 |  not recognized for ['015192425']\
 |  not recognized for ['015192439']\
 |  not recognized for ['015192439']\
p | not recognized for ['015192445']\
p | not recognized for ['015192445']\
 |  not recognized for ['015192446']\
 |  not recognized for ['015192446']\
p | not recognized for ['015192474']\
p | not recognized for ['015192474']\
0dy not recognized for ['015192506']\
0dy not recognized for ['015192506']\
 |  not recognized for ['015192509']\
 |  not recognized for ['015192509']\
  | not recognized for ['015192514']\
  | not recognized for ['015192514']\
 |  not recognized for ['015192525']\
 |  not recognized for ['015192525']\
 |  not recognized for ['015192612']\
 |  not recognized for ['015192612']\
 |  not recognized for ['015192625']\
 |  not recognized for ['015192625']\
0 | not recognized for ['015192677']\
0 | not recognized for ['015192677']\
 |  not recognized for ['015192741']\
 |  not recognized for ['015192741']\
 |  not recognized for ['015192772']\
 |  not recognized for ['015192772']\
| | not recognized for ['015192782']\
| | not recognized for ['015192782']\
 |  not recognized for ['015192788']\
 |  not recognized for ['015192788']\
 |  not recognized for ['015192789']\
 |  not recognized for ['015192789']\
 |  not recognized for ['015192790']\
 |  not recognized for ['015192790']\
 |  not recognized for ['015192793']\
 |  not recognized for ['015192793']\
 |  not recognized for ['015192795']\
 |  not recognized for ['015192795']\
 |  not recognized for ['015192796']\
 |  not recognized for ['015192796']\
 |  not recognized for ['015192797']\
 |  not recognized for ['015192797']\
 |  not recognized for ['015192798']\
 |  not recognized for ['015192798']\
 |  not recognized for ['015192799']\
 |  not recognized for ['015192799']\
 |  not recognized for ['015192801']\
 |  not recognized for ['015192801']\
 |  not recognized for ['015192803']\
 |  not recognized for ['015192803']\
 |  not recognized for ['015192807']\
 |  not recognized for ['015192807']\
 |  not recognized for ['015192808']\
 |  not recognized for ['015192808']\
 |  not recognized for ['015192809']\
 |  not recognized for ['015192809']\
| | not recognized for ['015192810']\
| | not recognized for ['015192810']\
 |  not recognized for ['015192813']\
 |  not recognized for ['015192813']\
 |  not recognized for ['015192814']\
 |  not recognized for ['015192814']\
| | not recognized for ['015192815']\
| | not recognized for ['015192815']\
1 | not recognized for ['015192821']\
1 | not recognized for ['015192821']\
 |  not recognized for ['015192828']\
 |  not recognized for ['015192828']\
 |  not recognized for ['015192829']\
 |  not recognized for ['015192829']\
 |  not recognized for ['015192833']\
 |  not recognized for ['015192833']\
1 | not recognized for ['015192838']\
1 | not recognized for ['015192838']\
 |  not recognized for ['015192840']\
 |  not recognized for ['015192840']\
 |  not recognized for ['015192841']\
 |  not recognized for ['015192841']\
 |  not recognized for ['015192842']\
 |  not recognized for ['015192842']\
 |  not recognized for ['015192843']\
 |  not recognized for ['015192843']\
 |  not recognized for ['015192844']\
 |  not recognized for ['015192844']\
| | not recognized for ['015192845']\
| | not recognized for ['015192845']\
 |  not recognized for ['015192848']\
 |  not recognized for ['015192848']\
p | not recognized for ['015192850']\
p | not recognized for ['015192850']\
 |  not recognized for ['015192861']\
 |  not recognized for ['015192861']\
 |  not recognized for ['015192867']\
 |  not recognized for ['015192867']\
 |  not recognized for ['015192870']\
 |  not recognized for ['015192870']\
0dy not recognized for ['015192871']\
0dy not recognized for ['015192871']\
 |  not recognized for ['015192872']\
 |  not recognized for ['015192872']\
 |  not recognized for ['015192894']\
 |  not recognized for ['015192894']\
| | not recognized for ['015192901']\
| | not recognized for ['015192901']\
 |  not recognized for ['015192910']\
 |  not recognized for ['015192910']\
dyi not recognized for ['015192936']\
dyi not recognized for ['015192936']\
| 0 not recognized for ['015192937']\
| 0 not recognized for ['015192937']\
 |  not recognized for ['015192938']\
 |  not recognized for ['015192938']\
p | not recognized for ['015192939']\
p | not recognized for ['015192939']\
0 | not recognized for ['015192943']\
0 | not recognized for ['015192943']\
| | not recognized for ['015192947']\
| | not recognized for ['015192947']\
 |  not recognized for ['015192957']\
 |  not recognized for ['015192957']\
 |  not recognized for ['015192963']\
 |  not recognized for ['015192963']\
d | not recognized for ['015192964']\
d | not recognized for ['015192964']\
| | not recognized for ['015192966']\
| | not recognized for ['015192966']\
| | not recognized for ['015192967']\
| | not recognized for ['015192967']\
 |  not recognized for ['015192972']\
 |  not recognized for ['015192972']\
0 | not recognized for ['015192979']\
0 | not recognized for ['015192979']\
| | not recognized for ['015192983']\
| | not recognized for ['015192983']\
0 | not recognized for ['015192986']\
0 | not recognized for ['015192986']\
 |  not recognized for ['015192997']\
 |  not recognized for ['015192997']\
 |  not recognized for ['015193005']\
 |  not recognized for ['015193005']\
 |  not recognized for ['015193011']\
 |  not recognized for ['015193011']\
 |  not recognized for ['015193036']\
 |  not recognized for ['015193036']\
 |  not recognized for ['015193039']\
 |  not recognized for ['015193039']\
 |  not recognized for ['015193054']\
 |  not recognized for ['015193054']\
| | not recognized for ['015193056']\
| | not recognized for ['015193056']\
 |  not recognized for ['015193061']\
 |  not recognized for ['015193061']\
 |  not recognized for ['015193065']\
 |  not recognized for ['015193065']\
 |  not recognized for ['015193067']\
 |  not recognized for ['015193067']\
 |  not recognized for ['015193070']\
 |  not recognized for ['015193070']\
| | not recognized for ['015193080']\
| | not recognized for ['015193080']\
 |  not recognized for ['015193082']\
 |  not recognized for ['015193082']\
 |  not recognized for ['015193083']\
 |  not recognized for ['015193083']\
 |  not recognized for ['015193084']\
 |  not recognized for ['015193084']\
 |  not recognized for ['015193085']\
 |  not recognized for ['015193085']\
 |  not recognized for ['015193086']\
 |  not recognized for ['015193086']\
 |  not recognized for ['015193091']\
 |  not recognized for ['015193091']\
 |  not recognized for ['015193094']\
 |  not recognized for ['015193094']\
 |  not recognized for ['015193095']\
 |  not recognized for ['015193095']\
 |  not recognized for ['015193107']\
 |  not recognized for ['015193107']\
 |  not recognized for ['015193113']\
 |  not recognized for ['015193113']\
| | not recognized for ['015193114']\
| | not recognized for ['015193114']\
 |  not recognized for ['015193118']\
 |  not recognized for ['015193118']\
1 | not recognized for ['015193125']\
1 | not recognized for ['015193125']\
 |  not recognized for ['015193181']\
 |  not recognized for ['015193181']\
 |  not recognized for ['015193190']\
 |  not recognized for ['015193190']\
byi not recognized for ['015195871']\
byi not recognized for ['015195871']\
 |  not recognized for ['015195882']\
 |  not recognized for ['015195882']\
| | not recognized for ['015196581']\
| | not recognized for ['015196581']\
| | not recognized for ['015196587']\
| | not recognized for ['015196587']\
| | not recognized for ['015196807']\
| | not recognized for ['015196807']\
| | not recognized for ['015196825']\
| | not recognized for ['015196825']\
| | not recognized for ['015196952']\
| | not recognized for ['015196952']\
cty not recognized for ['015197043']\
msh not recognized for ['015197043']\
nyb not recognized for ['015197043']\
msh not recognized for ['015197049']\
nyb not recognized for ['015197049']\
byi not recognized for ['015197183']\
byi not recognized for ['015197183']\
dyi not recognized for ['015197329']\
dyi not recognized for ['015197329']\
| | not recognized for ['015197866']\
| | not recognized for ['015197866']\
| | not recognized for ['015197981']\
| | not recognized for ['015197981']\
gid not recognized for ['015198276']\
|   not recognized for ['015198697']\
|   not recognized for ['015198697']\
00  not recognized for ['015199077']\
1 | not recognized for ['015199079']\
1 | not recognized for ['015199079']\
0 | not recognized for ['015199081']\
0 | not recognized for ['015199081']\
 |  not recognized for ['015199087']\
 |  not recognized for ['015199087']\
0 | not recognized for ['015199090']\
0 | not recognized for ['015199090']\
1 | not recognized for ['015199091']\
1 | not recognized for ['015199091']\
1 | not recognized for ['015199094']\
1 | not recognized for ['015199094']\
0 | not recognized for ['015199095']\
| | not recognized for ['015199098']\
| | not recognized for ['015199098']\
0 | not recognized for ['015199120']\
0 | not recognized for ['015199120']\
| | not recognized for ['015199121']\
| | not recognized for ['015199121']\
0 | not recognized for ['015199131']\
| | not recognized for ['015199133']\
| | not recognized for ['015199133']\
|0  not recognized for ['015199167']\
|0  not recognized for ['015199167']\
1 y not recognized for ['015199174']\
1 y not recognized for ['015199174']\
1 y not recognized for ['015199180']\
1 y not recognized for ['015199180']\
00  not recognized for ['015199181']\
00  not recognized for ['015199181']\
dyi not recognized for ['015199190']\
dyi not recognized for ['015199190']\
dyi not recognized for ['015199192']\
dyi not recognized for ['015199193']\
dyi not recognized for ['015199193']\
0 y not recognized for ['015199197']\
0 y not recognized for ['015199197']\
0 y not recognized for ['015199202']\
0 y not recognized for ['015199202']\
0 y not recognized for ['015199211']\
0 y not recognized for ['015199211']\
0 y not recognized for ['015199216']\
0 y not recognized for ['015199216']\
| | not recognized for ['015199241']\
| | not recognized for ['015199241']\
| | not recognized for ['015199242']\
| | not recognized for ['015199242']\
byi not recognized for ['015199255']\
0 y not recognized for ['015199261']\
0 y not recognized for ['015199261']\
dyi not recognized for ['015199281']\
dyi not recognized for ['015199281']\
ayi not recognized for ['015199285']\
ayi not recognized for ['015199285']\
1 y not recognized for ['015199288']\
1 y not recognized for ['015199288']\
0 y not recognized for ['015199292']\
0 y not recognized for ['015199292']\
00  not recognized for ['015199296']\
00  not recognized for ['015199296']\
0 y not recognized for ['015199302']\
0 y not recognized for ['015199302']\
dyi not recognized for ['015199305']\
dyi not recognized for ['015199305']\
1 | not recognized for ['015199320']\
1 | not recognized for ['015199320']\
dyi not recognized for ['015199330']\
dyi not recognized for ['015199330']\
dyi not recognized for ['015199351']\
dyi not recognized for ['015199351']\
1 y not recognized for ['015199372']\
1 y not recognized for ['015199372']\
00  not recognized for ['015199392']\
00  not recognized for ['015199392']\
h0y not recognized for ['015199401']\
h0y not recognized for ['015199401']\
0yi not recognized for ['015199402']\
0yi not recognized for ['015199402']\
cyi not recognized for ['015199430']\
cyi not recognized for ['015199430']\
0 y not recognized for ['015199442']\
0 y not recognized for ['015199442']\
0ay not recognized for ['015199515']\
0ay not recognized for ['015199515']\
0   not recognized for ['015199529']\
0   not recognized for ['015199529']\
0   not recognized for ['015199538']\
0   not recognized for ['015199538']\
0mu not recognized for ['015199539']\
001 not recognized for ['015199540']\
001 not recognized for ['015199540']\
0en not recognized for ['015199542']\
0en not recognized for ['015199542']\
 |  not recognized for ['015199557']\
 |  not recognized for ['015199557']\
0 y not recognized for ['015199558']\
0 y not recognized for ['015199558']\
 |  not recognized for ['015199564']\
 |  not recognized for ['015199564']\
0   not recognized for ['015199575']\
0   not recognized for ['015199575']\
|0  not recognized for ['015199588']\
|0  not recognized for ['015199588']\
dyi not recognized for ['015199595']\
dyi not recognized for ['015199595']\
dyi not recognized for ['015199640']\
dyi not recognized for ['015199640']\
byi not recognized for ['015199670']\
byi not recognized for ['015199670']\
dyi not recognized for ['015199672']\
dyi not recognized for ['015199672']\
0 y not recognized for ['015199678']\
0 y not recognized for ['015199678']\
0 y not recognized for ['015199680']\
0 y not recognized for ['015199714']\
0 y not recognized for ['015199714']\
|1  not recognized for ['015199758']\
|1  not recognized for ['015199758']\
0 y not recognized for ['015199759']\
|   not recognized for ['015199761']\
|   not recognized for ['015199761']\
dyi not recognized for ['015199825']\
dyi not recognized for ['015199825']\
|   not recognized for ['015199827']\
|   not recognized for ['015199827']\
1 y not recognized for ['015199831']\
| 0 not recognized for ['015199838']\
| 0 not recognized for ['015199838']\
|   not recognized for ['015199848']\
|   not recognized for ['015199848']\
|yi not recognized for ['015199857']\
|yi not recognized for ['015199857']\
0 e not recognized for ['015199867']\
byi not recognized for ['015199870']\
byi not recognized for ['015199870']\
0 | not recognized for ['015199973']\
0 | not recognized for ['015199973']\
byi not recognized for ['015200002']\
byi not recognized for ['015200002']\
|0  not recognized for ['015200035']\
|0  not recognized for ['015200035']\
0 y not recognized for ['015200037']\
0 y not recognized for ['015200037']\
 |  not recognized for ['015200057']\
 |  not recognized for ['015200057']\
0yi not recognized for ['015200081']\
0yi not recognized for ['015200081']\
 |  not recognized for ['015200086']\
 |  not recognized for ['015200086']\
0yi not recognized for ['015200092']\
0yi not recognized for ['015200092']\
0 0 not recognized for ['015200093']\
0 0 not recognized for ['015200093']\
0yi not recognized for ['015200095']\
byi not recognized for ['015200097']\
byi not recognized for ['015200097']\
0yi not recognized for ['015200103']\
0yi not recognized for ['015200103']\
dyi not recognized for ['015200104']\
dyi not recognized for ['015200104']\
1 y not recognized for ['015200117']\
1 y not recognized for ['015200117']\
| | not recognized for ['015200124']\
| | not recognized for ['015200124']\
0yi not recognized for ['015200127']\
0yi not recognized for ['015200145']\
0yi not recognized for ['015200145']\
dyi not recognized for ['015200149']\
dyi not recognized for ['015200149']\
dyi not recognized for ['015200154']\
dyi not recognized for ['015200154']\
ayi not recognized for ['015200191']\
ayi not recognized for ['015200191']\
dyi not recognized for ['015200210']\
dyi not recognized for ['015200210']\
|0d not recognized for ['015200260']\
|0d not recognized for ['015200260']\
|00 not recognized for ['015200271']\
|00 not recognized for ['015200271']\
dyi not recognized for ['015200272']\
dyi not recognized for ['015200272']\
|by not recognized for ['015200361']\
|by not recognized for ['015200361']\
| | not recognized for ['015200385']\
| | not recognized for ['015200385']\
 |  not recognized for ['015200386']\
 |  not recognized for ['015200386']\
 |  not recognized for ['015200387']\
 |  not recognized for ['015200387']\
|   not recognized for ['015200389']\
|   not recognized for ['015200389']\
byi not recognized for ['015200395']\
byi not recognized for ['015200395']\
0 y not recognized for ['015200416']\
0 y not recognized for ['015200416']\
|   not recognized for ['015200419']\
|   not recognized for ['015200419']\
|   not recognized for ['015200423']\
|   not recognized for ['015200423']\
|   not recognized for ['015200443']\
|   not recognized for ['015200443']\
|   not recognized for ['015200569']\
|   not recognized for ['015200569']\
|   not recognized for ['015200570']\
|   not recognized for ['015200570']\
 |0 not recognized for ['015200576']\
 |0 not recognized for ['015200576']\
|   not recognized for ['015200586']\
|   not recognized for ['015200586']\
|   not recognized for ['015200611']\
|   not recognized for ['015200611']\
|   not recognized for ['015200618']\
| 1 not recognized for ['015200641']\
| 1 not recognized for ['015200641']\
ayi not recognized for ['015200674']\
ayi not recognized for ['015200674']\
occ not recognized for ['015202241']\
occ not recognized for ['015202444']\
-gx not recognized for ['015614620']\
--- not recognized for ['015614620']\
mnu not recognized for ['015617135']\
jpg not recognized for ['015705053']\
frd not recognized for ['015858720']\
frd not recognized for ['015858720']\
lar not recognized for ['015859501']\
lar not recognized for ['015859501']\
ghm not recognized for ['015887290']\
ghm not recognized for ['015887290']\
anc not recognized for ['016037592']\
enl not recognized for ['016285199']\
yue not recognized for ['016324336']\
pcc not recognized for ['016693711']\
mhe not recognized for ['016949921']\
zlm not recognized for ['016949921']\
enf not recognized for ['016960737']\
pen not recognized for ['016998503']\
pen not recognized for ['016998503']\
fen not recognized for ['016998614']\
fen not recognized for ['016998614']\
end not recognized for ['017009155']\
end not recognized for ['017009155']\
fen not recognized for ['017009225']\
fen not recognized for ['017009225']\
inu not recognized for ['017153035']\
inu not recognized for ['017153035']\
ōle not recognized for ['017191820']\
ōle not recognized for ['017191820']\
ōle not recognized for ['017191821']\
ōle not recognized for ['017191821']\
ōle not recognized for ['017191822']\
ōle not recognized for ['017191822']\
ōle not recognized for ['017191823']\
ōle not recognized for ['017191823']\
ōle not recognized for ['017191824']\
ōle not recognized for ['017191824']\
ōle not recognized for ['017191825']\
ōle not recognized for ['017191825']\
ōle not recognized for ['017191826']\
ōle not recognized for ['017191826']\
ōle not recognized for ['017191827']\
ōle not recognized for ['017191827']\
ōle not recognized for ['017191828']\
ōle not recognized for ['017191828']\
ōle not recognized for ['017191829']\
ōle not recognized for ['017191829']\
ōle not recognized for ['017191830']\
ōle not recognized for ['017191830']\
ōle not recognized for ['017191831']\
ōle not recognized for ['017191831']\
ōle not recognized for ['017191832']\
ōle not recognized for ['017191832']\
ōle not recognized for ['017191833']\
ōle not recognized for ['017191833']\
ōle not recognized for ['017191834']\
ōle not recognized for ['017191834']\
ōle not recognized for ['017191835']\
ōle not recognized for ['017191835']\
ōle not recognized for ['017191836']\
ōle not recognized for ['017191836']\
ōle not recognized for ['017191837']\
ōle not recognized for ['017191837']\
ōle not recognized for ['017191838']\
ōle not recognized for ['017191838']\
ōle not recognized for ['017191839']\
ōle not recognized for ['017191839']\
ōle not recognized for ['017191840']\
ōle not recognized for ['017191840']\
ōle not recognized for ['017191841']\
ōle not recognized for ['017191841']\
ōle not recognized for ['017191842']\
ōle not recognized for ['017191842']\
ōle not recognized for ['017191843']\
ōle not recognized for ['017191843']\
ōle not recognized for ['017191844']\
ōle not recognized for ['017191844']\
ōle not recognized for ['017191845']\
ōle not recognized for ['017191845']\
ōle not recognized for ['017191846']\
ōle not recognized for ['017191846']\
ōle not recognized for ['017191847']\
ōle not recognized for ['017191847']\
ōle not recognized for ['017191848']\
ōle not recognized for ['017191848']\
ōle not recognized for ['017191849']\
ōle not recognized for ['017191849']\
ōle not recognized for ['017191850']\
ōle not recognized for ['017191850']\
ōle not recognized for ['017191851']\
ōle not recognized for ['017191851']\
ōle not recognized for ['017191852']\
ōle not recognized for ['017191852']\
ōle not recognized for ['017191853']\
ōle not recognized for ['017191853']\
ōle not recognized for ['017191854']\
ōle not recognized for ['017191854']\
ōle not recognized for ['017191855']\
ōle not recognized for ['017191855']\
ōle not recognized for ['017191856']\
ōle not recognized for ['017191856']\
ōle not recognized for ['017191857']\
ōle not recognized for ['017191857']\
ōle not recognized for ['017191858']\
ōle not recognized for ['017191858']\
ōle not recognized for ['017191859']\
ōle not recognized for ['017191859']\
ōle not recognized for ['017191860']\
ōle not recognized for ['017191860']\
ōle not recognized for ['017191861']\
ōle not recognized for ['017191861']\
ōle not recognized for ['017191862']\
ōle not recognized for ['017191862']\
ōle not recognized for ['017191863']\
ōle not recognized for ['017191863']\
ōle not recognized for ['017191864']\
ōle not recognized for ['017191864']\
ōle not recognized for ['017191865']\
ōle not recognized for ['017191865']\
ōle not recognized for ['017191866']\
ōle not recognized for ['017191866']\
ōle not recognized for ['017191867']\
ōle not recognized for ['017191867']\
ōle not recognized for ['017191868']\
ōle not recognized for ['017191868']\
ōle not recognized for ['017191869']\
ōle not recognized for ['017191869']\
ōle not recognized for ['017191870']\
ōle not recognized for ['017191870']\
ōle not recognized for ['017191871']\
ōle not recognized for ['017191871']\
ōle not recognized for ['017191872']\
ōle not recognized for ['017191872']\
ōle not recognized for ['017191873']\
ōle not recognized for ['017191873']\
ōle not recognized for ['017191874']\
ōle not recognized for ['017191874']\
ōle not recognized for ['017191875']\
ōle not recognized for ['017191875']\
ōle not recognized for ['017191876']\
ōle not recognized for ['017191876']\
ōle not recognized for ['017191877']\
ōle not recognized for ['017191877']\
ōle not recognized for ['017191878']\
ōle not recognized for ['017191878']\
ōle not recognized for ['017191879']\
ōle not recognized for ['017191879']\
ōle not recognized for ['017191880']\
ōle not recognized for ['017191880']\
ōle not recognized for ['017191881']\
ōle not recognized for ['017191881']\
ōle not recognized for ['017191882']\
ōle not recognized for ['017191882']\
ōle not recognized for ['017191883']\
ōle not recognized for ['017191883']\
ōle not recognized for ['017191884']\
ōle not recognized for ['017191884']\
ōle not recognized for ['017191885']\
ōle not recognized for ['017191885']\
ōle not recognized for ['017191886']\
ōle not recognized for ['017191886']\
ōle not recognized for ['017191887']\
ōle not recognized for ['017191887']\
ōle not recognized for ['017191888']\
ōle not recognized for ['017191888']\
ōle not recognized for ['017191889']\
ōle not recognized for ['017191889']\
ōle not recognized for ['017191890']\
ōle not recognized for ['017191890']\
ōle not recognized for ['017191891']\
ōle not recognized for ['017191891']\
ōle not recognized for ['017191892']\
ōle not recognized for ['017191892']\
ōle not recognized for ['017191893']\
ōle not recognized for ['017191893']\
ōle not recognized for ['017191894']\
ōle not recognized for ['017191894']\
ōle not recognized for ['017191895']\
ōle not recognized for ['017191895']\
ōle not recognized for ['017191896']\
ōle not recognized for ['017191896']\
ōle not recognized for ['017191897']\
ōle not recognized for ['017191897']\
ōle not recognized for ['017191898']\
ōle not recognized for ['017191898']\
ōle not recognized for ['017191899']\
ōle not recognized for ['017191899']\
ōle not recognized for ['017191900']\
ōle not recognized for ['017191900']\
ōle not recognized for ['017191901']\
ōle not recognized for ['017191901']\
ōle not recognized for ['017191902']\
ōle not recognized for ['017191902']\
ōle not recognized for ['017191903']\
ōle not recognized for ['017191903']\
ōle not recognized for ['017191904']\
ōle not recognized for ['017191904']\
ōle not recognized for ['017191905']\
ōle not recognized for ['017191905']\
ōle not recognized for ['017191906']\
ōle not recognized for ['017191906']\
ōle not recognized for ['017191907']\
ōle not recognized for ['017191907']\
ōle not recognized for ['017191908']\
ōle not recognized for ['017191908']\
ōle not recognized for ['017191909']\
ōle not recognized for ['017191909']\
ōle not recognized for ['017191910']\
ōle not recognized for ['017191910']\
ōle not recognized for ['017191911']\
ōle not recognized for ['017191911']\
ōle not recognized for ['017191912']\
ōle not recognized for ['017191912']\
ōle not recognized for ['017191913']\
ōle not recognized for ['017191913']\
ōle not recognized for ['017191914']\
ōle not recognized for ['017191914']\
ōle not recognized for ['017191915']\
ōle not recognized for ['017191915']\
ōle not recognized for ['017191916']\
ōle not recognized for ['017191916']\
ōle not recognized for ['017191917']\
ōle not recognized for ['017191917']\
ōle not recognized for ['017191918']\
ōle not recognized for ['017191918']\
ōle not recognized for ['017191919']\
ōle not recognized for ['017191919']\
ōle not recognized for ['017191920']\
ōle not recognized for ['017191920']\
ōle not recognized for ['017191921']\
ōle not recognized for ['017191921']\
ōle not recognized for ['017191922']\
ōle not recognized for ['017191922']\
ōle not recognized for ['017191923']\
ōle not recognized for ['017191923']\
ōle not recognized for ['017191924']\
ōle not recognized for ['017191924']\
ōle not recognized for ['017191925']\
ōle not recognized for ['017191925']\
ōle not recognized for ['017191926']\
ōle not recognized for ['017191926']\
ōle not recognized for ['017191927']\
ōle not recognized for ['017191927']\
ōle not recognized for ['017191928']\
ōle not recognized for ['017191928']\
ōle not recognized for ['017191929']\
ōle not recognized for ['017191929']\
ōle not recognized for ['017191930']\
ōle not recognized for ['017191930']\
ōle not recognized for ['017191931']\
ōle not recognized for ['017191931']\
ōle not recognized for ['017191932']\
ōle not recognized for ['017191932']\
ōle not recognized for ['017191933']\
ōle not recognized for ['017191933']\
ōle not recognized for ['017191934']\
ōle not recognized for ['017191934']\
ōle not recognized for ['017191935']\
ōle not recognized for ['017191935']\
ōle not recognized for ['017191936']\
ōle not recognized for ['017191936']\
ōle not recognized for ['017191937']\
ōle not recognized for ['017191937']\
ōle not recognized for ['017191938']\
ōle not recognized for ['017191938']\
ōle not recognized for ['017191939']\
ōle not recognized for ['017191939']\
ōle not recognized for ['017191940']\
ōle not recognized for ['017191940']\
ōle not recognized for ['017191941']\
ōle not recognized for ['017191941']\
ōle not recognized for ['017191942']\
ōle not recognized for ['017191942']\
ōle not recognized for ['017191943']\
ōle not recognized for ['017191943']\
ōle not recognized for ['017191944']\
ōle not recognized for ['017191944']\
ōle not recognized for ['017191945']\
ōle not recognized for ['017191945']\
ōle not recognized for ['017191946']\
ōle not recognized for ['017191946']\
ōle not recognized for ['017191947']\
ōle not recognized for ['017191947']\
ōle not recognized for ['017191948']\
ōle not recognized for ['017191948']\
ōle not recognized for ['017191949']\
ōle not recognized for ['017191949']\
ōle not recognized for ['017191950']\
ōle not recognized for ['017191950']\
ōle not recognized for ['017191951']\
ōle not recognized for ['017191951']\
ōle not recognized for ['017191952']\
ōle not recognized for ['017191952']\
ōle not recognized for ['017191953']\
ōle not recognized for ['017191953']\
ōle not recognized for ['017191954']\
ōle not recognized for ['017191954']\
ōle not recognized for ['017191955']\
ōle not recognized for ['017191955']\
ōle not recognized for ['017191956']\
ōle not recognized for ['017191956']\
lak not recognized for ['017192959']\
lak not recognized for ['017192960']\
lak not recognized for ['017192961']\
lak not recognized for ['017192962']\
lak not recognized for ['017192963']\
lak not recognized for ['017192964']\
lak not recognized for ['017192965']\
lak not recognized for ['017192966']\
lak not recognized for ['017192967']\
lak not recognized for ['017192968']\
lak not recognized for ['017192969']\
lak not recognized for ['017192970']\
lak not recognized for ['017192971']\
lak not recognized for ['017192972']\
lak not recognized for ['017192973']\
lak not recognized for ['017192974']\
lak not recognized for ['017192975']\
lak not recognized for ['017192976']\
lak not recognized for ['017192978']\
lak not recognized for ['017192979']\
lak not recognized for ['017192980']\
lak not recognized for ['017192981']\
lak not recognized for ['017192982']\
lak not recognized for ['017192983']\
lak not recognized for ['017192984']\
lak not recognized for ['017192985']\
lak not recognized for ['017192986']\
lak not recognized for ['017192987']\
lak not recognized for ['017192988']\
tz' not recognized for ['017240954']\
tz' not recognized for ['017240955']\
tz' not recognized for ['017240956']\
tz' not recognized for ['017240957']\
tz' not recognized for ['017240958']\
ass not recognized for ['017240964']\
kaq not recognized for ['017241490']\
kaq not recognized for ['017241490']\
kaq not recognized for ['017241492']\
kaq not recognized for ['017241492']\
kaq not recognized for ['017241494']\
kaq not recognized for ['017241494']\
kaq not recognized for ['017241496']\
kaq not recognized for ['017241496']\
wed not recognized for ['017241860']\
wed not recognized for ['017241860']\
rel not recognized for ['017241861']\
rel not recognized for ['017241861']\
wed not recognized for ['017241862']\
wed not recognized for ['017241862']\
fun not recognized for ['017241869']\
fun not recognized for ['017241869']\
wed not recognized for ['017241870']\
wed not recognized for ['017241870']\
the not recognized for ['017241871']\
the not recognized for ['017241871']\
the not recognized for ['017241872']\
the not recognized for ['017241872']\
fes not recognized for ['017241873']\
fes not recognized for ['017241873']\
fes not recognized for ['017241874']\
fes not recognized for ['017241874']\
fes not recognized for ['017241875']\
fes not recognized for ['017241875']\
fes not recognized for ['017241876']\
fes not recognized for ['017241876']\
fes not recognized for ['017241877']\
fes not recognized for ['017241877']\
fes not recognized for ['017241878']\
fes not recognized for ['017241878']\
fes not recognized for ['017241881']\
fes not recognized for ['017241881']\
rel not recognized for ['017241882']\
rel not recognized for ['017241882']\
rel not recognized for ['017241883']\
rel not recognized for ['017241883']\
fes not recognized for ['017241886']\
fes not recognized for ['017241886']\
fes not recognized for ['017241887']\
fes not recognized for ['017241887']\
rel not recognized for ['017241888']\
rel not recognized for ['017241888']\
fes not recognized for ['017241891']\
fes not recognized for ['017241891']\
fes not recognized for ['017241892']\
fes not recognized for ['017241892']\
rel not recognized for ['017241899']\
rel not recognized for ['017241899']\
wed not recognized for ['017241907']\
wed not recognized for ['017241907']\
rel not recognized for ['017241913']\
rel not recognized for ['017241913']\
rel not recognized for ['017241916']\
rel not recognized for ['017241916']\
rel not recognized for ['017241918']\
rel not recognized for ['017241918']\
fun not recognized for ['017241922']\
fun not recognized for ['017241922']\
fun not recognized for ['017241923']\
fun not recognized for ['017241923']\
tau not recognized for ['017243367']\
tau not recognized for ['017243367']\
bag not recognized for ['017243379']\
bag not recognized for ['017243379']\
but not recognized for ['017243383']\
but not recognized for ['017243383']\
suo not recognized for ['017292744']\
suo not recognized for ['017292744']\
fle not recognized for ['017300350']\
bil not recognized for ['017302457']\
bil not recognized for ['017302457']\
ddu not recognized for ['017303482']\
ser not recognized for ['017309051']\
ser not recognized for ['017309055']\
ser not recognized for ['017309062']\
ser not recognized for ['017309265']\
ser not recognized for ['017309266']\
ser not recognized for ['017309269']\
ser not recognized for ['017309273']\
ser not recognized for ['017309275']\
ser not recognized for ['017309277']\
isl not recognized for ['017310366']\
swi not recognized for ['017343593']\
swi not recognized for ['017343593']\
sev not recognized for ['017346711']\
sev not recognized for ['017346711']\
enk not recognized for ['017346755']\
enk not recognized for ['017346755']\
pri not recognized for ['017346768']\
pri not recognized for ['017346768']\
bio not recognized for ['017346840']\
bio not recognized for ['017346840']\
wit not recognized for ['017346843']\
wit not recognized for ['017346843']\
fle not recognized for ['017368068']\
fle not recognized for ['017368068']\
bco not recognized for ['017438686']\
kpg not recognized for ['017469350']\
l6. not recognized for ['017472251']\
l2. not recognized for ['017472251']\
lis not recognized for ['017476629']\
ost not recognized for ['017503400']\
ebs not recognized for ['017503400']\
coh not recognized for ['017503400']\
hbe not recognized for ['017504675']\
n-m not recognized for ['017505475']\
x-- not recognized for ['017505475']\
## Records failed to migrate due to Value errors found in Transformation - 292 things
no matching instance_formats sg =338  \\$aaudio cartridge$bsg$2rdacarrier for None \
No title for ['000559535'] for None \
No title for ['000809211'] for None \
No Instance type ID for None \
no matching instance_formats sg =338  \\$aaudio cartridge$bsg$2rdacarrier for None \
No Instance type ID for None \
No title for ['004305767'] for None \
No title for ['004898130'] for None \
No title for ['004982939'] for None \
No Instance type ID for None \
No title for ['010551627'] for None \
No title for ['010551754'] for None \
No title for ['013700849'] for None \
No Instance type ID for None \
No title for ['014012320'] for None \
No title for ['014031253'] for None \
No Instance type ID for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
no matching instance_formats c =338  \\$aonline resource$bc$2rdacarrier for None \
No title for ['014596426'] for None \
No title for ['014602200'] for None \
No title for ['014903868'] for None \
No title for ['014935567'] for None \
No title for ['014935576'] for None \
No title for ['014935603'] for None \
No title for ['014935614'] for None \
No title for ['014935650'] for None \
No title for ['014935663'] for None \
No title for ['014935666'] for None \
No title for ['014938796'] for None \
No title for ['014940775'] for None \
No title for ['014940799'] for None \
No title for ['014942710'] for None \
No title for ['014943015'] for None \
No title for ['014943028'] for None \
No title for ['014944219'] for None \
No title for ['014944443'] for None \
No title for ['014944463'] for None \
No title for ['014944466'] for None \
No title for ['014944478'] for None \
No title for ['014944481'] for None \
No title for ['014944495'] for None \
No title for ['014944509'] for None \
No title for ['014944583'] for None \
No title for ['014944622'] for None \
No title for ['014944763'] for None \
No title for ['014944782'] for None \
No title for ['014944801'] for None \
No title for ['014944813'] for None \
No title for ['014944837'] for None \
No title for ['014944838'] for None \
No title for ['014944881'] for None \
No title for ['014944916'] for None \
No title for ['014944948'] for None \
No title for ['014944951'] for None \
No title for ['014944953'] for None \
No title for ['014944986'] for None \
No title for ['014945037'] for None \
No title for ['014945049'] for None \
No title for ['014945095'] for None \
No title for ['014945125'] for None \
No title for ['014945132'] for None \
No title for ['014945142'] for None \
No title for ['014945160'] for None \
No title for ['014945184'] for None \
No title for ['014945235'] for None \
No title for ['014945243'] for None \
No title for ['014945289'] for None \
No title for ['014945303'] for None \
No title for ['014945329'] for None \
No title for ['014945332'] for None \
No title for ['014946640'] for None \
No title for ['014946653'] for None \
No title for ['014946731'] for None \
No title for ['014946962'] for None \
No title for ['014947066'] for None \
No title for ['014947071'] for None \
No title for ['014947099'] for None \
no matching instance_formats CD =338  \\$acompact disc$bCD$2obdrager for None \
no matching instance_formats v =338  \\$avideo$bv$2rdamedia for None \
No title for ['015188870'] for None \
No title for ['015189356'] for None \
No title for ['015194745'] for None \
No title for ['015194830'] for None \
No title for ['015195369'] for None \
No title for ['015195437'] for None \
No title for ['015195517'] for None \
No title for ['015196533'] for None \
No title for ['015198826'] for None \
No title for ['015199072'] for None \
No title for ['015199094'] for None \
no matching instance_formats n =338  \\$avolume$bn$2rdamedia for None \
no matching instance_formats n =338  \\$aunmediated$bn$2rdamedia for None \
no matching instance_formats n =338  \\$avolume$bn$2rdamedia for None \
no matching instance_formats bd =338  \\$avideodisc$bbd$2rdamedia for None \
No title for ['016287157'] for None \
No Instance type ID for None \
No title for ['016706270'] for None \
No title for ['016989191'] for None \
No title for ['016991702'] for None \
No title for ['016992006'] for None \
No title for ['016992038'] for None \
No title for ['016994239'] for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
no matching instance_formats crc =338  \\$aonline resource$bcrc$2rdacarrier for None \
No title for ['017090053'] for None \
no matching instance_formats rdacarrier =338  \\$avolume$bnc$brdacarrier$2rdacontent for None \
No title for ['017118246'] for None \
No title for ['017129634'] for None \
No Instance type ID for None \
## Bib records that failed to parse. - - 12 things
'utf-8' codec can't decode byte 0xef in position 39: unexpected end of data b'01059cam a2200289I  4500005001700000008004100017010001300058035002000071040002700091050002000118099001600138099001000154100002900164245007900193264009900272264001100371300004700382336002600429337002800455338002700483490004800510500006800558655001900626700005700645830004900702998001800751\x1e20140804145805.0\x1e750521119422 \xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2          \xcc\xb2\xef\x1e  \x1fa42022257\x1e  \x1fa(OCoLC)01347971\x1e  \x1fcRBN\x1fdOCL\x1fdSNN\x1fdUtOrBLW\x1e 0\x1faPS3503.O365\x1fbT5\x1e  \x1fa825\x1faB6393t\x1e  \x1faPlays\x1e1 \x1faBolton, Guy,\x1fd1884-1979.\x1e10\x1faTheatre, :\x1fba comedy in three acts, /\x1fcby Guy Bolton and Somerset Maugham.\x1e 1\x1faNew York, N.Y., Los Angeles, Calif. :\x1fbS. French; [etc., etc.],\x1fc[i.e. between 1940 and 1949?]\x1e 4\x1fc\xc2\xa91942\x1e  \x1fa124 pages :\x1fb2 diagram on 1 leaf ;\x1fc19 cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e1 \x1faOn cover: French\'s standard library edition\x1e  \x1fa"Copyright, 1937 (in novel form), by William Somerset Maugham."\x1e 7\x1faPlays.\x1f2rbgenr\x1e1 \x1faMaugham, W. Somerset\x1fq(William Somerset),\x1fd1874-1965\x1e 0\x1faOn cover: French\'s standard library edition.\x1e  \x1faAM\x1fb000359903\x1e\x1d'\
'utf-8' codec can't decode byte 0xef in position 39: unexpected end of data b'01166nam a2200289I  4500005001700000008004100017035002000058040002800078090002900106099002400135100003900159245008300198264011300281300004400394336002600438337002800464338002700492490009300519500001700612504002700629650003800656650002800694650002300722700002100745830009200766998001800858\x1e20140805011257.0\x1e730508s1963    inua     b    000 0 engu\xef\x1e  \x1fa(OCoLC)00617255\x1e  \x1fcCWR\x1fdm.c.\x1fdSNN\x1fdUtOrBLW\x1e  \x1faLB1103\x1fb.S6 v.28, no.1-7\x1e  \x1fa158.52\x1faSol3m\x1fa28:5\x1e1 \x1faBirch, Herbert George,\x1fd1918-1973.\x1e10\x1faIntersensory development in children [by] Herbert G. Birch and Arthur Lefford.\x1e 1\x1fa[Lafayette, Ind.] :\x1fbChild Development publications of the Society for Research in Child Development,\x1fc1963.\x1e  \x1fa48 pages :\x1fbdiagrams, tables. ;\x1fc23 cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e1 \x1faMonographs of the Society for Research in Child Development ;\x1fvv.28, no. 5, serial no.89\x1e  \x1faCover title.\x1e  \x1faBibliography: p.47-48.\x1e 0\x1faSenses and sensation in children.\x1e 0\x1faPerception in children.\x1e 0\x1faChild development.\x1e1 \x1faLefford, Arthur.\x1e 0\x1faMonographs of the Society for Research in Child Development\x1fvv.28, no. 5, serial no.89.\x1e  \x1faMH\x1fb001089582\x1e\x1d'\
'utf-8' codec can't decode byte 0xef in position 39: unexpected end of data b"01050cam a2200265I  4500005001700000008004100017035002000058040003200078090001600110099001700126110005700143245006900200264007400269300002700343336002600370337002800396338002700424490007600451650005200527650004500579650004600624830007500670998001800745098002100763\x1e20140805000332.0\x1e750305119088 \xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2          \xcc\xb2\xef\x1e  \x1fa(OCoLC)01200959\x1e  \x1fcIAU\x1fdOCL\x1fdm/c\x1fdSNN\x1fdUtOrBLW\x1e  \x1faLB2334\x1fb.C3\x1e  \x1fa371\x1faC21b\x1fa2\x1e2 \x1faCarnegie Foundation for the Advancement of Teaching.\x1e14\x1faThe financial status of the professor in America and in Germany.\x1e 1\x1faNew York City :\x1fb[Knickerbocker Press (G. P. Putnam's Sons)],\x1fc[1908]\x1e  \x1fax, 101 pages ;\x1fc26 cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e1 \x1faBulletin (Carnegie Foundation for the Advancement of Teaching) ;\x1fvno. 2\x1e 0\x1faCollege teachers\x1fzUnited States\x1fxSalaries, etc.\x1e 0\x1faCollege teachers\x1fzCanada\x1fxSalaries, etc.\x1e 0\x1faCollege teachers\x1fzGermany\x1fxSalaries, etc.\x1e 0\x1faBulletin (Carnegie Foundation for the Advancement of Teaching)\x1fvno. 2.\x1e  \x1faSM\x1fb001429492\x1e11\x1faIXAPT\x1faC2b no. 2\x1e\x1d"\
'utf-8' codec can't decode byte 0xef in position 39: unexpected end of data b'01300nam a2200277I  4500005001700000008004100017010001300058035002000071040002200091050002200113099001800135100003400153245008700187264003700274300002800311336002600339337002800365338002700393490007100420501030300491504003000794630005900824630004700883830007400930998001801004\x1e20170922070756.0\x1e750411119344 \xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2          \xcc\xb2\xef\x1e  \x1fa34023296\x1e  \x1fa(OCoLC)01268657\x1e  \x1fcBPS\x1fdSNN\x1fdUtOrBLW\x1e00\x1faBS410\x1fb.Z5 vol.65\x1e  \x1fa205\x1faZ34b\x1fa65\x1e1 \x1faCaspari, Wilhelm,\x1fd1876-1947.\x1e10\x1faLieder und Gottesspr\xc3\xbcche der r\xc3\xbcckwanderer (Jesaja 40-55) /\x1fcvon Wilhelm Caspari.\x1e 1\x1faGiessen :\x1fbA. T\xc3\xb6pelmann,\x1fc1934.\x1e  \x1favi, 264 pages ;\x1fc24 cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e1 \x1faZeitschrift f\xc3\xbcr die alttestamentliche wissenschaft ;\x1fvBeihefte 65\x1e  \x1faBound with: Ezechielprobleme -- Die altorientalische Weisheit in ihrer israelitisch-j\xc3\xbcdischen Auspr\xc3\xa4gung : eine studie zur Nationalisierung der Weisheit in Israel -- Der Elohist als erz\xc3\xa4hler ein irrweg der Pentateuchkritik? : an der Genesis erl\xc3\xa4utert -- Name und Wort Gottes im Alten Testament.\x1e  \x1faBibliography: p. 262-263.\x1e00\x1faBible.\x1fpIsaiah, XL-LV\x1fxCriticism, interpretation, etc.\x1e00\x1faBible.\x1fpIsaiah, XL-LV\x1fxCriticism, Textual.\x1e 0\x1faBeihefte zur Zeitschrift f\xc3\xbcr die alttestamentliche Wissenschaft\x1fv65.\x1e  \x1faSM\x1fb001434261\x1e\x1d'\
'utf-8' codec can't decode byte 0xef in position 39: unexpected end of data b'01087cam a2200301I  4500005001700000008004100017010001300058035002000071040002200091050001500113099002600128100005800154245014300212264004700355300004600402336002600448337002800474338002700502490005100529504003100580650002300611650001600634650001400650740002200664830005200686998001800738098002900756\x1e20140805001127.0\x1e750506119388 \xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2          \xcc\xb2\xef\x1e  \x1fa38028387\x1e  \x1fa(OCoLC)01314827\x1e  \x1fcGAT\x1fdSNN\x1fdUtOrBLW\x1e00\x1faQA689\x1fb.B5\x1e  \x1fa378.73M6915\x1faJ4\x1fa13:2\x1e1 \x1faBlumenthal, Leonard M.\x1fq(Leonard Mascot),\x1fd1901-1984.\x1e10\x1faDistance geometries; :\x1fba study of the development of abstract metrics /\x1fc[by] Leonard M. Blumenthal. With an introduction by Karl Menger.\x1e 1\x1faColumbia :\x1fbUniversity of Missouri,\x1fc1938.\x1e  \x1fa2 preliminary leaves, 145 pages ;\x1fc27 cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e1 \x1faUniversity of Missouri studies ;\x1fvv. 13, no. 2\x1e  \x1faBibliography; p.[138]-142.\x1e 0\x1faDistance geometry.\x1e 0\x1faSet theory.\x1e 0\x1faTopology.\x1e0 \x1faAbstract metrics.\x1e 0\x1faUniversity of Missouri studies ;\x1fvv. 13, no. 2.\x1e  \x1faSM\x1fb001437235\x1e11\x1faIx83Mis\x1fa+M6u v.13, no.2\x1e\x1d'\
'utf-8' codec can't decode byte 0xef in position 39: unexpected end of data b'00930nam a2200265I  4500005001700000008004100017035002000058040002200078090001600100099002000116100002600136245010700162264005100269300002300320336002600343337002800369338002700397490005000424504002800474650003100502650003400533830005100567998001800618098002800636\x1e20140805062956.0\x1e730216119300 \xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2          \xcc\xb2\xef\x1e  \x1fa(OCoLC)00560311\x1e  \x1fcYNG\x1fdSNN\x1fdUtOrBLW\x1e  \x1faPC4261\x1fb.B8\x1e  \x1fa378.73M6915\x1faJ4\x1e1 \x1faBuffum, Mary Evaline.\x1e14\x1faThe construction of object pronouns in the works of modern Spanish writers, /\x1fcby Mary Evaline Buffum.\x1e 1\x1faColumbia :\x1fbThe University of Missouri,\x1fc1930.\x1e  \x1fa46 pages ;\x1fc27 cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e1 \x1faUniversity of Missouri studies ;\x1fvv. 5, no. 3\x1e  \x1faBibliography: p. 42-46.\x1e 0\x1faSpanish language\x1fxPronoun.\x1e 0\x1faSpanish language\x1fxWord order.\x1e 0\x1faUniversity of Missouri studies ;\x1fvv. 5, no. 3.\x1e  \x1faSM\x1fb001777730\x1e11\x1faIx83Mis\x1fa+M6u v.5, no.3\x1e\x1d'\
'utf-8' codec can't decode byte 0xef in position 39: unexpected end of data b'00964nam a2200253I  4500005001700000008004100017010001300058035002000071040002800091099002300119100003300142245006600175264004300241300001900284336002600303337002800329338002700357490006600384504009600450650003700546650002600583810008300609998001800692\x1e20140805063817.0\x1e730601118900 \xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2          \xcc\xb2\xef\x1e  \x1fa05036537\x1e  \x1fa(OCoLC)00635151\x1e  \x1fcHIR\x1fdm.c.\x1fdSNN\x1fdUtOrBLW\x1e  \x1fa379.73\x1faUn3c\x1fa1890\x1e1 \x1faCajori, Florian,\x1fd1859-1930.\x1e14\x1faThe teaching and history of mathematics in the United States.\x1e 1\x1faWashington :\x1fbGovt. Print. Off,\x1fc1890.\x1e  \x1fa400p. ;\x1fc24cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e1 \x1faU.S. Bureau of education. Circular of information, 1890. no.3\x1e  \x1fa"Bibliography of fluxions and calculus. Textbooks printed in the United States": p.395-400.\x1e 0\x1faMathematics\x1fxStudy and teaching.\x1e 0\x1faMathematics\x1fxHistory.\x1e1 \x1faUnited States.\x1fbBureau of Education.\x1ftCirculars of information ;\x1fv1890, no. 3.\x1e  \x1faSM\x1fb001784944\x1e\x1d'\
'utf-8' codec can't decode byte 0xef in position 39: unexpected end of data b'01087nam a2200289I  4500005001700000008004100017010001300058035002000071040002800091050001500119099001600134100004900150245003600199264005600235300003000291336002600321337002800347338002700375490010400402502005200506504003000558600003100588830009200619830005300711998001800764098001500782\x1e20140805070309.0\x1e731109119033 \xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2          \xcc\xb2\xef\x1e  \x1fa05033558\x1e  \x1fa(OCoLC)00739117\x1e  \x1fcTFW\x1fdm.c.\x1fdSNN\x1fdUtOrBLW\x1e 0\x1faB2347\x1fb.B8\x1e  \x1fa406\x1faW75\x1fa2\x1e1 \x1faBrauer, Herman G. A.\x1fq(Herman Gustav Adolph)\x1e14\x1faThe philosophy of Ernest Renan.\x1e 1\x1faMadison, Wis. :\x1fb[publisher not identified],\x1fc1903.\x1e  \x1fapages [205]-379. ;\x1fc24cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e1 \x1faBulletin of the University of Wisconsin. no. 55. Philology and literature series, v. 2, no. 3, 1903\x1e  \x1faThesis (Ph.D.) - University of Wisconsin, 1902.\x1e  \x1faBibliography: p. 372-377.\x1e10\x1faRenan, Ernest,\x1fd1823-1892.\x1e 0\x1faBulletin of the University of Wisconsin.\x1fpPhilology and literature series\x1fvv. 2, no. 3.\x1e 0\x1faBulletin of the University of Wisconsin\x1fvno. 55.\x1e  \x1faSM\x1fb001805961\x1e11\x1faBE39\x1faR2zb\x1e\x1d'\
'utf-8' codec can't decode byte 0xef in position 39: unexpected end of data b'01321nam a2200301I  4500005001700000008004100017010001300058035002000071040002200091050002700113099002100140100005000161245012000211264006200331300006400393336002600457337002800483338002700511490005000538490005500588583012900643600003100772600004700803700004600850830004900896830005600945998001801001\x1e20140805075454.0\x1e750723119288 \xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2          \xcc\xb2\xef\x1e  \x1fa28026606\x1e  \x1fa(OCoLC)01468115\x1e  \x1fcFUG\x1fdSNN\x1fdUtOrBLW\x1e 0\x1faQ11\x1fb.S7 vol. 81, no.4\x1e  \x1fa506\x1faSm69m\x1fa81:4\x1e1 \x1faBushnell, David I.\x1fq(David Ives),\x1fd1875-1941.\x1e10\x1faDrawing by Jacques Lemoyne de Morgues of Saturioua, :\x1fba Timucua chief in Florida, 1564 /\x1fcby David I. Bushnell,jr.\x1e 1\x1faCity of Washington :\x1fbThe Smithsonian institution,\x1fc1928.\x1e  \x1fa1 page leaves, 9 pages :\x1fb1 illustration, portrait ;\x1fc25cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e1 \x1faPublication (Smithsonian Institution) ;\x1fv2972\x1e1 \x1faSmithsonian miscellaneous collections. v.81, no. 4\x1e1 \x1facommitted to retain\x1fc20160630\x1fd20310630\x1ffEAST\x1fuhttp://eastlibraries.org/retained-materials\x1fzSmith copy: EAST commitment\x1f5MNS\x1e00\x1faSaturioua,\x1fcTimucua chief.\x1e10\x1faLe Moyne de Morgues, Jacques,\x1fd1533?-1588.\x1e1 \x1faLe Moyne de Morgues, Jacques,\x1fd1533?-1588\x1e 0\x1faPublication (Smithsonian Institution)\x1fv2972.\x1e 0\x1faSmithsonian miscellaneous collections. v.81, no. 4.\x1e  \x1faSM\x1fb001850894\x1e\x1d'\
'utf-8' codec can't decode byte 0xef in position 39: unexpected end of data b'01158nam a2200277I  4500005001700000008004100017010001300058035002000071040002700091050002300118099001500141100003300156245003400189264004900223300002200272336002600294337002800320338002700348500001100375500017900386500016000565700005000725700004400775700004300819998001800862\x1e20140805080215.0\x1e720322119288 \xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2          \xcc\xb2\xef\x1e  \x1fa28019609\x1e  \x1fa(OCoLC)00268895\x1e  \x1fcOUN\x1fdOCL\x1fdSNN\x1fdUtOrBLW\x1e 0\x1faPR6003.L8\x1fbR4 1928\x1e  \x1fa825\x1faB627r\x1e1 \x1faBlunden, Edmund,\x1fd1896-1974.\x1e10\x1faRetreat /\x1fcby Edmund Blunden.\x1e 1\x1fa[London] :\x1fbRichard Cobden-Sanderson,\x1fc1928.\x1e  \x1fa70 pages ;\x1fc23 cm\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e  \x1faPoems.\x1e  \x1faAmherst College Special Collections copy 1 is in dust jacket; copy 2 is accompanied by a letter from Blunden to G.E. de B. Wilmot (in file; envelope tipped into volume).\x1f5MA.\x1e  \x1faSC/RBR: In dust jacket; bookplate on front pastedown: Lamont House Library, Smith College. From the Library of Florence Corliss Lamont, class of 1893.\x1f5MNS\x1e1 \x1faLamont, Florence Corliss,\x1feformer owner.\x1f5MNS\x1e1 \x1faWilmot, G. E. de B.,\x1feformer owner.\x1f5MA\x1e1 \x1faCobden-Sanderson, Richard,\x1fepublisher.\x1e  \x1faSM\x1fb001857476\x1e\x1d'\
'ascii' codec can't decode byte 0xcc in position 0: ordinal not in range(128) b"04495cgm a2200829Ia 4500005001700000007001000017008004100027028004300068035002000111040012700131041002300258043001200281050002400293245021800317246003900535246003500574264006000609300005700669336005000726337002300776338003000799546005700829511005000886508010500936520069501041500011301736600003901849650004901888650004901937650003601986650002402022650004002046650005302086650005302139650004302192651004402235655002602279655002602305655003302331655003602364655002602400655003702426655004502463655004502508655004802553700002802601700002902629700003502658700003402693700002802727700003502755700003302790700002402823710002002847710005002867710003202917880020002949880006403149880004603213880008403259880002403343880002403367880003103391880003103422880002403453880003103477880003103508880002403539880005103563880003303614998001803647\x1e20200424081037.0\x1evd cvaizq\x1e041013s2004    ko 115            vlkor d\x1e41\x1faBDVD-030\x1fbP\xc5\xadrimi\xc5\x8f Ent'\xc5\x8ft'einm\xc5\x8fnt\xc5\xad\x1e  \x1fa(OCoLC)56957349\x1e  \x1faCOO\x1fbeng\x1fcCOO\x1fdWAU\x1fdOCL\x1fdOCLCA\x1fdOCLCQ\x1fdOCLCA\x1fdOCLCQ\x1fdWAU\x1fdOCLCQ\x1fdOCLCO\x1fdWAU\x1fdOCLCA\x1fdOCLCO\x1fdOCLCQ\x1fdOCLCO\x1fdRCE\x1fdOCLCF\x1fdOCLCO\x1e1 \x1fakor\x1fjeng\x1fjkor\x1fgkor\x1e  \x1faa-ko---\x1e 4\x1faPN1997.2\x1fb.I54 2004\x1e00\x1f6880-01\x1faIn\xc5\x8f kongju /\x1fcchegong, Unikorea ; chejak, Nau P'ill\xc5\xadm ; kih\xc5\x8fek/chejak, Yi Chun-dong ; w\xc5\x8fnan, Kw\xc5\x8fn Hye-w\xc5\x8fn ; sinario, Pak H\xc5\xadng-sik, Song Hye-jin ; p'\xc5\xadrodyus\xc5\x8f, Chin H\xc5\xadi-mun ; kamdok, Pak H\xc5\xadng-sik.\x1e1 \x1fiAlso known as:\x1faMy mother, Mermaid\x1e1 \x1fiAlso known as:\x1faLittle mermaid\x1e\xcc\x86\x1f6880-02\x1fa[S\xc5\x8ful] :\x1fbP\xc5\xadrimi\xc5\x8f Ent'\xc5\x8ft'einm\xc5\x8fnt\xc5\xad,\x1fc2004.\x1e  \x1fa2 videodiscs (115 min.) :\x1fbsound, color ;\x1fc4 3/4 in.\x1e  \x1fatwo-dimensional moving image\x1fbtdi\x1f2rdacontent\x1e  \x1favideo\x1fbv\x1f2rdamedia\x1e  \x1favideodisc\x1fbvd\x1f2rdacarrier\x1e  \x1faIn Korean with optional Korean or English subtitles.\x1e1 \x1f6880-03\x1faCh\xc5\x8fn To-y\xc5\x8fn, Pak Hae-il, Ko Tu-sim.\x1e  \x1f6880-04\x1faCh'wary\xc5\x8fng kamdok, Ch'oe Y\xc5\x8fng-t'aek ; p'y\xc5\x8fnjip, Kim Yang-il ; \xc5\xadmak, Cho S\xc5\x8fng-u (M & F).\x1e  \x1faNa-y\xc5\x8fng works at a post office and is sick and tired of being around her shamefully unyielding mother and her pushover father. The only thing that she can look forward to is her trip abroad in a few days. But one day, her father leaves home without any notice. Her mother doesn't care what happens to him and doesn't care to look for him. Na-y\xc5\x8fng has no choice but to give up her dream trip abroad and to search for her father instead. Once she arrives at her parents' hometown, Na-y\xc5\x8fng falls into the time and place her mother lived in 30 years ago. After falling into this mysterious world, Na-y\xc5\x8fng gets tangled up in the middle of the love that unfolds between her mother and father.\x1e  \x1faSpecial features (not subtitled) on disc 2 include: behind-the-scenes footage, outtakes, and deleted scenes.\x1e10\x1faKw\xc5\x8fn, Hye-w\xc5\x8fn\x1fvFilm adaptations.\x1e 0\x1faMothers and daughters\x1fzKorea (South)\x1fvDrama.\x1e 0\x1faFathers and daughters\x1fzKorea (South)\x1fvDrama.\x1e 0\x1faFamilies\x1fzKorea (South)\x1fvDrama.\x1e 0\x1faTime travel\x1fvDrama.\x1e 7\x1faFamilies.\x1f2fast\x1f0(OCoLC)fst01728849\x1e 7\x1faFathers and daughters.\x1f2fast\x1f0(OCoLC)fst00921890\x1e 7\x1faMothers and daughters.\x1f2fast\x1f0(OCoLC)fst01026997\x1e 7\x1faTime travel.\x1f2fast\x1f0(OCoLC)fst01151176\x1e 7\x1faKorea (South)\x1f2fast\x1f0(OCoLC)fst01206791\x1e 7\x1faFiction films.\x1f2lcgft\x1e 7\x1faFeature films.\x1f2lcgft\x1e 4\x1faFeature films\x1fzKorea (South)\x1e 4\x1faForeign language films\x1fxKorean.\x1e 7\x1faFeature films.\x1f2gsafd\x1e 7\x1faDrama.\x1f2fast\x1f0(OCoLC)fst01423879\x1e 7\x1faFeature films.\x1f2fast\x1f0(OCoLC)fst01710384\x1e 7\x1faFiction films.\x1f2fast\x1f0(OCoLC)fst01710264\x1e 7\x1faFilm adaptations.\x1f2fast\x1f0(OCoLC)fst01710491\x1e1 \x1f6880-05\x1faLee, Joon-dong.\x1e1 \x1f6880-06\x1faKw\xc5\x8fn, Hye-w\xc5\x8fn.\x1e1 \x1f6880-07\x1faPak, H\xc5\xadng-sik,\x1fd1962-\x1e1 \x1f6880-08\x1faSong, Hye-jin,\x1fd1974-\x1e1 \x1f6880-09\x1faChin, H\xc5\xadi-mun.\x1e1 \x1f6880-10\x1faCh\xc5\x8fn, To-y\xc5\x8fn,\x1fd1973-\x1e1 \x1f6880-11\x1faPark, Hae-il,\x1fd1977-\x1e1 \x1f6880-12\x1faKo, Tu-sim.\x1e2 \x1faUniKorea (Firm)\x1e2 \x1f6880-13\x1faP'\xc5\xadrimi\xc5\x8f Ent'\xc5\x8ft'einm\xc5\x8fnt'\xc5\xad (Firm)\x1e2 \x1f6880-14\x1faNau P\xca\xbbill\xc5\xadm (Chu)\x1e00\x1f6245-01/\x1fa\xec\x9d\xb8\xec\x96\xb4\xea\xb3\xb5\xec\xa3\xbc /\x1fc\xec\xa0\x9c\xea\xb3\xb5, Unikorea ; \xec\xa0\x9c\xec\x9e\x91, \xeb\x82\x98\xec\x9a\xb0\xed\x95\x84\xeb\xa6\x84 ; \xea\xb8\xb0\xed\x9a\x8d/\xec\xa0\x9c\xec\x9e\x91, \xec\x9d\xb4\xec\xa4\x80\xeb\x8f\x99 ; \xec\x9b\x90\xec\x95\x88, \xea\xb6\x8c\xed\x98\x9c\xec\x9b\x90 ; \xec\x8b\x9c\xeb\x82\x98\xeb\xa6\xac\xec\x98\xa4, \xeb\xb0\x95\xed\x9d\xa5\xec\x8b\x9d, \xec\x86\xa1\xed\x98\x9c\xec\xa7\x84 ; \xed\x94\x84\xeb\xa1\x9c\xeb\x93\x80\xec\x84\x9c, \xec\xa7\x84\xed\x9d\xac\xeb\xac\xb8 ; \xea\xb0\x90\xeb\x8f\x85, \xeb\xb0\x95\xed\x9d\xa5\xec\x8b\x9d.\x1e 1\x1f6264-02/\x1fa[\xec\x84\x9c\xec\x9a\xb8] :\x1fb\xed\x94\x84\xeb\xa6\xac\xeb\xaf\xb8\xec\x96\xb4\xec\x97\x94\xed\x84\xb0\xed\x85\x8c\xec\x9d\xb8\xeb\xa8\xbc\xed\x8a\xb8,\x1fc2004.\x1e1 \x1f6511-03/\x1fa\xec\xa0\x84\xeb\x8f\x84\xec\x97\xb0, \xeb\xb0\x95\xed\x95\xb4\xec\x9d\xbc, \xea\xb3\xa0\xeb\x91\x90\xec\x8b\xac.\x1e  \x1f6508-04/\x1fa\xec\xb4\xac\xec\x98\x81\xea\xb0\x90\xeb\x8f\x85, \xec\xb5\x9c\xec\x98\x81\xed\x83\x9d ; \xed\x8e\xb8\xec\xa7\x91, \xea\xb9\x80\xec\x96\x91\xec\x9d\xbc ; \xec\x9d\x8c\xec\x95\x85, \xec\xa1\xb0\xec\x84\xb1\xec\x9a\xb0 (M&F).\x1e1 \x1f6700-05/\x1fa\xec\x9d\xb4\xec\xa4\x80\xeb\x8f\x99.\x1e1 \x1f6700-06/\x1fa\xea\xb6\x8c\xed\x98\x9c\xec\x9b\x90.\x1e1 \x1f6700-07/\x1fa\xeb\xb0\x95\xed\x9d\xa5\xec\x8b\x9d,\x1fd1962-\x1e1 \x1f6700-08/\x1fa\xec\x86\xa1\xed\x98\x9c\xec\xa7\x84,\x1fd1974-\x1e1 \x1f6700-09/\x1fa\xec\xa7\x84\xed\x9d\xac\xeb\xac\xb8.\x1e1 \x1f6700-10/\x1fa\xec\xa0\x84\xeb\x8f\x84\xec\x97\xb0,\x1fd1973-\x1e1 \x1f6700-11/\x1fa\xeb\xb0\x95\xed\x95\xb4\xec\x9d\xbc,\x1fd1977-\x1e1 \x1f6700-12/\x1fa\xea\xb3\xa0\xeb\x91\x90\xec\x8b\xac.\x1e2 \x1f6710-13/\x1fa\xed\x94\x84\xeb\xa6\xac\xeb\xaf\xb8\xec\x96\xb4\xec\x97\x94\xed\x84\xb0\xed\x85\x8c\xec\x9d\xb8\xeb\xa8\xbc\xed\x8a\xb8 (Firm)\x1e2 \x1f6710-14/\x1fa\xeb\x82\x98\xec\x9a\xb0\xed\x95\x84\xeb\xa6\x84 (Firm)\x1e  \x1faSM\x1fb004450943\x1e\x1d"\
'utf-8' codec can't decode byte 0xef in position 39: unexpected end of data b'01049nam a2200265I  4500005001700000008004100017035002000058040002700078090002300105100003600128245010700164250010900271264004300380300003000423336002600453337002800479338002700507490004600534500004600580650002300626700004700649740002100696830004800717998001800765\x1e20140805191703.0\x1e750325119666 \xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2\xcc\xb2          \xcc\xb2\xef\x1e  \x1fa(OCoLC)01237183\x1e  \x1fcBOS\x1fdm/c\x1fdSNN\x1fdUtOrBLW\x1e  \x1faPQ6183\x1fb.B04 1966M\x1e1 \x1faCasta\xc3\xb1a, Hier\xc3\xb3nimo Francisco.\x1e10\x1faPrimera parte de los romances nuevos. /\x1fccompuestos por Hieronimo Francisco Casta\xc3\xb1a (Zaragoza, 1604).\x1e  \x1faReimpresos por vez primera del ejemplar \xc3\xbanico, con un estudio preliminar de Antonio Rodr\xc3\xadguez-Mo\xc3\xb1ino.\x1e 1\x1faValencia :\x1fbEditorial castalia,\x1fc1966.\x1e  \x1faxxxi, 113 pages ;\x1fc18 cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e1 \x1faFloresta; joyas po\xc3\xa9ticas espa\xc3\xb1olas,\x1fv10\x1e  \x1faPart of the pages are numbered as leaves.\x1e 0\x1faRomances, Spanish.\x1e1 \x1faRodr\xc3\xadguez Mo\xc3\xb1ino, Antonio R.,\x1fd1910-1970\x1e0 \x1faRomances nuevos.\x1e 0\x1faFloresta; joyas po\xc3\xa9ticas espa\xc3\xb1olas ;\x1fv10.\x1e  \x1faRC\x1fb004469932\x1e\x1d'\
done


# DEDUPED Bibliographic records transformation results
Time Run: 2020-10-28T21:37:52.223933
## Bibliographic records transformation counters
  Measure   | Count
--- | ---:
Bib records that faile transformation | 116
Bibs processed | 3,114,695
Incomplete entity mapping - 028 | 1
Incomplete entity mapping - 050 | 1
Incomplete entity mapping - 082 | 2
Incomplete entity mapping - 090 | 2
Incomplete entity mapping - 100 | 1
Incomplete entity mapping - 130 | 2
Incomplete entity mapping - 246 | 62
Incomplete entity mapping - 260 | 24,400
Incomplete entity mapping - 264 | 905,852
Incomplete entity mapping - 500 | 12
Incomplete entity mapping - 504 | 2
Incomplete entity mapping - 505 | 4
Incomplete entity mapping - 511 | 1
Incomplete entity mapping - 520 | 23
Incomplete entity mapping - 536 | 362
Incomplete entity mapping - 546 | 1
Incomplete entity mapping - 590 | 9,227
Incomplete entity mapping - 700 | 4
Incomplete entity mapping - 740 | 1
MARC21 Records successfully parsed | 3,114,693
MARC21 Records with encoding errors - parsing failed | 2
MARC21 records in file before parsing | 3,114,695
Number of Instances in map | 4,372,794
Successfully transformed bibs | 3,114,577
Total number of Tags processed | 75,350,388
Value Errors | 116
## Unmapped MARC tags
A list of the records not covered by the mapping rules. These rules can be customized to cover more fields. The counts next to the field name is the number of records with this field.
Tag | Count
--- | ---:
003 | 434,072
005 | 3,114,693
006 | 60,738
007 | 286,462
012 | 4,886
013 | 1
018 | 3
019 | 283,674
026 | 1
031 | 84
033 | 1,018
034 | 2,939
036 | 191
037 | 107,215
040 | 3,115,712
042 | 396,640
043 | 1,037,243
044 | 235
045 | 55,154
046 | 421
047 | 5,139
048 | 51,032
051 | 9,074
052 | 737
066 | 32,163
069 | 1
070 | 13,000
072 | 56,922
083 | 141
084 | 80,594
085 | 44
088 | 61,549
091 | 1
092 | 39,690
096 | 1,844
098 | 84,480
099 | 428,154
210 | 21,008
242 | 121
243 | 6
256 | 581
257 | 4
258 | 1
263 | 12,483
270 | 14
306 | 4,844
307 | 2
321 | 11,478
337 | 2,987,966
340 | 658
342 | 2
343 | 1
344 | 119
345 | 2
346 | 13
347 | 8,409
348 | 2,254
351 | 3
352 | 4
363 | 1
365 | 20
366 | 13
370 | 38
380 | 518
381 | 13
382 | 5,814
383 | 2,096
384 | 875
385 | 549
386 | 1,502
388 | 35
539 | 287
558 | 2
591 | 1
647 | 297
648 | 43,989
654 | 91
656 | 6
657 | 617
658 | 20
690 | 33,003
691 | 382
699 | 39
730 | 51,481
751 | 103
752 | 4,701
753 | 44
755 | 7
758 | 6
760 | 3,478
762 | 93
765 | 657
767 | 174
770 | 2,314
772 | 1,615
773 | 6,291
774 | 24
775 | 3,868
776 | 152,189
777 | 754
780 | 36,829
785 | 32,197
786 | 1
787 | 5,445
793 | 7,669
850 | 7,936
852 | 27
853 | 2
854 | 1
863 | 1
866 | 269
880 | 223,954
883 | 20
886 | 1,013
887 | 34
928 | 480,790
## Mapped FOLIO fields
The number of times a certain FOLIO field was filled with information
Fielname | Count
--- | ---:
alternativeTitles | 527,156
classifications | 2,903,673
contributors | 3,066,102
discoverySuppress | 3,114,577
editions | 475,387
electronicAccess | 87,075
id | 3,114,577
identifiers | 3,114,577
indexTitle | 3,114,564
instanceFormatIds | 2,986,232
instanceTypeId | 3,114,577
languages | 3,089,573
metadata | 3,114,577
notes | 2,971,975
physicalDescriptions | 3,102,788
publication | 3,060,521
publicationFrequency | 52,644
publicationRange | 74,846
series | 1,206,927
source | 3,114,577
staffSuppress | 3,114,577
subjects | 2,831,348
title | 3,114,577
## Unmapped FOLIO fields
The number of records missing certain FOLIO fields
Tag | Count
--- | ---:
alternativeTitles | 2,587,421
catalogedDate | 3,114,577
classifications | 210,904
contributors | 48,475
editions | 2,639,190
electronicAccess | 3,027,502
holdingsRecords2 | 3,114,577
hrid | 3,114,577
instanceFormatIds | 128,345
instanceFormats | 3,114,577
matchKey | 3,114,577
modeOfIssuanceId | 3,114,577
natureOfContentTermIds | 3,114,577
notes | 142,602
physicalDescriptions | 11,789
previouslyHeld | 3,114,577
publication | 54,056
publicationFrequency | 3,061,933
publicationRange | 3,039,731
series | 1,907,650
sourceRecordFormat | 3,114,577
statisticalCodeIds | 3,114,577
statusId | 3,114,577
statusUpdatedDate | 3,114,577
subjects | 283,229
tags | 3,114,577
## Unmapped conditions in rules
Conditions from the mapping-rules never covered by the transformation
Measure | Number
--- | ---:
## Record status counts
Record status in the records from Leader in position 05   Valid values are a - Increase in encoding level, c - Corrected or revised, d - Deleted, n - New, p - Increase in encoding level from prepublication
Measure | Number
--- | ---:
  | 25
/ | 1
0 | 1
3 | 1
5 | 1
8 | 1
I | 1
K | 1
a | 33,402
c | 1,537,223
g | 1
m | 1
n | 1,276,369
o | 2
p | 267,661
q | 1
s | 1
## Unrecognized language codes in records - 867 things
0en not recognized for ['000112266']\
0en not recognized for ['000112266']\
0en not recognized for ['000112267']\
0en not recognized for ['000112267']\
ong not recognized for ['000112735']\
frc not recognized for ['001271321']\
fle not recognized for ['001272975']\
fer not recognized for ['001276583']\
chz not recognized for ['000117883']\
enk not recognized for ['000120405']\
0en not recognized for ['000122811', '001561792']\
0en not recognized for ['000122811', '001561792']\
grm not recognized for ['001356717']\
ent not recognized for ['000695709', '001367854']\
cro not recognized for ['001419907']\
ser not recognized for ['001424384']\
fle not recognized for ['000011651', '001425967']\
ser not recognized for ['001427737']\
fle not recognized for ['001434724']\
cro not recognized for ['001438625', '002869866']\
fle not recognized for ['001438989']\
0en not recognized for ['001440572']\
0en not recognized for ['001440572']\
0en not recognized for ['016198321', '001442678']\
0en not recognized for ['016198321', '001442678']\
fer not recognized for ['000025835', '001442768']\
0 e not recognized for ['001444126']\
0 e not recognized for ['001444126']\
ung not recognized for ['001445168']\
fle not recognized for ['001446416']\
fle not recognized for ['001448321', '002889604']\
0en not recognized for ['001449946', '002892310', '000031799']\
0en not recognized for ['001449946', '002892310', '000031799']\
cro not recognized for ['001450067']\
0en not recognized for ['001450513']\
0en not recognized for ['001450513']\
0en not recognized for ['001450731']\
0en not recognized for ['001450731']\
0en not recognized for ['001450784']\
0en not recognized for ['001450784']\
0en not recognized for ['001450843']\
0en not recognized for ['001450843']\
0en not recognized for ['001450866']\
0en not recognized for ['001450866']\
fle not recognized for ['001452947']\
fle not recognized for ['001459855']\
0en not recognized for ['001469902', '002370821']\
0en not recognized for ['001469902', '002370821']\
jrc not recognized for ['000896214', '002401827', '001484613']\
cro not recognized for ['000132850']\
fle not recognized for ['001487530']\
rur not recognized for ['001508366']\
mhg not recognized for ['001509479']\
1at not recognized for ['001511251']\
psa not recognized for ['000914741', '001518340']\
0en not recognized for ['001522917']\
0en not recognized for ['001522917']\
wng not recognized for ['001523964']\
dna not recognized for ['001539351']\
dna not recognized for ['001542421']\
dna not recognized for ['001542421']\
0en not recognized for ['001542983']\
0en not recognized for ['001542983']\
iti not recognized for ['001545532']\
0en not recognized for ['001555163', '002445523']\
0en not recognized for ['001555163', '002445523']\
rur not recognized for ['001556892']\
enk not recognized for ['001559065']\
grk not recognized for ['001559708']\
0en not recognized for ['001559876']\
0en not recognized for ['001559876']\
0en not recognized for ['001561255']\
0en not recognized for ['000139917', '001582341']\
0en not recognized for ['000139917', '001582341']\
0en not recognized for ['001564213']\
0en not recognized for ['001564213']\
0en not recognized for ['001565962']\
0en not recognized for ['001565962']\
0en not recognized for ['001572150']\
0en not recognized for ['001572150']\
emg not recognized for ['001576020']\
ffr not recognized for ['001578495']\
0en not recognized for ['001584866', '000142006']\
0en not recognized for ['001584866', '000142006']\
csz not recognized for ['001594164', '002588644']\
0en not recognized for ['001598158']\
0en not recognized for ['001598158']\
0en not recognized for ['001600379']\
0en not recognized for ['001600379']\
0en not recognized for ['001604525']\
0en not recognized for ['001604525']\
grk not recognized for ['000145009']\
rur not recognized for ['001626841', '000982441']\
0en not recognized for ['001629041']\
0en not recognized for ['001629041']\
fle not recognized for ['002654715', '001630024']\
rur not recognized for ['001630622', '002655916', '000984574', '000177667']\
0en not recognized for ['001633404']\
0en not recognized for ['001633404']\
0en not recognized for ['001633410']\
0en not recognized for ['001633410']\
0en not recognized for ['001633871']\
0en not recognized for ['001633871']\
0en not recognized for ['001634034']\
0en not recognized for ['001634034']\
0en not recognized for ['001639749']\
0en not recognized for ['001639749']\
0en not recognized for ['001640363']\
0en not recognized for ['001640363']\
.k6 not recognized for ['001642312', '000186983']\
445 not recognized for ['001642312', '000186983']\
bl1 not recognized for ['001642312', '000186983']\
0en not recognized for ['001646098', '002704785']\
0en not recognized for ['001646098', '002704785']\
fle not recognized for ['001650522']\
fle not recognized for ['001652484']\
pre not recognized for ['001657920']\
ℓat not recognized for ['001658908']\
 fr not recognized for ['001659769']\
0en not recognized for ['001659851']\
0en not recognized for ['001659851']\
0en not recognized for ['002325124', '001669926']\
0en not recognized for ['002325124', '001669926']\
rur not recognized for ['001671802']\
fle not recognized for ['001678702']\
enf not recognized for ['000151622']\
0en not recognized for ['002746190', '001681242']\
0en not recognized for ['002746190', '001681242']\
ser not recognized for ['001683435']\
cro not recognized for ['001683435']\
ser not recognized for ['001683435']\
0en not recognized for ['001684457']\
0en not recognized for ['001684457']\
gen not recognized for ['001684756']\
0en not recognized for ['002752383', '001684999']\
0en not recognized for ['002752383', '001684999']\
ser not recognized for ['001685112']\
emg not recognized for ['001692156']\
lag not recognized for ['001694038']\
enh not recognized for ['000231930', '003328123', '001697718']\
0en not recognized for ['001703260']\
0en not recognized for ['001703260']\
fle not recognized for ['001709995']\
sap not recognized for ['001710468']\
epa not recognized for ['001716502', '000247380', '000761275']\
enf not recognized for ['001716659']\
ser not recognized for ['002789873', '001717172']\
cro not recognized for ['000257024', '003279528', '001727686']\
end not recognized for ['001731452', '002943259']\
cro not recognized for ['002965201', '001739781']\
ser not recognized for ['000157890']\
fle not recognized for ['001749732', '003010706']\
jun not recognized for ['000159120']\
'un not recognized for ['000282997', '001755580']\
cro not recognized for ['001757495', '000284761', '000772635', '001069299', '003024306']\
ser not recognized for ['001761015']\
115 not recognized for ['000160477']\
319 not recognized for ['000160477']\
701 not recognized for ['000160477']\
ser not recognized for ['001773568', '003056934']\
fle not recognized for ['001780200']\
tro not recognized for ['000162275']\
0en not recognized for ['000015501']\
0en not recognized for ['000015501']\
cro not recognized for ['001791730']\
.t6 not recognized for ['001800374']\
fle not recognized for ['000164599']\
fle not recognized for ['001810473']\
fle not recognized for ['001810473']\
ser not recognized for ['001811530']\
cro not recognized for ['001811696']\
cna not recognized for ['001811716']\
cna not recognized for ['001811716']\
fle not recognized for ['001817819']\
fle not recognized for ['001820662']\
oli not recognized for ['000167566']\
0en not recognized for ['001833765']\
0en not recognized for ['001833765']\
unk not recognized for ['001837245']\
0en not recognized for ['001839635']\
0en not recognized for ['001839635']\
fle not recognized for ['001843975']\
cro not recognized for ['000169233']\
cro not recognized for ['001140638', '002992610', '001859117']\
enf not recognized for ['001862961']\
gke not recognized for ['001864556', '003002324', '000378748', '001144990']\
egn not recognized for ['001867673', '001147235', '000381678']\
0en not recognized for ['001875952']\
0en not recognized for ['001875952']\
0en not recognized for ['001885585']\
0en not recognized for ['001885585']\
0en not recognized for ['002339594', '000391151', '001886889', '004861566']\
0en not recognized for ['002339594', '000391151', '001886889', '004861566']\
ico not recognized for ['002340856', '001886979']\
0en not recognized for ['001888862']\
0en not recognized for ['001888862']\
pen not recognized for ['001892108']\
emg not recognized for ['001893764']\
enf not recognized for ['001902104', '000407052']\
0en not recognized for ['001904482']\
0en not recognized for ['001904482']\
ghm not recognized for ['001905804']\
0en not recognized for ['001909627']\
0en not recognized for ['001909627']\
0en not recognized for ['001910016']\
0en not recognized for ['001910016']\
emn not recognized for ['000414183', '001910727', '002663959', '001176606']\
0en not recognized for ['000174801']\
0en not recognized for ['000174801']\
fle not recognized for ['001914035']\
0en not recognized for ['001915068', '002721417', '010746276']\
fle not recognized for ['001917498']\
0en not recognized for ['016195599', '001918858']\
0en not recognized for ['016195599', '001918858']\
ser not recognized for ['001921885', '000423196']\
0en not recognized for ['001925263', '011404747']\
0en not recognized for ['001926944', '010561301']\
0en not recognized for ['001926944', '010561301']\
0en not recognized for ['001927464', '011244661', '002869979']\
0en not recognized for ['001927464', '011244661', '002869979']\
0en not recognized for ['001928293', '002878308']\
0en not recognized for ['001928293', '002878308']\
0en not recognized for ['001929993']\
0en not recognized for ['001929993']\
0en not recognized for ['001930063', '002896397', '000799487']\
0en not recognized for ['001930063', '002896397', '000799487']\
cro not recognized for ['001195878', '001932148']\
ser not recognized for ['003001134', '001199121', '001936060']\
ser not recognized for ['001199421', '003004015', '001936357']\
ser not recognized for ['000439944', '001941336']\
cro not recognized for ['000443903', '001945850', '003122113']\
0en not recognized for ['001946992']\
0en not recognized for ['001946992']\
0en not recognized for ['001947414', '012463920']\
0en not recognized for ['001947414', '012463920']\
0en not recognized for ['001947947']\
0en not recognized for ['001947947']\
ris not recognized for ['001953069']\
end not recognized for ['000462967', '001963977']\
emn not recognized for ['001970487', '000468917']\
ite not recognized for ['001977075']\
frc not recognized for ['001978406']\
spe not recognized for ['000483093', '001983405']\
mhg not recognized for ['001987652']\
dng not recognized for ['001992192']\
rur not recognized for ['001992415']\
jpa not recognized for ['001995238']\
hug not recognized for ['001996495']\
cro not recognized for ['000017380']\
cro not recognized for ['000017381']\
vit not recognized for ['003664800', '001248077', '000507596', '002007853']\
end not recognized for ['002014235']\
ghm not recognized for ['002020852']\
grk not recognized for ['002027693']\
rur not recognized for ['002033860']\
emg not recognized for ['002048168']\
jpa not recognized for ['000547848', '002048761', '003765037']\
val not recognized for ['002061453']\
lag not recognized for ['002068582']\
ohi not recognized for ['000190035']\
cro not recognized for ['000018090']\
cce not recognized for ['002098367']\
fle not recognized for ['000018191']\
3ng not recognized for ['003963994', '001308601', '002107159']\
dng not recognized for ['002115127']\
enf not recognized for ['004009803', '002117968']\
fer not recognized for ['002119807']\
itr not recognized for ['002121165', '002121168']\
grk not recognized for ['002126860']\
tot not recognized for ['002143332']\
dca not recognized for ['002143898']\
dca not recognized for ['002143898']\
ent not recognized for ['002147612']\
0en not recognized for ['000197015']\
0en not recognized for ['000197015']\
ent not recognized for ['002153882']\
dam not recognized for ['002154479']\
dnc not recognized for ['002155911']\
emg not recognized for ['002156686']\
ait not recognized for ['002158102']\
fer not recognized for ['002159774']\
dag not recognized for ['002162466']\
cay not recognized for ['002162574', '000656860']\
fle not recognized for ['002166917']\
sue not recognized for ['002181265']\
stk not recognized for ['002194339']\
egn not recognized for ['002211472']\
emg not recognized for ['002216645']\
ehg not recognized for ['002228435']\
0en not recognized for ['002246591']\
0en not recognized for ['002246591']\
nig not recognized for ['002252592']\
rur not recognized for ['002290247']\
0en not recognized for ['000207513']\
0en not recognized for ['000207513']\
0en not recognized for ['000208084']\
0en not recognized for ['000208084']\
cpa not recognized for ['002299672']\
cpa not recognized for ['002299672']\
0en not recognized for ['002359090']\
shi not recognized for ['002359462']\
enr not recognized for ['000213983']\
--- not recognized for ['002376157']\
let not recognized for ['002377417']\
gue not recognized for ['002379760']\
sze not recognized for ['002384256']\
0en not recognized for ['002384844']\
0en not recognized for ['002384844']\
spe not recognized for ['002394818']\
rur not recognized for ['002400837']\
rur not recognized for ['002405803']\
e-g not recognized for ['002406222']\
ire not recognized for ['000217304']\
cro not recognized for ['002409149']\
0en not recognized for ['000217716']\
0en not recognized for ['000217716']\
ser not recognized for ['000020639']\
unk not recognized for ['002435110']\
unk not recognized for ['002435555']\
ssc not recognized for ['002470696']\
lar not recognized for ['002473049']\
ngm not recognized for ['002474057']\
ngm not recognized for ['002474057']\
unr not recognized for ['002495857']\
rou not recognized for ['000225431']\
don not recognized for ['002518785']\
sia not recognized for ['002522639']\
ser not recognized for ['002524029']\
rur not recognized for ['002524436']\
ens not recognized for ['002536097']\
agm not recognized for ['002536856']\
0en not recognized for ['000228096']\
0en not recognized for ['000228096']\
urs not recognized for ['002542352']\
aoa not recognized for ['002542357']\
nem not recognized for ['002542500']\
ekr not recognized for ['002543202']\
lag not recognized for ['000228942']\
ser not recognized for ['002550526']\
cro not recognized for ['000229817']\
cro not recognized for ['002579172']\
duc not recognized for ['002588226']\
ngm not recognized for ['002594807']\
ngm not recognized for ['002594807']\
e-f not recognized for ['002595533']\
ser not recognized for ['002597858']\
cro not recognized for ['002607409']\
tpn not recognized for ['002614639']\
end not recognized for ['002618233']\
cro not recognized for ['002618660']\
end not recognized for ['002619214']\
519 not recognized for ['002636608']\
55a not recognized for ['002636608']\
.n3 not recognized for ['002636608']\
for not recognized for ['002649987']\
0en not recognized for ['002653318']\
0en not recognized for ['002653318']\
cro not recognized for ['000238058']\
cro not recognized for ['000238058']\
nkr not recognized for ['002659113']\
enk not recognized for ['002660840']\
enf not recognized for ['002679749']\
fle not recognized for ['002681445']\
cro not recognized for ['002681627']\
sia not recognized for ['002683409']\
mor not recognized for ['002689295']\
fle not recognized for ['002691739']\
0en not recognized for ['002693206']\
0en not recognized for ['002693206']\
bag not recognized for ['002693560']\
cro not recognized for ['002693736']\
cro not recognized for ['002714221']\
vas not recognized for ['002729939']\
cro not recognized for ['002733637']\
yug not recognized for ['002734727']\
ser not recognized for ['002734753']\
0en not recognized for ['001013950', '001678978', '002741910']\
0en not recognized for ['001013950', '001678978', '002741910']\
fle not recognized for ['002742043']\
fle not recognized for ['002742248']\
fle not recognized for ['002742253']\
ser not recognized for ['002742694']\
cro not recognized for ['002743638']\
fle not recognized for ['002748277']\
cro not recognized for ['002749757']\
ser not recognized for ['000220382', '002750343']\
ser not recognized for ['002752876']\
ser not recognized for ['002753963']\
ser not recognized for ['002755593']\
cro not recognized for ['002755858']\
cro not recognized for ['002757571', '000232964']\
ser not recognized for ['002757897']\
ser not recognized for ['002757919']\
cro not recognized for ['002758481']\
ire not recognized for ['002763172']\
ser not recognized for ['002771582', '000238926']\
cro not recognized for ['000810687', '002773101']\
rak not recognized for ['002777664']\
ser not recognized for ['000242027', '002778280']\
ser not recognized for ['002778500']\
ser not recognized for ['002778845']\
cro not recognized for ['002782568']\
cro not recognized for ['002784472']\
cro not recognized for ['002784628']\
fle not recognized for ['002785401']\
cro not recognized for ['002788018']\
cro not recognized for ['002788721']\
cro not recognized for ['002791107']\
gri not recognized for ['002793227']\
cro not recognized for ['002793683']\
cro not recognized for ['002795228']\
pur not recognized for ['002797563']\
cro not recognized for ['002805052']\
ser not recognized for ['002806480', '000001899']\
ngm not recognized for ['002807462']\
ngm not recognized for ['002807462']\
ngm not recognized for ['002807671']\
ngm not recognized for ['002807671']\
ser not recognized for ['000003515', '002809538']\
fle not recognized for ['002809683']\
ser not recognized for ['002812400']\
fle not recognized for ['002819904']\
cro not recognized for ['002822119']\
fle not recognized for ['002828879']\
ser not recognized for ['002829641']\
gmb not recognized for ['000251645']\
fle not recognized for ['002835833']\
ser not recognized for ['002836006']\
fle not recognized for ['002839855']\
cro not recognized for ['002844696']\
ser not recognized for ['002857093', '000503312']\
cro not recognized for ['000253749']\
enf not recognized for ['002864676']\
ser not recognized for ['000254166']\
0en not recognized for ['000024096']\
0en not recognized for ['000024096']\
arb not recognized for ['002869059', '000022060']\
cro not recognized for ['002869440']\
fle not recognized for ['002870548']\
cro not recognized for ['002874986']\
ng  not recognized for ['002875393']\
ng  not recognized for ['002875393']\
0 e not recognized for ['002881004']\
0 e not recognized for ['002881004']\
0en not recognized for ['002882074']\
0en not recognized for ['002882074']\
cro not recognized for ['002891694']\
cro not recognized for ['002896000']\
fle not recognized for ['002896392']\
obj not recognized for ['002899091']\
cro not recognized for ['002899843']\
spe not recognized for ['002906508']\
end not recognized for ['002906828']\
cro not recognized for ['002909894']\
cro not recognized for ['002913870']\
ser not recognized for ['002915244']\
cro not recognized for ['002915244']\
hkr not recognized for ['002920891']\
cro not recognized for ['002922467']\
ser not recognized for ['002923117']\
cro not recognized for ['002923232']\
ser not recognized for ['002924172']\
cro not recognized for ['002924976']\
ser not recognized for ['002925652']\
ser not recognized for ['002926234']\
fle not recognized for ['002926355']\
cro not recognized for ['002926772']\
cro not recognized for ['000506288', '002928270']\
cro not recognized for ['002928274']\
ser not recognized for ['000255657', '002929983']\
cro not recognized for ['002935085']\
ser not recognized for ['002939422']\
ser not recognized for ['002942336']\
ser not recognized for ['002943360']\
ser not recognized for ['002945140']\
ser not recognized for ['002950050']\
cro not recognized for ['002950458']\
ser not recognized for ['000495296', '002950753']\
cro not recognized for ['002950994']\
ser not recognized for ['000521396', '002951347']\
cro not recognized for ['002954282']\
cro not recognized for ['000264743', '002956413']\
cro not recognized for ['002957170']\
enf not recognized for ['002966625']\
cro not recognized for ['002971571']\
cro not recognized for ['002971599']\
ngm not recognized for ['002971865']\
ngm not recognized for ['002971865']\
ser not recognized for ['002973713']\
cro not recognized for ['000277011', '002984811']\
cro not recognized for ['002984973']\
cro not recognized for ['002995184']\
ngm not recognized for ['002996513']\
ngm not recognized for ['002996513']\
fle not recognized for ['002997584']\
cro not recognized for ['002998239']\
fle not recognized for ['003003369']\
ser not recognized for ['003004014']\
ser not recognized for ['003004016']\
ser not recognized for ['003004102']\
cro not recognized for ['003004102']\
ngd not recognized for ['003008312']\
ngd not recognized for ['003008312']\
ser not recognized for ['003010566']\
ser not recognized for ['003030573']\
cro not recognized for ['003031179']\
cro not recognized for ['003037109']\
cro not recognized for ['003037346']\
ser not recognized for ['003038632']\
ser not recognized for ['003039489']\
ser not recognized for ['003039599']\
fle not recognized for ['003040204']\
ser not recognized for ['003040421']\
cro not recognized for ['003040763']\
cro not recognized for ['003041000']\
ser not recognized for ['003041333']\
cro not recognized for ['003046615', '000294692']\
ser not recognized for ['003046942']\
cca not recognized for ['003047784']\
cca not recognized for ['003047784']\
cro not recognized for ['003049050']\
cro not recognized for ['000265724']\
cro not recognized for ['003049913']\
fle not recognized for ['003053540']\
cro not recognized for ['003063290']\
fle not recognized for ['003066488']\
ngm not recognized for ['003067009']\
ngm not recognized for ['003067009']\
ser not recognized for ['001204530', '000440592', '003070393']\
ser not recognized for ['003070398']\
cro not recognized for ['003071615']\
cro not recognized for ['000309650', '003078177']\
cro not recognized for ['003094914']\
fle not recognized for ['003100085']\
cro not recognized for ['003105675']\
cro not recognized for ['003105680']\
ser not recognized for ['003106347']\
cro not recognized for ['003106347']\
ng  not recognized for ['003110349']\
ng  not recognized for ['003110349']\
fle not recognized for ['003111345']\
fle not recognized for ['003113521']\
cro not recognized for ['003115390']\
cro not recognized for ['003118142']\
ser not recognized for ['003122169']\
ser not recognized for ['003122177']\
gas not recognized for ['003122957']\
ngm not recognized for ['003125238']\
ngm not recognized for ['003125238']\
cro not recognized for ['003126050']\
ser not recognized for ['003133827']\
ser not recognized for ['000271395']\
n-u not recognized for ['003135048']\
ser not recognized for ['003136735', '000872182']\
ser not recognized for ['000271689']\
0en not recognized for ['003165554']\
0en not recognized for ['003165554']\
itl not recognized for ['000055298', '000893407', '003172916']\
0en not recognized for ['003181009']\
mym not recognized for ['003194090']\
dau not recognized for ['003198224']\
fle not recognized for ['003236137']\
fle not recognized for ['003254723']\
ser not recognized for ['003259101']\
0en not recognized for ['003261309']\
0en not recognized for ['003261309']\
0en not recognized for ['003264296']\
0en not recognized for ['003264296']\
cro not recognized for ['003265137']\
rur not recognized for ['003268171']\
0en not recognized for ['003268872']\
0en not recognized for ['003268872']\
cro not recognized for ['003276440']\
ser not recognized for ['000726169', '000884187', '000042791', '003278288']\
ser not recognized for ['003278779']\
cro not recognized for ['003278831']\
eny not recognized for ['003290445']\
cro not recognized for ['003291243']\
cro not recognized for ['000305097', '001086415', '003294437']\
0en not recognized for ['003303578']\
0en not recognized for ['003303578']\
sum not recognized for ['003316078']\
cro not recognized for ['003326880']\
cro not recognized for ['003326880']\
lsk not recognized for ['003328256']\
fle not recognized for ['003332890']\
enf not recognized for ['003361084']\
wan not recognized for ['003366512']\
ser not recognized for ['003375563']\
soa not recognized for ['003400159']\
ebg not recognized for ['003400159']\
fle not recognized for ['000292090']\
spd not recognized for ['003439571']\
dcg not recognized for ['003585621']\
dcg not recognized for ['003585621']\
fle not recognized for ['003609228']\
uka not recognized for ['003629999']\
sca not recognized for ['003652532', '001544079', '000105228']\
ser not recognized for ['000003103']\
cro not recognized for ['003673410']\
enr not recognized for ['003673572']\
qui not recognized for ['003675373']\
ung not recognized for ['003679311', '001678152']\
cro not recognized for ['003680197', '001428087', '000013558']\
thi not recognized for ['003681023', '001255428', '000813254', '000519579']\
rur not recognized for ['003681884']\
ser not recognized for ['003685898']\
rur not recognized for ['003694138']\
bab not recognized for ['003716143']\
fle not recognized for ['003747338']\
ser not recognized for ['003748658']\
ser not recognized for ['003748659']\
grk not recognized for ['001551790', '003780059', '000113086']\
0en not recognized for ['000315579']\
0en not recognized for ['000315579']\
jnp not recognized for ['003820647']\
cro not recognized for ['003826022']\
cro not recognized for ['003826025']\
pcc not recognized for ['003864540']\
src not recognized for ['003866964']\
ser not recognized for ['003870565']\
enf not recognized for ['003878718']\
fer not recognized for ['003882739']\
grk not recognized for ['003892396']\
ill not recognized for ['003912873']\
mia not recognized for ['003912873']\
pah not recognized for ['003916177']\
end not recognized for ['003922951']\
0en not recognized for ['000031780']\
0en not recognized for ['000031780']\
pah not recognized for ['003948141']\
frn not recognized for ['003957493']\
skv not recognized for ['003962844']\
ser not recognized for ['003963365']\
enb not recognized for ['003965497']\
0en not recognized for ['000032481']\
0en not recognized for ['000032481']\
0en not recognized for ['000032592']\
0en not recognized for ['000032592']\
ser not recognized for ['003999350']\
src not recognized for ['004011758']\
bbb not recognized for ['000535595', '004024720']\
e-f not recognized for ['000033086']\
ser not recognized for ['000339326']\
ser not recognized for ['000560511', '004085983']\
enf not recognized for ['002139183', '000636940', '004089867']\
sre not recognized for ['004106263']\
sqo not recognized for ['004106294']\
ser not recognized for ['004106663']\
ser not recognized for ['001334789', '002153751', '000649494', '004122085']\
iti not recognized for ['004224169']\
ite not recognized for ['004224169']\
enk not recognized for ['004225838']\
có not recognized for ['004268177']\
jen not recognized for ['004416069']\
231 not recognized for ['004423277']\
033 not recognized for ['004423277']\
unk not recognized for ['004423387']\
enh not recognized for ['004318973', '004436812', '004321947']\
cro not recognized for ['000035458']\
0en not recognized for ['004860636']\
0en not recognized for ['004860636']\
0en not recognized for ['003707148', '004860647']\
0en not recognized for ['003707148', '004860647']\
0en not recognized for ['004860669']\
0en not recognized for ['004860669']\
0en not recognized for ['004861275']\
0en not recognized for ['004861275']\
0en not recognized for ['004861335']\
0en not recognized for ['004861335']\
0en not recognized for ['004861621']\
0en not recognized for ['004861621']\
0en not recognized for ['001928860', '004862038', '000799363']\
0en not recognized for ['001928860', '004862038', '000799363']\
0en not recognized for ['016469256', '004862062', '001929552', '002892140']\
0en not recognized for ['016469256', '004862062', '001929552', '002892140']\
cro not recognized for ['004874289']\
rur not recognized for ['001157526', '004927115']\
enh not recognized for ['004973596', '004940404']\
cro not recognized for ['004955595']\
0en not recognized for ['000366032']\
0en not recognized for ['000366032']\
unk not recognized for ['004977787']\
och not recognized for ['004981040']\
0en not recognized for ['004996143']\
0en not recognized for ['004996143']\
enf not recognized for ['000367572']\
0en not recognized for ['000369286']\
0en not recognized for ['000369286']\
0en not recognized for ['000369295']\
0en not recognized for ['000369295']\
0en not recognized for ['010340390']\
0en not recognized for ['010340390']\
enh not recognized for ['010473009']\
0en not recognized for ['010588058', '002895045']\
0en not recognized for ['010588058', '002895045']\
ico not recognized for ['010619181']\
enh not recognized for ['010660306']\
fle not recognized for ['010813661']\
0en not recognized for ['010815898']\
0en not recognized for ['010815898']\
0en not recognized for ['010816618']\
0en not recognized for ['010816618']\
hew not recognized for ['010818052', '011049072']\
0en not recognized for ['011178065']\
0en not recognized for ['011178065']\
pcc not recognized for ['011190088']\
0en not recognized for ['011253231', '002390089']\
0en not recognized for ['011253231', '002390089']\
0en not recognized for ['011316877', '000729189']\
0en not recognized for ['011316877', '000729189']\
0en not recognized for ['011405511']\
0en not recognized for ['011405511']\
0en not recognized for ['011405512', '000923766']\
0en not recognized for ['011405512', '000923766']\
0en not recognized for ['011405538']\
0en not recognized for ['011405538']\
0en not recognized for ['000386671']\
0en not recognized for ['000386671']\
dcg not recognized for ['000387123']\
dcg not recognized for ['000387123']\
ijn not recognized for ['011252052', '011877323', '011250723']\
enk not recognized for ['011878557', '012112614', '011894478']\
enk not recognized for ['011878557', '012112614', '011894478']\
grk not recognized for ['011268513', '011246825', '012284744']\
enk not recognized for ['012295447', '012299502', '012315846']\
pcc not recognized for ['012381976', '012353357']\
srb not recognized for ['012465139']\
pcc not recognized for ['012295431', '012488413']\
rur not recognized for ['000397052']\
uru not recognized for ['012949711']\
ser not recognized for ['000403042']\
ned not recognized for ['014322483']\
are not recognized for ['014323359']\
grk not recognized for ['014390068']\
are not recognized for ['014631949']\
end not recognized for ['014665433']\
cyr not recognized for ['015006476']\
hua not recognized for ['015134680']\
guw not recognized for ['015694846']\
soa not recognized for ['015825683']\
rda not recognized for ['015844322']\
cro not recognized for ['000420019']\
eno not recognized for ['016182105']\
res not recognized for ['016187457']\
cro not recognized for ['016195508', '000487683']\
ser not recognized for ['000248621', '016196208']\
ser not recognized for ['016196209']\
ser not recognized for ['016196975']\
ser not recognized for ['016196976']\
ser not recognized for ['016197504']\
cro not recognized for ['016198283']\
fle not recognized for ['016199671']\
cro not recognized for ['016200586']\
cro not recognized for ['016201010']\
ngm not recognized for ['016201508']\
ngm not recognized for ['016201508']\
ser not recognized for ['016202127']\
cro not recognized for ['016202355']\
cro not recognized for ['016202422']\
yah not recognized for ['016206315']\
ser not recognized for ['016206619']\
ser not recognized for ['016206619']\
enf not recognized for ['016372801']\
0en not recognized for ['000426156', '002847369']\
0en not recognized for ['000426156', '002847369']\
enn not recognized for ['001683600', '016479145']\
1en not recognized for ['000429798']\
1en not recognized for ['000429798']\
0en not recognized for ['000799495', '000430142']\
0en not recognized for ['000799495', '000430142']\
v7a not recognized for ['016276561', '017117478']\
lbe not recognized for ['016276561', '017117478']\
fle not recognized for ['000441988']\
ire not recognized for ['000043399']\
ser not recognized for ['000452103']\
acr not recognized for ['000476805']\
fle not recognized for ['000501120']\
ser not recognized for ['000510161']\
fle not recognized for ['000511304']\
fle not recognized for ['000516966']\
ser not recognized for ['000524470']\
cro not recognized for ['000533811']\
igb not recognized for ['000534329']\
unk not recognized for ['000549081']\
enk not recognized for ['000556154']\
grk not recognized for ['000567587']\
lvt not recognized for ['000570259']\
end not recognized for ['000583966']\
jnp not recognized for ['000589932']\
asa not recognized for ['000624839']\
heg not recognized for ['000625693']\
jeb not recognized for ['000633104']\
unk not recognized for ['000646304']\
gew not recognized for ['000661345']\
jpa not recognized for ['000670224']\
end not recognized for ['000690660']\
hew not recognized for ['000062166']\
ser not recognized for ['000720723']\
cro not recognized for ['000720723']\
006 not recognized for ['000726955']\
jan not recognized for ['000744631']\
0en not recognized for ['000751240', '010164250']\
0en not recognized for ['000751240', '010164250']\
ser not recognized for ['000751382']\
neg not recognized for ['000752014']\
jpa not recognized for ['000227697', '003204217', '000758300', '001692513']\
uca not recognized for ['000776302']\
uca not recognized for ['000776302']\
0en not recognized for ['000803725']\
0en not recognized for ['000803725']\
ser not recognized for ['000810681']\
cro not recognized for ['000811009']\
0en not recognized for ['000068803']\
0en not recognized for ['000068803']\
jpa not recognized for ['000827159']\
cro not recognized for ['002843837', '000866639']\
cro not recognized for ['002911433', '000882117']\
0en not recognized for ['000073778']\
spq not recognized for ['000905589', '002499930']\
rur not recognized for ['000909059']\
s4r not recognized for ['000913104']\
enk not recognized for ['000921066']\
unk not recognized for ['002293735', '000094693', '000922017']\
ani not recognized for ['000952329']\
ser not recognized for ['000960935']\
spn not recognized for ['002601194', '000967671']\
rur not recognized for ['000163177', '000973948']\
src not recognized for ['000975586', '000748966']\
0en not recognized for ['000083638']\
0en not recognized for ['000083638']\
fle not recognized for ['000217223', '001014477']\
cro not recognized for ['001014484']\
cro not recognized for ['001014484']\
ser not recognized for ['001027363']\
itl not recognized for ['001027901', '000233776']\
ser not recognized for ['002779346', '001034453']\
ass not recognized for ['001035599']\
cro not recognized for ['001043937', '000255356', '002924097']\
0en not recognized for ['001525621', '000090519']\
0en not recognized for ['001525621', '000090519']\
ser not recognized for ['001049245', '000765560', '002946261', '000261547']\
cro not recognized for ['001063081']\
cro not recognized for ['000009017']\
unk not recognized for ['001064607']\
cro not recognized for ['001073225']\
ser not recognized for ['003039496', '001075276']\
cro not recognized for ['003042785', '000292722', '001075878']\
ser not recognized for ['001087296']\
cro not recognized for ['003079507', '001090520']\
cro not recognized for ['001102492', '003094418', '000326731', '000781588']\
fle not recognized for ['000330594', '001105664']\
n-u not recognized for ['001118044', '000345539']\
unk not recognized for ['000369443', '002985079', '001136969', '000788558']\
cro not recognized for ['001137867', '002986963']\
ser not recognized for ['001145679']\
end not recognized for ['001154959']\
grk not recognized for ['001169002', '000406865']\
arb not recognized for ['001177155']\
ser not recognized for ['001186343']\
grk not recognized for ['001194189']\
ser not recognized for ['001195054']\
cro not recognized for ['000481584', '001232596']\
cro not recognized for ['001232644']\
cro not recognized for ['001232645']\
cro not recognized for ['001232646']\
unk not recognized for ['001232647']\
## Records failed to migrate due to Value errors found in Transformation - 116 things
No title for ['001621513'] for None \
No title for ['001656459'] for None \
No title for ['001807895'] for None \
No title for ['001843746'] for None \
No title for ['001852236'] for None \
No title for ['000170293'] for None \
No title for ['002062130'] for None \
No title for ['002155884'] for None \
No title for ['000198627'] for None \
No title for ['002939365'] for None \
No title for ['003167139'] for None \
No Instance type ID for None \
No title for ['001035000', '003388703'] for None \
No title for ['003389316'] for None \
No title for ['003394063'] for None \
No title for ['003401932'] for None \
No title for ['003403439'] for None \
No title for ['003403519'] for None \
No title for ['003406376'] for None \
No title for ['003409645'] for None \
No title for ['003413362'] for None \
No title for ['003415006'] for None \
No title for ['003415017'] for None \
No title for ['003421066'] for None \
No title for ['003431696'] for None \
No title for ['003580878'] for None \
No Instance type ID for None \
No title for ['000330496'] for None \
No Instance type ID for None \
No title for ['000348853'] for None \
No Instance type ID for None \
No title for ['004483916'] for None \
No title for ['004483918'] for None \
No title for ['004483922'] for None \
No title for ['004483925'] for None \
No title for ['004483927'] for None \
No title for ['004939587'] for None \
No title for ['004986967'] for None \
No title for ['010492390'] for None \
No title for ['010507479'] for None \
No title for ['010547185'] for None \
No title for ['011156404'] for None \
No title for ['011205046'] for None \
No title for ['011228895'] for None \
No title for ['011228913'] for None \
No title for ['011228920'] for None \
No title for ['011244781'] for None \
No title for ['012155226'] for None \
No title for ['012155272'] for None \
No title for ['012155319'] for None \
No title for ['012155397'] for None \
No title for ['012285151'] for None \
No title for ['012408984'] for None \
No title for ['012457733'] for None \
no matching instance_formats rdacarrier =338  \\$avolume$brdacarrier for None \
No title for ['012565625'] for None \
no matching instance_formats rdacarrier =338  \\$avolume$brdacarrier for None \
no matching instance_formats rdacarrier =338  \\$avolume$brdacarrier for None \
no matching instance_formats rdacarrier =338  \\$avolume$brdacarrier for None \
no matching instance_formats rdacarrier =338  \\$avolume$brdacarrier for None \
No title for ['014074131'] for None \
no matching instance_formats rdacarrier =338  \\$avolume$brdacarrier$2rdacarrier for None \
No title for ['014169027'] for None \
no matching instance_formats rdacarrier =338  \\$avolume$brdacarrier for None \
No Instance type ID for None \
no matching instance_formats n =338  \\$aunmediated$bn$2rdamedia for None \
no matching instance_formats nd =338  \\$avolume$bnd$2rdacarrier for None \
No title for ['014717766'] for None \
no matching instance_formats nd =338  \\$avolume$bnd$2rdacarrier for None \
No title for ['015086230'] for None \
No title for ['015086232'] for None \
No title for ['015631668'] for None \
No title for ['015632228'] for None \
No title for ['015825832'] for None \
No title for ['016015208'] for None \
No title for ['016033898'] for None \
No title for ['016453904'] for None \
No title for ['003017648', '016476444', '001753533'] for None \
No title for ['001979294', '016526144'] for None \
no matching instance_formats ntc =338  \\$avolume$bntc$2rdacarrier for None \
No title for ['016947374'] for None \
no matching instance_formats n =338  \\$avolume$bn$2isbdmedia for None \
no matching instance_formats n =338  \\$avolume$bn$2rdamedia for None \
no matching instance_formats n =338  \\$avolume$bn$2rdamedia for None \
No title for ['017099175'] for None \
No title for ['017118275'] for None \
No title for ['017123417'] for None \
No title for ['017395572'] for None \
No title for ['017502875'] for None \
No title for ['017505225'] for None \
No title for ['000447897'] for None \
No Instance type ID for None \
No Instance type ID for None \
No Instance type ID for None \
No Instance type ID for None \
No Instance type ID for None \
No Instance type ID for None \
No Instance type ID for None \
No Instance type ID for None \
No Instance type ID for None \
No Instance type ID for None \
No Instance type ID for None \
No Instance type ID for None \
No Instance type ID for None \
No Instance type ID for None \
No Instance type ID for None \
No Instance type ID for None \
No Instance type ID for None \
No Instance type ID for None \
No Instance type ID for None \
No Instance type ID for None \
No title for ['000072332'] for None \
No title for ['000905630'] for None \
No title for ['000914521'] for None \
No title for ['000077982'] for None \
No title for ['001061285'] for None \
## Bib records that failed to parse. - - 2 things
'ascii' codec can't decode byte 0xcc in position 70: ordinal not in range(128) b'03818cam a2200541Ii 4500005001700000008004100017Es 056800058016002300626020002600649020002300675024001800698035002400716040008000740041001300820050002800833072001300861072001300874100005000887240002600937245003700963264003701000300004501037336002601082336003301108337002801141338002701169520110001196520018202296650005202478650003502530651006602565651004902631651005002680651003302730650005202763650005502815651004102870655003402911655002702945655003902972655005603011655005303067655003903120655004603159655003903205998001803244928001403262\x1e20190919141941.0\x1e171215s2017    gw a     6    000 1 ger d\x1ebeginnt mit einer Bahnfahrt durch die Vororte Hamburgs. Doch an den Ra\xcc\x88ndern der Dinge, die der Protagonistin Nacha begegnen, stehen Verweise auf tiefergehende Informationen. In den Fu\xc3\x9fnoten liegt die Basis fu\xcc\x88r das Hier und Jetzt. Deutsche und argentinische Wirklichkeiten und Vergangenheiten u\xcc\x88berlagern sich. Eine Erza\xcc\x88hlerin auf der Spurensuche nach ihrer argentinischen Familie, die unter der Milita\xcc\x88rdiktatur der Siebzigerjahre gelitten hat. Ein ungewo\xcc\x88hnliches Debu\xcc\x88t!" (Deutschlandfunk, Die besten 7 Bu\xcc\x88cher fu\xcc\x88r junge Leser im Monat November 2017).\x1e7 \x1fa1131273370\x1f2GyFmDB\x1e  \x1fa9783945034675\x1fq(pbk.)\x1e  \x1fa3945034671\x1fq(pbk.)\x1e3 \x1fa9783945034675\x1e  \x1fa(OCoLC)on1017094215\x1e  \x1faOHX\x1fbeng\x1ferda\x1fcOHX\x1fdNDD\x1fdWTU\x1fdOCLCO\x1fdKZS\x1fdOCLCO\x1fdOCLCF\x1fdEYM\x1fdOCLCO\x1fdUtOrBLW\x1e1 \x1fager\x1fhspa\x1e 4\x1faPN6790.A73\x1fbV65615 2017\x1e 7\x1faPN\x1f2lcco\x1e 7\x1faNC\x1f2lcco\x1e1 \x1faVollenweider, Nacha,\x1fd1983-\x1feartist,\x1feauthor.\x1e10\x1faNotas al pie.\x1flGerman\x1e10\x1faFussnoten /\x1fcNacha Vollenweider.\x1e 1\x1faBerlin :\x1fbAvant-Verlag,\x1fc[2017].\x1e  \x1fa205 pages :\x1fball illustrations ;\x1fc23 cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1fastill image\x1fbsti\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e  \x1faFu\xc3\x9fnoten beginnt mit einer Bahnfahrt durch die Vororte Hamburgs, einer Situation, wie sie allta\xcc\x88glicher nicht sein ko\xcc\x88nnte. Doch an den Ra\xcc\x88ndern der Dinge, die die Protagonistin Nacha dabei erlebt, stehen kleine Zahlen, als Verweise auf tiefergehende Informationen. Hier unten, im Reich der Fu\xc3\x9fnoten, spielen sich die Dinge ab, auf denen das, was im Jetzt statt findet, gru\xcc\x88ndet. Deutsche und argentinische Wirklichkeiten und Vergangenheiten u\xcc\x88berlagern sich - so wie die Grundrisspla\xcc\x88ne argentinischer Sta\xcc\x88dte und das Muster der Sitzbezu\xcc\x88ge der Bahn. Der Leser begleitet die Erza\xcc\x88hlerin auf einer Spurensuche nach ihrer argentinischen Familie, die unter der Milita\xcc\x88rdiktatur der Siebzigerjahre gelitten hat. Das wechselvolle Schicksal ihrer Vorfahren ist eng verknu\xcc\x88pft mit ihrem Leben als junge Frau in einer deutschen Gro\xc3\x9fstadt. Nacha Vollenweider entwickelt in ihrem Debu\xcc\x88t eine ungewo\xcc\x88hnliche, faszinierende Art des Erza\xcc\x88hlens: stilistisch ruhig und nu\xcc\x88chtern, aber inhaltlich gro\xc3\x9f und tiefgru\xcc\x88ndig - und verwendet nebenbei - voila\xcc\x80 - ein neues Genre: den Comic-Essay. \x1e  \x1faThe reader accompanies Nacha in pursuit of his Argentinean family, which suffered under the military dictatorship of the 1970s. German and Argentine realities and pasts overlap.\x1e 0\x1faFamily reunification\x1fxComic books, strips, etc.\x1e 0\x1faFamily reunification\x1fxFiction.\x1e 0\x1faArgentina\x1fxPolitics and government\x1fvComic books, strips, etc.\x1e 0\x1faArgentina\x1fxPolitics and government\x1fvFiction.\x1e 0\x1faArgentina\x1fxHistory\x1fvComic books, strips, etc.\x1e 0\x1faArgentina\x1fxHistory\x1fvFiction.\x1e 7\x1faFamily reunification.\x1f2fast\x1f0(OCoLC)fst01893695\x1e 7\x1faPolitics and government.\x1f2fast\x1f0(OCoLC)fst01919741\x1e 7\x1faArgentina.\x1f2fast\x1f0(OCoLC)fst01205614\x1e 7\x1faComics (Graphic works)\x1f2lcgft\x1e 7\x1faGraphic novels.\x1f2lcgft\x1e 4\x1faComics (Graphic works)\x1fzArgentina.\x1e 7\x1faComic books, strips, etc.\x1f2fast\x1f0(OCoLC)fst01423722\x1e 7\x1faComics (Graphic works)\x1f2fast\x1f0(OCoLC)fst01921613\x1e 7\x1faFiction.\x1f2fast\x1f0(OCoLC)fst01423787\x1e 7\x1faGraphic novels.\x1f2fast\x1f0(OCoLC)fst01726630\x1e 7\x1faHistory.\x1f2fast\x1f0(OCoLC)fst01411628\x1e  \x1faUM\x1fb017070238\x1e  \x1faAUTHORITY\x1e\x1d'\
'ascii' codec can't decode byte 0xcc in position 73: ordinal not in range(128) b'03916cam a2200421Ii 4500005001700000008004100017Anb018000058Anb002700238Lat113700265019001501402020001801417020001501435035002401450040005701474050002101531090002201552100003401574245009401608264004501702264001101747300003101758336002601789337002801815338002701843490011201870500009001982504005902072520004202131520033002173520069902503650004303202650004303245650005303288650002903341830009203370998001803462928001403480\x1e20200803112702.0\x1e200624s20202020gw       b    000 0 ger d\x1eetung" heutzutage vor allem mit Bezug auf die eucharistische Anbetung pra\xcc\x88sent. Doch reicht es viel tiefer. Die Schultheologie des Hochmittelalters reflektiert den Themenbereich \x1eetung und Verehrung" bzw. \x1erie und Dulie" in grundsa\xcc\x88tzlicher Weise, indem sie u\xcc\x88ber das Wesen, die verschiedenen Adressaten und die zugrundeliegende Tugend der Verehrung nachdenkt. Diese Debatten werden in der vorliegenden Arbeit nach dogmengeschichtlicher Methode analysiert. Dabei wird der Schwerpunkt auf ausgewa\xcc\x88hlte Autoren und deren thematisch einschla\xcc\x88gige Abhandlungen gelegt (Summa Halensis, Albertus Magnus, Bonaventura, Thomas von Aquin). Zu deren angemessener Kontextualisierung werden nicht nur Autoren wie Roland von Cremona, Richard Fishacre und Robert Kilwardby vergleichend herangezogen, sondern auch die vorausgehenden anbetungstheologischen Entwicklungen der Fru\xcc\x88hscholastik sowie der U\xcc\x88bergangsphase zur Hochscholastik (u.a. bei Wilhelm von Auxerre, Philipp dem Kanzler und Alexander von Hales) beru\xcc\x88cksichtigt. Aus der Erhebung der oftmals nur mikroanalytisch voneinander abzugrenzenden Schritte des Denkweges ergibt sich ein repra\xcc\x88sentatives und facettenreiches Bild der scholastischen Anbetungstheologie, die - trotz mancher eigener Schwa\xcc\x88chen - den heutigen Zugang zum Thema in vielfa\xcc\x88ltiger Weise bereichern kann." --back cover\x1e  \x1fa1156774147\x1e  \x1fa9783402103012\x1e  \x1fa340210301X\x1e  \x1fa(OCoLC)on1159720506\x1e  \x1faUV0\x1fbeng\x1ferda\x1fcUV0\x1fdUV0\x1fdISB\x1fdYDX\x1fdISB\x1fdSNN\x1fdUtOrBLW\x1e 4\x1faBR253\x1fb.O88 2020\x1e  \x1faB720\x1fb.B4 n.f. 85\x1e1 \x1faOtter, Josef,\x1fd1996-\x1feauthor.\x1e10\x1faAdoratio :\x1fbTheologie der Anbetung in der Scholastik des 13. Jahrhunderts /\x1fcJosef Otter.\x1e 1\x1faMu\xcc\x88nster :\x1fbAschendorff Verlag,\x1fc[2020]\x1e 4\x1fc\xc2\xa92020\x1e  \x1faxviii, 581 pages ;\x1fc23 cm.\x1e  \x1fatext\x1fbtxt\x1f2rdacontent\x1e  \x1faunmediated\x1fbn\x1f2rdamedia\x1e  \x1favolume\x1fbnc\x1f2rdacarrier\x1e1 \x1faBeitra\xcc\x88ge zur Geschichte der Philosophie und Theologie des Mittelalters,\x1fx0067-5024 ;\x1fvNeue Folge, Band 85\x1e  \x1faOriginally presented as the author\'s thesis (doctoral)--Universita\xcc\x88t Augsburg, 2018.\x1e  \x1faIncludes bibliographical references (pages [567]-581).\x1e  \x1fa"Im kirchlichen Umfeld ist das Thema \x1e3 \x1faThe Society of Oriental Liturgy (SOL) is an international academic society dedicated to the scholarly study of the various Eastern Christian liturgical traditions and related fields in all its aspects and phases, including allied disciplines, and its multiple methodologies. By this it unites scholars from all denominations.\x1e3 \x1faThis volume comprises sixteen selected papers from the Seventh Congress held in July 2018 in Presov, Slovakia, on very diverse traditions: Armenian, Byzantine, Coptic, Ethiopian, Georgian, and Syriac, across a wide range of countries and cultures. The authors study inter alia the texts of liturgical services, the genesis of liturgical books, their translations and adaptations, liturgical theology, architecture, liturgical history, and allusions to liturgy in popular literature. The papers discuss both the historical practice of diverse Eastern Churches and the current situation. Thus, the present collection of articles shows clearly the progress made in an attractive field of research.\x1e 0\x1faChurch history\x1fyMiddle Ages, 600-1500.\x1e 0\x1faEastern churches\x1fxLiturgy\x1fxCongresses.\x1e 0\x1faOriental Orthodox churches\x1fxLiturgy\x1fxCongresses.\x1e 0\x1faPublic worship\x1fxHistory.\x1e 0\x1faBeitra\xcc\x88ge zur Geschichte der Philosophie und Theologie des Mittelalters\x1fvn.F., Bd. 85.\x1e  \x1faSM\x1fb017475728\x1e  \x1faAUTHORITY\x1e\x1d'\

# Holdings transformation results
## Stats
Measure | Number
--- | ---:
Failed records | 3,100,765
Holdings records written to disk | 4,397,974
Records missing 852 | 135
Records that failed validation | 15
Records that failed validation ['permanentLocationId'] | 15
Records with multiple 852 fields | 13
Value errors | 3,100,765
bib id not in map | 3,100,615
## Legacy locations
Measure | Number
--- | ---:
ACASP | 6,763
ACDEP | 97,265
ACFST | 629,382
ACMUS | 17,805
ACRUS | 1,367
ACSCI | 68
FCANN | 36,415
FCDEP | 1
FCDPT | 107,917
FCWWW | 45
HCASC | 445
HCLIB | 120,080
MHASC | 83
MHLIB | 561,341
MHPSL | 16,600
MHSKM | 1
REN | 143
SCANN | 752,140
SCHIL | 91,737
SCJOS | 76,250
SCNLS | 614
SCSPC | 739
SCTYO | 2,778
SCYOU | 355
UMDUB | 1,694,085
UMIDA | 16,177
UMIMA | 10
UMMDA | 527
UMSCA | 417
UMSCI | 166,429
## FOLIO locations
Measure | Number
--- | ---:
ACDEP | 97,265
tech | 4,300,714
## Unmapped location codes
Measure | Number
--- | ---:
Legacy code - ACASP | 6,763
Legacy code - ACFST | 629,382
Legacy code - ACMUS | 17,805
Legacy code - ACRUS | 1,367
Legacy code - ACSCI | 68
Legacy code - FCANN | 36,415
Legacy code - FCDEP | 1
Legacy code - FCDPT | 107,917
Legacy code - FCWWW | 45
Legacy code - HCASC | 445
Legacy code - HCLIB | 120,080
Legacy code - MHASC | 83
Legacy code - MHLIB | 561,341
Legacy code - MHPSL | 16,600
Legacy code - MHSKM | 1
Legacy code - REN | 143
Legacy code - SCANN | 752,140
Legacy code - SCHIL | 91,737
Legacy code - SCJOS | 76,250
Legacy code - SCNLS | 614
Legacy code - SCSPC | 739
Legacy code - SCTYO | 2,778
Legacy code - SCYOU | 355
Legacy code - UMDUB | 1,694,085
Legacy code - UMIDA | 16,177
Legacy code - UMIMA | 10
Legacy code - UMMDA | 527
Legacy code - UMSCA | 417
Legacy code - UMSCI | 166,429
## Call number types (852 $2) values
Measure | Number
--- | ---:
Dewey Decimal classification | 445,546
Library of Congress classification | 3,297,280
National Library of Medicine classification | 36
Other scheme | 378,801
Other scheme () | 31,266
Shelving control number | 2,826
Superintendent of Documents classification | 100,295
Title | 3,002
## Unmapped FOLIO fields
Measure | Number
--- | ---:
acquisitionFormat | 4,397,989
acquisitionMethod | 4,397,989
bareHoldingsItems | 4,397,989
digitizationPolicy | 4,397,989
electronicAccess | 4,397,989
formerIds | 4,397,989
holdingsInstance | 4,397,989
holdingsItems | 4,397,989
holdingsTypeId | 4,397,989
illPolicy | 4,397,989
illPolicyId | 4,397,989
numberOfItems | 4,397,989
permanentLocation | 4,397,989
receiptStatus | 4,397,989
receivingHistory | 4,397,989
retentionPolicy | 4,397,989
sourceId | 4,397,989
statisticalCodeIds | 4,397,989
tags | 4,397,989
temporaryLocationId | 4,397,989
## Mapped FOLIO Fields
Measure | Number
--- | ---:
callNumber | 4,259,048
callNumberPrefix | 81,641
callNumberSuffix | 37,184
callNumberTypeId | 4,259,048
copyNumber | 5
holdingsStatements | 99,727
holdingsStatementsForIndexes | 1,662
holdingsStatementsForSupplements | 181
hrid | 4,397,989
id | 4,397,989
instanceId | 4,397,989
metadata | 4,397,989
notes | 1,076
permanentLocationId | 4,397,974
shelvingTitle | 1
## Failed records that needs to get fixed
Required field permanentLocationId is missing from 004929398\
Required field permanentLocationId is missing from 005012338\
Required field permanentLocationId is missing from 006151020\
Required field permanentLocationId is missing from 007917850\
Required field permanentLocationId is missing from 009876143\
Required field permanentLocationId is missing from 011763425\
Required field permanentLocationId is missing from 012422318\
Required field permanentLocationId is missing from 012479311\
Required field permanentLocationId is missing from 012785000\
Required field permanentLocationId is missing from 013610833\
Required field permanentLocationId is missing from 013610834\
Required field permanentLocationId is missing from 013619211\
Required field permanentLocationId is missing from 013867960\
Required field permanentLocationId is missing from 013888812\
Required field permanentLocationId is missing from 014313969\


Measure | Number
--- | ---:
Number of Legacy items in file | 10,133,074
Number of files processed | 8
Saving map of 8705522 old and new IDs to /home/theodor/data/five_colleges/goldenrod/results/item_id_map.json
## Top missing holdings ids 
## Top duplicate item ids
13509467-10                    - 4
13765098-10                    - 3
13612329-10                    - 3
13594720-10                    - 3
3.10184E+14                    - 3
B33573                         - 2
## Item transformation counters
Measure | Number
--- | ---:
Duplicate item ids | 595,731
Empty legacy id | 1
Holdings id not in map | 831,817
Missing location codes, adding "tech" | 258,810
Missing required field(s): holdingsRecordId | 2
Missing required field(s): materialTypeId | 2
Number of Items written to disk | 9,301,253
Number of records in file(s) | 10,133,074
Sucessfully transformed items | 9,301,253
Temp location code: 0 | 2
Temp location code: N | 8,635,482
Temp location code: Y | 665,773
Total failed items with Value errors | 831,821

## Mapped loan types - 162 things
Measure | Count
--- | ---:
1 Week - ACDEP - 10 | 24216
1 Week - ACFST - 10 | 34901
1 Week - ACFST - 18 | 26503
1 Week - ACMUS - 10 | 172
1 Week - MHLIB - 18 | 1201
1 Week - MHLRC - 18 | 25
1 Week - MHPSL - 16 | 415
1 Week - UMDUB - 11 | 138069
1 Week - UMDUB - 12 | 20747
1 Week - UMMDA - 06 | 80
1 Week - UMSCI - 11 | 84669
1 Week - UMSCI - 12 | 3158
1 Year - HCLIB - 20 | 669
2 Week - MHLIB - 09 | 273
2 Week - MHLIB - 19 | 9
2 Week - MHPSL - 19 | 2755
4 Week - HCLIB - 10 | 5629
4 Week - HCLIB - 19 | 183
4 Week - HCMED - 10 | 3381
4 Week - MHLIB - 10 | 121277
4 Week - MHLIB - 14 | 146434
4 Week - MHLIB - 16 | 22713
4 Week - MHSKM - 14 | 918
4 Week - SCANN - 10 | 17
4 Week - SCNLS - 10 | 8
4 Week - UMDUB - 06 | 27546
4 Week - UMDUB - 20 | 314018
4 Week - UMDUB - 22 | 16207
4 Week - UMDUB - 25 | 7119
4 Week - UMDUB - 27 | 16835
4 Week - UMMDA - 20 | 279
4 Week - UMMDA - 22 | 40
4 Week - UMSCI - 06 | 1
4 Week - UMSCI - 20 | 35827
4 Week - UMSCI - 25 | 12
Comm Catalog - UMDUB - 28 | 1087
Equipment 1 Day - UMMDA - 56 | 67
Equipment 3 Day - MHLIB - 08 | 18
Equipment 3 Day - MHLIB - 15 | 66
Equipment 3 Day - MHLIB - 21 | 692
Equipment 3 Day - MHPSL - 15 | 186
Equipment 3 Day - UMDML - 55 | 132
Equipment 3 Day - UMDML - 57 | 254
Equipment 3 Day - UMMDA - 53 | 81
Equipment 3 Day - UMMDA - 54 | 133
Equipment 3 Day - UMMDA - 55 | 53
Equipment 3 Day - UMMDA - 57 | 163
Equipment 4 Hour - UMDML - 52 | 54
Equipment 4 Hour - UMDML - 58 | 52
Internet - HCLIB - 04 | 23386
Internet - MHLIB - 04 | 172192
Internet - MHLRC - 04 | 3
Internet - SCANN - 04 | 7
Internet - SCJOS - 04 | 3
Internet - SCNLS - 04 | 998242
Internet - UMDUB - 04 | 458058
Limited - SCANN - 11 | 123918
Limited - SCANN - 12 | 14
Limited - SCANN - 13 | 3435
Limited - SCANN - 14 | 1
Limited - SCJOS - 11 | 1164
Limited - SCJOS - 12 | 19555
Limited - SCJOS - 13 | 3536
Limited - SCJOS - 14 | 16162
Limited - SCNLS - 11 | 17
Limited - SCNLS - 13 | 35
Limited - SCYOU - 11 | 41
Limited - SCYOU - 12 | 1
Limited - UMDUB - 07 | 8039
Non-circulating - ACASP -  | 6
Non-circulating - ACASP - 01 | 10
Non-circulating - ACASP - 02 | 119935
Non-circulating - ACDEP - 02 | 9
Non-circulating - ACFST -  | 1
Non-circulating - ACFST - 02 | 17688
Non-circulating - ACMUS - 02 | 3084
Non-circulating - ACSCI - 02 | 204
Non-circulating - HCASC - 02 | 6015
Non-circulating - HCLIB - 02 | 3193
Non-circulating - HCMED - 02 | 886
Non-circulating - MHASC - 02 | 17722
Non-circulating - MHLIB - 02 | 11504
Non-circulating - MHPSL - 02 | 949
Non-circulating - SCANN -  | 37
Non-circulating - SCANN - 02 | 1185
Non-circulating - SCANN - 03 | 4
Non-circulating - SCHIL -  | 30
Non-circulating - SCHIL - 02 | 6980
Non-circulating - SCHIL - 03 | 279
Non-circulating - SCJOS -  | 17
Non-circulating - SCJOS - 02 | 8026
Non-circulating - SCJOS - 03 | 6
Non-circulating - SCNLS -  | 63
Non-circulating - SCNLS - 02 | 33
Non-circulating - SCNLS - 03 | 2037
Non-circulating - SCSPC - 02 | 39755
Non-circulating - SCSPC - 03 | 312
Non-circulating - SCWST - 02 | 163
Non-circulating - SCYOU - 02 | 140
Non-circulating - UMDUB - 02 | 92581
Non-circulating - UMDUB - 03 | 27110
Non-circulating - UMDUB - 13 | 1781
Non-circulating - UMIMA - 02 | 19
Non-circulating - UMMDA - 02 | 1741
Non-circulating - UMMDA - 52 | 46
Non-circulating - UMSCA - 02 | 45688
Non-circulating - UMSCA - 13 | 141
Non-circulating - UMSCI - 02 | 12
Non-circulating - UMSCI - 13 | 5321
Reserve 1 Day  - HCLIB - 13 | 2
Reserve 1 Day - ACFST - 23 | 1
Reserve 1 Day - ACMUS - 23 | 7
Reserve 1 Day - ACSCI - 23 | 2
Reserve 1 Week  - SCJOS - 25 | 9
Reserve 1 Week  - SCYOU - 25 | 6
Reserve 3 Day - ACSCI - 24 | 1
Reserve 3 Day - MHLIB - 13 | 52
Reserve 4 Hour - ACFST - 22 | 597
Reserve 4 Hour - ACMED - 22 | 7
Reserve 4 Hour - ACMUS - 22 | 419
Reserve 4 Hour - ACSCI - 22 | 301
Reserve 4 Hour - HCLIB - 09 | 31
Reserve 4 Hour - MHLIB - 11 | 570
Reserve 4 Hour - MHLRC - 11 | 366
Reserve 4 Hour - MHPSL - 11 | 30
Reserve 4 Hour - SCANN - 20 | 3
Reserve 4 Hour - SCJOS - 20 | 225
Reserve 4 Hour - SCNLS - 20 | 792
Reserve 4 Hour - SCNLS - 27 | 1
Reserve 4 Hour - SCYOU - 20 | 790
Reserve 4 Hour - UMDUB - 31 | 5
Reserve 4 Hour - UMIDA - 31 | 76
Reserve 4 Hour - UMMDA - 31 | 6689
Reserve 4 Hour, due at closing - SCJOS - 21 | 298
Reserve 4 Hour, due at closing - SCYOU - 21 | 11
Semester - ACFST - 15 | 247
Semester - SCJOS - 66 | 18
Semester - SCYOU - 66 | 146
Standard Loan - ACDEP - 01 | 123922
Standard Loan - ACFST - 01 | 706905
Standard Loan - ACFST - 16 | 342
Standard Loan - ACMED - 01 | 3079
Standard Loan - ACMUS - 01 | 23474
Standard Loan - HCASC - 01 | 3
Standard Loan - HCLIB - 01 | 136854
Standard Loan - HCMED - 01 | 19
Standard Loan - MHLIB - 01 | 525598
Standard Loan - MHLRC - 01 | 283
Standard Loan - MHPSL - 01 | 24051
Standard Loan - MHPSL - 10 | 1671
Standard Loan - SCANN - 01 | 940797
Standard Loan - SCHIL - 01 | 77037
Standard Loan - SCJOS - 01 | 69291
Standard Loan - SCNLS - 01 | 826
Standard Loan - SCSPC - 01 | 3780
Standard Loan - SCWST - 01 | 5
Standard Loan - SCYOU - 01 | 329
Standard Loan - UMDML - 01 | 29
Standard Loan - UMDUB - 01 | 1654220
Standard Loan - UMIDA - 01 | 23397
Standard Loan - UMMDA - 01 | 134
Standard Loan - UMSCI - 01 | 169655

## Mapped Material Types - 41 things
Measure | Count
--- | ---:
Admin - ADMIN | 4805
Analog Game - GAME | 474
Archival material - ARCH | 15099
Artifact/Object - ART | 38
Artifact/Object - ARTI | 40
Audio CD - AUDCD | 19840
Audio CD - MUSCD | 33990
Audio CD - SPOK | 972
Audiocassette - ACASS | 1145
Book - BOOK | 5010242
CD-ROM - CDROM | 3027
DVD/Blu-ray - VDVD | 45898
Data File - DATA | 79
Database - DATAB | 901
Database - ONRES | 12048
E-Book - EBOOK | 2775318
E-Journal - EJOUR | 43942
E-Newspaper - NEWS | 227
E-Score - EMUS | 5
E-Thesis/Dissertation - ETHES | 761
E-Thesis/Dissertation - THES | 20286
Equipment - CAMRA | 69
Equipment - EQUIP | 9505
Equipment - HDPHN | 41
Equipment - KEY | 137
Equipment - LAPTP | 139
Film - FILM | 1656
Government Publication - GPUB | 990
Journal - ISSBD | 1359110
Journal - ISSUE | 115362
LP Phonorecord - LP | 31782
Map - MAP | 12371
Microform - MFILM | 69
Microform - MICR | 232313
Newspaper - NEWS | 227
Score - MUSIC | 135300
Streaming Audio - EAUDI | 125538
Streaming Audio - STRA | 3
Streaming Video - STRV | 8556
Supplement - SUPP | 131
Videocassette - VCASS | 19527

## Field Contents - Z30_ITEM_STATUS - 42 things
Measure | Count
--- | ---:
 | 155
01 | 4740746
02 | 463654
03 | 29807
04 | 3037220
05 | 2497
06 | 30278
07 | 9441
08 | 18
09 | 304
10 | 192270
11 | 757323
12 | 61545
13 | 133214
14 | 163545
15 | 3408
16 | 23522
17 | 25710
18 | 28046
19 | 2947
20 | 358862
21 | 1093
22 | 17629
23 | 19
24 | 15043
25 | 8553
27 | 16948
28 | 1087
31 | 6770
32 | 3
35 | 1
36 | 1
52 | 100
53 | 81
54 | 133
55 | 185
56 | 67
57 | 417
58 | 52
66 | 373
76 | 1
77 | 6

## Missing location codes - 48 things
Measure | Count
--- | ---:
ACDEP | 24216
ACDPM | 123931
AFASF | 1527
AFASH | 871
AFASL | 13973
AFASO | 1332
AFASR | 246
AFAST | 12483
AFASV | 55
AFASW | 1254
AFAV | 128
AFBLU | 232
AFCAS | 5
AFCHI | 21
AFDRM | 37
AFDVD | 13789
AFIN | 2110
AFMAP | 567
AFMIC | 5444
AFPER | 37505
AFREF | 16629
AFREP | 102
AFRES | 629
EBRAR | 2
MHCCM | 77
NOCOD | 1
SAMED | 26
SNNO | 2
SSCDD | 312
SSCMA | 170
SSCRE | 17
SSCSK | 31
SSNCD | 33
SSNFC | 2
SSNFL | 1
SSNMA | 122
SSNPE | 1
SSNRE | 1
SSRPR | 6
SSRPS | 726
SSRRE | 36
SSRVI | 3
SSTXT | 146
STSCD | 1
UDBKS | 5
UDPER | 1
UILL | 1
URFS | 1

## Unapped Material Types - 15 things
Measure | Count
--- | ---:
unspecified - AUDIO | 16211
unspecified - CARD | 19
unspecified - ERES | 16781
unspecified - EVIDE | 23609
unspecified - KIT | 19
unspecified - LASER | 1
unspecified - LSRDC | 45
unspecified - MUNC | 252
unspecified - NOMAP | 60
unspecified - NONPR | 15
unspecified - PERBD | 31652
unspecified - PRINT | 20
unspecified - SEED | 669
unspecified - STAT | 1290
unspecified - WSITE | 538

## Unmapped loan types - 112 things
Measure | Count
--- | ---:
Non-Circulating - ACASP - 10 | 5
Non-Circulating - ACDEP - 10 | 24216
Non-Circulating - ACFST - 04 | 79081
Non-Circulating - ACFST - 05 | 1
Non-Circulating - ACFST - 10 | 34901
Non-Circulating - ACFST - 18 | 26503
Non-Circulating - ACFST - 21 | 1
Non-Circulating - ACFST - 23 | 1
Non-Circulating - ACMUS - 10 | 172
Non-Circulating - ACMUS - 17 | 24783
Non-Circulating - ACMUS - 21 | 2
Non-Circulating - ACMUS - 23 | 7
Non-Circulating - ACRUS - 01 | 1
Non-Circulating - ACRUS - 02 | 23531
Non-Circulating - ACRUS - 03 | 8
Non-Circulating - ACSCI - 21 | 1
Non-Circulating - ACSCI - 23 | 2
Non-Circulating - FCANN - 01 | 38019
Non-Circulating - FCANN - 02 | 2
Non-Circulating - FCANN - 11 | 138516
Non-Circulating - FCANN - 12 | 1
Non-Circulating - FCANN - 13 | 1261
Non-Circulating - FCANN - 25 | 2
Non-Circulating - FCDPT - 01 | 196409
Non-Circulating - FCDPT - 02 | 24261
Non-Circulating - FCDPT - 11 | 252381
Non-Circulating - FCDPT - 12 | 91
Non-Circulating - FCDPT - 13 | 108562
Non-Circulating - FCWWW - 04 | 1306248
Non-Circulating - HCASC - 15 | 38
Non-Circulating - HCFP  - 01 | 358
Non-Circulating - HCLIB - 05 | 2
Non-Circulating - HCLIB - 06 | 2651
Non-Circulating - HCLIB - 07 | 1239
Non-Circulating - HCLIB - 16 | 31
Non-Circulating - HCLIB - 18 | 311
Non-Circulating - HCLIB - 21 | 58
Non-Circulating - HCLIB - 77 | 3
Non-Circulating - MHASC - 01 | 80
Non-Circulating - MHASC - 14 | 3
Non-Circulating - MHLIB - 07 | 144
Non-Circulating - MHLIB - 17 | 37
Non-Circulating - MHLIB - 18 | 1201
Non-Circulating - MHLIB - 20 | 4252
Non-Circulating - MHLRC - 15 | 881
Non-Circulating - MHLRC - 18 | 25
Non-Circulating - MHPSL - 07 | 19
Non-Circulating - MHPSL - 16 | 415
Non-Circulating - REN   - 02 | 26520
Non-Circulating - SCANN - 18 | 3
Non-Circulating - SCHIL - 10 | 27
Non-Circulating - SCHIL - 11 | 17190
Non-Circulating - SCHIL - 12 | 17974
Non-Circulating - SCHIL - 13 | 183
Non-Circulating - SCHIL - 20 | 172
Non-Circulating - SCHIL - 21 | 10
Non-Circulating - SCJOS - 05 | 2345
Non-Circulating - SCJOS - 18 | 3
Non-Circulating - SCJOS - 23 | 4
Non-Circulating - SCJOS - 24 | 122
Non-Circulating - SCNLS - 05 | 4
Non-Circulating - SCNLS - 22 | 1
Non-Circulating - SCNLS - 24 | 3
Non-Circulating - SCSPC - 11 | 349
Non-Circulating - SCSPC - 12 | 1
Non-Circulating - SCSPC - 20 | 39
Non-Circulating - SCTYO - 01 | 3535
Non-Circulating - SCTYO - 02 | 370
Non-Circulating - SCTYO - 03 | 51
Non-Circulating - SCTYO - 10 | 966
Non-Circulating - SCTYO - 11 | 42
Non-Circulating - SCTYO - 12 | 2
Non-Circulating - SCTYO - 13 | 8899
Non-Circulating - SCTYO - 20 | 1796
Non-Circulating - SCTYO - 22 | 54
Non-Circulating - SCTYO - 23 | 5
Non-Circulating - SCTYO - 24 | 7
Non-Circulating - SCTYO - 25 | 40
Non-Circulating - SCTYO - 27 | 112
Non-Circulating - SCTYO - 66 | 209
Non-Circulating - SCWST - 12 | 1
Non-Circulating - SCWST - 13 | 6
Non-Circulating - SCYOU - 05 | 143
Non-Circulating - SCYOU - 22 | 3
Non-Circulating - SNNO  -  | 1
Non-Circulating - SNNO  - 01 | 1
Non-Circulating - UMDPT - 02 | 5
Non-Circulating - UMDPT - 11 | 1
Non-Circulating - UMDUB - 05 | 2
Non-Circulating - UMDUB - 11 | 138069
Non-Circulating - UMDUB - 12 | 20747
Non-Circulating - UMDUB - 14 | 11
Non-Circulating - UMDUB - 16 | 1
Non-Circulating - UMDUB - 21 | 20
Non-Circulating - UMDUB - 24 | 14910
Non-Circulating - UMMDA - 06 | 80
Non-Circulating - UMMDA - 15 | 1990
Non-Circulating - UMMDA - 16 | 19
Non-Circulating - UMMDA - 17 | 11
Non-Circulating - UMMDA - 32 | 3
Non-Circulating - UMMDA - 35 | 1
Non-Circulating - UMMDA - 36 | 1
Non-Circulating - UMSCA - 25 | 1365
Non-Circulating - UMSCA - 76 | 1
Non-Circulating - UMSCI - 11 | 84669
Non-Circulating - UMSCI - 12 | 3158
Non-Circulating - UMSCI - 14 | 16
Non-Circulating - UMSCI - 16 | 1
Non-Circulating - UMSCI - 17 | 879
Non-Circulating - UMSCI - 77 | 3
Non-Circulating - YMAIN - 01 | 16156
Non-Circulating - YMAIN - 02 | 11453

## Mapped FOLIO fields
FOLIO Field | Mapped | Empty | Unmapped
--- | --- | --- | ---:
accessionNumber | 5332619 (53%) | 4800455 | 0
barcode | 10133073 (100%) | 1 | 0
chronology | 0 (0%) | 0 | 10133074
circulationNotes | 229556 (2%) | 9903518 | 0
copyNumber | 5780446 (57%) | 4352628 | 0
descriptionOfPieces | 0 (0%) | 0 | 10133074
discoverySuppress | 0 (0%) | 0 | 10133074
effectiveCallNumberComponents | 0 (0%) | 0 | 10133074
effectiveLocationId | 0 (0%) | 0 | 10133074
electronicAccess | 0 (0%) | 0 | 10133074
enumeration | 2010921 (20%) | 7290336 | 831817
formerIds | 10133074 (100%) | 0 | 0
holdingsRecord2 | 0 (0%) | 0 | 10133074
holdingsRecordId | 10133072 (100%) | 2 | 0
hrid | 0 (0%) | 0 | 10133074
id | 10133074 (100%) | 0 | 0
inTransitDestinationServicePointId | 0 (0%) | 0 | 10133074
itemDamagedStatusDate | 0 (0%) | 0 | 10133074
itemDamagedStatusId | 0 (0%) | 0 | 10133074
itemIdentifier | 0 (0%) | 0 | 10133074
itemLevelCallNumber | 9275317 (92%) | 857757 | 0
itemLevelCallNumberPrefix | 0 (0%) | 0 | 10133074
itemLevelCallNumberSuffix | 0 (0%) | 0 | 10133074
itemLevelCallNumberTypeId | 0 (0%) | 0 | 10133074
lastCheckIn | 0 (0%) | 0 | 10133074
materialTypeId | 10132917 (100%) | 157 | 0
metaData | 10133074 (100%) | 0 | 0
missingPieces | 0 (0%) | 0 | 10133074
missingPiecesDate | 0 (0%) | 0 | 10133074
notes | 5324544 (53%) | 35207752 | -30399222
numberOfMissingPieces | 0 (0%) | 0 | 10133074
numberOfPieces | 0 (0%) | 0 | 10133074
permanentLoanTypeId | 10130585 (100%) | 2489 | 0
permanentLocation | 0 (0%) | 0 | 10133074
permanentLocationId | 10130515 (100%) | 2559 | 0
purchaseOrderLineIdentifier | 0 (0%) | 0 | 10133074
statisticalCodeIds | 0 (0%) | 0 | 10133074
status | 10133074 (100%) | 0 | 0
tags | 0 (0%) | 0 | 10133074
temporaryLoanTypeId | 0 (0%) | 0 | 10133074
temporaryLocation | 0 (0%) | 0 | 10133074
temporaryLocationId | 9301257 (92%) | 0 | 831817
volume | 0 (0%) | 0 | 10133074
yearCaption | 1326607 (13%) | 7974650 | 831817

## Mapped Legacy fields
Legacy Field | Mapped | Empty | Unmapped
--- | --- | --- | ---:
SYSNO | 0 (0%) | 9301250 | 10133074
Z30_85X_TYPE | 0 (0%) | 9138172 | 10133074
Z30_ALPHA | 0 (0%) | 0 | 10133074
Z30_ARRIVAL_DATE | 0 (0%) | 0 | 10133074
Z30_BARCODE | 10133073 (100%) | 1 | 0
Z30_CALL_NO | 9275317 (92%) | 857757 | 0
Z30_CALL_NO_2 | 0 (0%) | 10132314 | 10133074
Z30_CALL_NO_2_KEY | 0 (0%) | 10131817 | 10133074
Z30_CALL_NO_2_TYPE | 0 (0%) | 10132388 | 10133074
Z30_CALL_NO_KEY | 0 (0%) | 798460 | 10133074
Z30_CALL_NO_TYPE | 0 (0%) | 1050997 | 10133074
Z30_CATALOGER | 0 (0%) | 3075815 | 10133074
Z30_CHRONOLOGICAL_I | 1326607 (13%) | 7974650 | 831817
Z30_CHRONOLOGICAL_J | 0 (0%) | 9194797 | 10133074
Z30_CHRONOLOGICAL_K | 0 (0%) | 9272694 | 10133074
Z30_CHRONOLOGICAL_L | 0 (0%) | 9301250 | 10133074
Z30_CHRONOLOGICAL_M | 0 (0%) | 9301187 | 10133074
Z30_COLLECTION | 10130515 (100%) | 2559 | 0
Z30_COPY_ID | 5780446 (57%) | 4352628 | 0
Z30_DATE_LAST_RETURN | 0 (0%) | 0 | 10133074
Z30_DEPOSITORY_ID | 0 (0%) | 9301230 | 10133074
Z30_DESCRIPTION | 2367066 (23%) | 7766008 | 0
Z30_ENUMERATION_A | 2010921 (20%) | 7290336 | 831817
Z30_ENUMERATION_B | 0 (0%) | 8815154 | 10133074
Z30_ENUMERATION_C | 0 (0%) | 9277398 | 10133074
Z30_ENUMERATION_D | 0 (0%) | 9301217 | 10133074
Z30_ENUMERATION_E | 0 (0%) | 9301257 | 10133074
Z30_ENUMERATION_F | 0 (0%) | 9301255 | 10133074
Z30_ENUMERATION_G | 0 (0%) | 9298909 | 10133074
Z30_ENUMERATION_H | 0 (0%) | 9301114 | 10133074
Z30_EXPECTED_ARRIVAL_DATE | 0 (0%) | 0 | 10133074
Z30_GAP_INDICATOR | 0 (0%) | 9301197 | 10133074
Z30_HOL_DOC_NUMBER_X | 10133072 (100%) | 2 | 0
Z30_HOUR_LAST_RETURN | 0 (0%) | 0 | 10133074
Z30_INVENTORY_NUMBER | 5332619 (53%) | 4800455 | 0
Z30_INVENTORY_NUMBER_DATE | 0 (0%) | 3 | 10133074
Z30_IP_LAST_RETURN | 0 (0%) | 7684514 | 10133074
Z30_IP_LAST_RETURN_V6 | 0 (0%) | 9301257 | 10133074
Z30_ISSUE_DATE | 0 (0%) | 0 | 10133074
Z30_ITEM_PROCESS_STATUS | 0 (0%) | 9858146 | 10133074
Z30_ITEM_STATISTIC | 0 (0%) | 9955675 | 10133074
Z30_ITEM_STATUS | 0 (0%) | 155 | 10133074
Z30_LAST_SHELF_REPORT_DATE | 0 (0%) | 3 | 10133074
Z30_LINKING_NUMBER | 0 (0%) | 2 | 10133074
Z30_MAINTENANCE_COUNT | 0 (0%) | 398 | 10133074
Z30_MATERIAL | 10132917 (100%) | 157 | 0
Z30_NOTE_CIRCULATION | 229556 (2%) | 9903518 | 0
Z30_NOTE_INTERNAL | 1003547 (10%) | 9129527 | 0
Z30_NOTE_OPAC | 590387 (6%) | 9542687 | 0
Z30_NO_LOANS | 0 (0%) | 0 | 10133074
Z30_ON_SHELF_DATE | 0 (0%) | 5 | 10133074
Z30_ON_SHELF_SEQ | 0 (0%) | 0 | 10133074
Z30_OPEN_DATE | 0 (0%) | 0 | 10133074
Z30_ORDER_NUMBER | 1363544 (13%) | 8769530 | 0
Z30_PAGES | 0 (0%) | 4395827 | 10133074
Z30_PRICE | 0 (0%) | 3882315 | 10133074
Z30_PROCESS_STATUS_DATE | 0 (0%) | 2 | 10133074
Z30_REC_KEY | 10133074 (100%) | 0 | 0
Z30_REC_KEY_2 | 0 (0%) | 2 | 10133074
Z30_REC_KEY_3 | 0 (0%) | 0 | 10133074
Z30_SHELF_REPORT_NUMBER | 0 (0%) | 9539530 | 10133074
Z30_SUB_LIBRARY | 10130585 (100%) | 2489 | 0
Z30_SUPP_INDEX_O | 0 (0%) | 9301001 | 10133074
Z30_TEMP_LOCATION | 9301257 (92%) | 0 | 831817
Z30_UPDATE_DATE | 0 (0%) | 0 | 10133074
Z30_UPD_TIME_STAMP | 0 (0%) | 2 | 10133074
