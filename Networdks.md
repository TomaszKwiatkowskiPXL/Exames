# Examen Networks

### Calculations

* Omzetten `Binair -> Decimaal`
  - Om binair te omzetten naar decimaal moet je de binaire vollegorde van rechts -> links
    met machten te begginen rekenen, stell je hebt getal `7` in binair is dat `0111`, dus
    wij gaan van rechts machten gebruiken van 2.

    | 0 | 1 | 1 | 1 |
    | - | - | - | - |
    |  2^3 | 2^2  | 2^1  | 1^1  |
    | 8 | 0 | 2 | 1 |
    |  `1 +2 + 4 +0`  | `=7` |

* Omzetten `Decimaal -> Binair`
  - Om decimaal naar binair te converteren gaan wij decimale getal telkens delen door 2. bv getal 512
    | `Dec`  | `=`  | `bin`|
    | - | - | - |
    |512/2 |256  | 0 |
    | 256/2  | 128 | 0 |
    | 128/2 | 64 | 0 |
    |  64/2  | 32 | 0 |
    | 16/2  | 8 | 0 |
    | 8/2 | 4 | 0 |
    | 4/2 | 2 | 0 |
    |2/2 | 1 | 0 |
    | 1/2 | 0.5 | 1 |
    
 - `Nu gaan wij de onderste getal naar links plaaten`
      | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |0 | 0 | 0 |
      | - | - | - | - | - | - | -  | -  | - | - | - |
      | 512 | 256 | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 | 0 |
      | 1 | x | x | x | x | x | x | x | x | x | x |
- (indien er een getal extra er zou zijn bv bij de 32ste bit dan doe je 512+32)

* Omzetten `Hexodecimaal -> decimaal & binair`
 
    
| Hex | Dec | Bin  |
|-----|-----|------|
| A   | 10  | 1010 |
| B   | 11  | 1011 |
| C   | 12  | 1100 |
| D   | 13  | 1101 |
| E   | 14  | 1110 |
| F   | 15  | 1111 |

* Omzetten `decimaal -> Hexodecimaal`
  - Omzetten van decimalen naar hexodecimalen doen wij met de getal te delen door 16 de uitkomst doen we maal en dan krijg
  
    bv:
    | - |
    |756/16 =47.25 (47*16= 752 dus rest 4 (756-752))|
    |47/16 = 2.93 (2*16=32 rest 47-32= 15(hex = F))|
    |word rest ->2/16 = 0 (0*16 = 0 rest = 2)|
       | Ant   `=4F2` |

    -Een betere voorbeeld 1432
    | - |
    | 1432/16 = 89.5  (89*16 = 1424 (1432 - 1424 rest 8)) |
    | 89/16 = 5,56 (5*16 = 80 rest = 9) |
    | -> word rest  5/16 = 0 (0*16(rest word 5))  |
    | Antw= `895` |

* Omzetten `Octalen naar decimalen`
  - Bij octae getalen werken wij met machten van 8 ipv 16.
    
    | Cijfer | Berekening        | Resultaat     |
    |--------|-------------------|---------------|
    | 7 × 8⁰ | 7 × 1             | 7             |
    | 3 × 8¹ | 3 × 8             | 24            |
    | 2 × 8² | 2 × 64 (8² = 64)  | 128           |
    * `7 + 24 + 128 = 159`

  
