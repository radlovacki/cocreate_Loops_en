# Characters and strings

The character data type, commonly referred to as char, is used to represent
individual characters. Since computers can only store binary values, characters
must be encoded as numbers. In modern computer systems, either ASCII or Unicode
encoding schemes are used. Older programming languages (e.g., C) typically rely
on ASCII, while modern languages (e.g., C#) support Unicode.

Understanding how characters and strings are represented will help you to
handle text correctly in the following lesson, ensuring proper data processing.

## ASCII

ASCII *(American Standard Code for Information Interchange)* is a 7-bit binary
code, represented in memory with 8 bits (one byte). It defines 128 characters,
including letters, digits, punctuation marks, and control characters:

```text
DEC OCT HEX CH    DEC OCT HEX CH    DEC OCT HEX CH    DEC OCT HEX CH
---------------   ---------------   ---------------   ---------------
0   0   00  NUL   32  40  20  SPACE 64  100 40  @     96  140 60  `
1   1   01  SOH   33  41  21  !     65  101 41  A     97  141 61  a
2   2   02  STX   34  42  22  "     66  102 42  B     98  142 62  b
3   3   03  ETX   35  43  23  #     67  103 43  C     99  143 63  c
4   4   04  EOT   36  44  24  $     68  104 44  D     100 144 64  d
5   5   05  ENQ   37  45  25  %     69  105 45  E     101 145 65  e
6   6   06  ACK   38  46  26  &     70  106 46  F     102 146 66  f
7   7   07  BEL   39  47  27  '     71  107 47  G     103 147 67  g
8   10  08  BS    40  50  28  (     72  110 48  H     104 150 68  h
9   11  09  HT    41  51  29  )     73  111 49  I     105 151 69  i
10  12  0A  LF    42  52  2A  *     74  112 4A  J     106 152 6A  j
11  13  0B  VT    43  53  2B  +     75  113 4B  K     107 153 6B  k
12  14  0C  FF    44  54  2C  ,     76  114 4C  L     108 154 6C  l
13  15  0D  CR    45  55  2D  -     77  115 4D  M     109 155 6D  m
14  16  0E  SO    46  56  2E  .     78  116 4E  N     110 156 6E  n
15  17  0F  SI    47  57  2F  /     79  117 4F  O     111 157 6F  o
16  20  10  DLE   48  60  30  0     80  120 50  P     112 160 70  p
17  21  11  DC1   49  61  31  1     81  121 51  Q     113 161 71  q
18  22  12  DC2   50  62  32  2     82  122 52  R     114 162 72  r
19  23  13  DC3   51  63  33  3     83  123 53  S     115 163 73  s
20  24  14  DC4   52  64  34  4     84  124 54  T     116 164 74  t
21  25  15  NAK   53  65  35  5     85  125 55  U     117 165 75  u
22  26  16  SYN   54  66  36  6     86  126 56  V     118 166 76  v
23  27  17  ETB   55  67  37  7     87  127 57  W     119 167 77  w
24  30  18  CAN   56  70  38  8     88  130 58  X     120 170 78  x
25  31  19  EM    57  71  39  9     89  131 59  Y     121 171 79  y
26  32  1A  SUB   58  72  3A  :     90  132 5A  Z     122 172 7A  z
27  33  1B  ESC   59  73  3B  ;     91  133 5B  [     123 173 7B  {
28  34  1C  FS    60  74  3C  <     92  134 5C  \     124 174 7C  |
29  35  1D  GS    61  75  3D  =     93  135 5D  ]     125 175 7D  }
30  36  1E  RS    62  76  3E  >     94  136 5E  ^     126 176 7E  ~
31  37  1F  US    63  77  3F  ?     95  137 5F  _     127 177 7F  DEL
```

## Unicode

Unicode is an extended character set that includes all ASCII codes as its first
part. In Unicode, the first 128 code values (U+0000 to U+007F) are completely
identical to ASCII codes. Beyond that, Unicode defines more than 150,000
characters from writing systems around the world. For example, the specific
Latin characters of the Serbian alphabet are defined like this...

| Code   | Symbol | DEC     |
|--------|--------|---------|
| U+0106 | Ć      | 262     |
| U+0107 | ć      | 263     |
| U+010C | Č      | 268     |
| U+010D | č      | 269     |
| U+0110 | Đ      | 272     |
| U+0111 | đ      | 273     |
| U+0160 | Š      | 288     |
| U+0161 | š      | 289     |
| U+017D | Ž      | 381     |
| U+017E | ž      | 382     |

...Latin letters written with two characters are defined like this...

| Code   | Symbol | DEC     |
|--------|--------|---------|
| U+01C4 | Ǆ      | 452     |
| U+01C5 | ǅ      | 453     |
| U+01C6 | ǆ      | 454     |
| U+01C7 | Ǉ      | 455     |
| U+01C8 | ǈ      | 456     |
| U+01C9 | ǉ      | 457     |
| U+01CA | Ǌ      | 458     |
| U+01CB | ǋ      | 459     |
| U+01CC | ǌ      | 460     |

...and the Cyrillic characters of the Serbian alphabet are defined like this:

| Code   | Symbol | DEC     |
|--------|--------|---------|
| U+0410 | А      | 1040    |
| U+0411 | Б      | 1041    |
| U+0412 | В      | 1042    |
| U+0413 | Г      | 1043    |
| U+0414 | Д      | 1044    |
| U+0402 | Ђ      | 1026    |
| U+0415 | Е      | 1045    |
| U+0416 | Ж      | 1046    |
| U+0417 | З      | 1047    |
| U+0418 | И      | 1048    |
| U+0408 | Ј      | 1032    |
| U+041A | К      | 1050    |
| U+041B | Л      | 1051    |
| U+0409 | Љ      | 1033    |
| U+041C | М      | 1052    |
| U+041D | Н      | 1053    |
| U+040A | Њ      | 1034    |
| U+041E | О      | 1054    |
| U+041F | П      | 1055    |
| U+0420 | Р      | 1056    |
| U+0421 | С      | 1057    |
| U+0422 | Т      | 1058    |
| U+040B | Ћ      | 1035    |
| U+0423 | У      | 1059    |
| U+0424 | Ф      | 1060    |
| U+0425 | Х      | 1061    |
| U+0426 | Ц      | 1062    |
| U+0427 | Ч      | 1063    |
| U+040F | Џ      | 1039    |
| U+0428 | Ш      | 1064    |
| U+0430 | а      | 1072    |
| U+0431 | б      | 1073    |
| U+0432 | в      | 1074    |
| U+0433 | г      | 1075    |
| U+0434 | д      | 1076    |
| U+0452 | ђ      | 1106    |
| U+0435 | е      | 1077    |
| U+0436 | ж      | 1078    |
| U+0437 | з      | 1079    |
| U+0438 | и      | 1080    |
| U+0458 | ј      | 1112    |
| U+043A | к      | 1082    |
| U+043B | л      | 1083    |
| U+0459 | љ      | 1113    |
| U+043C | м      | 1084    |
| U+043D | н      | 1085    |
| U+045A | њ      | 1114    |
| U+043E | о      | 1086    |
| U+043F | п      | 1087    |
| U+0440 | р      | 1088    |
| U+0441 | с      | 1089    |
| U+0442 | т      | 1090    |
| U+045B | ћ      | 1115    |
| U+0443 | у      | 1091    |
| U+0444 | ф      | 1092    |
| U+0445 | х      | 1093    |
| U+0446 | ц      | 1094    |
| U+0447 | ч      | 1095    |
| U+045F | џ      | 1119    |
| U+0448 | ш      | 1096    |

Although some Latin and Cyrillic letters appear to be the same, their Unicode
code values are different. For example, the Latin capital letter A is encoded
as U+0041, while the Cyrillic capital letter A is encoded as U+0410.

## Strings

A string is a sequence of characters arranged in a specific order. Each
character can be a letter, digit, punctuation mark, whitespace, or symbol.
Strings are fundamental in computing because they represent text, file names,
user input, and much more.

A string is typically represented as a contiguous block of memory. Some systems
terminate strings with a special marker like a null character `'\0'` to
indicate the end, while others may store the length explicitly.
