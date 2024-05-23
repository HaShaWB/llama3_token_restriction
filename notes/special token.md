## Special token
- tokens that are used for special purpose
- ex: <end_of_sequence>, <\\n>

1. Punctuation or Whitespace : 0~255
   - includes number or alphabet
2. Special token : 128000~128255
3. top n : select token that most commonly exist
```
top_100_in_wikitext = {1027, 520, 12, 13, 15, 16, 527, 17, 18, 20, 19, 21, 1047, 24, 1049, 22, 1051, 539, 23, 1053, 31, 551, 555, 1077, 568, 571, 574, 578, 1101, 1102, 82, 2652, 617, 1139, 662, 1174, 1176, 679, 1193, 59562, 682, 1202, 704, 706, 709, 719, 720, 220, 763, 1283, 264, 279, 1306, 284, 291, 810, 813, 814, 304, 311, 1847, 315, 320, 832, 323, 330, 2380, 339, 1364, 2391, 358, 872, 362, 364, 1389, 369, 883, 374, 889, 1403, 892, 387, 389, 902, 922, 927, 420, 430, 1455, 433, 1461, 439, 449, 459, 32213, 477, 994, 2550, 505, 1023}
```
1. target token set : tokens that i want to generate
	- words containing target token
	- explite rule
		- target token
		- target token + .,?!
		- target token + space
		- target token with Capital