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

Here's another example. To search for the word "fire" in all text files in the current directory, you would use the following command:

```
$ grep fire *.txt
```
Which yields:

```
$ grep fire *.txt
Algarve-History.txt:Portugal’s greatest misfortune struck on All Saint’s Day, 1 November 1755. With the candlelit churches crowded with worshippers, a monstrous earthquake struck, followed by fast-spreading fires and a devastating tidal wave that swept over the Algarve inland as far as 6.5 km (4 miles). The exact casualty figure will never be known, but it is estimated that 5,000 died immediately and between 40,000 and 60,000 perished as a result of secondary injuries and the ensuing famine and pestilence. The epicenter of the earthquake is thought to have been off the Algarve coast, possibly between Tavira and Faro, but it devastated places as far away as the capital, Lisbon. Witnesses claim to have seen a fiery volcano erupt from beneath the sea just before the first jolt.
Algarve-History.txt:Bloodshed would haunt the remaining years of the Portuguese monarchy. On 1 February 1908, the royal family was riding in an open carriage along the Lisbon river front plaza, Terreiro do Paço, when an assassin opened fire and killed King Carlos and the heir to the throne, Prince Luis Filipe. The prince’s younger brother, Prince Manuel, was also hit, but he survived and was thus propelled to the throne at the tender age of 19.
Algarve-WhereToGo.txt:You can walk to this area easily from the central squares, but it’s also fun to go by tram or instead to board the landmark 30-meter (98-foot) Elevador de Santa Justa, which you’ll find just off the Rossio square in the Baixa, the lower city. This 1902 Victorian marvel of iron and glass was built by Raul Mesnier. The longer, slower way back downhill meanders through the upmarket shopping area of Chiado, now totally rebuilt after a 1988 fire that swept through the district.        
...
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

Here's another example. To search for the word "penis" in all files in the directory "written_2" and its subdirectories, you would use the following command:

```
grep -r penis written_2
```

Which yields:
```
$ grep -r penis written_2
written_2/travel_guides/berlitz1/WhatToJapan.txt:        cultural barriers: the human penis. Phalluses huge and humble, wooden
written_2/travel_guides/berlitz2/Bali-WhereToGo.txt:Several temples in the area are worth a short stop. Pura Kebo Edan has a statue of the giant Bima, standing 3 m (10 ft) tall, with multiple penises, trampling on a copulating couple. A collection of ancient statuary includes some dating from the 13th century. There’s more fine carved stonework at the 14th-century Pura Pusering Jagat, known as the “Temple of the Navel of the World.” During a full moon, childless couples pray at the stone shrines depicting lingam and yoni (male and female genitalia).
```

## 3. Search for a pattern and display only the matching text:
By default, grep will display the entire line that contains the pattern. However, you can use the -o option to display only the matching text. For example, to search for the word "Acropolis" in a file called "Athens-History.txt" and display only the matching text, you would use the following command:

```
grep -o Acropolis Athens-History.txt
```

This command will display only the matching text:

```
$ grep -o Acropolis Athens-History.txt
Acropolis
Acropolis
Acropolis
Acropolis
Acropolis
Acropolis
```

Here's another example. To search for the word "sea" in a file called "Bahamas-History.txt" and display only the matching text, you would use the following command:
```
$ grep -o sea Bahamas-History.txt
```

which yields:
```
$ grep -o sea Bahamas-History.txt
sea
sea
sea
sea
sea
```

## 4. Search for a pattern and exclude certain files or directories:
You can use the --exclude and --exclude-dir options to exclude certain files or directories from your search. For example, to search for the word "pee" in all text files in the current directory, but exclude any files with names containing "Athens", you would use the following command:

```
grep --exclude "Athens" pee *.txt
```

This yields:

```
$ grep --exclude "Athens" pee *.txt
Amsterdam-Intro.txt:Amsterdam is a wonderful city for visitors. Small enough to stroll around, and with the canal side streets too narrow for tour buses, you can’t drive past all the best attractions at high speed. Here, there is no glass window between you and reality. You have to feel the summer sun, or see your breath on a crisp winter morning as you step out to see what Amsterdam is all about. If you take a canal tour, the quiet boats allow you to float slowly along, away from the noise of the modern world.
Amsterdam-WhereToGo.txt:Cross the river via Magere Brug then travel one block north and take a left along the northern bank of the Herengracht Canal. Here you will get your first glimpse of the canal system which was built during Amsterdam’s Golden Age and revolutionized the city. During its time, probably the most sought after and expensive real estate in the world. Herengracht particularly has many beautiful houses which can really only be appreciated by an afternoon strolling by them (see box page 66). This part of town is still mostly residential and many houses have been converted into apartments for successful Amsterdammers. It is fascinating to peek inside at the ultra-modern interiors, which give a feel of the flair the Dutch seem to have for interior design.
Amsterdam-WhereToGo.txt:Haarlem, situated only 19 km (12 miles) from Amsterdam is the birthplace of Frans Hals, father of The Dutch School of painting which developed during the Golden Age. He was a peer of Rembrandt’s among others.
Athens-History.txt:But Athens was never to regain her earlier military or political influence. A new star rose in the north — that of Philip II of Macedon, father of Alexander the Great. He advanced the far-sighted scheme of a federation of Greek states, which Athens resisted. Some Athenians even urged the Assembly to declare war on the Macedonian King. (The fiery Philippics, speeches on the subject by master orator Demosthenes, rate among the finest of their kind.) Following defeat at the battle of Chaeronea in 338 b.c., however, the Athenians accepted an alliance with other states and even sent Philip a gold crown as a token of submission.
Athens-WhereToGo.txt:In the northeastern area, you’ll come to the Hill of the Pnyx, meeting place of the Assembly of Athens. Loosely translated, pnyx means “crowded or tightly packed place,” and in ancient times this was a highly populated area. You’ll see the outlines of walls, including the defensive Themistoklean Wall, between the bushes or under the turf as you stroll. The Pnyx meeting place can be found below the summit on the northeastern side of the hill. When democracy was established at the end of the sixth century b.c. the debating chamber moved from the Agora to this structure and it was here that the great statesmen of Greece made their speeches at the rostrum. Seats were provided for the 5,000 citizens of the city needed for a decision-making quorum, who would listen to the arguments of Pericles and Themistocles.     
...   
```

Here's another example. To search for the word "happy" in all text files in the current directory, but exclude any files with names containing "Athens", you would use the following command:

```
grep --exclude "Athens" happy *.txt
```

This yields:

```
$ grep --exclude "Athens" happy *.txt
Amsterdam-WhereToGo.txt:The Dutch Royal barge (last used in 1962) is also kept in air-conditioned splendor, but perhaps pride of place — and certainly what brings 18th-century seafaring to life — is the re-creation of a Dutch East India ship The Amsterdam which sits in the dock outside. She is the life-size replica of a real ship completed in 1748, but more than this, The Amsterdam has a “press-ganged” crew to man her. As you explore her decks, the captain will illustrate his course with charts of the time, the doctor will explain his rather primitive treatments, and the ordinary seamen will be happy to sing you a Dutch sea shanty.
Amsterdam-WhereToGo.txt:This landscape is no accident or happy coincidence but a living museum created in 1960, which has brought together a number of farmhouses, windmills, dairies, and barns — real agricultural buildings which would have been demolished had they not been relocated here. Zaanse Schans has working mills, cheese-making factories, and clog workshops, situated on a canalside. You are free to explore at your own pace and maybe enjoy a pannekoeken (pancake) while you’re there.
Bahamas-History.txt:Since independence the Bahamas has kept British systems of judiciary and government yet has moved closer economically to its near neighbor, the US. The Bahamian Government has deliberately pursued tourism as the major industry of the Bahamian commonwealth and is happy to welcome many millions of visitors to its shores. The growth in cruise traffic has been particularly strong. The other islands, called the Family Islands by the government but generally referred to as the Out Islands by the tourist trade, have not shared this huge growth in numbers of visitors. Together they offer tourists almost any form of vacation experience, from the bustle of the busy city to the silence of the desert island.
...
```



