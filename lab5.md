# Lab Report 5: Researching Commands Pt. 2
**In this lab, we will investigate various command-line options for the grep command.**

## The grep Command
The grep command is a powerful tool used in Unix-based operating systems to search for text patterns in files. It allows users to search for specific strings or regular expressions within a file or across multiple files, making it an incredibly useful tool for programmers, system administrators, and anyone who needs to quickly search through large amounts of text data. Additionally, grep offers several options and modifiers that allow users to further refine their searches, making it a versatile and customizable tool for text searching and filtering. In this lab report, I will investigate a few different ways of using this command in the ``/written_2`` folder.

-----

## 1. Search for a pattern in multiple files:
You can also search for a pattern in multiple files at once by using a wildcard character. For example, to search for the word "toilet" in all text files in the current directory, you would use the following command:

```
$ grep toilet *.txt
```

Since we are in ``/written_2/travel_guides/berlitz2``, this command will find all text files in our directory containing the string "toilet":

```
$ grep toilet *.txt
CanaryIslands-WhereToGo.txt:This is really of little interest, and the roads often leave something to be desired. However, a trip up the eastern coast from Santa Cruz to just south of Barlovento isn’t too long, and the rather serpentine road runs through some pretty scenery. Make the first stop the miradores of Bartolomé and La Montaña, with the latter being a little higher and affording beautiful vistas along the coast in both directions. Head next for the seaside village of San Andrés and its natural swimming pools at Charco Azul (blue pool). A little inland from San Andrés and Sauces is the Bosque de Los Tilos, the largest wooded area in the whole Canary Islands and designated a “Biosphere Reserve” under the protection of UNESCO. Heritage of Mankind is the information center above the restaurant (open Monday–Friday 8am–3pm). The final destination though is a lovely, remote site just before Barlovento where, after a tortuously twisting journey down through banana plantations, you will reach the Piscinas Fajana; literally swimming pools built into the rocks and fed by the ocean waters that often crash into them. Showers and toilets are on hand, as is the pleasant La Gaviota (the Seagull), a restaurant/bar, and the views north of the cliffs falling straight into the ocean and being pounded by waves are breathtaking.
Costa-WhatToDo.txt:The main resort beaches offer all kinds of sports equipment for rent, as well as beach umbrellas and loungers. The larger beach restaurants have toilet facilities, and some provide changing rooms.
Crete-WhereToGo.txt:Evans made numerous remarkable finds at the site, since it had been covered and left undisturbed following the 1350 b.c. disaster. Pottery intricately painted with marine life, bronze figurines, and exquisite jewels — many of these were discovered in the rock cut tombs of Palace Period — yet it is the mundane and simple things which make Knossós so fascinating. Evidence of early water piping, central heating, and sanitation shows a remarkable sophistication — look for the toilet room next to the Queens chamber for evidence of a flushing system! Continue past the remains of a hypostyle hall which was the Customs House to the start of the Royal Road leading north to the coast, still in exceptional condition and far better than most thoroughfares on Crete until only a few years ago.
```

## 2. Search for a pattern in a directory and its subdirectories:
To search for a pattern in all files in a directory and its subdirectories, you can use the -r option. For example, to search for the word "toilet" in all files in the directory "written_2" and its subdirectories, you would use the following command:

```
grep -r toilet written_2
```

This command will search written_2 and all subdirectories for files containing "toilet":

```
$ grep -r toilet written_2
written_2/non-fiction/OUP/Berk/CH4.txt:•Teaching. At times, caregivers use pretending as a pleasurable way to teach children real-world skills. For example, Michael’s mother capitalized on make-believe to encourage her 3-year-old to use the toilet. Reluctant at ﬁrst, Michael became an eager learner after being put in charge of toilet training his teddy bear.61
written_2/travel_guides/berlitz1/WhatToHongKong.txt:        changing rooms, toilets, and snack stands. On Hong Kong Island, Repulse
written_2/travel_guides/berlitz1/WhatToIbiza.txt:        sun-seekers, all equally happy that restaurants, toilets, showers, and
written_2/travel_guides/berlitz1/WhereToIndia.txt:        her toilet with handmaidens holding her cosmetics.
written_2/travel_guides/berlitz1/WhereToMadrid.txt:        Room, as sumptuous as it sounds, leads to the king’s own toilet,
written_2/travel_guides/berlitz2/CanaryIslands-WhereToGo.txt:This is really of little interest, and the roads often leave something to be desired. However, a trip up the eastern coast from Santa Cruz to just south of Barlovento isn’t too long, and the rather serpentine road runs through some pretty scenery. Make the first stop the miradores of Bartolomé and La Montaña, with the latter being a little higher and affording beautiful vistas along the coast in both directions. Head next for the seaside village of San Andrés and its natural swimming pools at Charco Azul (blue pool). A little inland from San Andrés and Sauces is the Bosque de Los Tilos, the largest wooded area in the whole Canary Islands and designated a “Biosphere Reserve” under the protection of UNESCO. Heritage of Mankind is the information center above the restaurant (open Monday–Friday 8am–3pm). The final destination though is a lovely, remote site just before Barlovento where, after a tortuously twisting journey down through banana plantations, you will reach the Piscinas Fajana; literally swimming pools built into the rocks and fed by the ocean waters that often crash into them. Showers and toilets are on hand, as is the pleasant La Gaviota (the Seagull), a restaurant/bar, and the views north of the cliffs falling straight into the ocean and being pounded by waves are breathtaking.
written_2/travel_guides/berlitz2/Costa-WhatToDo.txt:The main resort beaches offer all kinds of sports equipment for rent, as well as beach umbrellas and loungers. The larger beach restaurants have toilet facilities, and some provide changing rooms.
written_2/travel_guides/berlitz2/Crete-WhereToGo.txt:Evans made numerous remarkable finds at the site, since it had been covered and left undisturbed following the 1350 b.c. disaster. Pottery intricately painted with marine life, bronze figurines, and exquisite jewels — many of these were discovered in the rock cut tombs of Palace Period — yet it is the mundane and simple things which make Knossós so fascinating. Evidence of early water piping, central heating, and sanitation shows a remarkable sophistication — look for the toilet room next to the Queens chamber for evidence of a flushing system! Continue past the remains of a hypostyle hall which was the Customs House to the start of the Royal Road leading north to the coast, still in exceptional condition and far better than most thoroughfares on Crete until only a few years ago.  

```

## 3. Search for a pattern and display only the matching text:
By default, grep will display the entire line that contains the pattern. However, you can use the -o option to display only the matching text. For example, to search for the word "marble statue" in a file called "Athens-History.txt" and display only the matching text, you would use the following command:

```

## 4. Search for a pattern and exclude certain files or directories:
You can use the --exclude and --exclude-dir options to exclude certain files or directories from your search. For example, to search for the word "apple" in all text files in the current directory, but exclude any files with the extension ".log", you would use the following command:
