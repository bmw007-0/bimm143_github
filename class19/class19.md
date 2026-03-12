# Class 19: Cancer Mutation Mini-Project
Brian Wong (PID: A18639001)

``` r
library(bio3d)

ngs <- read.fasta("A18639001_mutant_seq.fa")
ngs
```

                   1        .         .         .         .         .         60 
    wt_healthy     MGAIGLLWLLPLLLSTAAVGSGMGTGQRAGSPAAGPPLQPREPLSYSRLQRKSLAVDFVV
    mutant_tumor   MGAIGLLWLLPLLLSTAAVGSGMGTGQRAGSPAAGPPLQPREPLSYSRLQRKSLAVDFVV
                   ************************************************************ 
                   1        .         .         .         .         .         60 

                  61        .         .         .         .         .         120 
    wt_healthy     PSLFRVYARDLLLPPSSSELKAGRPEARGSLALDCAPLLRLLGPAPGVSWTAGSPAPAEA
    mutant_tumor   PSLFRVYARDLLLPPSSSELKAGRPEARGSLALDCAPLLRLLGPAPGVSWTAGSPAPAEA
                   ************************************************************ 
                  61        .         .         .         .         .         120 

                 121        .         .         .         .         .         180 
    wt_healthy     RTLSRVLKGGSVRKLRRAKQLVLELGEEAILEGCVGPPGEAAVGLLQFNLSELFSWWIRQ
    mutant_tumor   RTLSRVLKGGSVRKLRRAKQLVLELGEEAILEGCVGPPGEAAVGLLQFNLSELFSWWIRQ
                   ************************************************************ 
                 121        .         .         .         .         .         180 

                 181        .         .         .         .         .         240 
    wt_healthy     GEGRLRIRLMPEKKASEVGREGRLSAAIRASQPRLLFQIFGTGHSSLESPTNMPSPSPDY
    mutant_tumor   GEGRLRIRLMPEKKASEVGREGRLSAAIRASQPRLLFQIFGTGHSSLESPTNMPSPSPDY
                   ************************************************************ 
                 181        .         .         .         .         .         240 

                 241        .         .         .         .         .         300 
    wt_healthy     FTWNLTWIMKDSFPFLSHRSRYGLECSFDFPCELEYSPPLHDLRNQSWSWRRIPSEEASQ
    mutant_tumor   FTWNLTWIMKDSFPFLSHRSRYGLECSFDFPCELEYSPPLHDLRNQSWSWRRIPSEEASQ
                   ************************************************************ 
                 241        .         .         .         .         .         300 

                 301        .         .         .         .         .         360 
    wt_healthy     MDLLDGPGAERSKEMPRGSFLLLNTSADSKHTILSPWMRSSSEHCTLAVSVHRHLQPSGR
    mutant_tumor   MDLLDGPGAERSKEMPRGSFLLLNTSADSKHTILSPWMRSSSEHCTLAVSVHRHLQPSGR
                   ************************************************************ 
                 301        .         .         .         .         .         360 

                 361        .         .         .         .         .         420 
    wt_healthy     YIAQLLPHNEAAREILLMPTPGKHGWTVLQGRIGRPDNPFRVALEYISSGNRSLSAVDFF
    mutant_tumor   YIAQLLPHNEAAREILLMPTPGKHGWTVLQGRIGRPDNPFRVALEYISSGNRSLSAVDFF
                   ************************************************************ 
                 361        .         .         .         .         .         420 

                 421        .         .         .         .         .         480 
    wt_healthy     ALKNCSEGTSPGSKMALQSSFTCWNGTVLQLGQACDFHQDCAQGEDESQMCRKLPVGFYC
    mutant_tumor   ALKNCSEGTSPGSKMALQSSFTCWNGTVLQLGQACDFHQDCAQGEDESQMCRKLPVGFYC
                   ************************************************************ 
                 421        .         .         .         .         .         480 

                 481        .         .         .         .         .         540 
    wt_healthy     NFEDGFCGWTQGTLSPHTPQWQVRTLKDARFQDHQDHALLLSTTDVPASESATVTSATFP
    mutant_tumor   NFEDGFCGWTQGTLSPHTPQWQVRTLKDARFQDHQDHALLLSTTDVPASESATVTSATFP
                   ************************************************************ 
                 481        .         .         .         .         .         540 

                 541        .         .         .         .         .         600 
    wt_healthy     APIKSSPCELRMSWLIRGVLRGNVSLVLVENKTGKEQGRMVWHVAAYEGLSLWQWMVLPL
    mutant_tumor   APIKSSPCELRMSWLIRGVLRGNVSLVLVENKTGKEQGRMVWHVAAYEGLSLWQWMVLPL
                   ************************************************************ 
                 541        .         .         .         .         .         600 

                 601        .         .         .         .         .         660 
    wt_healthy     LDVSDRFWLQMVAWWGQGSRAIVAFDNISISLDCYLTISGEDKILQNTAPKSRNLFERNP
    mutant_tumor   LDVSDRFWLQMVAWWGQGSRAIVAFDNISISLDCYLTISGEDKILQNTAPKSRNLFERNP
                   ************************************************************ 
                 601        .         .         .         .         .         660 

                 661        .         .         .         .         .         720 
    wt_healthy     NKELKPGENSPRQTPIFDPTVHWLFTTCGASGPHGPTQAQCNNAYQNSNLSVEVGSEGPL
    mutant_tumor   NKELKPGENSPRQTPIFDPTVHWLFTTCGASGPHGPTQAQCNNAYQNSNLSVEVGSEGPL
                   ************************************************************ 
                 661        .         .         .         .         .         720 

                 721        .         .         .         .         .         780 
    wt_healthy     KGIQIWKVPATDTYSISGYGAAGGKGGKNTMMRSHGVSVLGIFNLEKDDMLYILVGQQGE
    mutant_tumor   KGIQIWKVPATDTYSISGYGAAGGKGGKNTMMRSHGVSVLGIFNLEKDDMLYILVGQQGE
                   ************************************************************ 
                 721        .         .         .         .         .         780 

                 781        .         .         .         .         .         840 
    wt_healthy     DACPSTNQLIQKVCIGENNVIEEEIRVNRSVHEWAGGGGGGGGATYVFKMKDGVPVPLII
    mutant_tumor   DACPSTNQLIQKVCIGENNVIEEEIRVNRSVHEWAGGGGGGGGATYVFKMKDGVPVPLII
                   ************************************************************ 
                 781        .         .         .         .         .         840 

                 841        .         .         .         .         .         900 
    wt_healthy     AAGGGGRAYGAKTDTFHPERLENNSSVLGLNGNSGAAGGGGGWNDNTSLLWAGKSLQEGA
    mutant_tumor   AAGGGGRAYGAKTDTFHPERLENNSSVLGLNGNSGAAGGGGGWNDNTSLLWAGKSLQEGA
                   ************************************************************ 
                 841        .         .         .         .         .         900 

                 901        .         .         .         .         .         960 
    wt_healthy     TGGHSCPQAMKKWGWETRGGFGGGGGGCSSGGGGGGYIGGNAASNNDPEMDGEDGVSFIS
    mutant_tumor   TGGHSCPQAMKKWGWETRGGFGGGGGGCSSGGGGGGYIGGNAASNNDPEMDGEDGVSFIS
                   ************************************************************ 
                 901        .         .         .         .         .         960 

                 961        .         .         .         .         .         1020 
    wt_healthy     PLGILYTPALKVMEGHGEVNIKHYLNCSHCEVDECHMDPESHKVICFCDHGTVLAEDGVS
    mutant_tumor   PLGILYTPALKVMEGHGEVNIKHYLNCSHCEVDECHMDPESHKVICFCDHGTVLAEDGVS
                   ************************************************************ 
                 961        .         .         .         .         .         1020 

                1021        .         .         .         .         .         1080 
    wt_healthy     CIVSPTPEPHLPLSLILSVVTSALVAALVLAFSGIMIVYRRKHQELQAMQMELQSPEYKL
    mutant_tumor   CIVSPTPEPHLPLSLILSVVTSALVAALVLAFSGIMIVYRRKHQELQAMQMELQSPEYKL
                   ************************************************************ 
                1021        .         .         .         .         .         1080 

                1081        .         .         .         .         .         1140 
    wt_healthy     SKLRTSTIMTDYNPNYCFAGKTSSISDLKEVPRKNITLIRGLGHGAFGEVYEGQVSGMPN
    mutant_tumor   SKLRTSTIMTDYNPNYCFAGKTSSISDLKEVPRKNITLIRGLGHGAFGEVYEGQVSGMPN
                   ************************************************************ 
                1081        .         .         .         .         .         1140 

                1141        .         .         .         .         .         1200 
    wt_healthy     DPSPLQVAVKTLPEVCSEQDELDFLMEALIISKFNHQNIVRCIGVSLQSLPRFILLELMA
    mutant_tumor   DPSPVQVAVKTLPEVCSEQDELDFLMEALIISKFNHQNIVRCIGVSLQSLPRFILLELMA
                   ****^******************************************************* 
                1141        .         .         .         .         .         1200 

                1201        .         .         .         .         .         1260 
    wt_healthy     GGDLKSFLRETRPRPSQPSSLAMLDLLHVARDIACGCQYLEENHFIHRDIAARNCLLTCP
    mutant_tumor   GGDLKSFLRETRPRPSQPSSLAMLDLLHVARDEACGCQYLERNHFIHRDIAARNCLLTCP
                   ******************************** ******** ****************** 
                1201        .         .         .         .         .         1260 

                1261        .         .         .         .         .         1320 
    wt_healthy     GPGRVAKIGDFGMARDIYRASYYRKGGCAMLPVKWMPPEAFMEGIFTSKTDTWSFGVLLW
    mutant_tumor   GPGRVAKIGDFGMARDIYRASYYRKGGCAMLPVKWMPPEAFMEGIFTSKTDYWSFGVLLW
                   *************************************************** ******** 
                1261        .         .         .         .         .         1320 

                1321        .         .         .         .         .         1380 
    wt_healthy     EIFSLGYMPYPSKSNQEVLEFVTSGGRMDPPKNCPGPVYRIMTQCWQHQPEDRPNFAIIL
    mutant_tumor   EIFSLGYMPYPSKSNQEVLEFVTSGGRMDPPKNCPGPVYRIMTQCWQHQPEDRPNFAIIL
                   ************************************************************ 
                1321        .         .         .         .         .         1380 

                1381        .         .         .         .         .         1440 
    wt_healthy     ERIEYCTQDPDVINTALPIEYGPLVEEEEKVPVRPKDPEGVPPLLVSQQAKREEERSPAA
    mutant_tumor   ERIEYCTQDPDVINTALPIEYGPLVEEEEKVPVRPKDPEGVPPLLVSQQAKREEERSPAA
                   ************************************************************ 
                1381        .         .         .         .         .         1440 

                1441        .         .         .         .         .         1500 
    wt_healthy     PPPLPTTSSGKAAKKPTAAEISVRVPRGPAVEGGHVNMAFSQSNPPSELHKVHGSRNKPT
    mutant_tumor   PPPLPTTSSGKAAKKPTAAEISVRVPRGPAVEGGHVNMAFSQSNPPSELHKVHGSRNKPT
                   ************************************************************ 
                1441        .         .         .         .         .         1500 

                1501        .         .         .         .         .         1560 
    wt_healthy     SLWNPTYGSWFTEKPTKKNNPIAKKEPHDRGNLGLEGSCTVPPNVATGRLPGASLLLEPS
    mutant_tumor   SLWNPTYGSWFTEKPTKKNNPIAKKEPHDRGNLGLEGSCTVPPNVATGRLPGASLLLEPS
                   ************************************************************ 
                1501        .         .         .         .         .         1560 

                1561        .         .         .         .         .         1620 
    wt_healthy     SLTANMKEVPLFRLRHFPCGNVNYGYQQQGLPLEAATAPGAGHYEDTILKSKNSMNQPGP
    mutant_tumor   SLTANMKEVPLFRLRHFPCGNVNYGYQQQGLPLEAATAPGAGHYEDTILKSKNSMNQPGP
                   ************************************************************ 
                1561        .         .         .         .         .         1620 

    Call:
      read.fasta(file = "A18639001_mutant_seq.fa")

    Class:
      fasta

    Alignment dimensions:
      2 sequence rows; 1620 position columns (1620 non-gap, 0 gap) 

    + attr: id, ali, call

> Q1. \[1pt\] What protein do these sequences correspond to? (Give both
> full gene/protein name and official symbol).

Official gene/protein name: ALK, Chain A, ALK tyrosine kinase receptor
Protein/Official symbol: 7NX3_A.

``` r
blast.pdb(ngs)
```

    Warning in blast.pdb(ngs): Multiple sequences detected - using only the first
    sequence in input object

     Searching ... please wait (updates every 5 seconds) RID = V628A9VW016 
     ...........
     Reporting 1370 hits

    $hit.tbl
               queryid subjectids identity alignmentlength mismatches gapopens
    1    Query_2244025     7NX3_A  100.000             383          0        0
    2    Query_2244025     7N00_A  100.000             378          0        0
    3    Query_2244025     4FOB_A   99.717             353          1        0
    4    Query_2244025     7LS0_A   99.718             354          1        0
    5    Query_2244025     7MZW_A  100.000             353          0        0
    6    Query_2244025     3AOX_A  100.000             343          0        0
    7    Query_2244025     9GBE_A   99.417             343          2        0
    8    Query_2244025     3L9P_A   99.125             343          3        0
    9    Query_2244025     3LCS_A   99.125             343          3        0
    10   Query_2244025     4Z55_A   99.705             339          1        0
    11   Query_2244025     4DCE_A   99.700             333          1        0
    12   Query_2244025     7NWZ_A   98.555             346          3        1
    13   Query_2244025     4FNZ_A   99.694             327          1        0
    14   Query_2244025     4FNX_A   99.388             327          2        0
    15   Query_2244025     4FNW_A   99.388             327          2        0
    16   Query_2244025     2XP2_A   99.688             320          1        0
    17   Query_2244025     2YFX_A   99.375             320          2        0
    18   Query_2244025     8ARJ_A  100.000             319          0        0
    19   Query_2244025     5AA9_A   99.375             320          2        0
    20   Query_2244025     2YHV_A   99.687             319          1        0
    21   Query_2244025     4ANL_A   99.687             319          1        0
    22   Query_2244025     4ANS_A   99.373             319          2        0
    23   Query_2244025     6E0R_A  100.000             317          0        0
    24   Query_2244025     2YJR_A   99.687             319          1        0
    25   Query_2244025     5A9U_A   99.375             320          2        0
    26   Query_2244025     2YJS_A   99.687             319          1        0
    27   Query_2244025     7BTT_A   99.686             318          1        0
    28   Query_2244025     5AA8_A   99.062             320          3        0
    29   Query_2244025     4TT7_A   99.685             317          1        0
    30   Query_2244025     2XB7_A  100.000             314          0        0
    31   Query_2244025     6MX8_A  100.000             307          0        0
    32   Query_2244025     7MZY_A  100.000             314          0        0
    33   Query_2244025     7LRZ_A   99.677             310          1        0
    34   Query_2244025     3ZBF_A   49.147             293        143        3
    35   Query_2244025     7Z5W_A   49.470             283        140        2
    36   Query_2244025     9QEK_A   49.296             284        141        2
    37   Query_2244025   8PYI_AAA   44.816             299        158        3
    38   Query_2244025     3LVP_A   43.974             307        165        3
    39   Query_2244025     1P4O_A   44.816             299        158        3
    40   Query_2244025     1M7N_A   44.816             299        158        3
    41   Query_2244025     5FXQ_A   44.828             290        154        2
    42   Query_2244025     5FXR_A   44.828             290        154        2
    43   Query_2244025     1JQH_A   44.828             290        154        2
    44   Query_2244025     3QQU_A   45.775             284        148        2
    45   Query_2244025     2OJ9_A   45.583             283        148        2
    46   Query_2244025     3LW0_A   45.583             283        148        2
    47   Query_2244025     3O23_A   45.583             283        148        2
    48   Query_2244025     4D2R_A   45.583             283        148        2
    49   Query_2244025     3I81_A   45.583             283        148        2
    50   Query_2244025     5FXS_A   44.483             290        155        2
    51   Query_2244025     3D94_A   45.583             283        148        2
    52   Query_2244025     2ZM3_A   43.793             290        157        2
    53   Query_2244025     1K3A_A   44.523             283        151        2
    54   Query_2244025     3ETA_A   43.648             307        158        5
    55   Query_2244025     1I44_A   45.714             280        144        3
    56   Query_2244025     1IRK_A   45.714             280        144        3
    57   Query_2244025     4IBM_A   45.714             280        144        3
    58   Query_2244025     5E1S_A   45.357             280        145        3
    59   Query_2244025     5HHW_A   45.357             280        145        3
    60   Query_2244025     3EKK_A   45.357             280        145        3
    61   Query_2244025     1P14_A   45.357             280        145        3
    62   Query_2244025     9OYZ_B   40.244             410        225        7
    63   Query_2244025     8EYR_A   40.548             365        186        6
    64   Query_2244025     6JK8_A   40.278             360        189        5
    65   Query_2244025     8DWN_A   45.000             280        146        3
    66   Query_2244025     2Z8C_A   44.643             280        147        3
    67   Query_2244025     1GAG_A   44.643             280        147        3
    68   Query_2244025     1RQQ_A   44.643             280        147        3
    69   Query_2244025     6PYH_A   40.000             365        188        6
    70   Query_2244025     4XLV_A   44.643             280        147        3
    71   Query_2244025     7TYJ_A   43.464             306        166        3
    72   Query_2244025     7SL1_A   41.573             356        182        8
    73   Query_2244025     8DTL_A   41.573             356        182        8
    74   Query_2244025     8EYX_A   41.573             356        182        8
    75   Query_2244025     8U4B_A   41.573             356        182        8
    76   Query_2244025     7BW7_A   41.573             356        182        8
    77   Query_2244025     8VJB_A   41.573             356        182        8
    78   Query_2244025     7VKO_A   40.836             311        172        3
    79   Query_2244025     7PG0_A   41.573             356        182        8
    80   Query_2244025     4ASZ_A   42.182             275        149        3
    81   Query_2244025     8J5W_A   40.895             313        167        4
    82   Query_2244025     6PXV_A   42.059             340        175        7
    83   Query_2244025     4YNE_A   40.850             306        169        3
    84   Query_2244025     6IQN_A   41.275             298        163        3
    85   Query_2244025     4AOJ_A   40.575             313        168        4
    86   Query_2244025     7VKM_A   40.514             311        173        3
    87   Query_2244025     6NSP_A   41.275             298        163        3
    88   Query_2244025     6D1Y_A   40.575             313        168        4
    89   Query_2244025     5H3Q_A   40.575             313        168        4
    90   Query_2244025     4F0I_A   41.275             298        163        3
    91   Query_2244025     7XAF_A   41.275             298        163        3
    92   Query_2244025     5KMI_A   40.575             313        168        4
    93   Query_2244025     5KML_A   40.575             313        168        4
    94   Query_2244025     6PL1_A   40.575             313        168        4
    95   Query_2244025     5JFS_A   41.275             298        163        3
    96   Query_2244025     5WR7_A   40.909             308        164        4
    97   Query_2244025     6D22_A   41.275             298        163        3
    98   Query_2244025     6NPT_A   40.575             313        168        4
    99   Query_2244025     4GT5_A   41.275             298        163        3
    100  Query_2244025     6NSS_A   40.575             313        168        4
    101  Query_2244025     4PMM_A   41.522             289        157        3
    102  Query_2244025     8J5X_A   40.940             298        164        3
    103  Query_2244025     3V5Q_A   40.614             293        157        5
    104  Query_2244025     5I8A_A   42.049             283        152        3
    105  Query_2244025     5KVT_A   42.049             283        152        3
    106  Query_2244025     4YMJ_A   40.614             293        157        5
    107  Query_2244025     1LUF_A   40.972             288        148        5
    108  Query_2244025     4CSV_A   43.885             278        140        5
    109  Query_2244025     9EF1_A   39.032             310        168        3
    110  Query_2244025     5U6B_A   40.214             281        154        5
    111  Query_2244025     6PNX_A   40.070             287        157        5
    112  Query_2244025     6JMF_A   42.804             271        141        3
    113  Query_2244025     8XKP_A   42.804             271        141        3
    114  Query_2244025     8UDV_A   40.288             278        157        4
    115  Query_2244025     3BKB_A   42.804             271        141        3
    116  Query_2244025     8UDT_A   40.288             278        157        4
    117  Query_2244025     6KZC_A   39.130             299        151        6
    118  Query_2244025     9CD7_A   39.721             287        158        5
    119  Query_2244025     8S9P_C   35.356             379        212        9
    120  Query_2244025     4K33_A   39.721             287        158        5
    121  Query_2244025     3CD3_A   42.435             271        142        3
    122  Query_2244025     8YKI_A   38.235             306        171        7
    123  Query_2244025     4XCU_A   41.135             282        156        5
    124  Query_2244025     5FLF_A   39.721             287        158        6
    125  Query_2244025     9KFU_A   39.236             288        158        5
    126  Query_2244025     3GQL_A   38.235             306        171        7
    127  Query_2244025     7WCW_A   41.237             291        152        7
    128  Query_2244025     5XFF_A   40.816             294        155        7
    129  Query_2244025     8KH9_A   40.476             294        156        7
    130  Query_2244025     4QQJ_A   41.237             291        152        7
    131  Query_2244025     6VG3_A   37.102             283        170        5
    132  Query_2244025     7WCX_A   40.893             291        153        7
    133  Query_2244025     4UXQ_A   40.893             291        153        7
    134  Query_2244025     6TU9_A   39.931             288        159        3
    135  Query_2244025     5XFJ_A   40.476             294        156        7
    136  Query_2244025     7DTZ_A   40.893             291        153        7
    137  Query_2244025     6JPE_A   40.893             291        153        7
    138  Query_2244025     5JKG_A   40.893             291        153        7
    139  Query_2244025     4WUN_A   39.373             287        159        6
    140  Query_2244025     5A4C_A   39.373             287        159        6
    141  Query_2244025     5AM7_A   39.373             287        159        6
    142  Query_2244025     4RWI_A   39.373             287        159        6
    143  Query_2244025     4ZSA_A   39.373             287        159        6
    144  Query_2244025     4F63_A   39.373             287        159        6
    145  Query_2244025     3RHX_A   39.373             287        159        6
    146  Query_2244025     4QQT_A   40.893             291        153        7
    147  Query_2244025     1AGW_A   39.373             287        159        6
    148  Query_2244025     3JS2_A   39.373             287        159        6
    149  Query_2244025     3C4F_A   39.373             287        159        6
    150  Query_2244025     6LVM_A   38.889             288        159        5
    151  Query_2244025     5ZV2_A   39.373             287        159        6
    152  Query_2244025     5VND_A   39.373             287        159        6
    153  Query_2244025     5A46_A   38.065             310        173        8
    154  Query_2244025     4TYE_A   40.550             291        154        7
    155  Query_2244025     4QQ5_A   40.893             291        153        7
    156  Query_2244025     8W5C_A   40.550             291        154        7
    157  Query_2244025     5NUD_A   40.550             291        154        7
    158  Query_2244025     3TT0_A   37.864             309        170        7
    159  Query_2244025     6YI8_A   40.550             291        154        7
    160  Query_2244025     7VJL_A   40.550             291        154        7
    161  Query_2244025     7F3M_A   40.550             291        154        7
    162  Query_2244025     8Y22_A   39.024             287        160        6
    163  Query_2244025     6NVL_A   39.024             287        160        6
    164  Query_2244025     6IUO_A   40.550             291        154        7
    165  Query_2244025     4QQC_A   40.550             291        154        7
    166  Query_2244025     7WCL_A   39.024             287        160        6
    167  Query_2244025     6MZW_A   39.024             287        160        6
    168  Query_2244025     7AAY_A   37.544             285        169        6
    169  Query_2244025     3KXX_A   39.024             287        160        6
    170  Query_2244025     2PZP_A   37.979             287        163        4
    171  Query_2244025     2PWL_A   37.979             287        163        4
    172  Query_2244025     2PZ5_A   37.979             287        163        4
    173  Query_2244025     6FEK_A   39.209             278        162        3
    174  Query_2244025     3GQI_A   37.582             306        173        7
    175  Query_2244025     6XRG_A   39.510             286        157        5
    176  Query_2244025     2PZR_A   37.631             287        164        4
    177  Query_2244025     6LVL_A   37.631             287        164        4
    178  Query_2244025     4J98_A   37.631             287        164        4
    179  Query_2244025     8E1X_A   37.979             287        163        4
    180  Query_2244025     4J97_A   37.631             287        164        4
    181  Query_2244025     3RI1_A   37.631             287        164        4
    182  Query_2244025     7KIA_A   37.631             287        164        4
    183  Query_2244025     9U7E_A   37.631             287        164        4
    184  Query_2244025     8STG_A   37.631             287        164        4
    185  Query_2244025     8SWE_A   37.631             287        164        4
    186  Query_2244025     1GJO_A   37.631             287        164        4
    187  Query_2244025   7OZY_AAA   37.631             287        164        4
    188  Query_2244025     2PVY_A   37.631             287        164        4
    189  Query_2244025     9U3N_A   37.631             287        164        4
    190  Query_2244025     9BHI_A   37.884             293        169        7
    191  Query_2244025     4J99_A   37.631             287        164        4
    192  Query_2244025     5UHN_A   37.631             287        164        4
    193  Query_2244025     2Q0B_A   37.631             287        164        4
    194  Query_2244025     4J96_A   37.631             287        164        4
    195  Query_2244025     8W1L_A   38.415             328        184        7
    196  Query_2244025     5U6C_A   37.459             307        177        8
    197  Query_2244025     2I0V_A   38.415             328        184        7
    198  Query_2244025     2PY3_A   37.631             287        164        4
    199  Query_2244025     7AAZ_A   37.716             289        167        7
    200  Query_2244025     2Z60_A   39.161             286        158        5
    201  Query_2244025     3OY3_A   39.161             286        158        5
    202  Query_2244025     7CQE_A   37.716             289        167        7
    203  Query_2244025     3BEA_A   38.344             326        185        7
    204  Query_2244025     3B2T_A   37.282             287        165        4
    205  Query_2244025     2PSQ_A   37.631             287        164        4
    206  Query_2244025     6LVK_A   37.631             287        164        4
    207  Query_2244025     2PVF_A   36.601             306        176        5
    208  Query_2244025     7OAM_A   37.716             289        167        7
    209  Query_2244025     2P0C_A   37.716             289        167        7
    210  Query_2244025     5UGL_A   37.631             287        164        4
    211  Query_2244025     7DXL_A   37.716             289        167        7
    212  Query_2244025     5AMN_A   38.849             278        164        2
    213  Query_2244025     3CLY_A   36.601             306        176        5
    214  Query_2244025     2QOH_A   39.161             286        158        5
    215  Query_2244025     5TC0_A   37.716             289        167        7
    216  Query_2244025     1FPU_A   39.161             286        158        5
    217  Query_2244025     4TWP_A   39.161             286        158        5
    218  Query_2244025     3OXZ_A   39.161             286        158        5
    219  Query_2244025     2IVS_A   37.543             293        161        3
    220  Query_2244025     5EG3_A   35.948             306        178        5
    221  Query_2244025     7TNH_A   39.365             315        175        7
    222  Query_2244025     8W3D_A   37.282             287        165        4
    223  Query_2244025     7AAX_A   38.686             274        156        6
    224  Query_2244025     2G1T_A   38.908             293        163        5
    225  Query_2244025     5TD2_A   37.857             280        162        6
    226  Query_2244025     8H75_A   37.282             287        165        4
    227  Query_2244025     4WA9_A   39.161             286        158        5
    228  Query_2244025     3QRJ_A   39.576             283        155        5
    229  Query_2244025     5UI0_A   37.282             287        165        4
    230  Query_2244025     2I1M_A   38.650             326        184        7
    231  Query_2244025     6XR6_A   39.161             286        158        5
    232  Query_2244025     2HIW_A   38.333             300        159        6
    233  Query_2244025     7M5Z_A   38.686             274        156        6
    234  Query_2244025     3QUP_A   36.545             301        169        6
    235  Query_2244025     4ZOG_A   39.161             286        158        5
    236  Query_2244025     2E2B_A   39.161             286        158        5
    237  Query_2244025     6WXJ_A   38.110             328        185        7
    238  Query_2244025     8W3B_A   37.282             287        165        4
    239  Query_2244025     2G2F_A   38.908             293        163        5
    240  Query_2244025     5HU9_A   39.576             283        155        5
    241  Query_2244025     3QRI_A   39.576             283        155        5
    242  Query_2244025     8W2X_A   37.282             287        165        4
    243  Query_2244025     3LCD_A   38.199             322        187        6
    244  Query_2244025     6BL8_A   38.811             286        159        5
    245  Query_2244025     6I82_A   37.543             293        161        3
    246  Query_2244025     5UGX_A   37.282             287        165        4
    247  Query_2244025     3PYY_A   39.161             286        158        5
    248  Query_2244025     2HZI_A   38.796             299        157        6
    249  Query_2244025     8W38_A   37.282             287        165        4
    250  Query_2244025     2HYY_A   39.576             283        155        5
    251  Query_2244025     3DK3_A   38.811             286        159        5
    252  Query_2244025     7N9G_A   39.576             283        155        5
    253  Query_2244025     2F4J_A   39.161             286        158        5
    254  Query_2244025     3DK7_A   38.811             286        159        5
    255  Query_2244025     7CC2_A   39.161             286        158        5
    256  Query_2244025     3DK6_A   39.161             286        158        5
    257  Query_2244025     4HW7_A   37.015             335        186        6
    258  Query_2244025     6V6Q_A   36.452             310        178        6
    259  Query_2244025     2OGV_A   39.159             309        178        6
    260  Query_2244025     2HZ0_A   39.928             278        151        5
    261  Query_2244025     6I83_A   37.201             293        162        3
    262  Query_2244025     2V7A_A   38.811             286        159        5
    263  Query_2244025     8JQI_B   38.065             310        173        8
    264  Query_2244025     2IVT_A   37.201             293        162        3
    265  Query_2244025     4XEY_A   39.161             286        158        5
    266  Query_2244025     2IVV_A   37.201             293        162        3
    267  Query_2244025     2QOC_A   37.288             295        168        7
    268  Query_2244025     6IN0_A   37.895             285        161        6
    269  Query_2244025     7W7Y_A   38.811             286        159        5
    270  Query_2244025     2QOB_A   37.288             295        168        7
    271  Query_2244025     6AGX_A   36.585             287        167        4
    272  Query_2244025     4HVS_A   37.500             304        173        6
    273  Query_2244025     2QOK_A   37.124             299        171        7
    274  Query_2244025     2QOO_A   37.124             299        171        7
    275  Query_2244025     8H7F_A   39.223             283        156        5
    276  Query_2244025     6T2W_A   37.015             335        186        6
    277  Query_2244025     2QOD_A   36.709             316        177        8
    278  Query_2244025     2GQG_A   39.223             283        156        5
    279  Query_2244025     8SSN_A   39.161             286        158        5
    280  Query_2244025     3DZQ_A   37.288             295        168        7
    281  Query_2244025     7W7X_A   39.223             283        156        5
    282  Query_2244025     6VHG_A   37.201             293        162        3
    283  Query_2244025     8CGC_A   37.015             335        186        6
    284  Query_2244025     5I9U_A   38.112             286        156        6
    285  Query_2244025     8XPV_A   38.112             286        156        6
    286  Query_2244025     2QOI_A   36.789             299        172        7
    287  Query_2244025     5MO4_A   38.811             286        159        5
    288  Query_2244025     2GSF_A   36.392             316        178        8
    289  Query_2244025     3LCO_A   37.888             322        177        6
    290  Query_2244025     3FXX_A   36.392             316        178        8
    291  Query_2244025     2QO7_A   36.392             316        178        8
    292  Query_2244025     1OPK_A   38.811             286        159        5
    293  Query_2244025     7RUN_A   37.201             293        162        3
    294  Query_2244025     2QOL_A   36.789             299        172        7
    295  Query_2244025     1MQB_A   38.112             286        156        6
    296  Query_2244025     8FLN_A   38.321             274        151        5
    297  Query_2244025     5FM2_A   37.201             293        162        3
    298  Query_2244025     2QOF_A   37.895             285        161        6
    299  Query_2244025     6NJA_A   36.860             293        163        3
    300  Query_2244025     4OTF_A   38.321             274        151        5
    301  Query_2244025     7KJA_A   36.646             322        172        8
    302  Query_2244025     7KJC_A   36.646             322        172        8
    303  Query_2244025     4NWM_A   38.321             274        151        5
    304  Query_2244025     7KJB_A   36.646             322        172        8
    305  Query_2244025     8JOT_A   35.838             346        186        6
    306  Query_2244025     2FO0_A   38.811             286        159        5
    307  Query_2244025     6NZM_A   38.321             274        151        5
    308  Query_2244025     4XLI_A   39.576             283        155        6
    309  Query_2244025     4YHF_A   38.321             274        151        5
    310  Query_2244025     6W7O_A   38.321             274        151        5
    311  Query_2244025     5P9F_A   38.321             274        151        5
    312  Query_2244025     2QON_A   36.789             299        172        7
    313  Query_2244025     4OT5_A   37.956             274        152        5
    314  Query_2244025     3GEN_A   38.321             274        151        5
    315  Query_2244025     6BIK_A   38.321             274        151        5
    316  Query_2244025     5ZZ4_A   38.321             274        151        5
    317  Query_2244025     6TFP_A   38.321             274        151        5
    318  Query_2244025     6J6M_A   38.321             274        151        5
    319  Query_2244025     5FBN_C   38.321             274        151        5
    320  Query_2244025     5J87_A   38.321             274        151        5
    321  Query_2244025     3OCT_A   38.321             274        151        5
    322  Query_2244025     7KXQ_A   38.321             274        151        5
    323  Query_2244025     5XYZ_A   38.321             274        151        5
    324  Query_2244025     6S90_A   38.321             274        151        5
    325  Query_2244025     3P08_A   38.321             274        151        5
    326  Query_2244025     8YVV_A   38.321             274        151        5
    327  Query_2244025     4Z3V_A   38.321             274        151        5
    328  Query_2244025     4ZLY_A   38.321             274        151        5
    329  Query_2244025     3PIX_A   38.321             274        151        5
    330  Query_2244025     8FLL_A   38.321             274        151        5
    331  Query_2244025     3OCS_A   38.321             274        151        5
    332  Query_2244025     7KHK_A   37.171             304        174        6
    333  Query_2244025     6O8I_A   38.321             274        151        5
    334  Query_2244025     7KHJ_A   37.171             304        174        6
    335  Query_2244025     5BPY_A   38.321             274        151        5
    336  Query_2244025     6NFI_A   38.321             274        151        5
    337  Query_2244025     6VXQ_A   38.321             274        151        5
    338  Query_2244025     6AUB_A   38.321             274        151        5
    339  Query_2244025     4RX5_A   38.321             274        151        5
    340  Query_2244025     2XYN_A   38.869             283        157        5
    341  Query_2244025     3ZFX_A   36.054             294        174        5
    342  Query_2244025     6E4F_A   38.321             274        151        5
    343  Query_2244025     1OPL_A   38.811             286        159        5
    344  Query_2244025     8PQG_A   36.755             302        176        5
    345  Query_2244025     6NE7_A   36.519             293        164        3
    346  Query_2244025     6XE4_A   38.321             274        151        5
    347  Query_2244025     4CKI_A   36.519             293        164        3
    348  Query_2244025     9ZLJ_A   38.321             274        151        5
    349  Query_2244025     5MJA_A   35.374             294        176        5
    350  Query_2244025     6MNY_A   38.321             274        151        5
    351  Query_2244025     4Y95_A   38.686             274        150        5
    352  Query_2244025     6UMW_A   36.054             294        174        5
    353  Query_2244025     1K2P_A   38.519             270        148        5
    354  Query_2244025     9KS5_A   38.869             283        157        5
    355  Query_2244025     6GQK_A   36.755             302        176        5
    356  Query_2244025     6GQJ_A   36.755             302        176        5
    357  Query_2244025     8PQ9_A   36.755             302        176        5
    358  Query_2244025     6JQR_A   36.508             315        178        5
    359  Query_2244025     6A32_A   35.417             336        191        7
    360  Query_2244025     4XUF_A   38.754             289        155        5
    361  Query_2244025     8FD9_A   38.321             274        151        5
    362  Query_2244025     1RJB_A   36.508             315        178        5
    363  Query_2244025     8XB1_A   36.508             315        178        5
    364  Query_2244025     7KPL_A   36.491             285        167        5
    365  Query_2244025     5X02_A   36.508             315        178        5
    366  Query_2244025     6AUA_A   37.956             274        152        5
    367  Query_2244025     8GC8_A   37.956             274        152        5
    368  Query_2244025     8XRR_A   35.417             336        191        7
    369  Query_2244025     8PQH_A   37.500             296        161        5
    370  Query_2244025     9GZH_A   37.500             296        161        5
    371  Query_2244025     6JOI_A   35.417             336        191        7
    372  Query_2244025     5GRN_A   35.417             336        191        7
    373  Query_2244025     4P2K_A   39.114             271        144        6
    374  Query_2244025     3K54_A   37.956             274        152        5
    375  Query_2244025     6IL3_A   36.508             315        178        5
    376  Query_2244025     5EK7_A   38.545             275        148        6
    377  Query_2244025     8PQJ_A   37.500             296        161        5
    378  Query_2244025     8S9F_A   37.956             274        152        5
    379  Query_2244025     4XI2_A   38.321             274        151        5
    380  Query_2244025     5MJB_A   35.034             294        177        5
    381  Query_2244025     4EBV_A   37.809             283        163        6
    382  Query_2244025     7NX0_B   54.019             311        134        2
    383  Query_2244025     4TRL_A   38.745             271        145        6
    384  Query_2244025     3MIY_A   39.033             269        146        6
    385  Query_2244025     6FER_A   37.415             294        159        7
    386  Query_2244025     4Y93_A   38.686             274        150        5
    387  Query_2244025     8E4T_A   36.620             284        166        5
    388  Query_2244025     3QGW_A   39.033             269        146        6
    389  Query_2244025     3V5J_A   39.033             269        146        6
    390  Query_2244025     1SM2_A   39.033             269        146        6
    391  Query_2244025     4HCT_A   39.033             269        146        6
    392  Query_2244025     2XYU_A   35.664             286        168        6
    393  Query_2244025     1MP8_A   38.433             268        152        6
    394  Query_2244025     2WD1_A   37.594             266        150        6
    395  Query_2244025     2ETM_A   38.433             268        152        6
    396  Query_2244025     4GU9_A   38.433             268        152        6
    397  Query_2244025     6I8Z_A   38.433             268        152        6
    398  Query_2244025     2Y6M_A   35.664             286        168        6
    399  Query_2244025     3PXK_A   38.433             268        152        6
    400  Query_2244025     3BZ3_A   38.433             268        152        6
    401  Query_2244025     4R1V_A   37.594             266        150        6
    402  Query_2244025     9SDI_A   38.433             268        152        6
    403  Query_2244025     8AN8_A   37.594             266        150        6
    404  Query_2244025     7B3Q_A   37.594             266        150        6
    405  Query_2244025     3T9T_A   39.033             269        146        6
    406  Query_2244025   7PI4_DDD   38.433             268        152        6
    407  Query_2244025     3ZZW_A   34.737             285        174        2
    408  Query_2244025     6SD9_A   37.594             266        150        6
    409  Query_2244025     4KNB_A   37.594             266        150        6
    410  Query_2244025     2J0M_B   38.433             268        152        6
    411  Query_2244025     8S93_A   38.321             274        151        5
    412  Query_2244025     3I5N_A   37.594             266        150        6
    413  Query_2244025     3Q6U_A   37.594             266        150        6
    414  Query_2244025     3LQ8_A   37.594             266        150        6
    415  Query_2244025     3F66_A   37.594             266        150        6
    416  Query_2244025     2RFN_A   37.594             266        150        6
    417  Query_2244025     4GT4_A   34.495             287        176        2
    418  Query_2244025     2JKM_A   38.060             268        153        6
    419  Query_2244025     5UAB_A   37.594             266        150        6
    420  Query_2244025     2G15_A   37.594             266        150        6
    421  Query_2244025     4GG5_A   37.594             266        150        6
    422  Query_2244025     2WGJ_A   37.594             266        150        6
    423  Query_2244025     2R2P_A   36.140             285        166        6
    424  Query_2244025     4EEV_A   37.594             266        150        6
    425  Query_2244025     2JKK_A   38.060             268        153        6
    426  Query_2244025     3BYS_A   40.000             285        141        8
    427  Query_2244025     2OG8_A   41.026             273        131        8
    428  Query_2244025     2OFV_A   40.000             285        141        8
    429  Query_2244025     3VW8_A   37.594             266        150        6
    430  Query_2244025     2OF2_A   40.000             285        141        8
    431  Query_2244025     2PL0_A   40.000             285        141        8
    432  Query_2244025     8VI1_A   37.218             266        151        6
    433  Query_2244025     9SZJ_A   37.218             266        151        6
    434  Query_2244025     9C1R_A   37.218             266        151        6
    435  Query_2244025     5HLW_A   37.218             266        151        6
    436  Query_2244025     8AW1_A   37.218             266        151        6
    437  Query_2244025     4KIO_A   38.662             269        147        6
    438  Query_2244025     3MPM_A   39.858             281        139        8
    439  Query_2244025     2HEL_A   35.664             286        168        6
    440  Query_2244025     8AU5_A   37.218             266        151        6
    441  Query_2244025     6HH1_A   38.206             301        171        6
    442  Query_2244025     2DQ7_X   38.571             280        152        7
    443  Query_2244025     3Q6W_A   37.218             266        151        6
    444  Query_2244025     4IWD_A   37.218             266        151        6
    445  Query_2244025     8AU3_A   37.218             266        151        6
    446  Query_2244025     8ANS_A   37.218             266        151        6
    447  Query_2244025     6SDC_A   37.218             266        151        6
    448  Query_2244025     8GMB_A   38.321             274        151        5
    449  Query_2244025     3SXR_A   38.182             275        152        5
    450  Query_2244025     6I99_A   38.182             275        152        5
    451  Query_2244025     3BYO_A   39.649             285        142        8
    452  Query_2244025     3BYM_A   39.649             285        142        8
    453  Query_2244025     3KXZ_A   39.649             285        142        8
    454  Query_2244025     3ZFM_A   32.993             294        183        5
    455  Query_2244025     1QPC_A   39.649             285        142        8
    456  Query_2244025     2ZM1_A   39.649             285        142        8
    457  Query_2244025     2OFU_A   39.649             285        142        8
    458  Query_2244025     5XY1_A   38.433             268        146        6
    459  Query_2244025     3CE3_A   36.466             266        153        6
    460  Query_2244025     6PDJ_A   39.649             285        142        8
    461  Query_2244025     3A4O_X   38.235             272        149        6
    462  Query_2244025     3KMM_A   39.649             285        142        8
    463  Query_2244025     3DKC_A   36.466             266        153        6
    464  Query_2244025     1R0P_A   36.466             266        153        6
    465  Query_2244025     3QTI_A   36.466             266        153        6
    466  Query_2244025     1QPD_A   39.649             285        142        8
    467  Query_2244025     3A4P_A   36.466             266        153        6
    468  Query_2244025     7EEF_A   35.664             286        168        6
    469  Query_2244025     2ZV7_A   38.060             268        147        6
    470  Query_2244025     3CC6_A   36.704             267        156        5
    471  Query_2244025     5TO8_A   36.704             267        156        5
    472  Query_2244025     3ET7_A   36.704             267        156        5
    473  Query_2244025     1JPA_A   32.993             294        183        5
    474  Query_2244025     4H1J_A   36.704             267        156        5
    475  Query_2244025     7EEC_A   35.664             286        168        6
    476  Query_2244025     5HOA_A   36.090             266        154        6
    477  Query_2244025     1FVR_A   36.237             287        163        6
    478  Query_2244025     1T46_A   36.184             304        177        6
    479  Query_2244025     4U0I_A   36.184             304        177        6
    480  Query_2244025     2OO8_X   35.714             294        169        6
    481  Query_2244025     3C1X_A   36.466             266        153        6
    482  Query_2244025     6MOB_A   36.721             305        174        7
    483  Query_2244025     2J0L_A   37.687             268        154        6
    484  Query_2244025     7ZW8_A   36.721             305        174        7
    485  Query_2244025     7EED_A   35.664             286        168        6
    486  Query_2244025     2REI_A   35.664             286        168        6
    487  Query_2244025     1T45_A   35.780             327        188        8
    488  Query_2244025     3G0E_A   35.780             327        188        8
    489  Query_2244025     5HOR_A   36.090             266        154        6
    490  Query_2244025     3PLS_A   37.175             269        153        6
    491  Query_2244025     2HEN_A   32.653             294        184        5
    492  Query_2244025     6CZ3_A   39.427             279        150        6
    493  Query_2244025     7AYM_A   35.548             301        160        7
    494  Query_2244025     2WQB_A   35.889             287        164        6
    495  Query_2244025     8X2A_A   37.455             275        154        5
    496  Query_2244025     3DKG_A   36.090             266        154        6
    497  Query_2244025     4X3J_A   35.889             287        164        6
    498  Query_2244025     3CJF_A   36.170             282        169        5
    499  Query_2244025     6ITV_A   35.780             327        188        8
    500  Query_2244025     1PKG_A   36.458             288        167        5
    501  Query_2244025     5DA3_A   39.273             275        148        6
    502  Query_2244025     5D7V_A   39.273             275        148        6
    503  Query_2244025     5H2U_A   39.273             275        148        6
    504  Query_2244025     4AW5_A   34.483             290        176        4
    505  Query_2244025     2HK5_A   38.545             275        149        7
    506  Query_2244025     5ZJ6_A   38.545             275        149        7
    507  Query_2244025     3G0F_A   35.474             327        189        8
    508  Query_2244025     3CJG_A   36.879             282        167        6
    509  Query_2244025     3WZD_A   36.014             286        168        5
    510  Query_2244025     2YN8_A   34.737             285        172        4
    511  Query_2244025     6TY3_A   38.060             268        153        6
    512  Query_2244025     2J0K_A   38.060             268        153        6
    513  Query_2244025     3ZEW_A   34.386             285        173        4
    514  Query_2244025     2J0J_A   38.060             268        153        6
    515  Query_2244025     6FNI_A   34.737             285        172        4
    516  Query_2244025     3VNT_A   37.063             286        165        7
    517  Query_2244025     7FEH_A   36.271             295        156        8
    518  Query_2244025     4MXY_A   38.434             281        151        8
    519  Query_2244025     6CZ2_A   39.068             279        151        6
    520  Query_2244025     3GEQ_A   38.214             280        153        7
    521  Query_2244025     5SAU_A   36.271             295        156        8
    522  Query_2244025     2XIR_A   36.014             286        168        5
    523  Query_2244025     3EWH_A   36.014             286        168        5
    524  Query_2244025     2VWU_A   34.386             285        173        4
    525  Query_2244025     3U6J_A   36.014             286        168        5
    526  Query_2244025     6GQO_A   36.014             286        168        5
    527  Query_2244025     3D7T_A   38.095             273        145        8
    528  Query_2244025     3ZOS_A   36.000             300        156        8
    529  Query_2244025     2BDF_A   38.434             281        151        8
    530  Query_2244025     4AGC_A   36.014             286        168        5
    531  Query_2244025     5BVK_A   36.000             300        156        8
    532  Query_2244025     8JF3_A   38.434             281        151        8
    533  Query_2244025     7NG7_A   37.857             280        154        7
    534  Query_2244025     3G6H_A   37.857             280        154        7
    535  Query_2244025     8HAQ_A   38.434             281        151        8
    536  Query_2244025     5FDP_A   36.000             300        156        8
    537  Query_2244025     4MXO_A   37.857             280        154        7
    538  Query_2244025     6E6E_A   38.571             280        150        8
    539  Query_2244025     7OTE_A   37.857             280        154        7
    540  Query_2244025     3D7U_A   38.095             273        145        8
    541  Query_2244025     6BRJ_A   36.000             300        156        8
    542  Query_2244025     1BYG_A   38.095             273        145        8
    543  Query_2244025     4MXX_A   37.857             280        154        7
    544  Query_2244025     7MO7_B   37.594             266        150        6
    545  Query_2244025     6Y23_A   36.000             300        156        8
    546  Query_2244025     2OIQ_A   37.857             280        154        7
    547  Query_2244025     3D7U_B   37.857             280        154        7
    548  Query_2244025     3OEZ_A   37.857             280        154        7
    549  Query_2244025     2QI8_A   37.857             280        154        7
    550  Query_2244025     3SVV_A   37.857             280        154        7
    551  Query_2244025     3U4W_A   38.043             276        151        7
    552  Query_2244025     9NS1_A   38.078             281        152        8
    553  Query_2244025     3ZFY_A   35.088             285        171        5
    554  Query_2244025     1VR2_A   35.664             286        169        5
    555  Query_2244025     1YOL_A   38.078             281        152        8
    556  Query_2244025     1QCF_A   38.686             274        148        7
    557  Query_2244025     9BYJ_A   38.686             274        148        7
    558  Query_2244025     4MCV_A   37.857             280        154        7
    559  Query_2244025     3C7Q_A   35.915             284        169        6
    560  Query_2244025     4LGH_A   37.857             280        154        7
    561  Query_2244025     2HWO_A   37.857             280        154        7
    562  Query_2244025     5T0P_A   37.857             280        154        7
    563  Query_2244025     9NS0_A   38.078             281        152        8
    564  Query_2244025     5SWH_A   37.500             280        155        7
    565  Query_2244025     3DQW_A   37.500             280        155        7
    566  Query_2244025     7ZVS_A   36.770             291        162        8
    567  Query_2244025     9BT8_C   37.993             279        153        7
    568  Query_2244025     1YOJ_A   37.722             281        153        8
    569  Query_2244025     9IRL_A   37.993             279        153        7
    570  Query_2244025     1FMK_A   37.993             279        153        7
    571  Query_2244025     1Y57_A   37.993             279        153        7
    572  Query_2244025     8JN8_A   37.993             279        153        7
    573  Query_2244025     2P2I_A   35.315             286        170        5
    574  Query_2244025     2H8H_A   37.993             279        153        7
    575  Query_2244025     2OH4_A   35.439             285        170        5
    576  Query_2244025     4K11_A   37.993             279        153        7
    577  Query_2244025     1YWN_A   35.315             286        170        5
    578  Query_2244025     1YI6_A   38.214             280        151        8
    579  Query_2244025     2P2H_A   35.315             286        170        5
    580  Query_2244025     1KSW_A   37.993             279        153        7
    581  Query_2244025     1K9A_A   38.095             273        145        8
    582  Query_2244025     8XN8_A   37.634             279        154        7
    583  Query_2244025     6F3F_A   37.634             279        154        7
    584  Query_2244025     2PTK_A   36.972             284        149        7
    585  Query_2244025     4LGG_A   37.729             273        150        7
    586  Query_2244025     1AD5_A   37.591             274        141        7
    587  Query_2244025     3KUL_A   32.095             296        181        6
    588  Query_2244025     6TUA_A   32.042             284        184        4
    589  Query_2244025     1U59_A   36.842             266        154        8
    590  Query_2244025     3KUL_B   31.757             296        182        6
    591  Query_2244025     7UY0_A   37.500             280        155        7
    592  Query_2244025     7UY0_B   37.500             280        155        7
    593  Query_2244025     2OZO_A   35.495             293        167        9
    594  Query_2244025     4K2R_A   35.495             293        167        9
    595  Query_2244025     7KP6_A   35.252             278        154       10
    596  Query_2244025     8FE9_A   35.252             278        154       10
    597  Query_2244025     4DFL_A   35.036             274        161        8
    598  Query_2244025     4RX7_A   35.036             274        161        8
    599  Query_2244025     4HZR_A   35.252             278        154       10
    600  Query_2244025     4RX9_A   35.036             274        161        8
    601  Query_2244025     4PV0_A   35.036             274        161        8
    602  Query_2244025     3EMG_A   33.798             287        171        8
    603  Query_2244025     6VQM_A   35.636             275        151       10
    604  Query_2244025     6VOV_A   35.036             274        161        8
    605  Query_2244025     3EQP_A   35.636             275        151       10
    606  Query_2244025     1U46_A   35.636             275        151       10
    607  Query_2244025     5ZXB_A   35.636             275        151       10
    608  Query_2244025     4F4P_A   35.036             274        161        8
    609  Query_2244025     4ID7_A   35.636             275        151       10
    610  Query_2244025     8X5K_A   35.036             274        161        8
    611  Query_2244025     4PX6_A   35.036             274        161        8
    612  Query_2244025     5TR6_A   35.036             274        161        8
    613  Query_2244025     5Y5T_A   35.036             274        161        8
    614  Query_2244025     4RSS_A   35.036             274        161        8
    615  Query_2244025     3SRV_B   35.036             274        161        8
    616  Query_2244025     1XBA_A   35.036             274        161        8
    617  Query_2244025     4YJO_A   35.036             274        161        8
    618  Query_2244025     3TUB_A   35.036             274        161        8
    619  Query_2244025     3TUC_A   35.036             274        161        8
    620  Query_2244025     4HZS_A   35.636             275        151       10
    621  Query_2244025     7JXH_A   34.909             275        162        7
    622  Query_2244025     3PP0_A   33.916             286        172        7
    623  Query_2244025     7PCD_A   33.916             286        172        7
    624  Query_2244025     3SRV_A   33.449             287        172        8
    625  Query_2244025     1U54_A   35.273             275        152       10
    626  Query_2244025     4EWH_A   35.273             275        152       10
    627  Query_2244025     8HV4_A   33.217             286        171        8
    628  Query_2244025     9S3X_A   33.217             286        171        8
    629  Query_2244025     6LUB_A   33.217             286        171        8
    630  Query_2244025     6HM6_A   34.672             274        162        8
    631  Query_2244025     9D3V_A   33.217             286        171        8
    632  Query_2244025     5XGN_A   32.867             286        172        8
    633  Query_2244025     8WD4_A   33.217             286        171        8
    634  Query_2244025     8H7X_A   32.867             286        172        8
    635  Query_2244025     2R4B_A   31.293             294        187        6
    636  Query_2244025     5GNK_A   32.867             286        172        8
    637  Query_2244025     9XU9_A   32.867             286        172        8
    638  Query_2244025     5GMP_A   32.867             286        172        8
    639  Query_2244025     8HY7_A   33.217             286        171        8
    640  Query_2244025     4RJ4_A   33.217             286        171        8
    641  Query_2244025     4G5P_A   32.867             286        172        8
    642  Query_2244025     9JQ1_A   32.867             286        172        8
    643  Query_2244025     5CNN_A   31.818             286        178        7
    644  Query_2244025     6S9B_A   33.217             286        171        8
    645  Query_2244025     4I24_A   32.867             286        172        8
    646  Query_2244025     3IKA_A   32.867             286        172        8
    647  Query_2244025     5Y9T_A   32.867             286        172        8
    648  Query_2244025     5ZWJ_A   32.867             286        172        8
    649  Query_2244025     6S9C_A   33.217             286        171        8
    650  Query_2244025     5FEE_A   32.867             286        172        8
    651  Query_2244025     2JIU_A   32.867             286        172        8
    652  Query_2244025     2JIT_A   32.867             286        172        8
    653  Query_2244025     4WKQ_A   32.867             286        172        8
    654  Query_2244025     2J5E_A   32.867             286        172        8
    655  Query_2244025     4ZSE_A   32.867             286        172        8
    656  Query_2244025     6TFU_A   32.867             286        172        8
    657  Query_2244025     5J9Z_A   32.867             286        172        8
    658  Query_2244025     5J9Y_A   32.867             286        172        8
    659  Query_2244025     3BBT_B   31.399             293        186        6
    660  Query_2244025     6V5N_A   32.867             286        172        8
    661  Query_2244025     8RRQ_A   32.867             286        175        7
    662  Query_2244025     4YJQ_A   32.867             286        175        7
    663  Query_2244025     6P1D_A   32.867             286        172        8
    664  Query_2244025     4ZJV_A   32.867             286        172        8
    665  Query_2244025     4TKS_A   32.867             286        172        8
    666  Query_2244025     5CAV_A   32.867             286        172        8
    667  Query_2244025     3VJO_A   32.867             286        172        8
    668  Query_2244025     7AEM_A   32.867             286        172        8
    669  Query_2244025     8HV2_A   32.867             286        172        8
    670  Query_2244025     2RFD_A   32.313             294        179        8
    671  Query_2244025     4LI5_A   32.867             286        172        8
    672  Query_2244025     1M14_A   32.867             286        172        8
    673  Query_2244025     4G5J_A   32.867             286        172        8
    674  Query_2244025     5FED_A   32.867             286        172        8
    675  Query_2244025     4I23_A   32.867             286        172        8
    676  Query_2244025     2GS2_A   32.867             286        172        8
    677  Query_2244025     2ITW_A   32.867             286        172        8
    678  Query_2244025     9FZR_A   32.867             286        172        8
    679  Query_2244025     4I21_A   32.867             286        172        8
    680  Query_2244025     4LL0_A   32.867             286        172        8
    681  Query_2244025     9KLW_A   32.867             286        172        8
    682  Query_2244025     5C26_A   32.867             286        175        7
    683  Query_2244025     6JZ0_A   32.867             286        172        8
    684  Query_2244025     3HNG_A   42.683             164         90        2
    685  Query_2244025     7UKV_A   32.867             286        172        8
    686  Query_2244025     4JQ7_A   32.867             286        172        8
    687  Query_2244025     8A27_A   32.867             286        172        8
    688  Query_2244025     9H42_A   32.867             286        172        8
    689  Query_2244025     2RGP_A   32.867             286        172        8
    690  Query_2244025     9N6G_A   32.867             286        172        8
    691  Query_2244025     4FL2_A   33.798             287        171        8
    692  Query_2244025     8PO3_A   32.867             286        172        8
    693  Query_2244025     3LZB_A   32.867             286        172        8
    694  Query_2244025     8PO4_A   32.867             286        172        8
    695  Query_2244025     9BY4_A   32.867             286        172        8
    696  Query_2244025     8KFQ_A   32.867             286        172        8
    697  Query_2244025     7OXB_A   32.867             286        172        8
    698  Query_2244025     4RIW_B   32.867             286        172        8
    699  Query_2244025     4FL3_A   33.798             287        171        8
    700  Query_2244025   9QXN_AAA   32.867             286        172        8
    701  Query_2244025     3W2O_A   32.867             286        172        8
    702  Query_2244025     5Y25_A   32.867             286        172        8
    703  Query_2244025     4I1Z_A   32.867             286        172        8
    704  Query_2244025     1XKK_A   32.867             286        172        8
    705  Query_2244025     2GS7_A   32.867             286        172        8
    706  Query_2244025     3UG1_A   32.517             286        173        8
    707  Query_2244025     8VB5_A   33.448             290        172        8
    708  Query_2244025     5XDL_A   32.867             286        172        8
    709  Query_2244025     8D73_A   32.867             286        172        8
    710  Query_2244025     6JWL_A   32.867             286        172        8
    711  Query_2244025     4HJO_A   32.867             286        172        8
    712  Query_2244025     4LQM_A   32.867             286        172        8
    713  Query_2244025     2EB3_A   32.867             286        172        8
    714  Query_2244025     2ITT_A   32.867             286        172        8
    715  Query_2244025     4R3P_A   32.867             286        172        8
    716  Query_2244025     8U8X_A   32.441             299        181        8
    717  Query_2244025     7K1H_A   32.867             286        172        8
    718  Query_2244025     4I20_A   32.867             286        172        8
    719  Query_2244025     2EB2_A   32.517             286        173        8
    720  Query_2244025     8A2B_A   32.867             286        172        8
    721  Query_2244025     2ITN_A   32.517             286        173        8
    722  Query_2244025     4RT7_A   45.029             171         87        3
    724  Query_2244025     9QBG_A   30.829             386        232       11
    725  Query_2244025     9QBF_A   30.829             386        232       11
    726  Query_2244025     7MN5_B   30.075             399        244       11
    727  Query_2244025     7MN6_B   30.075             399        244       11
    728  Query_2244025     3GOP_A   32.517             286        173        8
    729  Query_2244025     9U8C_A   31.104             299        186        8
    730  Query_2244025     6JRJ_A   33.217             286        171        8
    731  Query_2244025     8DSW_A   32.414             290        172        9
    732  Query_2244025     9DF2_A   32.526             289        172        9
    733  Query_2244025     6S89_A   33.217             286        171        8
    734  Query_2244025     4LRM_A   32.526             289        172        9
    735  Query_2244025     8PO0_A   32.526             289        172        9
    736  Query_2244025     9DF3_A   32.526             289        172        9
    737  Query_2244025     8PO1_A   32.526             289        172        9
    738  Query_2244025     7LGS_A   32.526             289        172        9
    739  Query_2244025     9FQP_A   32.526             289        172        9
    740  Query_2244025     7TVD_A   32.517             286        170        9
    741  Query_2244025     9P9U_A   32.867             286        172        8
    742  Query_2244025     9P9U_A   32.867             286        172        8
    743  Query_2244025     6JRK_A   33.217             286        171        8
    744  Query_2244025     3VHE_A   41.143             175         99        2
    745  Query_2244025     3VID_A   41.143             175         99        2
    746  Query_2244025     3VHK_A   41.143             175         99        2
    747  Query_2244025     1Y6A_A   41.143             175         99        2
    748  Query_2244025     6SEQ_A   31.597             288        175        8
    749  Query_2244025     7SYD_A   32.867             286        172        8
    750  Query_2244025     7SZ0_A   32.867             286        172        8
    751  Query_2244025     5WNO_A   30.000             270        177        4
    752  Query_2244025     8DFQ_A   45.098             153         80        2
    753  Query_2244025     8DFM_A   45.098             153         80        2
    754  Query_2244025     8DFP_A   45.098             153         80        2
    755  Query_2244025     5TQ5_A   29.000             300        184        9
    756  Query_2244025     3UGC_A   28.620             297        183        9
    757  Query_2244025     4BBE_A   28.716             296        182        9
    758  Query_2244025     6TPD_A   28.328             293        181        9
    759  Query_2244025     8G6Z_A   28.667             300        185        9
    760  Query_2244025     7LL5_A   28.716             296        182        9
    761  Query_2244025     4RIY_A   31.769             277        168        6
    762  Query_2244025     7RN6_A   28.716             296        182        9
    763  Query_2244025     7LL4_A   28.716             296        182        9
    764  Query_2244025     7TEU_A   28.378             296        183        9
    765  Query_2244025     5USY_A   28.716             296        182        9
    766  Query_2244025     6VGL_A   28.716             296        182        9
    767  Query_2244025     4E6D_A   29.054             296        181        9
    768  Query_2244025     3KRR_A   28.956             297        182        9
    769  Query_2244025     4ZIM_A   28.667             300        185        9
    770  Query_2244025     4YTC_A   28.378             296        183        9
    771  Query_2244025     5TQ4_A   28.667             300        185        9
    772  Query_2244025     5HEZ_A   28.716             296        182        9
    773  Query_2244025     8G8O_A   28.667             300        185        9
    774  Query_2244025     4GL9_A   29.054             296        181        9
    775  Query_2244025     3IO7_A   28.378             296        183        9
    776  Query_2244025     3TJC_A   28.667             300        185        9
    777  Query_2244025     4E4M_A   28.716             296        182        9
    778  Query_2244025     5TQ3_A   28.716             296        182        9
    779  Query_2244025     7Q7I_A   28.571             308        186       10
    780  Query_2244025     3JY9_A   28.378             296        183        9
    781  Query_2244025     5TQ6_A   28.716             296        182        9
    782  Query_2244025     2B7A_A   28.716             296        182        9
    783  Query_2244025     3Q32_A   28.523             298        184        9
    784  Query_2244025     4HGE_A   28.716             296        182        9
    785  Query_2244025     6WTN_A   28.716             296        182        9
    786  Query_2244025     7UYW_A   28.669             293        180        9
    787  Query_2244025     4D0W_A   28.716             296        182        9
    788  Query_2244025     5WEV_A   28.716             296        182        9
    789  Query_2244025     4RIX_A   31.408             277        169        6
    790  Query_2244025     3E62_A   28.716             296        182        9
    791  Query_2244025     3KEX_A   31.408             277        169        6
    792  Query_2244025     4AQC_A   28.716             296        182        9
    793  Query_2244025     8BM2_A   28.716             296        182        9
    794  Query_2244025     6OP9_A   31.408             277        169        6
    795  Query_2244025     4RIW_A   31.408             277        169        6
    796  Query_2244025     4UYA_A   30.721             319        180       10
    797  Query_2244025     8BX6_A   28.716             296        182        9
    798  Query_2244025     2W1I_A   28.617             311        190       10
    799  Query_2244025     3LMG_A   31.408             277        169        6
    800  Query_2244025     3RVG_A   28.716             296        182        9
    801  Query_2244025     5KHW_A   29.283             321        200        7
    802  Query_2244025     6AAJ_A   28.378             296        183        9
    803  Query_2244025     3ZMM_A   28.378             296        183        9
    804  Query_2244025     2XA4_A   28.378             296        183        9
    805  Query_2244025     6C7Y_A   30.796             289        173        7
    806  Query_2244025     5F1Z_A   31.000             300        168        8
    807  Query_2244025     3NYX_A   31.000             300        168        8
    808  Query_2244025     4GVJ_A   31.419             296        164        8
    809  Query_2244025     3NZ0_A   31.419             296        164        8
    810  Query_2244025     5CEN_A   31.068             309        181       10
    811  Query_2244025     8DEG_A   31.068             309        181       10
    812  Query_2244025     4E1Z_A   30.952             294        162        8
    813  Query_2244025     7UYR_A   31.250             288        155        9
    814  Query_2244025     4GIH_A   31.081             296        165        8
    815  Query_2244025     6AAM_A   31.119             286        158        8
    816  Query_2244025     4E20_A   31.010             287        157        8
    817  Query_2244025     6N7A_A   30.450             289        174        7
    818  Query_2244025     6GGH_A   30.450             289        174        7
    819  Query_2244025     6TPE_A   30.450             289        174        7
    820  Query_2244025     3EYG_A   30.450             289        174        7
    821  Query_2244025     4E4L_A   30.450             289        174        7
    822  Query_2244025     4RIO_A   31.034             290        158        9
    823  Query_2244025     6ELR_A   30.450             289        174        7
    824  Query_2244025     4HVD_A   31.034             290        158        9
    825  Query_2244025     7T6F_A   29.154             319        199        7
    827  Query_2244025     4OLI_A   30.000             330        190       10
    828  Query_2244025     5TOZ_A   31.034             290        158        9
    829  Query_2244025     3PJC_A   31.034             290        158        9
    830  Query_2244025   7Q6H_AAA   31.034             290        158        9
    831  Query_2244025     7MN5_A   28.571             364        221       10
    832  Query_2244025     3LXK_A   31.034             290        158        9
    833  Query_2244025     4PY1_A   31.119             286        158        8
    834  Query_2244025     3LXN_A   31.119             286        158        8
    835  Query_2244025     5LWM_A   30.333             300        167        9
    836  Query_2244025     4QPS_A   30.690             290        159        9
    837  Query_2244025     3ZC6_A   30.822             292        156       10
    838  Query_2244025     5W86_A   30.822             292        156       10
    839  Query_2244025     7UYV_A   30.822             292        156       10
    840  Query_2244025     7C3N_A   30.822             292        156       10
    841  Query_2244025     6HZV_A   30.822             292        156       10
    842  Query_2244025     8GW3_A   30.249             281        173        8
    843  Query_2244025     3DTC_A   29.825             285        174        8
    844  Query_2244025     4YHT_A   29.123             285        172        9
    845  Query_2244025     4FK3_A   28.571             294        180        9
    846  Query_2244025     8C7Y_A   29.066             289        175        9
    847  Query_2244025     1YVJ_A   30.345             290        160       10
    848  Query_2244025     4Z16_A   30.345             290        160       10
    849  Query_2244025     4UY9_A   29.825             285        174        8
    850  Query_2244025     4V0G_B   30.479             292        157       10
    851  Query_2244025     6V34_A   28.231             294        181        9
    852  Query_2244025     4WO5_A   29.293             297        178       10
    853  Query_2244025     4CQE_A   28.276             290        178        9
    854  Query_2244025     4XV1_A   28.276             290        178        9
    855  Query_2244025     4V0G_A   30.479             292        157       10
    856  Query_2244025     5JRQ_A   28.772             285        173        9
    857  Query_2244025     6P3D_A   28.276             290        178        9
    858  Query_2244025     3OG7_A   28.772             285        173        9
    859  Query_2244025     4RZV_A   29.066             289        175        9
    860  Query_2244025     5CSW_A   29.066             289        175        9
    861  Query_2244025     6XFP_A   29.066             289        175        9
    862  Query_2244025     7P3V_A   28.772             285        173        9
    863  Query_2244025     6U2H_C   28.571             294        180        9
    864  Query_2244025     4JVG_A   29.066             289        175        9
    865  Query_2244025     5GJD_A   30.435             276        169        8
    866  Query_2244025     4GS6_A   30.435             276        169        8
    867  Query_2244025     4XV9_A   29.066             289        175        9
    868  Query_2244025     4L52_A   30.435             276        169        8
    869  Query_2244025     2EVA_A   30.435             276        169        8
    870  Query_2244025     4O91_A   30.435             276        169        8
    871  Query_2244025     3C4C_A   29.066             289        175        9
    872  Query_2244025     9FPD_A   30.108             279        172        8
    873  Query_2244025     8F7O_A   28.720             289        176        9
    874  Query_2244025     3PPZ_A   28.904             301        187       10
    875  Query_2244025     5HI2_A   29.167             288        171        9
    876  Query_2244025     5ITA_A   28.276             290        178        9
    877  Query_2244025     3P86_A   28.571             301        188       10
    878  Query_2244025     5X5O_A   27.597             308        183       11
    879  Query_2244025     5HES_A   27.852             298        175       11
    880  Query_2244025    9RPV_N1   27.458             295        180        9
    881  Query_2244025     4YZM_A   27.055             292        181       13
    882  Query_2244025     8C0A_A   23.944             284        193        7
    883  Query_2244025     6G3C_A   24.113             282        191        7
    884  Query_2244025     6D2I_A   24.113             282        191        7
    885  Query_2244025     5WIJ_A   23.944             284        193        7
    886  Query_2244025     5I4N_A   23.944             284        193        7
    887  Query_2244025     4FVP_A   24.113             282        191        7
    888  Query_2244025     8B8N_A   23.944             284        193        7
    889  Query_2244025   8ATB_AAA   27.305             282        174        7
    890  Query_2244025     8C08_A   24.199             281        190        7
    891  Query_2244025   8ATL_AAA   27.305             282        174        7
    892  Query_2244025     4FVR_A   23.944             284        193        7
    893  Query_2244025     5NXD_A   26.316             285        175        7
    894  Query_2244025     7F7W_A   23.944             284        193        7
    895  Query_2244025     4TPT_A   26.316             285        175        7
    896  Query_2244025     8EX2_A   23.592             284        194        7
    897  Query_2244025     8C09_A   23.944             284        193        7
    898  Query_2244025     4F0F_A   26.370             292        183       13
    899  Query_2244025   8ATL_BBB   27.305             282        174        7
    900  Query_2244025     9ND3_A   23.944             284        193        7
    901  Query_2244025     9ND5_A   23.944             284        193        7
    902  Query_2244025     4F1O_A   26.370             292        183       13
    903  Query_2244025     9GB9_A   29.577             213        127        6
    904  Query_2244025     4F1M_A   27.551             294        177       15
    905  Query_2244025     9F32_A   26.182             275        175        8
    906  Query_2244025     8P5G_A   26.182             275        175        8
    907  Query_2244025     6MNH_A   26.182             275        175        8
    908  Query_2244025     4WNO_A   26.182             275        175        8
    909  Query_2244025     6QAS_A   26.182             275        175        8
    910  Query_2244025     8SV9_A   26.182             275        175        8
    911  Query_2244025     4L00_A   25.676             296        192       11
    912  Query_2244025     5EBZ_A   28.571             217        131        7
    913  Query_2244025     6EG9_A   33.010             206        120        6
    914  Query_2244025     4L01_A   25.676             296        192       11
    915  Query_2244025     6THW_A   33.010             206        120        6
    916  Query_2244025     8P5H_A   26.182             275        175        8
    917  Query_2244025     6F3E_A   33.010             206        120        6
    918  Query_2244025     2NRY_A   33.010             206        120        6
    919  Query_2244025     3A7F_A   26.786             280        180        9
    920  Query_2244025     7B30_A   26.882             279        179        9
    921  Query_2244025     6O8U_A   33.010             206        120        6
    922  Query_2244025     5UIS_A   33.010             206        120        6
    923  Query_2244025     7QG3_A   33.010             206        120        6
    924  Query_2244025     4QML_A   26.690             281        181        9
    925  Query_2244025     6MOM_A   33.010             206        120        6
    926  Query_2244025     6THX_A   33.010             206        120        6
    927  Query_2244025     5W84_A   33.010             206        120        6
    928  Query_2244025     4RMZ_A   33.010             206        120        6
    929  Query_2244025     6LXY_A   33.010             206        120        6
    930  Query_2244025     4U8Z_A   26.786             280        180        9
    931  Query_2244025     4W8E_A   26.786             280        180        9
    932  Query_2244025     9NA2_A   33.010             206        120        6
    933  Query_2244025     4Y73_A   33.010             206        120        6
    934  Query_2244025     6O94_A   33.010             206        120        6
    935  Query_2244025     5K72_A   33.010             206        120        6
    936  Query_2244025     9PSU_A   33.010             206        120        6
    937  Query_2244025     7C2V_A   33.010             206        120        6
    938  Query_2244025     2NRU_A   33.010             206        120        6
    939  Query_2244025     2OIB_A   33.010             206        120        6
    940  Query_2244025   8BR5_AAA   33.010             206        120        6
    941  Query_2244025     6N8G_A   33.010             206        120        6
    942  Query_2244025     5UIQ_A   33.010             206        120        6
    943  Query_2244025     5UIT_A   33.010             206        120        6
    944  Query_2244025     6F3D_A   33.010             206        120        6
    945  Query_2244025     6F3G_A   33.010             206        120        6
    946  Query_2244025     7C2W_A   33.010             206        120        6
    947  Query_2244025     6F3I_A   33.010             206        120        6
    948  Query_2244025     8V1O_A   33.010             206        120        6
    949  Query_2244025     8SCV_A   31.163             215        112        6
    950  Query_2244025     6CTH_A   31.696             224        133        8
    951  Query_2244025     4U97_A   32.524             206        121        6
    952  Query_2244025     6EGD_A   32.524             206        121        6
    953  Query_2244025     8DKS_A   33.010             206        120        6
    954  Query_2244025     8WTF_A   32.524             206        121        6
    826  Query_2244025     7T6F_A   26.174             298        196       11
    955  Query_2244025     1U5Q_A   26.246             301        175       10
    956  Query_2244025     7Z4V_A   27.622             286        167       10
    957  Query_2244025     2GCD_A   26.573             286        170        9
    958  Query_2244025     3S95_A   26.882             279        166        9
    959  Query_2244025     3CKX_A   26.740             273        175        9
    960  Query_2244025     3ZHP_C   26.966             267        170        9
    961  Query_2244025     3CKW_A   26.740             273        175        9
    962  Query_2244025     4O27_B   26.966             267        170        9
    963  Query_2244025     9V70_A   28.986             207        123        7
    964  Query_2244025     2XIK_A   27.622             286        167       10
    965  Query_2244025     6C4D_A   25.794             252        156       10
    966  Query_2244025     9LBG_A   25.253             297        193       11
    967  Query_2244025     9V71_A   28.986             207        123        7
    968  Query_2244025     6GR8_A   27.273             264        169        8
    969  Query_2244025     6C3E_A   25.794             252        156       10
    970  Query_2244025     9HY8_A   25.794             252        156       10
    971  Query_2244025     7FCZ_A   25.794             252        156       10
    972  Query_2244025     5XD6_A   25.352             284        179        9
    973  Query_2244025     6NYH_A   25.794             252        156       10
    974  Query_2244025     2O8Y_A   30.841             214        112        6
    975  Query_2244025     5HVJ_A   26.523             279        167        9
    976  Query_2244025     5HX6_A   25.794             252        156       10
    977  Query_2244025     5HVK_A   26.855             283        161       10
    978  Query_2244025     4NZW_B   26.923             286        169        9
    979  Query_2244025     6NW2_A   25.794             252        156       10
    980  Query_2244025     9WYR_A   28.502             207        124        7
    981  Query_2244025     9GTG_A   25.794             252        156       10
    982  Query_2244025     9MZY_A   25.820             244        152        9
    983  Query_2244025     9MZZ_A   25.820             244        152        9
    984  Query_2244025     9D51_A   25.283             265        174       10
    985  Query_2244025     9MZX_A   25.820             244        152        9
    986  Query_2244025     6VPJ_A   27.273             275        155        9
    987  Query_2244025     6QAT_A   26.415             265        168       10
    988  Query_2244025     9LBF_A   24.916             297        194       11
    989  Query_2244025     4ITH_A   25.820             244        152        9
    990  Query_2244025     2WTW_A   27.273             275        155        9
    991  Query_2244025     9M41_A   24.916             297        194       11
    992  Query_2244025     2C6E_A   26.370             292        170        9
    993  Query_2244025     6BDN_A   26.159             302        182       11
    994  Query_2244025     4J8M_A   27.273             275        155        9
    995  Query_2244025     4ZJI_A   25.379             264        175        8
    996  Query_2244025     2BMC_A   27.273             275        155        9
    997  Query_2244025     3NRM_A   27.273             275        155        9
    998  Query_2244025     3W10_A   27.273             275        155        9
    999  Query_2244025     3R21_A   27.273             275        155        9
    1000 Query_2244025     3H0Y_A   27.273             275        155        9
    1001 Query_2244025     6VPI_A   26.909             275        156        9
    1002 Query_2244025     2J4Z_A   27.273             275        155        9
    1003 Query_2244025     4ZLO_A   25.379             264        175        8
    1004 Query_2244025     3FDN_A   27.273             275        155        9
    1005 Query_2244025     5OBJ_A   27.273             275        155        9
    1006 Query_2244025     5EW9_A   27.273             275        155        9
    1007 Query_2244025     4NEU_A   25.820             244        152        9
    1008 Query_2244025     2J50_A   27.273             275        155        9
    1009 Query_2244025     3UNZ_A   27.273             275        155        9
    1010 Query_2244025     5DN3_A   27.273             275        155        9
    1011 Query_2244025     1MUO_A   27.273             275        155        9
    1012 Query_2244025     3COH_A   27.273             275        155        9
    1013 Query_2244025     4C3P_A   27.273             275        155        9
    1014 Query_2244025     8C1M_A   27.273             275        155        9
    1015 Query_2244025     6C83_A   27.273             275        155        9
    1016 Query_2244025     4BN1_A   26.909             275        156        9
    1017 Query_2244025     1MQ4_A   27.273             275        155        9
    1018 Query_2244025     2DWB_A   27.273             275        155        9
    1019 Query_2244025     6I2U_A   27.273             275        155        9
    1020 Query_2244025     3W16_A   27.273             275        155        9
    1021 Query_2244025     4PRJ_A   27.273             275        155        9
    1022 Query_2244025     3E5A_A   27.273             275        155        9
    1023 Query_2244025     5ZAN_A   27.273             275        155        9
    1024 Query_2244025     1OL5_A   27.273             275        155        9
    1025 Query_2244025     2XNG_A   27.273             275        155        9
    1026 Query_2244025     3EFW_A   27.273             275        155        9
    1027 Query_2244025     2C6D_A   27.273             275        155        9
    1028 Query_2244025     7O2V_A   27.273             275        155        9
    1029 Query_2244025   9ESA_AAA   26.515             264        171        8
    1030 Query_2244025     4JAI_A   27.273             275        155        9
    1031 Query_2244025     8SSP_A   27.273             275        155        9
    1032 Query_2244025     2XRU_A   27.273             275        155        9
    1033 Query_2244025     3HA6_A   27.273             275        155        9
    1034 Query_2244025     3LAU_A   27.273             275        155        9
    1035 Query_2244025     3FXZ_A   25.000             264        176        8
    1036 Query_2244025     2X6D_A   27.273             275        155        9
    1037 Query_2244025     4UZD_A   27.273             275        155        9
    1038 Query_2244025     9GFZ_A   27.397             219        123        7
    1039 Query_2244025     3W2C_A   27.273             275        155        9
    1040 Query_2244025     5DT3_A   27.273             275        155        9
    1041 Query_2244025     8JF4_A   27.273             275        155        9
    1042 Query_2244025     2W1D_A   27.273             275        155        9
    1043 Query_2244025     5DT4_A   27.273             275        155        9
    1044 Query_2244025     6XKA_A   27.273             275        155        9
    1045 Query_2244025     5DOS_A   27.273             275        155        9
    1046 Query_2244025     6VPL_A   27.273             275        155        9
    1047 Query_2244025     4EQC_A   25.000             264        176        8
    1048 Query_2244025     6VPG_A   27.273             275        155        9
    1049 Query_2244025     2W1C_A   27.273             275        155        9
    1050 Query_2244025     3Q52_A   25.000             264        176        8
    1051 Query_2244025     4ZY4_A   25.000             264        176        8
    1052 Query_2244025     1F3M_C   25.000             264        176        8
    1053 Query_2244025     7VTO_A   25.000             264        176        8
    1054 Query_2244025     3DXN_A   24.691             243        149       10
    1055 Query_2244025     1YHV_A   25.000             264        176        8
    1056 Query_2244025     8X5Z_A   25.000             264        176        8
    1057 Query_2244025     4O0R_A   25.000             264        176        8
    1058 Query_2244025     9D4X_A   25.000             264        176        8
    1059 Query_2244025     1OL6_A   26.909             275        156        9
    1060 Query_2244025     5DEW_A   25.000             264        176        8
    1061 Query_2244025     2WTV_A   26.909             275        156        9
    1062 Query_2244025     2WQE_A   26.909             275        156        9
    1063 Query_2244025     2XNE_A   26.909             275        156        9
    1064 Query_2244025     7ZTL_A   26.129             310        178       11
    1065 Query_2244025     3RZF_A   29.358             218        129       10
    1066 Query_2244025     2BFY_A   27.372             274        172        8
    1067 Query_2244025     9KS6_A   26.909             275        156        9
    1068 Query_2244025     3QA8_A   29.358             218        129       10
    1069 Query_2244025     4O0W_A   26.909             275        156        9
    1070 Query_2244025     4P90_A   25.000             264        176        8
    1071 Query_2244025     10SL_A   25.514             243        156        8
    1072 Query_2244025     3GGF_A   27.803             223        139        7
    1073 Query_2244025     5KBQ_A   25.000             264        176        8
    1074 Query_2244025     5K3Y_A   27.372             274        172        8
    1075 Query_2244025     3Q4Z_A   24.621             264        177        8
    1076 Query_2244025     3IS5_A   25.746             268        174       10
    1077 Query_2244025     4KS7_A   27.068             266        164       11
    1078 Query_2244025     9Z8K_B   24.583             240        162        7
    1079 Query_2244025     5AAD_A   26.909             275        156        9
    1080 Query_2244025     4CEG_A   26.909             275        156        9
    1081 Query_2244025     9BZG_A   26.909             275        156        9
    1082 Query_2244025     10JU_B   24.583             240        162        7
    1083 Query_2244025     5LXM_A   26.909             275        156        9
    1084 Query_2244025     5OS2_A   26.909             275        156        9
    1085 Query_2244025     9KDS_A   26.909             275        156        9
    1086 Query_2244025     5ORL_A   26.909             275        156        9
    1087 Query_2244025     10BL_A   25.514             243        156        8
    1088 Query_2244025     4O0U_A   26.909             275        156        9
    1089 Query_2244025     4IEB_A   26.087             230        147        9
    1090 Query_2244025     2C30_A   27.068             266        164       11
    1091 Query_2244025     6FD3_A   25.000             264        176        8
    1092 Query_2244025     5OS5_A   26.909             275        156        9
    1093 Query_2244025     9Z8K_A   24.583             240        162        7
    1094 Query_2244025     10JU_A   24.583             240        162        7
    1095 Query_2244025     8C1K_A   26.909             275        156        9
    1096 Query_2244025     5OSD_A   26.909             275        156        9
    1097 Query_2244025     8GUW_A   26.909             275        156        9
    1098 Query_2244025     8C15_A   26.909             275        156        9
    1099 Query_2244025     4KIK_A   27.189             217        135        7
    1100 Query_2244025     6VBZ_A   24.653             288        188       13
    1101 Query_2244025     6VPH_A   26.909             275        156        9
    1102 Query_2244025     4B8L_A   27.372             274        172        8
    1103 Query_2244025     4C2V_A   27.372             274        172        8
    1104 Query_2244025     4B8M_A   27.372             274        172        8
    1105 Query_2244025     2VRX_A   27.372             274        172        8
    1106 Query_2244025     3DAJ_A   26.909             275        156        9
    1107 Query_2244025     2BFX_A   27.372             274        172        8
    1108 Query_2244025     4M68_A   25.210             238        156       10
    1109 Query_2244025     3D14_A   26.909             275        156        9
    1110 Query_2244025     3HZT_A   24.691             243        149       10
    1111 Query_2244025     9N48_A   24.621             264        177        8
    1112 Query_2244025     4FZA_B   27.014             211        136        5
    1113 Query_2244025     4C2W_A   27.372             274        172        8
    1114 Query_2244025     5ODT_A   26.545             275        157        9
    1115 Query_2244025     4KIK_B   26.728             217        136        7
    1116 Query_2244025     3QBN_A   26.909             275        156        9
    1117 Query_2244025     8OMV_A   26.728             217        136        7
    1118 Query_2244025     7JUW_B   22.408             299        203       10
    1119 Query_2244025     8BW9_D   25.743             303        184       14
    1120 Query_2244025     3HX4_A   26.087             230        147        9
    1121 Query_2244025     4E3C_A   26.728             217        136        7
    1122 Query_2244025     6HJJ_A   26.545             275        157        9
    1123 Query_2244025     3KU2_A   26.087             230        147        9
    1124 Query_2244025     8OF5_A   26.545             275        157        9
    1125 Query_2244025     5DVR_A   26.087             230        147        9
    1126 Query_2244025     4YGA_A   26.087             230        147        9
    1127 Query_2244025     3DFA_A   26.809             235        150        9
    1128 Query_2244025     2WEI_A   26.809             235        150        9
    1129 Query_2244025     2JAM_A   23.404             235        158        7
    1130 Query_2244025     5EYK_A   26.838             272        172        8
    1131 Query_2244025     4BTF_A   25.210             238        156       10
    1132 Query_2244025     9AXH_C   22.222             288        195       10
    1133 Query_2244025     2QKW_B   26.042             288        173       10
    1134 Query_2244025     3HGK_A   26.042             288        173       10
    1135 Query_2244025     9D8S_A   26.087             253        160       10
    1136 Query_2244025     3IGO_A   26.809             235        150        9
    1137 Query_2244025     8PR7_A   26.182             275        158        9
    1138 Query_2244025     6VC0_A   23.368             291        192       13
    1139 Query_2244025     3MA6_A   26.087             230        147        9
    1140 Query_2244025     4AF3_A   26.562             256        165        8
    1141 Query_2244025     4M97_A   26.087             230        147        9
    1142 Query_2244025   8C12_AAA   29.189             185        116        7
    1143 Query_2244025     2F57_A   29.189             185        116        7
    1144 Query_2244025     3I79_A   26.087             230        147        9
    1145 Query_2244025     3LM0_A   27.083             192        126        5
    1146 Query_2244025     2Y4I_B   21.192             302        201       11
    1147 Query_2244025     3I7C_A   26.087             230        147        9
    1148 Query_2244025     5KKR_B   21.192             302        201       11
    1149 Query_2244025     8PAV_A   23.711             291        170       10
    1150 Query_2244025     3COM_A   23.711             291        170       10
    1151 Query_2244025     6YAT_A   23.711             291        170       10
    1152 Query_2244025     7JUQ_B   21.192             302        201       11
    1153 Query_2244025    9FQR_Er   25.210             238        151        8
    1154 Query_2244025     5FG8_A   23.629             237        165        7
    1155 Query_2244025     9IIC_A   23.158             285        179       10
    1156 Query_2244025     2CN5_A   27.200             250        149       11
    1157 Query_2244025     2YCR_A   27.200             250        149       11
    1158 Query_2244025     2W0J_A   27.200             250        149       11
    1159 Query_2244025     2YCF_A   27.200             250        149       11
    1160 Query_2244025     2XK9_A   27.200             250        149       11
    1161 Query_2244025     5WNI_A   24.026             308        202       12
    1162 Query_2244025     8A66_A   24.762             210        139        6
    1163 Query_2244025     2W4O_A   24.206             252        154        8
    1164 Query_2244025     5DH3_A   24.651             215        143        6
    723  Query_2244025     4RT7_A   29.412             136         94        2
    1165 Query_2244025     8A5J_A   23.636             275        170        9
    1166 Query_2244025     3LIJ_A   23.552             259        177        9
    1167 Query_2244025     4JDJ_A   29.570             186        112        7
    1168 Query_2244025     8A66_B   24.762             210        139        5
    1169 Query_2244025     5VED_A   29.570             186        112        7
    1170 Query_2244025   9R1W_AAA   25.581             215        146        6
    1171 Query_2244025     3I6U_A   26.071             280        171       12
    1172 Query_2244025     4FIE_A   29.570             186        112        7
    1173 Query_2244025     8YHK_A   29.570             186        112        7
    1174 Query_2244025     8AHG_A   28.507             221        134        8
    1175 Query_2244025     4FIF_A   29.570             186        112        7
    1176 Query_2244025     3I6W_A   26.071             280        171       12
    1177 Query_2244025     5UPL_A   29.570             186        112        7
    1178 Query_2244025     4MVF_A   24.891             229        144        9
    1179 Query_2244025     2CDZ_A   29.570             186        112        7
    1180 Query_2244025     2X4Z_A   28.507             221        134        8
    1181 Query_2244025     4XBR_A   28.507             221        134        8
    1182 Query_2244025     4O0V_A   29.570             186        112        7
    1183 Query_2244025     2Q0N_A   29.570             186        112        7
    1184 Query_2244025     5XVA_A   29.570             186        112        7
    1185 Query_2244025     2V5Q_A   25.581             215        146        6
    1186 Query_2244025     5XVF_A   28.507             221        134        8
    1187 Query_2244025     4XBU_A   29.570             186        112        7
    1188 Query_2244025     2BVA_A   28.507             221        134        8
    1189 Query_2244025     4LG4_A   24.286             210        140        6
    1190 Query_2244025     3KB7_A   25.581             215        146        6
    1191 Query_2244025     2YAC_A   25.581             215        146        6
    1192 Query_2244025     2OU7_A   25.581             215        146        6
    1193 Query_2244025     3THB_A   25.581             215        146        6
    1194 Query_2244025     2V7O_A   23.077             234        162        7
    1195 Query_2244025     4LGD_A   24.424             217        145        6
    1196 Query_2244025     4J52_A   25.581             215        146        6
    1197 Query_2244025     2RKU_A   25.581             215        146        6
    1198 Query_2244025     5TA6_A   25.581             215        146        6
    1199 Query_2244025     5IG1_A   24.473             237        160        7
    1200 Query_2244025     2WEL_A   24.138             232        156        8
    1201 Query_2244025     3KN5_A   27.389             157        104        3
    1202 Query_2244025     5VLO_A   24.138             232        156        8
    1203 Query_2244025     7S46_A   29.032             186        113        7
    1204 Query_2244025     6AO5_A   24.286             210        140        6
    1205 Query_2244025     9BLH_A   24.138             232        156        8
    1206 Query_2244025     2VN9_A   24.138             232        156        8
    1207 Query_2244025     8USO_A   24.138             232        156        8
    1208 Query_2244025     7S47_A   29.032             186        113        7
    1209 Query_2244025     9P6A_A   28.000             225        124        8
    1210 Query_2244025     3FHR_A   27.397             146         96        5
    1211 Query_2244025     3R1N_A   27.397             146         96        5
    1212 Query_2244025     2JC6_A   22.358             246        161        6
    1213 Query_2244025     3BHH_A   22.944             231        160        7
    1214 Query_2244025   6T28_AAA   22.764             246        160        6
    1215 Query_2244025     8E05_A   26.484             219        144        8
    1216 Query_2244025     3MDY_A   23.779             307        160       14
    1217 Query_2244025     8E04_A   26.484             219        144        8
    1218 Query_2244025     6QP5_A   22.269             238        155        6
    1219 Query_2244025     8FAC_A   26.484             219        144        8
    1220 Query_2244025     7MX3_A   23.345             287        175       10
    1221 Query_2244025     8T6K_A   22.944             231        160        7
    1222 Query_2244025     4YSJ_A   26.840             231        144        9
    1223 Query_2244025     2KUP_B  100.000              19          0        0
    1224 Query_2244025     6BWK_A   23.276             232        154       10
    1225 Query_2244025     9LFU_A   23.693             287        174       11
    1226 Query_2244025     1A06_A   21.862             247        167        6
    1227 Query_2244025     6LBA_A   27.230             213        132       10
    1228 Query_2244025     6W4O_A   23.377             231        159        7
    1229 Query_2244025     7UJR_A   23.377             231        159        7
    1230 Query_2244025     6O5Z_A   23.276             232        154       10
    1231 Query_2244025     8SLZ_A   23.276             232        154       10
    1232 Query_2244025     5KNJ_A   24.895             237        144       11
    1233 Query_2244025     2VZ6_A   23.377             231        159        7
    1234 Query_2244025     5U6Y_A   23.377             231        159        7
    1235 Query_2244025     4MWI_A   21.595             301        192       13
    1236 Query_2244025     4M67_A   21.595             301        192       13
    1237 Query_2244025     7MON_B   23.345             287        175       11
    1238 Query_2244025     7B55_B   23.377             231        159        7
    1239 Query_2244025     3MFR_A   27.513             189        129        7
    1240 Query_2244025     6LK6_A   21.595             301        192       13
    1241 Query_2244025     6BXI_A   22.264             265        147       10
    1242 Query_2244025     4TXC_A   27.027             185        119        7
    1243 Query_2244025     3MY0_A   26.840             231        125        9
    1244 Query_2244025     4FG7_A   22.374             219        154        5
    1245 Query_2244025     3RP9_A   22.131             244        126       12
    1246 Query_2244025     4FG8_A   22.374             219        154        5
    1247 Query_2244025     4FG9_A   22.374             219        154        5
    1248 Query_2244025     6LK5_A   21.595             301        192       13
    1249 Query_2244025     9D5I_A   24.823             282        176       14
    1250 Query_2244025     3MTF_A   26.180             233        124       11
    1251 Query_2244025     9D5H_A   24.823             282        176       14
    1252 Query_2244025     2W4J_A   27.027             185        119        6
    1253 Query_2244025     1WVW_A   27.027             185        119        6
    1254 Query_2244025     4PF4_A   27.027             185        119        6
    1255 Query_2244025     9RDA_A   25.287             261        146       12
    1256 Query_2244025     3H9R_A   25.287             261        146       12
    1257 Query_2244025     2Y4P_A   27.027             185        119        6
    1258 Query_2244025     4TL0_A   27.027             185        119        7
    1259 Query_2244025     6FHB_A   27.027             185        119        7
    1260 Query_2244025     4UV0_A   27.027             185        119        7
    1261 Query_2244025     5AUT_A   27.027             185        119        6
    1262 Query_2244025     1P4F_A   27.027             185        119        6
    1263 Query_2244025     1IG1_A   27.027             185        119        6
    1264 Query_2244025     3F5U_A   27.027             185        119        6
    1265 Query_2244025     3DFC_B   27.027             185        119        6
    1266 Query_2244025     3GU4_A   27.027             185        119        6
    1267 Query_2244025     6FHA_A   27.027             185        119        7
    1268 Query_2244025     8UWR_A   25.523             239        130       11
    1269 Query_2244025     3KMW_A   24.823             282        176       14
    1270 Query_2244025     2W4K_A   27.027             185        119        6
    1271 Query_2244025     9MIU_A   27.027             185        119        6
    1272 Query_2244025     6EIX_A   25.287             261        146       12
    1273 Query_2244025     2XZS_A   27.027             185        119        6
    1274 Query_2244025     6QMO_A   27.027             185        119        6
    1275 Query_2244025     6QN4_A   27.027             185        119        6
    1276 Query_2244025     8FX4_D   23.111             225        134        8
    1277 Query_2244025     2X0G_A   27.027             185        119        7
    1278 Query_2244025     4B4L_A   27.568             185        118        7
    1279 Query_2244025     2Y0A_A   27.027             185        119        6
    1280 Query_2244025     9D8Z_A   25.287             261        146       12
    1281 Query_2244025     2XUU_A   27.807             187        115        7
    1282 Query_2244025     9IWX_A   22.222             288        179       12
    1283 Query_2244025     9D8F_A   26.180             233        124       11
    1284 Query_2244025     6UNR_A   26.180             233        124       11
    1285 Query_2244025     6UNQ_A   26.180             233        124       11
    1286 Query_2244025     2JBO_A   27.143             140         93        5
    1287 Query_2244025     3GOK_A   27.143             140         93        5
    1288 Query_2244025     3R2B_A   27.143             140         93        5
    1289 Query_2244025     6TCA_A   27.143             140         93        5
    1290 Query_2244025     2PZY_A   27.143             140         93        5
    1291 Query_2244025     2OZA_A   27.143             140         93        5
    1292 Query_2244025     6JUX_A   26.407             231        122       11
    1293 Query_2244025     4TYH_A   27.143             140         93        5
    1294 Query_2244025     2ONL_C   27.143             140         93        5
    1295 Query_2244025     4M66_A   22.222             288        179       12
    1296 Query_2244025     3FPM_A   27.143             140         93        5
    1297 Query_2244025     1KWP_A   27.143             140         93        5
    1298 Query_2244025     2P3G_X   27.143             140         93        5
    1299 Query_2244025     4DYM_A   26.407             231        122       11
    1300 Query_2244025     3R2Y_A   27.143             140         93        5
    1301 Query_2244025     3KA0_A   27.143             140         93        5
    1302 Query_2244025     6T8X_A   27.143             140         93        5
    1303 Query_2244025     6MIB_A   24.823             282        176       14
    1304 Query_2244025     6KA4_A   23.707             232        154        9
    1305 Query_2244025     8XU4_A   25.714             140         95        4
    1306 Query_2244025     9R59_A   25.714             140         95        4
    1307 Query_2244025     4M69_A   23.024             291        173       13
    1308 Query_2244025     1NXK_A   27.143             140         93        5
    1309 Query_2244025     7UP4_A   24.841             157         88        4
    1310 Query_2244025     2KUQ_A  100.000              19          0        0
    1311 Query_2244025     3GU8_A   26.486             185        120        6
    1312 Query_2244025     3D5V_A   24.473             237        157        9
    1313 Query_2244025     5YV8_A   27.461             193        103       10
    1314 Query_2244025     2ZV2_A   27.461             193        103       10
    1315 Query_2244025     3D5W_A   24.473             237        157        9
    1316 Query_2244025     3D5X_A   24.268             239        159        9
    1317 Query_2244025     3D5U_A   24.473             237        157        9
    1318 Query_2244025     6CMJ_A   24.706             255        151       12
    1319 Query_2244025     5UY6_A   27.461             193        103       10
    1320 Query_2244025     5YKS_A   22.789             294        178       14
    1321 Query_2244025     3KGA_A   25.000             140         75        4
    1322 Query_2244025     8H59_A   25.225             222        141        9
    1323 Query_2244025     8ZTC_A   25.225             222        141        9
    1324 Query_2244025     5Z33_A   25.225             222        141        9
    1325 Query_2244025     7KPV_A   29.348              92         60        2
    1326 Query_2244025     6FYP_A   22.041             245        149       11
    1327 Query_2244025     2EU9_A   22.041             245        149       11
    1328 Query_2244025     6FT7_A   22.041             245        149       11
    1329 Query_2244025     2WU6_A   22.041             245        149       11
    1330 Query_2244025     2EXE_A   22.041             245        149       11
    1331 Query_2244025     3KMU_A   24.113             282        178       14
    1332 Query_2244025     6YTY_A   22.041             245        149       11
    1333 Query_2244025     3N9X_A   22.121             330        193       14
    1334 Query_2244025     4HNI_A   24.028             283        166       16
    1335 Query_2244025     9B3S_A   22.989             174        115        8
    1336 Query_2244025     7LIR_A   33.000             100         60        2
    1337 Query_2244025     8VXF_A   22.857             175        116        8
    1338 Query_2244025     6KHF_A   21.600             250        154       11
    1339 Query_2244025     3NIE_A   23.109             238        129       12
    1340 Query_2244025     5X17_A   21.264             174        120        6
    1341 Query_2244025     5MQV_A   21.264             174        120        6
    1342 Query_2244025     3UYS_A   22.857             175        116        8
    1343 Query_2244025     4KB8_A   21.387             173        119        6
    1344 Query_2244025     6RCG_A   22.857             175        116        8
    1345 Query_2244025     4TN6_A   22.857             175        116        8
    1346 Query_2244025     5IH4_A   22.857             175        116        8
    1347 Query_2244025     8VXD_A   22.857             175        116        8
    1348 Query_2244025     8D7M_A   22.857             175        116        8
    1349 Query_2244025     4JJR_A   22.857             175        116        8
    1350 Query_2244025     4TW9_A   22.857             175        116        8
    1351 Query_2244025     8IZC_A   22.857             175        116        8
    1352 Query_2244025     1CKI_A   22.857             175        116        8
    1353 Query_2244025     6PXN_A   21.387             173        119        6
    1354 Query_2244025     6PXP_A   22.857             175        116        8
    1355 Query_2244025     9BCV_A   23.176             233        145       10
    1356 Query_2244025     9BCL_A   23.176             233        145       10
    1357 Query_2244025     9DZH_A   23.176             233        145       10
    1358 Query_2244025     5OKT_A   21.264             174        120        6
    1359 Query_2244025     7P7F_A   22.857             175        116        8
    1360 Query_2244025     5CZO_A   24.242             165         91        7
    1361 Query_2244025     5CYZ_A   24.242             165         91        7
    1362 Query_2244025     4XH0_A   22.973             222        126       10
    1363 Query_2244025     4XHL_A   24.118             170         94        8
    1364 Query_2244025     9CWM_A   34.483              58         23        2
    1365 Query_2244025     4LQS_A   21.637             171        116        5
    1366 Query_2244025     4LQP_A   21.637             171        116        5
    1367 Query_2244025     7T4S_F   23.958             192        122       11
    1368 Query_2244025     9I3V_A   34.483              58         23        2
    1369 Query_2244025     3SV0_A   27.711             166         90        9
    1370 Query_2244025    9Y9Z_20   25.166             151         79        5
         q.start q.end s.start s.end   evalue bitscore positives mlog.evalue pdb.id
    1        648  1030       1   383 0.00e+00    793.0    100.00 709.1962086 7NX3_A
    2        648  1025       2   379 0.00e+00    782.0    100.00 709.1962086 7N00_A
    3       1058  1410       1   353 0.00e+00    739.0     99.72 709.1962086 4FOB_A
    4        677  1030      15   368 0.00e+00    731.0     99.72 709.1962086 7LS0_A
    5        673  1025       1   353 0.00e+00    730.0    100.00 709.1962086 7MZW_A
    6       1069  1411       2   344 0.00e+00    719.0    100.00 709.1962086 3AOX_A
    7       1069  1411       2   344 0.00e+00    716.0     99.71 709.1962086 9GBE_A
    8       1068  1410      25   367 0.00e+00    712.0     99.13 709.1962086 3L9P_A
    9       1068  1410       2   344 0.00e+00    711.0     99.13 709.1962086 3LCS_A
    10      1072  1410       1   339 0.00e+00    709.0     99.71 709.1962086 4Z55_A
    11      1078  1410       1   333 0.00e+00    697.0     99.70 709.1962086 4DCE_A
    12       648   993       1   344 0.00e+00    694.0     98.55 709.1962086 7NWZ_A
    13      1084  1410       1   327 0.00e+00    685.0     99.69 709.1962086 4FNZ_A
    14      1084  1410       1   327 0.00e+00    683.0     99.69 709.1962086 4FNX_A
    15      1084  1410       1   327 0.00e+00    682.0     99.39 709.1962086 4FNW_A
    16      1092  1411       8   327 0.00e+00    671.0    100.00 709.1962086 2XP2_A
    17      1092  1411       8   327 0.00e+00    671.0    100.00 709.1962086 2YFX_A
    18      1093  1411       3   321 0.00e+00    671.0    100.00 709.1962086 8ARJ_A
    19      1092  1411       8   327 0.00e+00    670.0     99.69 709.1962086 5AA9_A
    20      1093  1411      24   342 0.00e+00    670.0    100.00 709.1962086 2YHV_A
    21      1093  1411      24   342 0.00e+00    669.0     99.69 709.1962086 4ANL_A
    22      1093  1411      24   342 0.00e+00    668.0     99.69 709.1962086 4ANS_A
    23      1090  1406       6   322 0.00e+00    668.0    100.00 709.1962086 6E0R_A
    24      1093  1411      24   342 0.00e+00    668.0     99.69 709.1962086 2YJR_A
    25      1092  1411       8   327 0.00e+00    667.0     99.69 709.1962086 5A9U_A
    26      1093  1411      24   342 0.00e+00    667.0     99.69 709.1962086 2YJS_A
    27      1093  1410       3   320 0.00e+00    666.0     99.69 709.1962086 7BTT_A
    28      1092  1411       8   327 0.00e+00    666.0     99.38 709.1962086 5AA8_A
    29      1095  1411       2   318 0.00e+00    664.0    100.00 709.1962086 4TT7_A
    30      1094  1407       2   315 0.00e+00    660.0    100.00 709.1962086 2XB7_A
    31      1094  1400       1   307 0.00e+00    646.0    100.00 709.1962086 6MX8_A
    32       673   986       2   315 0.00e+00    642.0    100.00 709.1962086 7MZY_A
    33       677   986       2   311 0.00e+00    633.0     99.68 709.1962086 7LRZ_A
    34      1095  1384      17   306 5.49e-88    291.0     70.65 200.9245599 3ZBF_A
    35      1105  1384       7   289 1.74e-87    290.0     71.73 199.7710180 7Z5W_A
    36      1104  1384       2   285 4.13e-87    288.0     71.48 198.9066257 9QEK_A
    37      1089  1384       1   295 6.31e-83    277.0     62.21 189.2724270 8PYI_a
    38      1081  1384      15   317 8.48e-83    277.0     61.56 188.9768523 3LVP_A
    39      1089  1384       1   295 9.68e-83    276.0     62.54 188.8445008 1P4O_A
    40      1089  1384       1   295 1.10e-82    276.0     62.21 188.7166674 1M7N_A
    41      1098  1384       3   289 1.45e-81    272.0     62.76 186.1378290 5FXQ_A
    42      1098  1384       3   289 1.48e-81    272.0     62.76 186.1173504 5FXR_A
    43      1098  1384       3   289 1.50e-81    272.0     62.76 186.1039274 1JQH_A
    44      1104  1384       2   282 1.55e-81    272.0     63.73 186.0711376 3QQU_A
    45      1105  1384       9   288 4.53e-81    271.0     63.60 184.9986706 2OJ9_A
    46      1105  1384       6   285 5.49e-81    270.0     63.96 184.8064643 3LW0_A
    47      1105  1384       7   286 6.07e-81    270.0     63.60 184.7060339 3O23_A
    48      1105  1384       4   283 7.65e-81    270.0     63.60 184.4746869 4D2R_A
    49      1105  1384       9   288 7.68e-81    270.0     63.60 184.4707730 3I81_A
    50      1098  1384       3   289 2.56e-80    269.0     62.41 183.2668002 5FXS_A
    51      1105  1384       3   282 7.82e-80    267.0     62.90 182.1501229 3D94_A
    52      1098  1384       3   289 4.79e-78    262.0     61.72 178.0351068 2ZM3_A
    53      1105  1384       1   280 5.15e-77    259.0     62.19 175.6600554 1K3A_A
    54      1110  1412      12   307 5.70e-77    259.0     60.59 175.5585860 3ETA_A
    55      1105  1380       8   283 5.74e-77    259.0     63.21 175.5515930 1I44_A
    56      1105  1380       8   283 7.45e-77    259.0     62.86 175.2908381 1IRK_A
    57      1105  1380       8   283 1.81e-76    258.0     62.50 174.4031402 4IBM_A
    58      1105  1380      10   285 3.24e-76    257.0     62.86 173.8208937 5E1S_A
    59      1105  1380       9   284 3.70e-76    257.0     62.86 173.6881342 5HHW_A
    60      1105  1380       9   284 5.19e-76    256.0     62.50 173.3497334 3EKK_A
    61      1105  1380       8   283 5.87e-76    256.0     62.50 173.2266124 1P14_A
    62      1043  1435    1879  2285 6.00e-76    282.0     58.78 173.2047076 9OYZ_B
    63      1026  1384     904  1243 5.40e-75    276.0     57.26 171.0074830 8EYR_A
    64      1028  1384     931  1267 8.99e-75    276.0     57.22 170.4977691 6JK8_A
    65      1105  1380       8   283 1.62e-74    252.0     62.14 169.9088707 8DWN_A
    66      1105  1380       5   280 1.36e-73    249.0     61.79 167.7812271 2Z8C_A
    67      1105  1380       8   283 2.23e-73    249.0     61.79 167.2867102 1GAG_A
    68      1105  1380       8   283 2.73e-73    248.0     61.43 167.0844102 1RQQ_A
    69      1026  1384     900  1239 3.28e-73    271.0     56.99 166.9008684 6PYH_A
    70      1105  1380      30   305 6.51e-73    248.0     61.43 166.2153723 4XLV_A
    71      1082  1384     946  1247 2.08e-71    265.0     61.76 162.7511737 7TYJ_A
    72      1093  1434     986  1329 2.27e-70    262.0     57.58 160.3611767 7SL1_A
    73      1093  1434     959  1302 2.43e-70    262.0     57.58 160.2930653 8DTL_A
    74      1093  1434     959  1302 2.63e-70    262.0     57.58 160.2139727 8EYX_A
    75      1093  1434     996  1339 9.87e-70    260.0     57.58 158.8914567 8U4B_A
    76      1093  1434     969  1312 1.13e-69    260.0     57.58 158.7561538 7BW7_A
    77      1093  1434     984  1327 1.18e-69    260.0     57.58 158.7128570 8VJB_A
    78      1095  1397      19   325 1.29e-69    239.0     55.31 158.6237292 7VKO_A
    79      1093  1434     984  1327 1.45e-69    260.0     57.58 158.5068079 7PG0_A
    80      1108  1376       7   277 1.63e-69    237.0     59.27 158.3897914 4ASZ_A
    81      1093  1397      10   312 6.59e-69    236.0     55.59 156.9928181 8J5W_A
    82      1105  1434     973  1300 6.83e-69    258.0     58.82 156.9570467 6PXV_A
    83      1100  1397       1   302 1.13e-68    235.0     55.56 156.4535687 4YNE_A
    84      1108  1397       2   295 1.28e-68    234.0     56.38 156.3289262 6IQN_A
    85      1093  1397      26   328 1.33e-68    236.0     55.27 156.2906074 4AOJ_A
    86      1095  1397      19   325 1.35e-68    236.0     54.98 156.2756817 7VKM_A
    87      1108  1397       3   296 1.56e-68    234.0     56.38 156.1311005 6NSP_A
    88      1093  1397      17   319 1.57e-68    235.0     55.27 156.1247107 6D1Y_A
    89      1093  1397      21   323 1.60e-68    235.0     55.27 156.1057827 5H3Q_A
    90      1108  1397       6   299 1.65e-68    234.0     56.38 156.0750110 4F0I_A
    91      1108  1397       5   298 1.85e-68    234.0     56.38 155.9606007 7XAF_A
    92      1093  1397      20   322 2.01e-68    235.0     55.27 155.8776516 5KMI_A
    93      1093  1397      21   323 2.07e-68    235.0     55.27 155.8482377 5KML_A
    94      1093  1397       9   311 2.15e-68    234.0     55.27 155.8103185 6PL1_A
    95      1108  1397      14   307 2.18e-68    234.0     56.38 155.7964614 5JFS_A
    96      1093  1392       5   302 2.18e-68    234.0     55.84 155.7964614 5WR7_A
    97      1108  1397      13   306 2.26e-68    234.0     56.38 155.7604215 6D22_A
    98      1093  1397       3   305 2.27e-68    234.0     55.27 155.7560065 6NPT_A
    99      1108  1397      12   305 2.34e-68    234.0     56.38 155.7256354 4GT5_A
    100     1093  1397       9   311 2.53e-68    234.0     55.27 155.6475670 6NSS_A
    101     1108  1388       2   286 7.62e-68    232.0     57.09 154.5450100 4PMM_A
    102     1108  1397       5   298 1.88e-67    231.0     56.04 153.6419295 8J5X_A
    103     1100  1381       1   287 6.31e-67    230.0     57.34 152.4310656 3V5Q_A
    104     1108  1382       5   283 6.42e-67    230.0     57.24 152.4137831 5I8A_A
    105     1108  1382       2   280 9.19e-67    229.0     57.24 152.0550853 5KVT_A
    106     1100  1381       1   287 9.23e-67    229.0     57.34 152.0507422 4YMJ_A
    107     1110  1379      43   326 1.03e-65    228.0     58.33 149.6384722 1LUF_A
    108     1107  1384       4   265 1.44e-64    222.0     56.83 147.0008028 4CSV_A
    109     1090  1384    1348  1651 1.96e-64    244.0     59.03 146.6925015 9EF1_A
    110     1111  1384      20   293 2.64e-63    220.0     58.36 144.0920819 5U6B_A
    111     1110  1384      31   314 4.11e-63    220.0     56.79 143.6494378 6PNX_A
    112     1114  1384     112   368 4.66e-63    221.0     60.15 143.5238454 6JMF_A
    113     1114  1384     112   368 5.28e-63    221.0     60.15 143.3989348 8XKP_A
    114     1110  1384      13   284 5.29e-63    218.0     57.19 143.3970426 8UDV_A
    115     1114  1384     114   370 5.98e-63    221.0     60.15 143.2744403 3BKB_A
    116     1110  1384      13   284 6.60e-63    218.0     57.19 143.1757912 8UDT_A
    117     1108  1381       3   295 7.36e-63    219.0     55.52 143.0668009 6KZC_A
    118     1110  1384      19   302 1.19e-62    218.0     56.79 142.5863225 9CD7_A
    119     1029  1383     490   859 1.94e-62    233.0     54.09 142.0975878 8S9P_C
    120     1110  1384      32   315 1.95e-62    218.0     56.79 142.0924464 4K33_A
    121     1114  1384     114   370 7.07e-62    218.0     59.78 140.8044153 3CD3_A
    122     1110  1400      15   317 8.19e-62    216.0     56.54 140.6573619 8YKI_A
    123     1108  1384      11   287 1.07e-61    215.0     57.80 140.3900320 4XCU_A
    124     1110  1384      17   300 1.07e-61    215.0     57.14 140.3900320 5FLF_A
    125     1110  1384      19   302 1.29e-61    215.0     55.90 140.2030485 9KFU_A
    126     1110  1400      24   326 1.60e-61    215.0     56.54 139.9876870 3GQL_A
    127     1108  1384      15   300 2.70e-61    214.0     57.04 139.4644389 7WCW_A
    128     1105  1384      14   302 3.58e-61    214.0     56.80 139.1823279 5XFF_A
    129     1105  1384       3   291 4.41e-61    213.0     56.80 138.9738160 8KH9_A
    130     1108  1384      29   314 4.87e-61    214.0     57.04 138.8745967 4QQJ_A
    131     1100  1379       7   284 5.37e-61    213.0     60.07 138.7768628 6VG3_A
    132     1108  1384      15   300 5.67e-61    213.0     57.04 138.7225016 7WCX_A
    133     1108  1384      15   300 5.84e-61    213.0     57.04 138.6929599 4UXQ_A
    134     1106  1383      11   294 5.87e-61    213.0     56.25 138.6878360 6TU9_A
    135     1105  1384      14   302 6.19e-61    213.0     56.80 138.6347556 5XFJ_A
    136     1108  1384      15   300 6.49e-61    213.0     57.04 138.5874281 7DTZ_A
    137     1108  1384      17   302 7.30e-61    213.0     57.04 138.4698163 6JPE_A
    138     1108  1384      17   302 8.27e-61    213.0     57.04 138.3450562 5JKG_A
    139     1110  1384      18   301 8.43e-61    213.0     56.79 138.3258939 4WUN_A
    140     1110  1384      14   297 8.64e-61    213.0     56.79 138.3012881 5A4C_A
    141     1110  1384      17   300 8.92e-61    213.0     56.79 138.2693947 5AM7_A
    142     1110  1384      24   307 9.06e-61    213.0     56.79 138.2538216 4RWI_A
    143     1110  1384      15   298 1.03e-60    212.0     56.79 138.1255468 4ZSA_A
    144     1110  1384      16   299 1.10e-60    212.0     56.79 138.0597954 4F63_A
    145     1110  1384      13   296 1.15e-60    212.0     56.79 138.0153436 3RHX_A
    146     1108  1384      29   314 1.18e-60    213.0     57.04 137.9895911 4QQT_A
    147     1110  1384      17   300 1.20e-60    212.0     56.79 137.9727840 1AGW_A
    148     1110  1384      24   307 1.26e-60    213.0     56.79 137.9239939 3JS2_A
    149     1110  1384       9   292 1.31e-60    212.0     56.79 137.8850784 3C4F_A
    150     1110  1384      20   303 1.35e-60    212.0     55.56 137.8550010 6LVM_A
    151     1110  1384      13   296 1.42e-60    212.0     56.79 137.8044487 5ZV2_A
    152     1110  1384      16   299 1.43e-60    212.0     56.79 137.7974311 5VND_A
    153     1110  1403      36   342 1.98e-60    214.0     56.13 137.4720087 5A46_A
    154     1108  1384      17   302 2.55e-60    211.0     56.70 137.2190122 4TYE_A
    155     1108  1384      29   314 2.62e-60    212.0     56.70 137.1919313 4QQ5_A
    156     1108  1384       7   292 3.39e-60    211.0     56.70 136.9342757 8W5C_A
    157     1108  1384      13   298 3.42e-60    211.0     56.70 136.9254650 5NUD_A
    158     1095  1384      43   348 3.74e-60    213.0     55.34 136.8360200 3TT0_A
    159     1108  1384      13   298 3.76e-60    211.0     56.70 136.8306866 6YI8_A
    160     1108  1384       7   292 3.88e-60    210.0     56.70 136.7992704 7VJL_A
    161     1108  1384      17   302 4.20e-60    211.0     56.70 136.7200211 7F3M_A
    162     1110  1384      15   298 5.53e-60    210.0     56.45 136.4449178 8Y22_A
    163     1110  1384      16   299 5.65e-60    210.0     56.45 136.4234500 6NVL_A
    164     1108  1384      28   313 5.65e-60    211.0     56.70 136.4234500 6IUO_A
    165     1108  1384      29   314 5.76e-60    211.0     56.70 136.4041681 4QQC_A
    166     1110  1384      17   300 6.47e-60    210.0     56.45 136.2879295 7WCL_A
    167     1110  1384      18   301 6.54e-60    210.0     56.45 136.2771684 6MZW_A
    168     1111  1392      16   294 6.60e-60    209.0     58.95 136.2680359 7AAY_A
    169     1110  1384      24   307 7.66e-60    210.0     56.45 136.1190936 3KXX_A
    170     1110  1384      31   314 8.07e-60    210.0     55.05 136.0669521 2PZP_A
    171     1110  1384      31   314 9.14e-60    210.0     55.05 135.9424452 2PWL_A
    172     1110  1384      31   314 1.22e-59    210.0     55.05 135.6536696 2PZ5_A
    173     1110  1384      19   292 1.77e-59    208.0     56.83 135.2815409 6FEK_A
    174     1110  1400      24   326 1.90e-59    209.0     55.88 135.2106666 3GQI_A
    175     1107  1392       5   274 1.94e-59    208.0     56.29 135.1898325 6XRG_A
    176     1110  1384      31   314 2.15e-59    209.0     55.05 135.0870526 2PZR_A
    177     1110  1384      20   303 2.85e-59    208.0     54.70 134.8052015 6LVL_A
    178     1110  1384      31   314 2.90e-59    209.0     55.05 134.7878097 4J98_A
    179     1110  1384      37   320 3.22e-59    209.0     54.70 134.6831391 8E1X_A
    180     1110  1384      31   314 3.25e-59    209.0     55.05 134.6738655 4J97_A
    181     1110  1384      20   303 3.36e-59    208.0     54.70 134.6405795 3RI1_A
    182     1110  1384      15   298 3.37e-59    208.0     54.36 134.6376077 7KIA_A
    183     1110  1384      11   294 3.49e-59    208.0     54.70 134.6026188 9U7E_A
    184     1110  1384      23   306 3.50e-59    208.0     54.70 134.5997575 8STG_A
    185     1110  1384      23   306 3.56e-59    208.0     54.70 134.5827599 8SWE_A
    186     1110  1384      23   306 3.88e-59    208.0     54.70 134.4966853 1GJO_A
    187     1110  1384      15   298 4.07e-59    207.0     54.70 134.4488775 7OZY_a
    188     1110  1384      31   314 4.09e-59    208.0     54.70 134.4439755 2PVY_A
    189     1110  1384      18   301 4.43e-59    207.0     54.36 134.3641209 9U3N_A
    190     1111  1396      33   319 5.10e-59    208.0     58.02 134.2232799 9BHI_A
    191     1110  1384      31   314 5.46e-59    208.0     54.70 134.1550717 4J99_A
    192     1110  1384      31   314 6.18e-59    208.0     54.70 134.0312022 5UHN_A
    193     1110  1384      31   314 6.43e-59    207.0     54.70 133.9915459 2Q0B_A
    194     1110  1384      31   314 8.66e-59    207.0     54.70 133.6938058 4J96_A
    195     1074  1389       6   327 9.10e-59    207.0     52.13 133.6442461 8W1L_A
    196     1095  1392      15   315 1.01e-58    207.0     56.68 133.5399851 5U6C_A
    197     1074  1389       8   329 1.06e-58    207.0     52.13 133.4916665 2I0V_A
    198     1110  1384      31   314 1.09e-58    207.0     54.70 133.4637577 2PY3_A
    199     1111  1392      14   296 1.10e-58    206.0     58.13 133.4546252 7AAZ_A
    200     1107  1392       6   275 1.27e-58    206.0     56.64 133.3109185 2Z60_A
    201     1107  1392       6   275 1.29e-58    205.0     56.64 133.2952932 3OY3_A
    202     1111  1392      12   294 1.29e-58    206.0     58.13 133.2952932 7CQE_A
    203     1074  1389       8   327 1.30e-58    207.0     53.37 133.2875711 3BEA_A
    204     1110  1384      18   301 1.32e-58    206.0     54.36 133.2723037 3B2T_A
    205     1110  1384      77   360 1.36e-58    208.0     54.70 133.2424507 2PSQ_A
    206     1110  1384      20   303 1.37e-58    206.0     54.36 133.2351247 6LVK_A
    207     1110  1400      31   333 1.46e-58    207.0     53.92 133.1714990 2PVF_A
    208     1111  1392      14   296 1.57e-58    206.0     58.13 133.0988598 7OAM_A
    209     1111  1392      31   313 1.65e-58    206.0     58.13 133.0491601 2P0C_A
    210     1110  1384      31   314 1.88e-58    206.0     54.70 132.9186636 5UGL_A
    211     1111  1392      14   296 2.18e-58    205.0     58.13 132.7706105 7DXL_A
    212     1110  1384      19   293 2.25e-58    205.0     55.76 132.7390052 5AMN_A
    213     1110  1400      31   333 2.33e-58    206.0     53.92 132.7040671 3CLY_A
    214     1107  1392       6   275 2.51e-58    205.0     56.29 132.6296526 2QOH_A
    215     1111  1392      32   314 3.00e-58    206.0     58.13 132.4513231 5TC0_A
    216     1107  1392      11   280 3.13e-58    204.0     56.29 132.4089024 1FPU_A
    217     1107  1392       1   270 3.18e-58    204.0     56.29 132.3930542 4TWP_A
    218     1107  1392       6   275 3.34e-58    204.0     56.29 132.3439646 3OXZ_A
    219     1110  1384      19   307 3.71e-58    205.0     53.92 132.2389035 2IVS_A
    220     1110  1400      31   333 3.77e-58    206.0     54.25 132.2228604 5EG3_A
    221     1088  1389      21   332 3.99e-58    206.0     52.38 132.1661442 7TNH_A
    222     1110  1384      31   314 4.02e-58    206.0     54.70 132.1586535 8W3D_A
    223     1111  1378      16   283 4.16e-58    204.0     58.39 132.1244203 7AAX_A
    224     1100  1392       1   277 4.26e-58    204.0     55.29 132.1006662 2G1T_A
    225     1111  1384       6   279 4.29e-58    204.0     58.57 132.0936487 5TD2_A
    226     1110  1384      19   302 4.63e-58    205.0     54.36 132.0173785 8H75_A
    227     1107  1392       7   276 4.69e-58    204.0     55.94 132.0045028 4WA9_A
    228     1107  1389      11   277 4.95e-58    203.0     56.54 131.9505478 3QRJ_A
    229     1110  1384      31   314 5.07e-58    205.0     54.36 131.9265946 5UI0_A
    230     1074  1389       8   327 5.91e-58    205.0     52.76 131.7732896 2I1M_A
    231     1107  1392       5   274 5.92e-58    204.0     55.94 131.7715989 6XR6_A
    232     1093  1392       4   277 6.03e-58    204.0     54.67 131.7531884 2HIW_A
    233     1111  1378      31   298 6.60e-58    204.0     58.39 131.6628657 7M5Z_A
    234     1111  1395      20   314 7.23e-58    205.0     54.15 131.5716964 3QUP_A
    235     1107  1392       5   274 7.56e-58    203.0     55.94 131.5270642 4ZOG_A
    236     1107  1392      11   280 7.65e-58    203.0     55.94 131.5152297 2E2B_A
    237     1074  1389       5   326 7.74e-58    205.0     51.83 131.5035337 6WXJ_A
    238     1110  1384      31   314 8.51e-58    204.0     54.36 131.4086935 8W3B_A
    239     1100  1392       1   277 9.48e-58    203.0     55.29 131.3007511 2G2F_A
    240     1107  1389      10   276 9.71e-58    202.0     56.18 131.2767791 5HU9_A
    241     1107  1389      11   277 1.00e-57    202.0     56.18 131.2473503 3QRI_A
    242     1110  1384      31   314 1.03e-57    204.0     54.36 131.2177915 8W2X_A
    243     1074  1389       8   323 1.04e-57    204.0     52.17 131.2081296 3LCD_A
    244     1107  1392       1   270 1.11e-57    202.0     56.29 131.1429903 6BL8_A
    245     1110  1384      19   307 1.12e-57    204.0     53.58 131.1340216 6I82_A
    246     1110  1384      31   314 1.21e-57    204.0     54.36 131.0567299 5UGX_A
    247     1107  1392      19   288 1.22e-57    203.0     55.94 131.0484994 3PYY_A
    248     1091  1389       4   276 1.31e-57    202.0     54.85 130.9773232 2HZI_A
    249     1110  1384      31   314 1.39e-57    204.0     54.36 130.9180466 8W38_A
    250     1107  1389       6   272 1.39e-57    202.0     56.18 130.9180466 2HYY_A
    251     1107  1392       4   273 1.42e-57    202.0     56.29 130.8966934 3DK3_A
    252     1107  1389       5   271 1.44e-57    202.0     56.18 130.8827072 7N9G_A
    253     1107  1392       7   276 1.58e-57    202.0     55.94 130.7899255 2F4J_A
    254     1107  1392       4   273 1.63e-57    202.0     56.29 130.7587703 3DK7_A
    255     1107  1392      33   302 1.69e-57    203.0     55.94 130.7226218 7CC2_A
    256     1107  1392       4   273 2.27e-57    202.0     55.94 130.4275705 3DK6_A
    257     1074  1389      12   340 2.63e-57    204.0     50.45 130.2803665 4HW7_A
    258     1110  1403      65   371 2.81e-57    206.0     53.87 130.2141658 6V6Q_A
    259     1088  1389      10   315 3.08e-57    202.0     52.43 130.1224207 2OGV_A
    260     1107  1384       6   267 3.17e-57    201.0     56.47 130.0936187 2HZ0_A
    261     1110  1384      19   307 3.38e-57    202.0     53.58 130.0294746 6I83_A
    262     1107  1392       7   276 4.21e-57    201.0     55.94 129.8098877 2V7A_A
    263     1110  1403     472   778 4.26e-57    216.0     56.13 129.7980811 8JQI_B
    264     1110  1384      19   307 5.07e-57    202.0     53.58 129.6240095 2IVT_A
    265     1107  1392     118   387 5.37e-57    205.0     55.94 129.5665224 4XEY_A
    266     1110  1384      19   307 5.47e-57    202.0     53.58 129.5480717 2IVV_A
    267     1100  1390       1   282 8.24e-57    202.0     57.97 129.1383500 2QOC_A
    268     1109  1390       3   274 9.96e-57    201.0     58.25 128.9487732 6IN0_A
    269     1107  1392       5   274 9.98e-57    199.0     55.59 128.9467672 7W7Y_A
    270     1100  1390       1   282 1.01e-56    202.0     57.97 128.9348149 2QOB_A
    271     1110  1384       9   292 1.02e-56    201.0     53.66 128.9249626 6AGX_A
    272     1095  1384      26   326 1.12e-56    202.0     52.30 128.8314365 4HVS_A
    273     1096  1390      26   311 1.16e-56    203.0     57.53 128.7963452 2QOK_A
    274     1096  1390      26   311 1.25e-56    203.0     57.53 128.7216217 2QOO_A
    275     1107  1389      10   276 1.33e-56    199.0     55.83 128.6595863 8H7F_A
    276     1074  1389       1   329 1.38e-56    201.0     50.45 128.6226817 6T2W_A
    277     1079  1390      15   311 1.39e-56    202.0     56.33 128.6154615 2QOD_A
    278     1107  1389      11   277 1.43e-56    199.0     55.83 128.5870908 2GQG_A
    279     1107  1392     171   440 1.43e-56    205.0     55.94 128.5870908 8SSN_A
    280     1100  1390      18   299 1.46e-56    202.0     57.97 128.5663288 3DZQ_A
    281     1107  1389       5   271 1.49e-56    199.0     55.83 128.5459891 7W7X_A
    282     1110  1384      16   304 1.68e-56    200.0     53.24 128.4259714 6VHG_A
    283     1074  1389      12   340 1.77e-56    201.0     50.45 128.3737857 8CGC_A
    284     1116  1395      19   289 2.64e-56    199.0     56.64 127.9739863 5I9U_A
    285     1116  1395      18   288 2.82e-56    199.0     56.64 127.9080283 8XPV_A
    286     1096  1390      26   311 3.29e-56    202.0     57.53 127.7538776 2QOI_A
    287     1107  1392     213   482 3.77e-56    205.0     56.29 127.6176902 5MO4_A
    288     1079  1390      15   311 3.80e-56    201.0     56.33 127.6097641 2GSF_A
    289     1088  1389       3   321 3.85e-56    200.0     50.62 127.5966921 3LCO_A
    290     1079  1390      13   309 4.07e-56    201.0     56.33 127.5411222 3FXX_A
    291     1079  1390      15   311 4.30e-56    201.0     56.33 127.4861502 2QO7_A
    292     1107  1392     213   482 4.47e-56    205.0     56.29 127.4473768 1OPK_A
    293     1110  1384      39   327 4.52e-56    200.0     53.24 127.4362532 7RUN_A
    294     1096  1390      26   311 5.21e-56    201.0     57.19 127.2941854 2QOL_A
    295     1116  1395      46   316 5.69e-56    199.0     56.64 127.2060550 1MQB_A
    296     1110  1383      10   265 6.08e-56    197.0     55.11 127.1397605 8FLN_A
    297     1110  1384      60   348 6.53e-56    200.0     53.24 127.0683583 5FM2_A
    298     1109  1390      40   311 6.74e-56    201.0     58.25 127.0367053 2QOF_A
    299     1110  1384      19   307 7.25e-56    199.0     53.24 126.9637637 6NJA_A
    300     1110  1383       5   260 7.56e-56    197.0     55.11 126.9218940 4OTF_A
    301     1116  1428      27   325 8.35e-56    201.0     54.66 126.8225037 7KJA_A
    302     1116  1428      27   325 8.68e-56    201.0     54.66 126.7837437 7KJC_A
    303     1110  1383       2   257 8.79e-56    196.0     55.11 126.7711505 4NWM_A
    304     1116  1428      27   325 9.73e-56    201.0     54.97 126.6695513 7KJB_A
    305     1074  1389      12   351 1.18e-55    199.0     48.84 126.4766657 8JOT_A
    306     1107  1392     210   479 1.24e-55    204.0     55.94 126.4270687 2FO0_A
    307     1110  1383      17   272 1.31e-55    196.0     55.11 126.3721530 6NZM_A
    308     1107  1389       1   267 1.38e-55    196.0     55.83 126.3200966 4XLI_A
    309     1110  1383      15   270 1.43e-55    196.0     55.11 126.2845057 4YHF_A
    310     1110  1383      14   269 1.48e-55    196.0     55.11 126.2501380 6W7O_A
    311     1110  1383      16   271 1.51e-55    196.0     55.11 126.2300705 5P9F_A
    312     1096  1390      26   311 1.56e-55    200.0     57.19 126.1974943 2QON_A
    313     1110  1383      20   275 1.60e-55    196.0     55.11 126.1721765 4OT5_A
    314     1110  1383      20   275 1.71e-55    196.0     55.11 126.1056867 3GEN_A
    315     1110  1383       5   260 1.73e-55    196.0     55.11 126.0940587 6BIK_A
    316     1110  1383       8   263 1.76e-55    196.0     55.11 126.0768663 5ZZ4_A
    317     1110  1383      13   268 1.76e-55    196.0     55.11 126.0768663 6TFP_A
    318     1110  1383       6   261 1.79e-55    196.0     55.11 126.0599645 6J6M_A
    319     1110  1383       8   263 1.82e-55    196.0     55.11 126.0433436 5FBN_C
    320     1110  1383      12   267 1.82e-55    196.0     55.11 126.0433436 5J87_A
    321     1110  1383       5   260 1.84e-55    196.0     55.11 126.0324145 3OCT_A
    322     1110  1383       7   262 1.85e-55    196.0     55.11 126.0269945 7KXQ_A
    323     1110  1383       5   260 1.91e-55    196.0     55.11 125.9950769 5XYZ_A
    324     1110  1383       4   259 1.91e-55    196.0     55.11 125.9950769 6S90_A
    325     1110  1383       4   259 1.95e-55    196.0     55.11 125.9743507 3P08_A
    326     1110  1383       3   258 1.99e-55    196.0     55.11 125.9540455 8YVV_A
    327     1110  1383      20   275 1.99e-55    196.0     55.11 125.9540455 4Z3V_A
    328     1110  1383       8   263 2.00e-55    196.0     55.11 125.9490329 4ZLY_A
    329     1110  1383      11   266 2.01e-55    196.0     55.11 125.9440454 3PIX_A
    330     1110  1383      10   265 2.12e-55    196.0     55.11 125.8907640 8FLL_A
    331     1110  1383       5   260 2.18e-55    196.0     55.11 125.8628552 3OCS_A
    332     1095  1384      26   326 2.20e-55    198.0     51.97 125.8537228 7KHK_A
    333     1110  1383       6   261 2.22e-55    196.0     55.11 125.8446729 6O8I_A
    334     1095  1384      26   326 2.29e-55    198.0     51.97 125.8136283 7KHJ_A
    335     1110  1383       4   259 2.32e-55    195.0     55.11 125.8006129 5BPY_A
    336     1110  1383       5   260 2.32e-55    195.0     55.11 125.8006129 6NFI_A
    337     1110  1383      30   285 2.34e-55    196.0     55.11 125.7920292 6VXQ_A
    338     1110  1383       2   257 2.35e-55    195.0     55.11 125.7877648 6AUB_A
    339     1110  1383       5   260 2.54e-55    195.0     55.11 125.7100160 4RX5_A
    340     1107  1389      25   291 2.84e-55    196.0     54.77 125.5983761 2XYN_A
    341     1109  1399      14   296 3.20e-55    196.0     54.42 125.4790293 3ZFX_A
    342     1110  1383      27   282 3.31e-55    196.0     55.11 125.4452319 6E4F_A
    343     1107  1392     252   521 3.44e-55    204.0     55.94 125.4067086 1OPL_A
    344     1095  1384      20   318 3.67e-55    197.0     50.99 125.3419885 8PQG_A
    345     1110  1384      19   307 3.75e-55    196.0     52.90 125.3204243 6NE7_A
    346     1110  1383       5   260 4.07e-55    195.0     55.11 125.2385371 6XE4_A
    347     1110  1384      19   307 4.17e-55    196.0     52.90 125.2142641 4CKI_A
    348     1110  1383      15   270 4.28e-55    195.0     55.47 125.1882271 9ZLJ_A
    349     1109  1399      21   303 4.28e-55    196.0     55.44 125.1882271 5MJA_A
    350     1110  1383      13   268 4.52e-55    195.0     55.47 125.1336681 6MNY_A
    351     1110  1383       3   258 4.64e-55    194.0     54.01 125.1074657 4Y95_A
    352     1109  1399      17   299 4.70e-55    196.0     54.42 125.0946176 6UMW_A
    353     1114  1383       4   255 5.38e-55    194.0     55.19 124.9594917 1K2P_A
    354     1107  1389       5   271 6.68e-55    194.0     55.12 124.7430621 9KS5_A
    355     1095  1384      21   319 8.06e-55    196.0     50.66 124.5552666 6GQK_A
    356     1095  1384      21   319 8.06e-55    196.0     50.66 124.5552666 6GQJ_A
    357     1095  1384      20   318 8.06e-55    196.0     50.66 124.5552666 8PQ9_A
    358     1081  1376       4   315 9.12e-55    196.0     51.75 124.4317103 6JQR_A
    359     1071  1384       3   334 9.79e-55    197.0     50.60 124.3608187 6A32_A
    360     1107  1376       1   286 9.94e-55    195.0     53.63 124.3456131 4XUF_A
    361     1110  1383       2   257 1.05e-54    194.0     54.74 124.2908049 8FD9_A
    362     1081  1376      11   322 1.24e-54    196.0     51.75 124.1244836 1RJB_A
    363     1081  1376      13   324 1.28e-54    196.0     51.75 124.0927349 8XB1_A
    364     1109  1390       2   275 1.31e-54    194.0     55.09 124.0695679 7KPL_A
    365     1081  1376      14   325 1.48e-54    196.0     51.75 123.9475529 5X02_A
    366     1110  1383       3   258 1.48e-54    193.0     54.74 123.9475529 6AUA_A
    367     1110  1383       8   263 1.60e-54    193.0     54.74 123.8695914 8GC8_A
    368     1071  1384       3   334 1.71e-54    196.0     50.30 123.8031017 8XRR_A
    369     1110  1384      38   330 1.72e-54    196.0     52.70 123.7972707 8PQH_A
    370     1110  1384      41   333 1.79e-54    196.0     52.70 123.7573794 9GZH_A
    371     1071  1384      22   353 2.64e-54    196.0     50.60 123.3688161 6JOI_A
    372     1071  1384       3   334 2.73e-54    196.0     50.30 123.3352934 5GRN_A
    373     1116  1380      36   291 2.84e-54    193.0     57.20 123.2957910 4P2K_A
    374     1110  1383      20   275 3.28e-54    192.0     54.74 123.1517516 3K54_A
    375     1081  1376      37   348 3.42e-54    196.0     51.75 123.1099545 6IL3_A
    376     1116  1384      45   304 3.51e-54    193.0     57.09 123.0839790 5EK7_A
    377     1110  1384      38   330 4.38e-54    195.0     52.36 122.8625463 8PQJ_A
    378     1110  1383      16   271 7.33e-54    191.0     55.11 122.3476195 8S9F_A
    379     1110  1383     183   438 8.53e-54    197.0     55.47 122.1960057 4XI2_A
    380     1109  1399      21   303 9.35e-54    192.0     55.10 122.1042187 5MJB_A
    381     1095  1377      19   288 3.02e-53    191.0     56.54 120.9317531 4EBV_A
    382      683   984       6   316 3.04e-53    191.0     65.92 120.9251524 7NX0_B
    383     1116  1380      36   291 3.80e-53    190.0     56.83 120.7020089 4TRL_A
    384     1115  1383       8   258 3.97e-53    189.0     56.88 120.6582438 3MIY_A
    385     1108  1379       3   293 5.12e-53    190.0     53.74 120.4038555 6FER_A
    386     1110  1383     184   439 5.97e-53    194.0     54.38 120.2502630 4Y93_A
    387     1109  1392       8   277 7.54e-53    189.0     58.10 120.0167877 8E4T_A
    388     1115  1383      28   278 7.63e-53    189.0     57.25 120.0049221 3QGW_A
    389     1115  1383       8   258 9.00e-53    188.0     56.88 119.8397854 3V5J_A
    390     1115  1383       6   256 9.61e-53    188.0     56.88 119.7742057 1SM2_A
    391     1115  1383      11   261 1.16e-52    187.0     56.88 119.5860048 4HCT_A
    392     1109  1391       3   275 1.18e-52    188.0     56.64 119.5689104 2XYU_A
    393     1110  1377      11   265 1.54e-52    188.0     57.84 119.3026424 1MP8_A
    394     1122  1383      30   283 1.64e-52    188.0     56.77 119.2397286 2WD1_A
    395     1110  1377       8   262 1.64e-52    187.0     57.84 119.2397286 2ETM_A
    396     1110  1377       9   263 1.67e-52    187.0     57.84 119.2216012 4GU9_A
    397     1110  1377       8   262 1.71e-52    187.0     57.84 119.1979315 6I8Z_A
    398     1109  1391       9   281 1.73e-52    188.0     56.64 119.1863034 2Y6M_A
    399     1110  1377       9   263 1.74e-52    187.0     57.84 119.1805397 3PXK_A
    400     1110  1377       3   257 1.77e-52    187.0     57.84 119.1634453 3BZ3_A
    401     1122  1383      30   283 1.78e-52    188.0     56.77 119.1578115 4R1V_A
    402     1110  1377       7   261 1.82e-52    187.0     57.84 119.1355883 9SDI_A
    403     1122  1383      34   287 1.87e-52    188.0     56.77 119.1084864 8AN8_A
    404     1122  1383      37   290 1.87e-52    188.0     56.77 119.1084864 7B3Q_A
    405     1115  1383       9   259 1.91e-52    187.0     56.88 119.0873216 3T9T_A
    406     1110  1377       2   256 1.92e-52    187.0     57.84 119.0820996 7PI4_d
    407     1108  1383       3   284 1.92e-52    188.0     52.63 119.0820996 3ZZW_A
    408     1122  1383      47   300 1.93e-52    189.0     56.77 119.0769048 6SD9_A
    409     1122  1383      25   278 2.02e-52    187.0     56.77 119.0313273 4KNB_A
    410     1110  1377       6   260 2.10e-52    187.0     57.84 118.9924875 2J0M_B
    411     1110  1383     194   449 2.25e-52    193.0     54.74 118.9234946 8S93_A
    412     1122  1383      37   290 2.47e-52    188.0     56.77 118.8302067 3I5N_A
    413     1122  1383      38   291 2.50e-52    188.0     56.77 118.8181341 3Q6U_A
    414     1122  1383      36   289 2.57e-52    188.0     56.77 118.7905189 3LQ8_A
    415     1122  1383      33   286 2.60e-52    188.0     56.77 118.7789134 3F66_A
    416     1122  1383      38   291 2.85e-52    188.0     56.77 118.6871058 2RFN_A
    417     1106  1383      18   301 3.33e-52    188.0     52.61 118.5314525 4GT4_A
    418     1110  1377       6   260 3.47e-52    187.0     57.84 118.4902702 2JKM_A
    419     1122  1383      67   320 3.49e-52    189.0     56.77 118.4845231 5UAB_A
    420     1122  1383      56   309 3.65e-52    188.0     56.77 118.4396977 2G15_A
    421     1122  1383      57   310 3.72e-52    188.0     56.77 118.4207012 4GG5_A
    422     1122  1383      35   288 3.74e-52    187.0     56.77 118.4153392 2WGJ_A
    423     1109  1390      17   288 3.74e-52    187.0     56.49 118.4153392 2R2P_A
    424     1122  1383      55   308 3.87e-52    188.0     56.77 118.3811703 4EEV_A
    425     1110  1377       6   260 4.08e-52    186.0     57.84 118.3283278 2JKK_A
    426     1106  1384      11   271 4.41e-52    186.0     54.39 118.2505501 3BYS_A
    427     1110  1376       4   252 4.58e-52    186.0     55.31 118.2127258 2OG8_A
    428     1106  1384      10   270 4.81e-52    186.0     54.39 118.1637278 2OFV_A
    429     1122  1383      60   313 4.92e-52    188.0     56.77 118.1411163 3VW8_A
    430     1106  1384       5   265 5.02e-52    186.0     54.39 118.1209949 2OF2_A
    431     1106  1384      15   275 6.40e-52    186.0     54.39 117.8781268 2PL0_A
    432     1122  1383      47   300 8.70e-52    187.0     56.77 117.5711018 8VI1_A
    433     1122  1383      47   300 1.03e-51    186.0     56.77 117.4022809 9SZJ_A
    434     1122  1383      38   291 1.04e-51    186.0     56.77 117.3926190 9C1R_A
    435     1122  1383      28   281 1.07e-51    186.0     56.77 117.3641811 5HLW_A
    436     1122  1383      34   287 1.37e-51    186.0     56.77 117.1170290 8AW1_A
    437     1115  1383       8   258 1.62e-51    184.0     56.51 116.9494136 4KIO_A
    438     1110  1384       5   261 1.95e-51    184.0     54.80 116.7640104 3MPM_A
    439     1109  1391      24   296 1.99e-51    186.0     56.29 116.7437051 2HEL_A
    440     1122  1383      34   287 2.01e-51    185.0     56.39 116.7337050 8AU5_A
    441     1095  1384       3   299 2.19e-51    185.0     52.82 116.6479382 6HH1_A
    442     1106  1384       1   261 2.55e-51    184.0     57.50 116.4957464 2DQ7_X
    443     1122  1383      37   290 3.27e-51    185.0     56.77 116.2470498 3Q6W_A
    444     1122  1383      38   291 3.44e-51    185.0     56.77 116.1963683 4IWD_A
    445     1122  1383      34   287 3.51e-51    184.0     56.77 116.1762237 8AU3_A
    446     1122  1383      34   287 3.54e-51    184.0     56.39 116.1677130 8ANS_A
    447     1122  1383      47   300 3.74e-51    185.0     56.39 116.1127541 6SDC_A
    448     1110  1383     396   651 3.93e-51    194.0     54.74 116.0632003 8GMB_A
    449     1110  1384       4   260 5.15e-51    183.0     52.73 115.7928430 3SXR_A
    450     1110  1384      14   270 5.44e-51    183.0     52.73 115.7380607 6I99_A
    451     1106  1384       5   265 6.44e-51    183.0     54.04 115.5693112 3BYO_A
    452     1106  1384       6   266 7.03e-51    182.0     54.04 115.4816530 3BYM_A
    453     1106  1384      13   273 7.14e-51    183.0     54.04 115.4661270 3KXZ_A
    454     1109  1399      14   296 7.21e-51    184.0     53.40 115.4563708 3ZFM_A
    455     1106  1384       5   265 8.39e-51    182.0     54.04 115.3047992 1QPC_A
    456     1106  1384      11   271 8.82e-51    183.0     54.04 115.2548179 2ZM1_A
    457     1106  1384       7   267 9.03e-51    182.0     54.04 115.2312874 2OFU_A
    458     1110  1376       8   257 9.32e-51    182.0     55.97 115.1996771 5XY1_A
    459     1122  1383      38   291 1.01e-50    184.0     56.77 115.1193043 3CE3_A
    460     1106  1384      14   274 1.04e-50    183.0     54.04 115.0900339 6PDJ_A
    461     1106  1376       5   258 1.05e-50    182.0     55.51 115.0804645 3A4O_X
    462     1106  1384      14   274 1.08e-50    182.0     54.04 115.0522936 3KMM_A
    463     1122  1383      39   292 1.19e-50    184.0     56.77 114.9553013 3DKC_A
    464     1122  1383      36   289 1.23e-50    183.0     56.77 114.9222405 1R0P_A
    465     1122  1383      38   291 1.30e-50    183.0     56.77 114.8668904 3QTI_A
    466     1106  1384       5   265 1.32e-50    182.0     54.04 114.8516229 1QPD_A
    467     1122  1383      43   296 1.55e-50    183.0     56.77 114.6909997 3A4P_A
    468     1109  1391      28   300 1.71e-50    182.0     56.29 114.5927613 7EEF_A
    469     1110  1376       8   257 1.76e-50    182.0     55.97 114.5639408 2ZV7_A
    470     1111  1377       9   262 1.99e-50    182.0     55.81 114.4411200 3CC6_A
    471     1111  1377      10   263 2.05e-50    182.0     55.81 114.4114149 5TO8_A
    472     1111  1377       5   258 2.11e-50    181.0     55.81 114.3825667 3ET7_A
    473     1109  1399      28   310 2.43e-50    182.0     53.40 114.2413634 1JPA_A
    474     1111  1377      21   274 2.61e-50    182.0     55.81 114.1699044 4H1J_A
    475     1109  1391      28   300 2.84e-50    182.0     55.94 114.0854506 7EEC_A
    476     1122  1383      36   289 3.27e-50    182.0     56.77 113.9444647 5HOA_A
    477     1122  1397      33   310 3.47e-50    182.0     53.31 113.8851001 1FVR_A
    478     1095  1384       3   303 3.63e-50    182.0     50.66 113.8400220 1T46_A
    479     1095  1384       5   305 3.80e-50    182.0     50.66 113.7942536 4U0I_A
    480     1115  1397      16   300 3.86e-50    182.0     52.72 113.7785875 2OO8_X
    481     1122  1383      97   350 3.97e-50    184.0     56.77 113.7504886 3C1X_A
    482     1095  1384       2   302 4.07e-50    182.0     51.48 113.7256117 6MOB_A
    483     1110  1377       6   260 4.47e-50    181.0     56.72 113.6318662 2J0L_A
    484     1095  1384      17   317 4.59e-50    182.0     51.80 113.6053746 7ZW8_A
    485     1109  1391      28   300 4.86e-50    181.0     55.59 113.5482162 7EED_A
    486     1109  1391      38   310 5.30e-50    182.0     55.94 113.4615478 2REI_A
    487     1073  1384       2   321 5.85e-50    182.0     50.46 113.3628130 1T45_A
    488     1073  1384       7   326 6.33e-50    182.0     50.46 113.2839544 3G0E_A
    489     1122  1383      36   289 8.94e-50    181.0     56.39 112.9387191 5HOR_A
    490     1120  1384      27   283 9.10e-50    180.0     54.65 112.9209802 3PLS_A
    491     1109  1399       2   284 9.39e-50    180.0     53.06 112.8896094 2HEN_A
    492     1106  1383       2   262 1.23e-49    179.0     53.76 112.6196554 6CZ3_A
    493     1110  1379      28   325 1.25e-49    181.0     51.83 112.6035260 7AYM_A
    494     1122  1397      30   307 1.31e-49    181.0     53.31 112.5566424 2WQB_A
    495     1110  1384       2   258 1.37e-49    179.0     52.00 112.5118588 8X2A_A
    496     1122  1383      39   292 1.45e-49    181.0     56.39 112.4551060 3DKG_A
    497     1122  1397      29   306 1.75e-49    180.0     53.31 112.2670538 4X3J_A
    498     1110  1383      23   301 2.34e-49    179.0     52.48 111.9765186 3CJF_A
    499     1073  1384       2   321 2.41e-49    180.0     50.15 111.9470428 6ITV_A
    500     1110  1384      35   319 2.85e-49    180.0     51.39 111.7793506 1PKG_A
    501     1110  1383       2   258 3.13e-49    177.0     53.82 111.6856366 5DA3_A
    502     1110  1383       2   258 3.29e-49    178.0     53.82 111.6357820 5D7V_A
    503     1110  1383       2   258 3.42e-49    177.0     53.82 111.5970290 5H2U_A
    504     1104  1390       4   282 3.47e-49    178.0     52.41 111.5825150 4AW5_A
    505     1106  1379       7   262 4.48e-49    177.0     54.91 111.3270465 2HK5_A
    506     1106  1379      18   273 4.58e-49    178.0     54.91 111.3049706 5ZJ6_A
    507     1073  1384       7   326 5.45e-49    179.0     50.15 111.1310539 3G0F_A
    508     1110  1383      23   301 8.79e-49    178.0     52.84 110.6530548 3CJG_A
    509     1110  1383      15   297 9.05e-49    178.0     51.75 110.6239048 3WZD_A
    510     1109  1390      14   287 9.85e-49    177.0     52.98 110.5391981 2YN8_A
    511     1110  1377     388   642 1.02e-48    187.0     57.84 110.5042818 6TY3_A
    512     1110  1377     386   640 1.13e-48    187.0     57.84 110.4018668 2J0K_A
    513     1109  1390      14   287 1.25e-48    177.0     52.98 110.3009409 3ZEW_A
    514     1110  1377     386   640 1.34e-48    187.0     57.84 110.2314148 2J0J_A
    515     1109  1390      13   286 1.41e-48    177.0     52.98 110.1804948 6FNI_A
    516     1110  1383      25   307 1.45e-48    177.0     52.45 110.1525209 3VNT_A
    517     1110  1377      17   306 1.56e-48    177.0     51.86 110.0793986 7FEH_A
    518     1106  1384      10   270 1.57e-48    176.0     55.87 110.0730088 4MXY_A
    519     1106  1383       2   262 1.59e-48    176.0     53.41 110.0603504 6CZ2_A
    520     1106  1384      10   270 1.65e-48    176.0     55.00 110.0233092 3GEQ_A
    521     1110  1377      12   301 1.66e-48    177.0     51.86 110.0172669 5SAU_A
    522     1110  1383      23   305 1.79e-48    177.0     51.75 109.9418688 2XIR_A
    523     1110  1383      14   296 2.01e-48    177.0     51.40 109.8259497 3EWH_A
    524     1109  1390      11   284 2.12e-48    177.0     52.98 109.7726684 2VWU_A
    525     1110  1383      14   296 2.32e-48    177.0     51.40 109.6825173 3U6J_A
    526     1110  1383      23   305 2.37e-48    177.0     51.75 109.6611945 6GQO_A
    527     1114  1385      12   261 2.66e-48    175.0     56.41 109.5457583 3D7T_A
    528     1110  1377       6   301 2.89e-48    177.0     51.67 109.4628280 3ZOS_A
    529     1106  1384       3   263 3.69e-48    175.0     55.52 109.2184580 2BDF_A
    530     1110  1383      60   342 3.95e-48    177.0     51.75 109.1503689 4AGC_A
    531     1110  1377      15   310 4.04e-48    176.0     51.67 109.1278398 5BVK_A
    532     1106  1384       7   267 4.18e-48    175.0     55.52 109.0937732 8JF3_A
    533     1106  1384      11   271 4.22e-48    175.0     55.36 109.0842493 7NG7_A
    534     1106  1384      10   270 4.30e-48    175.0     55.00 109.0654694 3G6H_A
    535     1106  1384       1   261 4.43e-48    175.0     55.52 109.0356849 8HAQ_A
    536     1110  1377      28   323 4.73e-48    177.0     51.67 108.9701593 5FDP_A
    537     1106  1384      10   270 4.73e-48    175.0     55.36 108.9701593 4MXO_A
    538     1107  1384       1   260 4.83e-48    175.0     55.71 108.9492380 6E6E_A
    539     1106  1384      17   277 5.00e-48    175.0     55.36 108.9146466 7OTE_A
    540     1114  1385       6   255 5.95e-48    174.0     56.41 108.7406932 3D7U_A
    541     1110  1377      42   337 6.90e-48    177.0     51.67 108.5925631 6BRJ_A
    542     1114  1385      21   270 7.31e-48    174.0     56.41 108.5348412 1BYG_A
    543     1106  1384      10   270 7.44e-48    174.0     55.36 108.5172136 4MXX_A
    544     1122  1383    1084  1337 7.68e-48    190.0     56.77 108.4854649 7MO7_B
    545     1110  1377      41   336 9.04e-48    176.0     51.67 108.3224253 6Y23_A
    546     1106  1384      10   270 9.46e-48    174.0     54.64 108.2770121 2OIQ_A
    547     1106  1384       1   261 9.56e-48    174.0     54.64 108.2664967 3D7U_B
    548     1106  1384      10   270 1.18e-47    174.0     54.64 108.0559849 3OEZ_A
    549     1106  1384      10   270 1.19e-47    174.0     55.00 108.0475461 2QI8_A
    550     1106  1384      10   270 1.20e-47    174.0     54.64 108.0391778 3SVV_A
    551     1110  1384       3   259 1.64e-47    173.0     55.07 107.7268031 3U4W_A
    552     1106  1384      10   270 1.87e-47    173.0     55.16 107.5955609 9NS1_A
    553     1109  1390      14   287 2.02e-47    174.0     52.63 107.5184019 3ZFY_A
    554     1110  1383      23   305 2.34e-47    174.0     51.40 107.3713484 1VR2_A
    555     1106  1384       7   267 2.36e-47    173.0     55.16 107.3628378 1YOL_A
    556     1107  1379     181   435 2.36e-47    178.0     55.11 107.3628378 1QCF_A
    557     1107  1379     181   435 2.55e-47    178.0     55.11 107.2854060 9BYJ_A
    558     1106  1384       2   262 2.60e-47    172.0     54.64 107.2659879 4MCV_A
    559     1110  1383      25   305 2.62e-47    174.0     52.11 107.2583251 3C7Q_A
    560     1106  1384       1   261 2.73e-47    172.0     54.64 107.2171978 4LGH_A
    561     1106  1384      10   270 2.99e-47    173.0     54.64 107.1262260 2HWO_A
    562     1106  1384      10   270 3.56e-47    172.0     54.29 106.9517388 5T0P_A
    563     1106  1384      10   270 4.31e-47    172.0     55.16 106.7605615 9NS0_A
    564     1106  1384      10   270 4.61e-47    172.0     54.29 106.6932715 5SWH_A
    565     1106  1384      10   270 5.28e-47    172.0     54.64 106.5575733 3DQW_A
    566     1098  1375      13   294 6.88e-47    174.0     53.26 106.2928807 7ZVS_A
    567     1107  1384     202   461 9.09e-47    177.0     55.56 106.0143245 9BT8_C
    568     1106  1384       7   267 9.68e-47    171.0     55.16 105.9514375 1YOJ_A
    569     1107  1384     176   435 9.74e-47    176.0     55.56 105.9452583 9IRL_A
    570     1107  1384     177   436 9.96e-47    176.0     55.56 105.9229223 1FMK_A
    571     1107  1384     177   436 1.09e-46    176.0     55.56 105.8327366 1Y57_A
    572     1107  1384     261   520 1.45e-46    178.0     55.56 105.5473507 8JN8_A
    573     1110  1383      14   296 1.47e-46    172.0     51.05 105.5336519 2P2I_A
    574     1107  1384     260   519 1.56e-46    178.0     55.56 105.4742285 2H8H_A
    575     1110  1383      24   305 1.90e-46    171.0     51.23 105.2770604 2OH4_A
    576     1107  1384     175   434 2.60e-46    175.0     55.56 104.9634028 4K11_A
    577     1110  1383      23   305 2.87e-46    171.0     51.05 104.8646022 1YWN_A
    578     1107  1384       1   260 2.87e-46    169.0     55.00 104.8646022 1YI6_A
    579     1110  1383      14   296 3.02e-46    171.0     50.70 104.8136574 2P2H_A
    580     1107  1384     177   436 3.06e-46    175.0     55.56 104.8004994 1KSW_A
    581     1114  1385     193   442 5.36e-46    174.0     56.04 104.2399503 1K9A_A
    582     1107  1384     176   435 5.53e-46    174.0     55.20 104.2087265 8XN8_A
    583     1107  1384     180   439 6.62e-46    174.0     55.20 104.0288189 6F3F_A
    584     1107  1384     178   437 2.08e-45    172.0     53.17 102.8839613 2PTK_A
    585     1113  1384       1   254 3.21e-45    166.0     54.58 102.4500582 4LGG_A
    586     1107  1379     175   419 7.63e-45    171.0     53.65 101.5842413 1AD5_A
    587     1109  1399      44   324 9.01e-45    167.0     52.36 101.4179941 3KUL_A
    588     1100  1381      28   304 2.73e-44    165.0     52.11 100.3094425 6TUA_A
    589     1122  1386      18   270 4.86e-44    164.0     54.14  99.7327057 1U59_A
    590     1109  1399      44   324 1.10e-43    164.0     52.03  98.9158488 3KUL_B
    591     1106  1384     182   442 1.30e-41    161.0     52.14  94.1436245 7UY0_A
    592     1106  1384     182   442 1.33e-41    161.0     52.14  94.1208099 7UY0_B
    593     1103  1386     317   596 3.30e-41    164.0     52.56  93.2120663 2OZO_A
    594     1103  1386     317   596 5.53e-41    163.0     52.56  92.6958010 4K2R_A
    595     1111  1379      17   277 1.39e-40    154.0     52.16  91.7741000 7KP6_A
    596     1111  1379      17   277 1.43e-40    154.0     52.16  91.7457293 8FE9_A
    597     1113  1383       5   264 1.64e-40    153.0     53.28  91.6087075 4DFL_A
    598     1113  1383      15   274 1.65e-40    153.0     53.28  91.6026284 4RX7_A
    599     1111  1379       9   269 1.68e-40    153.0     51.80  91.5846099 4HZR_A
    600     1113  1383      15   274 1.69e-40    153.0     53.28  91.5786752 4RX9_A
    601     1113  1383       5   264 1.75e-40    153.0     53.28  91.5437879 4PV0_A
    602     1111  1394      21   291 1.80e-40    153.0     51.92  91.5156171 3EMG_A
    603     1114  1379      18   275 1.94e-40    153.0     52.36  91.4407157 6VQM_A
    604     1113  1383       5   264 2.06e-40    153.0     53.28  91.3806977 6VOV_A
    605     1114  1379       8   265 2.31e-40    152.0     52.00  91.2661562 3EQP_A
    606     1114  1379      18   275 2.34e-40    153.0     52.36  91.2532528 1U46_A
    607     1114  1379       8   265 2.36e-40    152.0     52.00  91.2447421 5ZXB_A
    608     1113  1383       3   262 2.36e-40    152.0     53.28  91.2447421 4F4P_A
    609     1114  1379       8   265 2.46e-40    152.0     52.00  91.2032424 4ID7_A
    610     1113  1383      12   271 2.48e-40    152.0     53.28  91.1951452 8X5K_A
    611     1113  1383      15   274 2.57e-40    153.0     53.28  91.1594978 4PX6_A
    612     1113  1383      15   274 2.66e-40    153.0     53.28  91.1250776 5TR6_A
    613     1113  1383      15   274 2.71e-40    153.0     53.28  91.1064551 5Y5T_A
    614     1113  1383      12   271 3.15e-40    152.0     53.28  90.9560013 4RSS_A
    615     1113  1383       9   268 3.32e-40    152.0     53.28  90.9034389 3SRV_B
    616     1113  1383      15   274 4.07e-40    152.0     53.28  90.6997607 1XBA_A
    617     1113  1383      13   272 4.23e-40    152.0     53.28  90.6612017 4YJO_A
    618     1113  1383      25   284 5.78e-40    152.0     53.28  90.3490000 3TUB_A
    619     1113  1383      25   284 6.77e-40    152.0     53.28  90.1909026 3TUC_A
    620     1114  1379      12   269 7.10e-40    153.0     52.00  90.1433089 4HZS_A
    621     1119  1390      25   285 8.13e-40    152.0     51.64  90.0078428 7JXH_A
    622     1108  1390      11   282 8.78e-40    153.0     51.05  89.9309273 3PP0_A
    623     1108  1390      10   281 8.83e-40    152.0     51.05  89.9252487 7PCD_A
    624     1111  1394       7   277 1.60e-39    150.0     51.57  89.3308150 3SRV_A
    625     1114  1379      18   275 2.74e-39    150.0     52.00  88.7928607 1U54_A
    626     1114  1379       8   265 2.88e-39    149.0     51.64  88.7430283 4EWH_A
    627     1108  1390      14   282 3.40e-39    151.0     52.10  88.5770432 8HV4_A
    628     1108  1390      12   280 3.49e-39    150.0     52.10  88.5509169 9S3X_A
    629     1108  1390      14   282 3.56e-39    151.0     52.10  88.5310581 6LUB_A
    630     1113  1383       8   267 3.59e-39    149.0     52.92  88.5226664 6HM6_A
    631     1108  1390      15   283 3.72e-39    150.0     52.10  88.4870950 9D3V_A
    632     1108  1390      16   284 4.07e-39    150.0     52.10  88.3971756 5XGN_A
    633     1108  1390      14   282 4.18e-39    150.0     52.10  88.3705074 8WD4_A
    634     1108  1390      15   283 4.41e-39    150.0     52.10  88.3169439 8H7X_A
    635     1099  1390      23   303 4.75e-39    150.0     50.00  88.2426740 2R4B_A
    636     1108  1390      16   284 5.58e-39    149.0     52.10  88.0816299 5GNK_A
    637     1108  1390      16   284 1.02e-38    149.0     51.75  87.4784309 9XU9_A
    638     1108  1390      16   284 1.11e-38    149.0     52.10  87.3938735 5GMP_A
    639     1108  1390      13   281 1.14e-38    149.0     52.10  87.3672053 8HY7_A
    640     1108  1390      14   282 1.18e-38    149.0     52.10  87.3327191 4RJ4_A
    641     1108  1390      15   283 1.21e-38    149.0     52.10  87.3076132 4G5P_A
    642     1108  1390      16   284 1.24e-38    149.0     51.75  87.2831222 9JQ1_A
    643     1108  1390      12   283 1.25e-38    150.0     51.75  87.2750900 5CNN_A
    644     1108  1390      11   279 1.28e-38    149.0     52.10  87.2513735 6S9B_A
    645     1108  1390      14   282 1.33e-38    149.0     52.10  87.2130546 4I24_A
    646     1108  1390      16   284 1.34e-38    149.0     52.10  87.2055639 3IKA_A
    647     1108  1390      18   286 1.39e-38    149.0     52.10  87.1689298 5Y9T_A
    648     1108  1390      34   302 1.42e-38    150.0     52.10  87.1475767 5ZWJ_A
    649     1108  1390      14   282 1.43e-38    149.0     52.10  87.1405591 6S9C_A
    650     1108  1390      13   281 1.45e-38    149.0     52.10  87.1266700 5FEE_A
    651     1108  1390      13   281 1.48e-38    149.0     52.10  87.1061914 2JIU_A
    652     1108  1390      12   280 1.57e-38    149.0     52.10  87.0471579 2JIT_A
    653     1108  1390      15   283 1.63e-38    149.0     51.75  87.0096535 4WKQ_A
    654     1108  1390      12   280 1.63e-38    149.0     51.75  87.0096535 2J5E_A
    655     1108  1390      16   284 1.70e-38    149.0     52.10  86.9676053 4ZSE_A
    656     1108  1390      18   286 1.70e-38    149.0     52.10  86.9676053 6TFU_A
    657     1108  1390      12   280 1.79e-38    149.0     52.10  86.9160179 5J9Z_A
    658     1108  1390      11   279 1.90e-38    149.0     52.10  86.8563796 5J9Y_A
    659     1100  1390       1   280 2.00e-38    149.0     49.83  86.8050864 3BBT_B
    660     1108  1390      13   281 2.14e-38    149.0     52.10  86.7374277 6V5N_A
    661     1111  1394      12   282 2.21e-38    147.0     50.35  86.7052410 8RRQ_A
    662     1111  1394      11   281 2.35e-38    147.0     50.35  86.6438182 4YJQ_A
    663     1108  1390      12   280 2.44e-38    148.0     52.10  86.6062355 6P1D_A
    664     1108  1390      16   284 2.56e-38    148.0     51.75  86.5582263 4ZJV_A
    665     1108  1390      17   285 2.83e-38    148.0     51.75  86.4579568 4TKS_A
    666     1108  1390      14   282 3.10e-38    148.0     51.75  86.3668314 5CAV_A
    667     1108  1390      19   287 3.21e-38    148.0     51.75  86.3319626 3VJO_A
    668     1108  1390      31   299 3.27e-38    149.0     51.75  86.3134435 7AEM_A
    669     1108  1390      16   284 3.28e-38    148.0     51.75  86.3103901 8HV2_A
    670     1100  1390       1   277 3.28e-38    148.0     51.36  86.3103901 2RFD_A
    671     1108  1390      15   283 3.32e-38    148.0     51.75  86.2982688 4LI5_A
    672     1108  1390      18   286 3.34e-38    148.0     51.75  86.2922627 1M14_A
    673     1108  1390      15   283 3.39e-38    148.0     51.75  86.2774036 4G5J_A
    674     1108  1390      13   281 3.62e-38    148.0     51.75  86.2117595 5FED_A
    675     1108  1390      14   282 3.67e-38    148.0     51.75  86.1980419 4I23_A
    676     1108  1390      15   283 3.73e-38    148.0     51.75  86.1818253 2GS2_A
    677     1108  1390      12   280 3.85e-38    148.0     51.75  86.1501604 2ITW_A
    678     1108  1390      14   282 3.89e-38    148.0     51.75  86.1398244 9FZR_A
    679     1108  1390      14   282 3.93e-38    148.0     51.75  86.1295941 4I21_A
    680     1108  1390      16   284 4.01e-38    148.0     51.75  86.1094423 4LL0_A
    681     1108  1390      15   283 4.06e-38    148.0     51.75  86.0970506 9KLW_A
    682     1111  1394      23   293 4.09e-38    147.0     50.35  86.0896886 5C26_A
    683     1108  1390      12   280 4.21e-38    147.0     51.75  86.0607709 6JZ0_A
    684     1221  1383     196   356 4.23e-38    149.0     62.80  86.0560315 3HNG_A
    685     1108  1390      13   281 4.25e-38    147.0     51.75  86.0513146 7UKV_A
    686     1108  1390      14   282 4.30e-38    147.0     51.75  86.0396185 4JQ7_A
    687     1108  1390      11   279 4.41e-38    147.0     51.75  86.0143588 8A27_A
    688     1108  1390      13   281 4.46e-38    147.0     51.75  86.0030848 9H42_A
    689     1108  1390       6   274 4.52e-38    147.0     51.75  85.9897215 2RGP_A
    690     1108  1390      12   280 4.66e-38    147.0     51.75  85.9592181 9N6G_A
    691     1111  1394     366   636 4.83e-38    154.0     51.92  85.9233871 4FL2_A
    692     1108  1390      15   283 5.01e-38    147.0     51.75  85.8867976 8PO3_A
    693     1108  1390      12   280 5.22e-38    147.0     51.75  85.8457361 3LZB_A
    694     1108  1390      13   281 5.56e-38    147.0     51.75  85.7826354 8PO4_A
    695     1108  1390      23   291 5.62e-38    147.0     51.75  85.7719019 9BY4_A
    696     1108  1390      11   279 5.80e-38    147.0     51.75  85.7403756 8KFQ_A
    697     1108  1390      13   281 5.93e-38    147.0     51.75  85.7182093 7OXB_A
    698     1108  1390      30   298 5.98e-38    148.0     51.75  85.7098130 4RIW_B
    699     1111  1394     365   635 5.99e-38    154.0     51.92  85.7081421 4FL3_A
    700     1108  1390      31   299 6.01e-38    148.0     51.75  85.7048088 9QXN_a
    701     1108  1390      16   284 6.21e-38    147.0     51.75  85.6720726 3W2O_A
    702     1108  1390      17   285 6.30e-38    147.0     51.75  85.6576839 5Y25_A
    703     1108  1390      14   282 6.38e-38    147.0     51.75  85.6450654 4I1Z_A
    704     1108  1390      37   305 6.53e-38    148.0     51.75  85.6218266 1XKK_A
    705     1108  1390      15   283 6.66e-38    147.0     51.75  85.6021140 2GS7_A
    706     1108  1390      19   287 8.79e-38    147.0     51.75  85.3246188 3UG1_A
    707     1108  1390      11   286 8.88e-38    147.0     50.34  85.3144320 8VB5_A
    708     1108  1390      16   284 9.26e-38    147.0     51.40  85.2725295 5XDL_A
    709     1108  1390      33   301 9.38e-38    147.0     51.75  85.2596538 8D73_A
    710     1108  1390      16   284 9.43e-38    147.0     51.40  85.2543374 6JWL_A
    711     1108  1390      22   290 9.53e-38    147.0     51.75  85.2437888 4HJO_A
    712     1108  1390      16   284 1.04e-37    147.0     51.40  85.1564277 4LQM_A
    713     1108  1390      19   287 1.08e-37    147.0     51.40  85.1186874 2EB3_A
    714     1108  1390      12   280 1.17e-37    146.0     51.40  85.0386447 2ITT_A
    715     1108  1390      12   280 1.22e-37    146.0     51.40  84.9967976 4R3P_A
    716     1099  1390      12   296 1.45e-37    147.0     50.17  84.8240849 8U8X_A
    717     1108  1390      16   284 1.49e-37    146.0     51.40  84.7968723 7K1H_A
    718     1108  1390      14   282 1.61e-37    146.0     51.40  84.7194143 4I20_A
    719     1108  1390      19   287 1.97e-37    146.0     51.40  84.5176149 2EB2_A
    720     1108  1390      11   279 1.99e-37    145.0     51.40  84.5075138 8A2B_A
    721     1108  1390      12   280 2.40e-37    145.0     51.40  84.3201797 2ITN_A
    722     1210  1376     226   393 3.71e-37    147.0     58.48  83.8846166 4RT7_A
    724     1008  1390     664  1017 3.99e-37    155.0     48.45  83.8118572 9QBG_A
    725     1008  1390     664  1017 3.99e-37    155.0     48.45  83.8118572 9QBF_A
    726     1008  1403     630   996 6.23e-37    154.0     47.62  83.3662721 7MN5_B
    727     1008  1403     630   996 6.50e-37    154.0     47.62  83.3238463 7MN6_B
    728     1108  1390      46   314 7.03e-37    145.0     51.40  83.2454617 3GOP_A
    729     1098  1390       7   291 8.21e-37    144.0     50.84  83.0902955 9U8C_A
    730     1108  1390      16   284 1.49e-36    143.0     52.45  82.4942872 6JRJ_A
    731     1108  1390      16   288 1.67e-36    143.0     51.03  82.3802397 8DSW_A
    732     1108  1390      15   286 1.69e-36    143.0     51.21  82.3683348 9DF2_A
    733     1108  1390      18   286 1.70e-36    143.0     52.45  82.3624351 6S89_A
    734     1108  1390      16   287 2.09e-36    143.0     51.21  82.1558993 4LRM_A
    735     1108  1390      14   285 2.30e-36    143.0     51.21  82.0601542 8PO0_A
    736     1108  1390      15   286 2.59e-36    142.0     50.87  81.9414055 9DF3_A
    737     1108  1390      14   285 3.17e-36    142.0     51.21  81.7393318 8PO1_A
    738     1108  1390      13   284 3.82e-36    142.0     51.21  81.5528129 7LGS_A
    739     1108  1390      14   285 4.67e-36    142.0     51.21  81.3519043 9FQP_A
    740     1108  1390      23   288 4.70e-36    142.0     51.40  81.3455008 7TVD_A
    741     1108  1390      12   280 9.89e-36    148.0     51.75  80.6015392 9P9U_A
    742     1108  1390     363   631 9.89e-36    148.0     51.75  80.6015392 9P9U_A
    743     1108  1390      16   284 1.50e-35    140.0     52.10  80.1850131 6JRK_A
    744     1210  1383     179   350 2.50e-35    140.0     56.57  79.6741875 3VHE_A
    745     1210  1383     177   348 2.60e-35    140.0     56.57  79.6349668 3VID_A
    746     1210  1383     186   357 3.01e-35    140.0     56.57  79.4885382 3VHK_A
    747     1210  1383     184   355 3.26e-35    140.0     56.57  79.4087511 1Y6A_A
    748     1113  1385     130   410 7.28e-35    147.0     51.39  78.6053474 6SEQ_A
    749     1108  1390     707   975 8.68e-35    147.0     51.75  78.4294567 7SYD_A
    750     1108  1390     707   975 2.35e-34    145.0     51.40  77.4334778 7SZ0_A
    751     1118  1386      26   284 3.31e-34    136.0     47.78  77.0909450 5WNO_A
    752     1233  1384     770   919 3.23e-33    142.0     60.13  74.8128259 8DFQ_A
    753     1233  1384     772   921 3.66e-33    141.0     60.13  74.6878449 8DFM_A
    754     1233  1384     774   923 3.90e-33    141.0     60.13  74.6243315 8DFP_A
    755     1103  1384       2   290 2.35e-32    130.0     47.67  72.8283076 5TQ5_A
    756     1106  1384       2   287 1.56e-31    127.0     48.15  70.9354521 3UGC_A
    757     1107  1384       4   288 2.40e-31    127.0     47.97  70.5046691 4BBE_A
    758     1110  1384       2   283 4.40e-31    126.0     48.12  69.8985333 6TPD_A
    759     1103  1384      22   310 5.20e-31    127.0     47.33  69.7314793 8G6Z_A
    760     1107  1384       1   285 6.50e-31    125.0     47.64  69.5083357 7LL5_A
    761     1119  1390      18   278 6.82e-31    127.0     47.29  69.4602784 4RIY_A
    762     1107  1384       6   290 7.04e-31    125.0     47.64  69.4285297 7RN6_A
    763     1107  1384       5   289 8.00e-31    125.0     47.64  69.3006963 7LL4_A
    764     1107  1384      25   309 8.98e-31    126.0     47.97  69.1851380 7TEU_A
    765     1107  1384      24   308 1.01e-30    126.0     47.64  69.0676025 5USY_A
    766     1107  1384      16   300 1.11e-30    125.0     47.64  68.9731928 6VGL_A
    767     1107  1384       6   290 1.27e-30    125.0     47.64  68.8385359 4E6D_A
    768     1106  1384       2   287 1.43e-30    125.0     47.81  68.7198783 3KRR_A
    769     1103  1384      19   307 2.26e-30    125.0     47.67  68.2621880 4ZIM_A
    770     1107  1384       4   288 2.72e-30    124.0     47.97  68.0769209 4YTC_A
    771     1103  1384       2   290 2.93e-30    124.0     47.33  68.0025504 5TQ4_A
    772     1107  1384      10   294 4.15e-30    124.0     47.64  67.6544445 5HEZ_A
    773     1103  1384      22   310 4.18e-30    124.0     47.33  67.6472415 8G8O_A
    774     1107  1384       5   289 4.23e-30    123.0     47.64  67.6353508 4GL9_A
    775     1107  1384      21   305 4.32e-30    124.0     47.97  67.6142974 3IO7_A
    776     1103  1384       2   290 4.33e-30    123.0     47.33  67.6119852 3TJC_A
    777     1107  1384      10   294 4.52e-30    124.0     47.64  67.5690408 4E4M_A
    778     1107  1384      12   296 4.83e-30    124.0     47.64  67.5027063 5TQ3_A
    779     1095  1384      17   308 4.84e-30    124.0     47.08  67.5006381 7Q7I_A
    780     1107  1384      21   305 5.09e-30    124.0     47.97  67.4502750 3JY9_A
    781     1107  1384      12   296 5.56e-30    123.0     47.64  67.3619547 5TQ6_A
    782     1107  1384       1   285 5.92e-30    123.0     47.64  67.2992163 2B7A_A
    783     1105  1384       1   287 6.17e-30    123.0     47.65  67.2578540 3Q32_A
    784     1107  1384       8   292 6.20e-30    123.0     47.64  67.2530035 4HGE_A
    785     1107  1384       7   291 6.41e-30    123.0     47.64  67.2196935 6WTN_A
    786     1110  1384       2   283 6.51e-30    123.0     47.78  67.2042133 7UYW_A
    787     1107  1384       6   290 7.03e-30    123.0     47.64  67.1273661 4D0W_A
    788     1107  1384      27   311 7.07e-30    123.0     47.64  67.1216923 5WEV_A
    789     1119  1390      18   278 7.48e-30    124.0     46.93  67.0653200 4RIX_A
    790     1107  1384       2   286 7.87e-30    122.0     47.64  67.0144947 3E62_A
    791     1119  1390      18   278 7.89e-30    123.0     46.93  67.0119567 3KEX_A
    792     1107  1384       9   293 8.05e-30    123.0     47.64  66.9918807 4AQC_A
    793     1107  1384      25   309 8.17e-30    123.0     47.64  66.9770839 8BM2_A
    794     1119  1390      39   299 8.18e-30    124.0     46.93  66.9758606 6OP9_A
    795     1119  1390      18   278 8.22e-30    123.0     46.93  66.9709826 4RIW_A
    796     1111  1414      23   315 8.31e-30    124.0     44.51  66.9600932 4UYA_A
    797     1107  1384      24   308 9.05e-30    123.0     47.64  66.8747880 8BX6_A
    798     1095  1384      19   318 9.38e-30    123.0     46.62  66.8389730 2W1I_A
    799     1119  1390      36   296 1.11e-29    124.0     46.93  66.6706077 3LMG_A
    800     1107  1384       7   291 1.16e-29    122.0     47.64  66.6265477 3RVG_A
    801     1081  1384       2   312 1.51e-29    122.0     43.30  66.3628580 5KHW_A
    802     1107  1384       7   291 3.62e-29    121.0     46.96  65.4884937 6AAJ_A
    803     1107  1384       6   290 3.78e-29    120.0     46.96  65.4452437 3ZMM_A
    804     1107  1384       6   290 3.85e-29    120.0     46.96  65.4268945 2XA4_A
    805     1113  1384       5   283 4.32e-29    120.0     44.29  65.3117123 6C7Y_A
    806     1103  1380       3   285 6.03e-29    120.0     44.67  64.9782207 5F1Z_A
    807     1103  1380       3   285 6.59e-29    120.0     44.67  64.8894143 3NYX_A
    808     1103  1376       3   281 7.18e-29    120.0     44.26  64.8036683 4GVJ_A
    809     1103  1376       3   281 7.89e-29    120.0     44.59  64.7093716 3NZ0_A
    810     1107  1414       5   282 1.03e-28    119.0     46.60  64.4428238 5CEN_A
    811     1107  1414      27   304 1.79e-28    119.0     46.60  63.8901670 8DEG_A
    812     1106  1376       1   276 2.49e-28    118.0     43.54  63.5600999 4E1Z_A
    813     1113  1376       6   274 2.74e-28    118.0     45.49  63.4644247 7UYR_A
    814     1103  1376       3   281 3.18e-28    118.0     44.26  63.3155014 4GIH_A
    815     1113  1376      10   278 3.23e-28    118.0     44.76  63.2999005 6AAM_A
    816     1113  1376       7   275 3.46e-28    117.0     43.90  63.2311140 4E20_A
    817     1113  1384      22   300 4.64e-28    118.0     43.94  62.9376682 6N7A_A
    818     1113  1384      10   288 5.93e-28    117.0     43.94  62.6923584 6GGH_A
    819     1113  1384       9   287 6.50e-28    117.0     43.94  62.6005804 6TPE_A
    820     1113  1384       8   286 6.66e-28    117.0     43.94  62.5762631 3EYG_A
    821     1113  1384      20   298 7.13e-28    117.0     43.94  62.5080714 4E4L_A
    822     1114  1379      13   284 7.55e-28    117.0     46.21  62.4508350 4RIO_A
    823     1113  1384      19   297 8.51e-28    117.0     43.94  62.3311407 6ELR_A
    824     1114  1379      10   281 9.41e-28    117.0     46.21  62.2306097 4HVD_A
    825     1083  1384     841  1149 9.72e-28    124.0     43.89  62.1981970 7T6F_A
    827     1074  1380     313   624 9.98e-28    122.0     44.24  62.1717995 4OLI_A
    828     1114  1379      17   288 1.15e-27    117.0     46.21  62.0300356 5TOZ_A
    829     1114  1379      11   282 1.32e-27    117.0     46.21  61.8921658 3PJC_A
    830     1114  1379      23   294 1.41e-27    117.0     46.21  61.8262078 7Q6H_a
    831     1033  1390     642   972 1.59e-27    123.0     45.60  61.7060635 7MN5_A
    832     1114  1379      23   294 1.78e-27    117.0     46.21  61.5931841 3LXK_A
    833     1113  1376      30   298 1.80e-27    116.0     44.41  61.5820108 4PY1_A
    834     1113  1376      30   298 2.02e-27    116.0     44.41  61.4667000 3LXN_A
    835     1104  1379       1   282 5.30e-27    114.0     45.33  60.5020907 5LWM_A
    836     1114  1379      10   281 1.04e-26    113.0     45.86  59.8279917 4QPS_A
    837     1114  1379       8   279 1.48e-26    113.0     46.58  59.4751703 3ZC6_A
    838     1114  1379       7   278 1.59e-26    113.0     46.23  59.4034784 5W86_A
    839     1114  1379      11   282 1.96e-26    112.0     46.58  59.1942679 7UYV_A
    840     1114  1379      11   282 2.24e-26    113.0     46.58  59.0607366 7C3N_A
    841     1114  1379       6   277 2.44e-26    112.0     46.23  58.9752144 6HZV_A
    842     1103  1381       9   268 2.71e-26    113.0     46.98  58.8702638 8GW3_A
    843     1108  1383       1   268 3.53e-26    111.0     44.21  58.6059145 3DTC_A
    844     1110  1384       3   267 4.77e-26    111.0     47.37  58.3048661 4YHT_A
    845     1106  1389      16   289 1.04e-25    110.0     47.28  57.5254066 4FK3_A
    846     1106  1384       6   274 1.34e-25    110.0     47.40  57.2719577 8C7Y_A
    847     1114  1379       7   278 1.55e-25    110.0     45.86  57.1263724 1YVJ_A
    848     1114  1379      12   283 1.62e-25    110.0     46.21  57.0822012 4Z16_A
    849     1108  1383       3   270 1.85e-25    110.0     44.21  56.9494417 4UY9_A
    850     1114  1379       5   276 1.92e-25    109.0     46.23  56.9123021 4V0G_B
    851     1106  1389       7   280 2.37e-25    109.0     47.28  56.7017374 6V34_A
    852     1098  1384      18   292 2.59e-25    109.0     47.14  56.6129694 4WO5_A
    853     1110  1389       6   275 2.85e-25    108.0     47.24  56.5173083 4CQE_A
    854     1110  1389      20   289 2.88e-25    109.0     47.24  56.5068370 4XV1_A
    855     1114  1379       5   276 2.89e-25    109.0     46.23  56.5033708 4V0G_A
    856     1110  1384       8   272 3.28e-25    108.0     47.37  56.3767839 5JRQ_A
    857     1110  1389      25   294 3.58e-25    109.0     47.24  56.2892645 6P3D_A
    858     1110  1384      20   284 3.59e-25    109.0     47.37  56.2864751 3OG7_A
    859     1106  1384       5   273 4.25e-25    108.0     47.40  56.1177083 4RZV_A
    860     1106  1384       6   274 4.26e-25    108.0     47.06  56.1153582 5CSW_A
    861     1106  1384      12   280 4.29e-25    108.0     47.06  56.1083406 6XFP_A
    862     1110  1384       5   269 4.59e-25    108.0     47.37  56.0407473 7P3V_A
    863     1106  1389       2   275 4.74e-25    108.0     46.94  56.0085902 6U2H_C
    864     1106  1384       8   276 4.75e-25    108.0     47.06  56.0064827 4JVG_A
    865     1108  1381       3   257 4.98e-25    109.0     46.38  55.9591974 5GJD_A
    866     1108  1381       3   257 5.17e-25    109.0     46.38  55.9217546 4GS6_A
    867     1106  1384      16   284 5.28e-25    108.0     47.06  55.9007012 4XV9_A
    868     1108  1381       3   257 5.37e-25    108.0     46.38  55.8837994 4L52_A
    869     1108  1381       2   256 5.47e-25    108.0     46.38  55.8653487 2EVA_A
    870     1108  1381       2   256 6.06e-25    108.0     46.38  55.7629175 4O91_A
    871     1106  1384       4   272 6.07e-25    108.0     47.06  55.7612687 3C4C_A
    872     1105  1381       1   258 7.00e-25    108.0     46.24  55.6187172 9FPD_A
    873     1106  1384       7   275 9.75e-25    107.0     47.06  55.2873600 8F7O_A
    874     1089  1381      10   291 1.24e-24    108.0     47.18  55.0469309 3PPZ_A
    875     1106  1384      12   275 1.33e-24    107.0     47.22  54.9768633 5HI2_A
    876     1110  1389      25   294 1.41e-24    107.0     46.90  54.9184525 5ITA_A
    877     1089  1381      10   291 4.33e-24    106.0     47.18  53.7964747 3P86_A
    878     1100  1397       1   278 5.99e-23    103.0     43.83  51.1693657 5X5O_A
    879     1110  1397       8   275 1.16e-22    102.0     44.30  50.5084520 5HES_A
    880     1110  1397      10   277 4.61e-22    105.0     43.73  49.1286442 9RPV_n
    881     1106  1383      11   284 2.31e-19     92.0     47.95  42.9118692 4YZM_A
    882     1108  1383       2   270 2.89e-19     91.7     45.07  42.6878603 8C0A_A
    883     1110  1383       3   269 5.35e-19     90.5     45.04  42.0720202 6G3C_A
    884     1110  1383       4   270 6.11e-19     90.5     45.04  41.9391900 6D2I_A
    885     1108  1383       2   270 6.47e-19     90.5     45.07  41.8819407 5WIJ_A
    886     1108  1383       3   271 6.99e-19     90.9     44.72  41.8046362 5I4N_A
    887     1110  1383       4   270 7.06e-19     90.9     45.39  41.7946717 4FVP_A
    888     1108  1383       2   270 7.54e-19     90.5     44.72  41.7288946 8B8N_A
    889     1122  1387      30   296 9.61e-19     90.5     42.91  41.4863125 8ATB_a
    890     1111  1383       5   270 1.05e-18     90.1     45.20  41.3977415 8C08_A
    891     1122  1387      30   296 1.30e-18     90.1     42.91  41.1841674 8ATL_a
    892     1108  1383       2   270 1.34e-18     89.7     44.72  41.1538621 4FVR_A
    893     1122  1384       4   275 1.37e-18     90.1     42.11  41.1317209 5NXD_A
    894     1108  1383       2   270 1.48e-18     89.4     44.72  41.0544896 7F7W_A
    895     1122  1384       2   273 1.55e-18     90.1     42.11  41.0082767 4TPT_A
    896     1108  1383       2   270 1.80e-18     89.4     45.07  40.8587450 8EX2_A
    897     1108  1383       2   270 2.00e-18     89.4     44.72  40.7533845 8C09_A
    898     1106  1383      11   284 2.12e-18     89.4     47.26  40.6951156 4F0F_A
    899     1122  1387      30   296 2.71e-18     89.4     42.91  40.4495830 8ATL_b
    900     1108  1383       2   270 3.16e-18     88.6     45.07  40.2959596 9ND3_A
    901     1108  1383       2   270 3.35e-18     88.6     45.07  40.2375713 9ND5_A
    902     1106  1383      11   284 4.93e-18     88.2     46.92  39.8511927 4F1O_A
    903     1115  1324      20   212 7.75e-18     87.8     49.30  39.3988388 9GB9_A
    904     1106  1383      11   284 1.28e-17     87.0     47.96  38.8970865 4F1M_A
    905     1110  1376      17   271 1.82e-17     86.3     43.27  38.5451101 9F32_A
    906     1110  1376      16   270 2.02e-17     86.3     43.27  38.4408491 8P5G_A
    907     1110  1376      12   266 2.57e-17     85.9     43.27  38.2000407 6MNH_A
    908     1110  1376      19   273 2.61e-17     85.9     43.27  38.1845964 4WNO_A
    909     1110  1376      19   273 3.09e-17     85.9     43.27  38.0157755 6QAS_A
    910     1110  1376      15   269 4.05e-17     85.5     43.27  37.7452297 8SV9_A
    911     1111  1394      22   301 5.40e-17     85.5     43.24  37.4575476 4L00_A
    912     1122  1330      16   216 5.55e-17     88.6     47.00  37.4301487 5EBZ_A
    913     1122  1324      44   234 5.93e-17     85.5     47.57  37.3639224 6EG9_A
    914     1111  1394      22   301 6.44e-17     85.1     42.91  37.2814180 4L01_A
    915     1122  1324      40   230 6.66e-17     85.1     47.57  37.2478271 6THW_A
    916     1110  1376      16   270 6.96e-17     84.7     42.91  37.2037671 8P5H_A
    917     1122  1324      29   219 7.60e-17     84.7     47.57  37.1157983 6F3E_A
    918     1122  1324      39   229 7.61e-17     85.1     47.57  37.1144834 2NRY_A
    919     1105  1381      13   270 7.93e-17     85.1     44.29  37.0732935 3A7F_A
    920     1106  1381      24   280 8.07e-17     85.1     44.44  37.0557931 7B30_A
    921     1122  1324      34   224 8.17e-17     85.1     47.57  37.0434777 6O8U_A
    922     1122  1324      55   245 8.22e-17     85.1     47.57  37.0373764 5UIS_A
    923     1122  1324      40   230 8.24e-17     85.1     47.57  37.0349462 7QG3_A
    924     1105  1382      20   278 8.50e-17     85.1     44.13  37.0038804 4QML_A
    925     1122  1324      35   225 9.11e-17     84.7     47.57  36.9345739 6MOM_A
    926     1122  1324      40   230 9.13e-17     84.7     47.57  36.9323809 6THX_A
    927     1122  1324      37   227 9.14e-17     84.7     47.57  36.9312862 5W84_A
    928     1122  1324      39   229 9.42e-17     84.7     47.57  36.9011115 4RMZ_A
    929     1122  1324      37   227 9.75e-17     84.7     47.57  36.8666793 6LXY_A
    930     1105  1381       5   262 9.80e-17     84.3     44.29  36.8615642 4U8Z_A
    931     1105  1381       5   262 9.87e-17     84.3     44.29  36.8544467 4W8E_A
    932     1122  1324      36   226 9.88e-17     84.7     47.57  36.8534341 9NA2_A
    933     1122  1324      34   224 9.94e-17     84.7     47.57  36.8473796 4Y73_A
    934     1122  1324      49   239 1.03e-16     84.7     47.57  36.8118027 6O94_A
    935     1122  1324      33   223 1.03e-16     84.7     47.57  36.8118027 5K72_A
    936     1122  1324      36   226 1.05e-16     84.7     47.57  36.7925713 9PSU_A
    937     1122  1324      32   222 1.07e-16     84.3     47.57  36.7737028 7C2V_A
    938     1122  1324      39   229 1.07e-16     84.7     47.57  36.7737028 2NRU_A
    939     1122  1324      33   223 1.07e-16     84.3     47.57  36.7737028 2OIB_A
    940     1122  1324      31   221 1.09e-16     84.3     47.57  36.7551838 8BR5_a
    941     1122  1324      29   219 1.12e-16     84.3     47.57  36.7280328 6N8G_A
    942     1122  1324      55   245 1.16e-16     84.7     47.57  36.6929415 5UIQ_A
    943     1122  1324      55   245 1.20e-16     84.7     47.57  36.6590399 5UIT_A
    944     1122  1324      29   219 1.21e-16     84.3     47.57  36.6507411 6F3D_A
    945     1122  1324      29   219 1.21e-16     84.3     47.57  36.6507411 6F3G_A
    946     1122  1324      30   220 1.25e-16     84.3     47.57  36.6182179 7C2W_A
    947     1122  1324      54   244 1.53e-16     84.3     47.57  36.4160938 6F3I_A
    948     1122  1324      59   249 1.54e-16     84.3     47.57  36.4095791 8V1O_A
    949     1122  1324      37   227 1.94e-16     84.0     45.58  36.1786735 8SCV_A
    950     1104  1324       6   212 2.02e-16     84.0     47.77  36.1382640 6CTH_A
    951     1122  1324      44   234 2.74e-16     83.6     47.57  35.8334036 4U97_A
    952     1122  1324      34   224 2.76e-16     83.2     47.57  35.8261308 6EGD_A
    953     1122  1324     192   382 2.89e-16     85.5     47.57  35.7801050 8DKS_A
    954     1122  1324      29   219 3.39e-16     82.8     47.57  35.6205316 8WTF_A
    826     1111  1398     577   860 4.55e-16     86.3     42.95  35.3262343 7T6F_A
    955     1100  1381      33   305 5.53e-16     83.2     42.19  35.1311737 1U5Q_A
    956     1098  1375       9   262 7.19e-16     82.0     41.61  34.8686703 7Z4V_A
    957     1108  1381       9   266 7.83e-16     82.0     42.66  34.7833990 2GCD_A
    958     1118  1377      12   271 7.87e-16     82.0     41.22  34.7783034 3S95_A
    959     1112  1381       5   255 8.06e-16     82.0     43.96  34.7544479 3CKX_A
    960     1112  1375      25   269 8.12e-16     81.6     43.82  34.7470313 3ZHP_C
    961     1112  1381       5   255 8.44e-16     82.0     43.96  34.7083792 3CKW_A
    962     1112  1375       4   248 9.51e-16     81.3     43.45  34.5890176 4O27_B
    963     1122  1324      55   241 1.08e-15     82.0     47.83  34.4618154 9V70_A
    964     1098  1375       8   261 1.18e-15     81.3     41.61  34.3732620 2XIK_A
    965     1156  1388      56   295 1.33e-15     81.3     44.44  34.2535975 6C4D_A
    966     1080  1373     160   430 1.36e-15     83.2     41.75  34.2312917 9LBG_A
    967     1122  1324      28   214 1.51e-15     81.3     47.83  34.1266667 9V71_A
    968     1120  1381      16   258 1.57e-15     80.5     44.70  34.0877008 6GR8_A
    969     1156  1388      56   295 1.60e-15     80.9     44.44  34.0687728 6C3E_A
    970     1156  1388      56   295 1.66e-15     80.9     44.44  34.0319588 9HY8_A
    971     1156  1388      56   295 1.77e-15     80.9     44.44  33.9677968 7FCZ_A
    972     1122  1384      30   301 1.78e-15     80.9     43.66  33.9621630 5XD6_A
    973     1156  1388      55   294 1.85e-15     80.9     44.44  33.9235908 6NYH_A
    974     1123  1324      31   220 1.85e-15     80.9     44.39  33.9235908 2O8Y_A
    975     1118  1377      16   275 2.11e-15     80.9     41.22  33.7920884 5HVJ_A
    976     1156  1388      62   301 2.48e-15     80.5     44.44  33.6305178 5HX6_A
    977     1118  1377      16   275 2.80e-15     80.5     40.28  33.5091570 5HVK_A
    978     1098  1375       9   262 3.00e-15     80.1     41.61  33.4401641 4NZW_B
    979     1156  1388      69   308 3.36e-15     80.1     44.44  33.3268354 6NW2_A
    980     1122  1324      28   214 3.72e-15     80.1     47.83  33.2250527 9WYR_A
    981     1156  1388      72   311 4.02e-15     80.1     44.44  33.1474945 9GTG_A
    982     1156  1382      46   277 6.87e-15     79.0     44.67  32.6116123 9MZY_A
    983     1156  1382      47   278 7.11e-15     79.0     44.67  32.5772742 9MZZ_A
    984     1112  1373      18   261 7.54e-15     79.0     42.64  32.5185542 9D51_A
    985     1156  1382      48   279 7.56e-15     78.6     44.67  32.5159052 9MZX_A
    986     1120  1381      40   282 8.05e-15     78.6     40.73  32.4531043 6VPJ_A
    987     1122  1376      19   266 9.21e-15     78.2     44.15  32.3184865 6QAT_A
    988     1080  1373     173   443 1.02e-14     80.5     41.75  32.2163887 9LBF_A
    989     1156  1382      53   284 1.05e-14     78.6     44.67  32.1874011 4ITH_A
    990     1120  1381      19   261 1.09e-14     78.2     40.36  32.1500136 2WTW_A
    991     1080  1373     241   511 1.39e-14     80.5     41.41  31.9068876 9M41_A
    992     1103  1381       2   261 2.05e-14     77.4     40.41  31.5183515 2C6E_A
    993     1101  1389      11   284 2.58e-14     77.8     39.74  31.2884019 6BDN_A
    994     1120  1381      15   257 3.07e-14     76.6     40.00  31.1145137 4J8M_A
    995     1112  1373      20   263 3.23e-14     77.0     40.91  31.0637092 4ZJI_A
    996     1120  1381      40   282 3.35e-14     77.0     40.00  31.0272310 2BMC_A
    997     1120  1381      17   259 3.36e-14     76.6     40.00  31.0242503 3NRM_A
    998     1120  1381      12   254 3.38e-14     76.6     40.00  31.0183156 3W10_A
    999     1120  1381      17   259 3.39e-14     76.6     40.00  31.0153614 3R21_A
    1000    1120  1381      14   256 3.42e-14     76.3     40.00  31.0065508 3H0Y_A
    1001    1120  1381      40   282 3.46e-14     77.0     40.73  30.9949227 6VPI_A
    1002    1120  1381      40   282 3.48e-14     77.0     40.00  30.9891590 2J4Z_A
    1003    1112  1373      18   261 3.85e-14     76.6     40.91  30.8881182 4ZLO_A
    1004    1120  1381      15   257 3.95e-14     76.3     40.00  30.8624757 3FDN_A
    1005    1120  1381      18   260 4.23e-14     76.3     40.00  30.7939893 5OBJ_A
    1006    1120  1381      18   260 4.25e-14     76.3     40.00  30.7892723 5EW9_A
    1007    1156  1382      62   293 4.30e-14     77.4     44.26  30.7775763 4NEU_A
    1008    1120  1381      14   256 4.32e-14     76.3     40.00  30.7729359 2J50_A
    1009    1120  1381      15   257 4.34e-14     76.3     40.00  30.7683170 3UNZ_A
    1010    1120  1381      18   260 4.40e-14     76.3     40.00  30.7545868 5DN3_A
    1011    1120  1381      31   273 4.42e-14     76.6     40.00  30.7500516 1MUO_A
    1012    1120  1381      14   256 4.49e-14     75.9     40.00  30.7343386 3COH_A
    1013    1120  1381      16   258 4.66e-14     76.3     40.00  30.6971759 4C3P_A
    1014    1120  1381      19   261 4.77e-14     75.9     40.00  30.6738450 8C1M_A
    1015    1120  1381      19   261 4.83e-14     76.3     40.00  30.6613448 6C83_A
    1016    1120  1381      19   261 4.88e-14     76.3     40.73  30.6510461 4BN1_A
    1017    1120  1381      18   260 4.92e-14     75.9     40.00  30.6428828 1MQ4_A
    1018    1120  1381      19   261 4.92e-14     76.3     39.64  30.6428828 2DWB_A
    1019    1120  1381      19   261 4.92e-14     76.3     40.00  30.6428828 6I2U_A
    1020    1120  1381      12   254 4.96e-14     76.3     40.00  30.6347856 3W16_A
    1021    1120  1381      15   257 4.96e-14     75.9     40.00  30.6347856 4PRJ_A
    1022    1120  1381      14   256 4.97e-14     75.9     40.00  30.6327715 3E5A_A
    1023    1120  1381      15   257 5.00e-14     76.3     40.00  30.6267534 5ZAN_A
    1024    1120  1381      16   258 5.02e-14     76.3     40.00  30.6227614 1OL5_A
    1025    1120  1381      17   259 5.20e-14     76.3     40.00  30.5875327 2XNG_A
    1026    1120  1381      13   255 5.23e-14     75.9     40.00  30.5817800 3EFW_A
    1027    1120  1381      14   256 5.25e-14     75.9     40.00  30.5779632 2C6D_A
    1028    1120  1381      33   275 5.31e-14     76.3     40.00  30.5665995 7O2V_A
    1029    1120  1381      41   283 5.45e-14     76.3     43.94  30.5405757 9ESA_a
    1030    1120  1381      25   267 5.52e-14     76.3     40.00  30.5278134 4JAI_A
    1031    1120  1381      18   260 5.52e-14     76.3     40.00  30.5278134 8SSP_A
    1032    1120  1381      14   256 5.66e-14     75.9     40.00  30.5027674 2XRU_A
    1033    1120  1381      14   256 5.67e-14     75.9     40.00  30.5010022 3HA6_A
    1034    1120  1381      14   256 5.72e-14     76.3     40.00  30.4922225 3LAU_A
    1035    1112  1373      18   261 5.78e-14     76.3     40.53  30.4817876 3FXZ_A
    1036    1120  1381      19   261 5.82e-14     75.9     40.00  30.4748910 2X6D_A
    1037    1120  1381      14   256 5.99e-14     75.9     40.00  30.4460999 4UZD_A
    1038    1115  1324      20   211 6.31e-14     76.3     46.58  30.3940556 9GFZ_A
    1039    1120  1381      10   252 6.34e-14     75.5     40.00  30.3893125 3W2C_A
    1040    1120  1381      14   256 6.36e-14     75.9     40.00  30.3861629 5DT3_A
    1041    1120  1381      11   253 6.43e-14     75.5     40.00  30.3752168 8JF4_A
    1042    1120  1381      17   259 6.44e-14     75.9     40.00  30.3736628 2W1D_A
    1043    1120  1381      14   256 6.54e-14     75.5     40.00  30.3582541 5DT4_A
    1044    1120  1381      40   282 6.80e-14     75.9     40.00  30.3192687 6XKA_A
    1045    1120  1381      14   256 6.98e-14     75.5     40.00  30.2931424 5DOS_A
    1046    1120  1381      40   282 6.99e-14     75.9     40.00  30.2917107 6VPL_A
    1047    1112  1373      22   265 7.61e-14     75.9     40.53  30.2067281 4EQC_A
    1048    1120  1381      40   282 7.95e-14     75.9     40.00  30.1630194 6VPG_A
    1049    1120  1381      17   259 8.20e-14     75.5     40.00  30.1320571 2W1C_A
    1050    1112  1373      19   262 9.33e-14     75.9     40.53  30.0029563 3Q52_A
    1051    1112  1373      19   262 1.14e-13     75.5     40.91  29.8025779 4ZY4_A
    1052    1112  1373      18   261 1.16e-13     75.5     40.15  29.7851862 1F3M_C
    1053    1112  1373      19   262 1.28e-13     75.5     40.91  29.6867461 7VTO_A
    1054    1119  1351      26   244 1.30e-13     75.1     47.33  29.6712419 3DXN_A
    1055    1112  1373      18   261 1.33e-13     75.1     40.15  29.6484273 1YHV_A
    1056    1112  1373      18   261 1.38e-13     75.1     40.15  29.6115227 8X5Z_A
    1057    1112  1373      18   261 1.82e-13     74.7     40.91  29.3347697 4O0R_A
    1058    1112  1373      17   260 1.93e-13     74.7     40.91  29.2760862 9D4X_A
    1059    1120  1381      16   258 2.02e-13     74.3     40.00  29.2305087 1OL6_A
    1060    1112  1373      18   261 2.11e-13     74.7     40.91  29.1869183 5DEW_A
    1061    1120  1381      19   261 2.19e-13     74.3     40.00  29.1497047 2WTV_A
    1062    1120  1381      11   253 2.34e-13     73.9     39.64  29.0834553 2WQE_A
    1063    1120  1381      17   259 2.37e-13     73.9     40.00  29.0707163 2XNE_A
    1064    1089  1381      10   285 2.64e-13     74.3     39.68  28.9628273 7ZTL_A
    1065    1122  1330      23   224 3.06e-13     76.6     46.33  28.8151913 3RZF_A
    1066    1108  1374       3   256 3.07e-13     73.9     40.51  28.8119286 2BFY_A
    1067    1120  1381      11   253 3.13e-13     73.6     39.64  28.7925732 9KS6_A
    1068    1122  1330      22   223 3.24e-13     76.6     46.33  28.7580329 3QA8_A
    1069    1120  1381      16   258 3.25e-13     73.6     40.00  28.7549512 4O0W_A
    1070    1112  1373      18   261 3.40e-13     73.9     40.53  28.7098308 4P90_A
    1071    1108  1340       1   228 3.53e-13     74.7     44.86  28.6723083 10SL_A
    1072    1100  1322      13   213 3.79e-13     73.9     45.29  28.6012402 3GGF_A
    1073    1112  1373      13   256 3.85e-13     73.6     40.53  28.5855331 5KBQ_A
    1074    1108  1374       4   257 3.87e-13     73.6     40.51  28.5803517 5K3Y_A
    1075    1112  1373      19   262 3.92e-13     73.9     40.53  28.5675146 3Q4Z_A
    1076    1120  1380      28   277 3.97e-13     73.6     45.15  28.5548401 3IS5_A
    1077    1146  1406      50   290 4.20e-13     73.6     43.23  28.4985217 4KS7_A
    1078    1108  1340       1   228 4.55e-13     74.3     43.75  28.4184790 9Z8K_B
    1079    1120  1381      19   261 4.64e-13     73.2     39.64  28.3988918 5AAD_A
    1080    1120  1381      19   261 4.68e-13     73.2     39.64  28.3903081 4CEG_A
    1081    1120  1381      19   261 5.00e-13     73.2     39.64  28.3241683 9BZG_A
    1082    1108  1340       1   228 5.16e-13     74.3     43.75  28.2926696 10JU_B
    1083    1120  1381      17   259 5.64e-13     73.2     39.64  28.2037221 5LXM_A
    1084    1120  1381      11   253 5.89e-13     72.8     39.64  28.1603502 5OS2_A
    1085    1120  1381      12   254 5.93e-13     72.8     39.64  28.1535820 9KDS_A
    1086    1120  1381      11   253 6.29e-13     72.4     39.64  28.0946451 5ORL_A
    1087    1108  1340       1   228 6.29e-13     73.9     44.44  28.0946451 10BL_A
    1088    1120  1381      16   258 6.33e-13     72.8     39.64  28.0883060 4O0U_A
    1089    1120  1345      55   265 6.46e-13     75.1     47.83  28.0679769 4IEB_A
    1090    1146  1406      72   312 6.50e-13     73.6     43.23  28.0618040 2C30_A
    1091    1112  1373      20   263 6.87e-13     73.2     40.53  28.0064421 6FD3_A
    1092    1120  1381      13   255 6.96e-13     72.4     39.64  27.9934267 5OS5_A
    1093    1108  1340       1   228 7.07e-13     73.9     43.33  27.9777457 9Z8K_A
    1094    1108  1340       1   228 7.27e-13     73.9     43.33  27.9498499 10JU_A
    1095    1120  1381      14   256 7.71e-13     72.4     39.64  27.8910880 8C1K_A
    1096    1120  1381      13   255 7.81e-13     72.4     39.64  27.8782012 5OSD_A
    1097    1120  1381      38   280 7.98e-13     72.8     39.64  27.8566678 8GUW_A
    1098    1120  1381      14   256 8.17e-13     72.4     39.64  27.8331373 8C15_A
    1099    1122  1330      27   228 9.37e-13     75.1     45.16  27.6960931 4KIK_A
    1100    1108  1383      14   284 9.49e-13     72.4     45.83  27.6833676 6VBZ_A
    1101    1120  1381      40   282 9.74e-13     72.4     39.64  27.6573651 6VPH_A
    1102    1108  1374       4   257 1.31e-12     72.0     40.15  27.3609940 4B8L_A
    1103    1108  1374       5   258 1.52e-12     71.6     40.15  27.2123108 4C2V_A
    1104    1108  1374       4   257 1.54e-12     71.6     40.15  27.1992387 4B8M_A
    1105    1108  1374       4   257 1.56e-12     71.6     40.15  27.1863353 2VRX_A
    1106    1120  1381      18   260 1.66e-12     71.6     39.64  27.1242035 3DAJ_A
    1107    1108  1374       3   256 1.75e-12     71.6     40.15  27.0714053 2BFX_A
    1108    1164  1391      55   280 1.76e-12     71.6     46.64  27.0657073 4M68_A
    1109    1120  1381      18   260 1.79e-12     71.2     39.64  27.0488055 3D14_A
    1110    1119  1351       9   227 1.79e-12     73.6     47.74  27.0488055 3HZT_A
    1111    1112  1373     255   498 1.89e-12     73.6     41.29  26.9944443 9N48_A
    1112    1112  1322       6   198 1.91e-12     71.6     45.02  26.9839179 4FZA_B
    1113    1108  1374       3   256 1.97e-12     71.2     40.15  26.9529876 4C2W_A
    1114    1120  1381      17   259 2.12e-12     71.2     39.64  26.8796050 5ODT_A
    1115    1122  1330      27   228 2.20e-12     73.9     44.70  26.8425638 4KIK_B
    1116    1120  1381      15   257 2.65e-12     70.9     39.27  26.6564615 3QBN_A
    1117    1122  1330      23   224 2.88e-12     73.6     44.70  26.5732308 8OMV_A
    1118    1099  1384      31   313 2.92e-12     71.6     45.48  26.5594375 7JUW_B
    1119    1101  1385      13   292 2.96e-12     71.2     43.23  26.5458318 8BW9_D
    1120    1120  1345      56   266 3.41e-12     72.8     47.39  26.4043088 3HX4_A
    1121    1122  1330      21   222 3.58e-12     73.2     44.70  26.3556583 4E3C_A
    1122    1120  1381      19   261 3.65e-12     70.5     39.27  26.3362939 6HJJ_A
    1123    1120  1345      55   265 3.77e-12     72.8     47.39  26.3039461 3KU2_A
    1124    1120  1381      19   261 4.00e-12     70.5     39.27  26.2447268 8OF5_A
    1125    1120  1345      73   283 4.28e-12     72.4     47.39  26.1770681 5DVR_A
    1126    1120  1345      56   266 4.56e-12     72.4     47.39  26.1136985 4YGA_A
    1127    1113  1345      23   237 5.39e-12     70.1     48.94  25.9464757 3DFA_A
    1128    1113  1345      23   237 5.46e-12     70.1     48.94  25.9335723 2WEI_A
    1129    1113  1345       8   222 6.06e-12     70.5     44.26  25.8293113 2JAM_A
    1130    1110  1374       2   253 6.53e-12     69.7     41.18  25.7546142 5EYK_A
    1131    1164  1391     241   466 7.48e-12     71.6     46.22  25.6187883 4BTF_A
    1132    1110  1384       8   279 7.72e-12     69.7     45.83  25.5872068 9AXH_C
    1133    1122  1388      47   315 9.40e-12     70.1     43.40  25.3903114 2QKW_B
    1134    1122  1388      47   315 1.03e-11     70.1     43.40  25.2988772 3HGK_A
    1135    1095  1345      16   243 1.87e-11     70.5     47.83  24.7024976 9D8S_A
    1136    1113  1345      23   237 2.13e-11     70.1     48.94  24.5723140 3IGO_A
    1137    1120  1381      17   259 2.33e-11     68.2     39.27  24.4825678 8PR7_A
    1138    1108  1383       8   282 2.35e-11     68.2     47.77  24.4740207 6VC0_A
    1139    1120  1345      38   248 3.17e-11     68.2     46.52  24.1747044 3MA6_A
    1140    1120  1373      29   263 3.72e-11     67.8     42.19  24.0147124 4AF3_A
    1141    1120  1345      33   243 7.11e-11     68.6     46.52  23.3669338 4M97_A
    1142    1146  1330      50   219 7.65e-11     67.0     46.49  23.2937304 8C12_a
    1143    1146  1330      72   241 8.07e-11     67.0     46.49  23.2402825 2F57_A
    1144    1120  1345      32   242 9.86e-11     68.2     46.52  23.0399499 3I79_A
    1145    1193  1380     105   286 1.65e-10     66.2     44.79  22.5250756 3LM0_A
    1146    1099  1384      18   298 3.31e-10     65.1     44.37  21.8289027 2Y4I_B
    1147    1120  1345      32   242 3.49e-10     66.2     46.52  21.7759492 3I7C_A
    1148    1099  1384      18   298 4.08e-10     65.1     44.37  21.6197539 5KKR_B
    1149    1108  1381      23   278 4.23e-10     64.7     39.52  21.5836489 8PAV_A
    1150    1108  1381      23   278 4.35e-10     64.7     39.52  21.5556751 3COM_A
    1151    1108  1381      23   278 4.43e-10     64.7     39.52  21.5374513 6YAT_A
    1152    1099  1384      41   321 5.18e-10     64.7     44.37  21.3810459 7JUQ_B
    1153    1094  1330      30   241 5.22e-10     65.5     39.92  21.3733535 9FQR_e
    1154    1115  1350      15   236 5.67e-10     63.9     40.93  21.2906618 5FG8_A
    1155    1108  1381      13   268 5.79e-10     64.3     40.70  21.2697186 9IIC_A
    1156    1113  1349      15   244 6.14e-10     64.3     41.60  21.2110262 2CN5_A
    1157    1113  1349       9   238 7.26e-10     64.3     41.60  21.0434711 2YCR_A
    1158    1113  1349       9   238 7.52e-10     64.3     41.60  21.0082848 2W0J_A
    1159    1113  1349       9   238 7.53e-10     64.3     41.60  21.0069559 2YCF_A
    1160    1113  1349       8   237 7.53e-10     64.3     41.60  21.0069559 2XK9_A
    1161    1122  1416      28   316 8.03e-10     64.3     41.23  20.9426664 5WNI_A
    1162    1108  1317       5   195 1.33e-09     63.2     43.81  20.4380869 8A66_A
    1163    1094  1339      39   259 1.43e-09     63.5     39.68  20.3655914 2W4O_A
    1164    1108  1322      21   216 1.57e-09     63.2     43.26  20.2721902 5DH3_A
    723     1081  1214      31   166 1.66e-09     63.9     48.53  20.2164482 4RT7_A
    1165    1118  1381       5   250 1.99e-09     62.4     40.00  20.0351312 8A5J_A
    1166    1119  1373      42   283 2.32e-09     63.5     42.86  19.8816987 3LIJ_A
    1167    1147  1330     102   270 2.59e-09     62.8     45.16  19.7716080 4JDJ_A
    1168    1108  1317       5   195 2.63e-09     62.0     42.86  19.7562820 8A66_B
    1169    1147  1330      75   243 2.81e-09     62.4     44.62  19.6900814 5VED_A
    1170    1166  1380      85   285 2.87e-09     62.4     40.00  19.6689538 9R1W_a
    1171    1086  1349     104   363 2.91e-09     63.2     40.36  19.6551128 3I6U_A
    1172    1147  1330     179   347 3.14e-09     63.2     44.62  19.5790430 4FIE_A
    1173    1147  1330      57   225 3.16e-09     62.0     44.62  19.5726938 8YHK_A
    1174    1112  1330      23   221 3.19e-09     62.0     42.53  19.5632449 8AHG_A
    1175    1147  1330     102   270 3.32e-09     62.4     44.62  19.5233011 4FIF_A
    1176    1086  1349     118   377 3.41e-09     62.8     40.36  19.4965535 3I6W_A
    1177    1147  1330     209   377 3.64e-09     62.8     44.62  19.4312822 5UPL_A
    1178    1122  1345      65   270 4.10e-09     62.8     44.10  19.3122789 4MVF_A
    1179    1147  1330      59   227 4.15e-09     61.6     44.62  19.3001575 2CDZ_A
    1180    1112  1330      22   220 4.42e-09     61.6     42.53  19.2371261 2X4Z_A
    1181    1112  1330      92   290 4.55e-09     62.0     42.53  19.2081386 4XBR_A
    1182    1147  1330      49   217 4.66e-09     61.2     44.62  19.1842504 4O0V_A
    1183    1147  1330      57   225 4.71e-09     61.6     44.62  19.1735779 2Q0N_A
    1184    1147  1330      49   217 5.06e-09     61.2     44.62  19.1018994 5XVA_A
    1185    1166  1380      70   270 5.07e-09     61.6     40.00  19.0999250 2V5Q_A
    1186    1112  1330      19   217 5.10e-09     61.2     42.53  19.0940253 5XVF_A
    1187    1147  1330      82   250 5.13e-09     61.6     44.62  19.0881602 4XBU_A
    1188    1112  1330      18   216 5.39e-09     61.2     42.53  19.0387205 2BVA_A
    1189    1108  1317       5   195 5.39e-09     61.2     43.81  19.0387205 4LG4_A
    1190    1166  1380      66   266 5.42e-09     61.2     40.00  19.0331700 3KB7_A
    1191    1166  1380      66   266 5.67e-09     61.2     40.00  18.9880767 2YAC_A
    1192    1166  1380      90   290 8.86e-09     60.8     40.00  18.5417191 2OU7_A
    1193    1166  1380      88   288 9.56e-09     60.8     40.00  18.4656781 3THB_A
    1194    1115  1346      32   249 1.01e-08     60.8     41.45  18.4107304 2V7O_A
    1195    1101  1317      13   210 1.07e-08     60.8     43.32  18.3530221 4LGD_A
    1196    1166  1380      63   263 1.10e-08     60.1     40.00  18.3253706 4J52_A
    1197    1166  1380      64   264 1.10e-08     60.1     40.00  18.3253706 2RKU_A
    1198    1166  1380     113   313 1.11e-08     60.8     40.00  18.3163207 5TA6_A
    1199    1103  1338       8   226 1.13e-08     60.8     43.04  18.2984631 5IG1_A
    1200    1118  1346       8   222 1.32e-08     60.5     41.38  18.1430490 2WEL_A
    1201    1176  1332      65   211 1.34e-08     60.5     43.95  18.1280111 3KN5_A
    1202    1118  1346      17   231 1.60e-08     59.7     41.38  17.9506771 5VLO_A
    1203    1147  1330     102   270 1.61e-08     60.1     44.62  17.9444466 7S46_A
    1204    1108  1317       4   194 1.61e-08     60.5     43.81  17.9444466 6AO5_A
    1205    1118  1346       7   221 1.75e-08     59.7     41.38  17.8610650 9BLH_A
    1206    1118  1346       8   222 1.78e-08     59.7     41.38  17.8440674 2VN9_A
    1207    1118  1346      17   231 2.68e-08     60.1     41.38  17.4348639 8USO_A
    1208    1147  1330     139   307 2.68e-08     59.7     44.62  17.4348639 7S47_A
    1209    1115  1324      35   236 3.64e-08     58.5     36.89  17.1286971 9P6A_A
    1210    1193  1338     102   237 3.75e-08     58.9     46.58  17.0989249 3FHR_A
    1211    1193  1338      83   218 3.78e-08     58.9     46.58  17.0909567 3R1N_A
    1212    1102  1340      10   232 6.84e-08     58.2     40.65  16.4978930 2JC6_A
    1213    1118  1346       8   222 7.44e-08     57.8     41.56  16.4138099 3BHH_A
    1214    1102  1340       9   231 7.55e-08     58.5     40.65  16.3991332 6T28_a
    1215    1163  1374    1304  1512 9.63e-08     59.3     42.92  16.1557975 8E05_A
    1216    1114  1373      37   316 9.94e-08     57.8     38.44  16.1241137 3MDY_A
    1217    1163  1374    1284  1492 1.01e-07     59.3     42.92  16.1081453 8E04_A
    1218    1110  1340      10   224 1.06e-07     57.4     40.76  16.0598267 6QP5_A
    1219    1163  1374    1336  1544 1.07e-07     58.9     42.92  16.0504370 8FAC_A
    1220    1122  1388      31   292 1.29e-07     57.4     40.07  15.8634534 7MX3_A
    1221    1118  1346     289   503 1.41e-07     58.5     41.56  15.7745059 8T6K_A
    1222    1120  1345      36   246 1.50e-07     57.8     46.32  15.7126305 4YSJ_A
    1223    1571  1589       1    19 1.70e-07     50.4    100.00  15.5874674 2KUP_B
    1224    1164  1383      63   282 2.29e-07     56.2     45.26  15.2895438 6BWK_A
    1225    1122  1388      58   319 2.38e-07     56.6     40.42  15.2509952 9LFU_A
    1226    1094  1340       8   228 2.43e-07     56.6     40.49  15.2302044 1A06_A
    1227    1193  1388     307   513 2.48e-07     57.4     44.13  15.2098371 6LBA_A
    1228    1118  1346      10   224 2.62e-07     57.0     40.69  15.1549213 6W4O_A
    1229    1118  1346       9   223 2.89e-07     55.5     40.69  15.0568391 7UJR_A
    1230    1164  1383      63   282 2.90e-07     55.8     45.26  15.0533849 6O5Z_A
    1231    1164  1383      63   282 2.93e-07     55.8     45.26  15.0430932 8SLZ_A
    1232    1164  1383      59   278 3.02e-07     55.8     44.30  15.0128388 5KNJ_A
    1233    1118  1346      26   240 3.18e-07     55.8     40.69  14.9612145 2VZ6_A
    1234    1118  1346       4   218 3.32e-07     56.6     40.69  14.9181309 5U6Y_A
    1235    1108  1383       8   289 3.64e-07     55.5     43.19  14.8261120 4MWI_A
    1236    1108  1383       7   288 3.95e-07     55.5     43.19  14.7443801 4M67_A
    1237    1122  1388      27   288 4.01e-07     55.8     40.42  14.7293044 7MON_B
    1238    1118  1346      17   231 4.11e-07     55.5     40.69  14.7046726 7B55_B
    1239    1163  1350      72   253 4.81e-07     55.8     41.80  14.5473986 3MFR_A
    1240    1108  1383       7   288 5.08e-07     55.1     43.19  14.4927844 6LK6_A
    1241    1119  1344      11   255 5.73e-07     55.5     40.38  14.3723801 6BXI_A
    1242    1163  1344      79   250 1.00e-06     54.3     43.24  13.8155106 4TXC_A
    1243    1114  1322       8   216 1.05e-06     54.3     38.96  13.7667204 3MY0_A
    1244    1122  1340      26   228 1.14e-06     53.9     42.01  13.6844823 4FG7_A
    1245    1122  1325      61   280 1.20e-06     54.7     40.98  13.6331890 3RP9_A
    1246    1122  1340      26   228 1.32e-06     53.9     42.01  13.5378788 4FG8_A
    1247    1122  1340      26   228 1.36e-06     53.9     42.01  13.5080259 4FG9_A
    1248    1108  1383     185   466 1.42e-06     54.7     43.19  13.4648537 6LK5_A
    1249    1114  1384      10   266 2.39e-06     52.8     40.78  12.9442172 9D5I_A
    1250    1114  1322       8   216 2.40e-06     53.1     41.63  12.9400418 3MTF_A
    1251    1114  1384      10   266 2.44e-06     52.8     40.78  12.9235125 9D5H_A
    1252    1163  1344      60   231 2.58e-06     52.8     42.16  12.8677212 2W4J_A
    1253    1163  1344      60   231 2.60e-06     52.8     42.16  12.8599991 1WVW_A
    1254    1163  1344      61   232 2.60e-06     52.8     42.16  12.8599991 4PF4_A
    1255    1087  1322      10   246 2.61e-06     53.1     41.00  12.8561603 9RDA_A
    1256    1087  1322       9   245 2.73e-06     53.1     41.00  12.8112089 3H9R_A
    1257    1163  1344      60   231 2.74e-06     52.8     42.16  12.8075526 2Y4P_A
    1258    1163  1344      62   233 2.76e-06     53.1     43.24  12.8002799 4TL0_A
    1259    1163  1344      63   234 2.82e-06     53.1     43.24  12.7787737 6FHB_A
    1260    1163  1344      62   233 2.83e-06     53.1     43.24  12.7752338 4UV0_A
    1261    1163  1344      60   231 2.90e-06     52.8     42.16  12.7507998 5AUT_A
    1262    1163  1344      59   230 2.90e-06     52.8     42.16  12.7507998 1P4F_A
    1263    1163  1344      59   230 2.92e-06     52.8     42.16  12.7439269 1IG1_A
    1264    1163  1344      60   231 2.94e-06     52.8     42.16  12.7371010 3F5U_A
    1265    1163  1344      60   231 2.94e-06     52.8     42.16  12.7371010 3DFC_B
    1266    1163  1344      60   231 2.94e-06     52.8     42.16  12.7371010 3GU4_A
    1267    1163  1344      63   234 2.95e-06     53.1     43.24  12.7337054 6FHA_A
    1268    1108  1322      24   238 2.95e-06     53.1     41.42  12.7337054 8UWR_A
    1269    1114  1384      10   266 2.97e-06     52.4     40.78  12.7269486 3KMW_A
    1270    1163  1344      60   231 3.08e-06     52.8     42.16  12.6905810 2W4K_A
    1271    1163  1344      59   230 3.11e-06     52.8     42.16  12.6808878 9MIU_A
    1272    1087  1322       9   245 3.24e-06     53.1     41.00  12.6399372 6EIX_A
    1273    1163  1344      60   231 3.26e-06     52.8     42.16  12.6337834 2XZS_A
    1274    1163  1344      63   234 3.28e-06     52.8     42.16  12.6276671 6QMO_A
    1275    1163  1344      63   234 3.28e-06     52.8     42.16  12.6276671 6QN4_A
    1276    1173  1379     172   375 3.45e-06     53.9     38.67  12.5771363 8FX4_D
    1277    1163  1344      60   231 3.50e-06     52.8     43.24  12.5627476 2X0G_A
    1278    1163  1344      62   233 3.50e-06     52.8     42.70  12.5627476 4B4L_A
    1279    1163  1344      60   231 3.52e-06     52.8     42.16  12.5570496 2Y0A_A
    1280    1087  1322       1   237 3.85e-06     52.8     41.00  12.4674374 9D8Z_A
    1281    1163  1344      60   231 3.86e-06     52.8     42.25  12.4648434 2XUU_A
    1282    1111  1376      17   281 4.61e-06     52.4     39.58  12.2872827 9IWX_A
    1283    1114  1322      14   222 4.62e-06     52.4     41.20  12.2851159 9D8F_A
    1284    1114  1322      37   245 5.68e-06     52.0     41.20  12.0785593 6UNR_A
    1285    1114  1322      37   245 5.68e-06     52.0     41.20  12.0785593 6UNQ_A
    1286    1193  1332      97   227 5.83e-06     52.0     45.00  12.0524936 2JBO_A
    1287    1193  1332     105   235 5.89e-06     52.0     45.00  12.0422546 3GOK_A
    1288    1193  1332      89   219 6.17e-06     52.0     45.00  11.9958117 3R2B_A
    1289    1193  1332      97   227 6.22e-06     52.4     45.00  11.9877407 6TCA_A
    1290    1193  1332      95   225 6.59e-06     52.0     45.00  11.9299572 2PZY_A
    1291    1193  1332      91   221 6.62e-06     52.0     45.00  11.9254152 2OZA_A
    1292    1116  1322       8   214 6.86e-06     51.6     41.13  11.8898031 6JUX_A
    1293    1193  1332      85   215 6.88e-06     52.0     45.00  11.8868919 4TYH_A
    1294    1193  1332     141   271 6.88e-06     52.4     45.00  11.8868919 2ONL_C
    1295    1111  1376      17   281 6.92e-06     52.0     39.24  11.8810948 4M66_A
    1296    1193  1332      96   226 6.92e-06     52.0     45.00  11.8810948 3FPM_A
    1297    1193  1332     135   265 7.02e-06     52.4     45.00  11.8667473 1KWP_A
    1298    1193  1332      91   221 7.17e-06     52.0     45.00  11.8456049 2P3G_X
    1299    1116  1322      10   216 7.26e-06     51.6     41.13  11.8331307 4DYM_A
    1300    1193  1332      90   220 7.53e-06     51.6     45.00  11.7966155 3R2Y_A
    1301    1193  1332      89   219 7.92e-06     51.6     45.00  11.7461194 3KA0_A
    1302    1193  1332     116   246 8.09e-06     51.6     45.00  11.7248818 6T8X_A
    1303    1114  1384      10   266 9.36e-06     50.8     40.43  11.5790653 6MIB_A
    1304    1174  1385     281   509 1.02e-05     52.4     41.38  11.4931228 6KA4_A
    1305    1193  1332      89   219 1.42e-05     50.8     44.29  11.1622686 8XU4_A
    1306    1193  1332      91   221 1.46e-05     50.8     44.29  11.1344890 9R59_A
    1307    1111  1376      17   281 1.57e-05     50.8     39.52  11.0618498 4M69_A
    1308    1193  1332     135   265 1.67e-05     50.8     43.57  11.0001018 1NXK_A
    1309    1176  1332      66   192 2.06e-05     50.1     40.76  10.7902195 7UP4_A
    1310    1571  1589     135   153 2.08e-05     48.1    100.00  10.7805576 2KUQ_A
    1311    1163  1344      60   231 3.02e-05     49.7     41.62  10.4076686 3GU8_A
    1312    1105  1337      31   249 3.45e-05     49.7     40.08  10.2745512 3D5V_A
    1313    1167  1341      86   259 3.61e-05     49.3     41.45  10.2292177 5YV8_A
    1314    1167  1341      86   259 3.87e-05     49.3     41.45  10.1596710 2ZV2_A
    1315    1105  1337      31   249 4.04e-05     49.3     40.08  10.1166808 3D5W_A
    1316    1103  1337      13   233 4.08e-05     49.3     39.75  10.1068285 3D5X_A
    1317    1105  1337      31   249 4.11e-05     49.3     40.08  10.0995024 3D5U_A
    1318    1095  1330      14   246 4.86e-05     49.3     41.18   9.9318870 6CMJ_A
    1319    1167  1341      78   251 4.87e-05     48.9     41.45   9.9298315 5UY6_A
    1320    1117  1384      15   285 9.43e-05     48.5     38.78   9.2690294 5YKS_A
    1321    1193  1332      91   200 3.16e-04     46.6     39.29   8.0597683 3KGA_A
    1322    1117  1330      20   224 4.68e-04     46.2     39.19   7.6670423 8H59_A
    1323    1117  1330      35   239 4.92e-04     46.2     39.19   7.6170318 8ZTC_A
    1324    1117  1330      34   238 5.54e-04     46.2     39.19   7.4983459 5Z33_A
    1325    1236  1325     273   361 6.29e-04     46.2     43.48   7.3713793 7KPV_A
    1326    1118  1339      34   259 3.00e-03     43.9     40.41   5.8091430 6FYP_A
    1327    1118  1339      23   248 3.00e-03     43.5     40.41   5.8091430 2EU9_A
    1328    1118  1339      34   259 3.00e-03     43.5     40.41   5.8091430 6FT7_A
    1329    1118  1339      55   280 3.00e-03     43.9     40.41   5.8091430 2WU6_A
    1330    1118  1339      32   257 3.00e-03     43.5     40.41   5.8091430 2EXE_A
    1331    1114  1384      10   266 4.00e-03     43.1     38.30   5.5214609 3KMU_A
    1332    1118  1339      34   259 7.00e-03     42.4     40.41   4.9618451 6YTY_A
    1333    1122  1418      34   332 8.00e-03     42.4     38.79   4.8283137 3N9X_A
    1334    1120  1379      15   271 2.60e-02     40.4     43.46   3.6496587 4HNI_A
    1335    1221  1379     100   269 3.70e-02     40.0     44.25   3.2968374 9B3S_A
    1336     684   783       8   100 4.70e-02     39.7     39.00   3.0576077 7LIR_A
    1337    1220  1379     100   270 5.00e-02     39.7     44.00   2.9957323 8VXF_A
    1338    1113  1339     153   383 5.20e-02     40.0     40.80   2.9565116 6KHF_A
    1339    1122  1325      36   253 5.50e-02     39.7     41.60   2.9004221 3NIE_A
    1340    1220  1379     101   271 5.60e-02     39.3     43.10   2.8824036 5X17_A
    1341    1220  1379     119   289 5.70e-02     39.3     43.10   2.8647040 5MQV_A
    1342    1220  1379     101   271 5.80e-02     39.3     44.00   2.8473123 3UYS_A
    1343    1221  1379     114   283 6.10e-02     39.3     43.35   2.7968814 4KB8_A
    1344    1220  1379     101   271 6.10e-02     39.3     44.00   2.7968814 6RCG_A
    1345    1220  1379      99   269 6.30e-02     39.3     44.00   2.7646206 4TN6_A
    1346    1220  1379      99   269 6.40e-02     39.3     44.00   2.7488722 5IH4_A
    1347    1220  1379     100   270 6.40e-02     39.3     44.00   2.7488722 8VXD_A
    1348    1220  1379     106   276 6.50e-02     39.3     44.00   2.7333680 8D7M_A
    1349    1220  1379      99   269 6.70e-02     39.3     44.00   2.7030627 4JJR_A
    1350    1220  1379      99   269 6.90e-02     39.3     44.00   2.6736488 4TW9_A
    1351    1220  1379      96   266 6.90e-02     39.3     44.00   2.6736488 8IZC_A
    1352    1220  1379      99   269 7.20e-02     39.3     44.00   2.6310892 1CKI_A
    1353    1221  1379     100   269 8.40e-02     39.3     42.77   2.4769385 6PXN_A
    1354    1220  1379      99   269 8.50e-02     38.9     44.00   2.4651040 6PXP_A
    1355    1165  1379     549   765 9.80e-02     39.3     41.20   2.3227878 9BCV_A
    1356    1165  1379     560   776 9.80e-02     39.3     41.20   2.3227878 9BCL_A
    1357    1165  1379     551   767 9.90e-02     39.3     41.20   2.3126354 9DZH_A
    1358    1220  1379     119   289 1.10e-01     38.5     42.53   2.2072749 5OKT_A
    1359    1220  1379     101   271 1.20e-01     38.5     43.43   2.1202635 7P7F_A
    1360    1120  1274      14   154 1.20e-01     38.5     41.82   2.1202635 5CZO_A
    1361    1120  1274      14   154 1.40e-01     38.5     41.82   1.9661129 5CYZ_A
    1362    1120  1328      13   202 2.40e-01     37.7     41.44   1.4271164 4XH0_A
    1363    1120  1279      13   157 3.30e-01     37.4     42.35   1.1086626 4XHL_A
    1364     439   481    2744  2801 6.50e-01     37.0     46.55   0.4307829 9CWM_A
    1365    1119  1285     107   263 6.60e-01     36.6     40.94   0.4155154 4LQS_A
    1366    1119  1285     107   263 7.00e-01     36.2     40.94   0.3566749 4LQP_A
    1367     450   636     625   797 7.30e-01     36.6     43.23   0.3147107 7T4S_F
    1368     439   481    2744  2801 7.70e-01     36.6     46.55   0.2613648 9I3V_A
    1369    1118  1275      11   154 8.60e-01     35.8     45.18   0.1508229 3SV0_A
    1370     917  1037       3   149 8.90e+00     32.3     39.07  -2.1860513 9Y9Z_2
              acc
    1      7NX3_A
    2      7N00_A
    3      4FOB_A
    4      7LS0_A
    5      7MZW_A
    6      3AOX_A
    7      9GBE_A
    8      3L9P_A
    9      3LCS_A
    10     4Z55_A
    11     4DCE_A
    12     7NWZ_A
    13     4FNZ_A
    14     4FNX_A
    15     4FNW_A
    16     2XP2_A
    17     2YFX_A
    18     8ARJ_A
    19     5AA9_A
    20     2YHV_A
    21     4ANL_A
    22     4ANS_A
    23     6E0R_A
    24     2YJR_A
    25     5A9U_A
    26     2YJS_A
    27     7BTT_A
    28     5AA8_A
    29     4TT7_A
    30     2XB7_A
    31     6MX8_A
    32     7MZY_A
    33     7LRZ_A
    34     3ZBF_A
    35     7Z5W_A
    36     9QEK_A
    37   8PYI_AAA
    38     3LVP_A
    39     1P4O_A
    40     1M7N_A
    41     5FXQ_A
    42     5FXR_A
    43     1JQH_A
    44     3QQU_A
    45     2OJ9_A
    46     3LW0_A
    47     3O23_A
    48     4D2R_A
    49     3I81_A
    50     5FXS_A
    51     3D94_A
    52     2ZM3_A
    53     1K3A_A
    54     3ETA_A
    55     1I44_A
    56     1IRK_A
    57     4IBM_A
    58     5E1S_A
    59     5HHW_A
    60     3EKK_A
    61     1P14_A
    62     9OYZ_B
    63     8EYR_A
    64     6JK8_A
    65     8DWN_A
    66     2Z8C_A
    67     1GAG_A
    68     1RQQ_A
    69     6PYH_A
    70     4XLV_A
    71     7TYJ_A
    72     7SL1_A
    73     8DTL_A
    74     8EYX_A
    75     8U4B_A
    76     7BW7_A
    77     8VJB_A
    78     7VKO_A
    79     7PG0_A
    80     4ASZ_A
    81     8J5W_A
    82     6PXV_A
    83     4YNE_A
    84     6IQN_A
    85     4AOJ_A
    86     7VKM_A
    87     6NSP_A
    88     6D1Y_A
    89     5H3Q_A
    90     4F0I_A
    91     7XAF_A
    92     5KMI_A
    93     5KML_A
    94     6PL1_A
    95     5JFS_A
    96     5WR7_A
    97     6D22_A
    98     6NPT_A
    99     4GT5_A
    100    6NSS_A
    101    4PMM_A
    102    8J5X_A
    103    3V5Q_A
    104    5I8A_A
    105    5KVT_A
    106    4YMJ_A
    107    1LUF_A
    108    4CSV_A
    109    9EF1_A
    110    5U6B_A
    111    6PNX_A
    112    6JMF_A
    113    8XKP_A
    114    8UDV_A
    115    3BKB_A
    116    8UDT_A
    117    6KZC_A
    118    9CD7_A
    119    8S9P_C
    120    4K33_A
    121    3CD3_A
    122    8YKI_A
    123    4XCU_A
    124    5FLF_A
    125    9KFU_A
    126    3GQL_A
    127    7WCW_A
    128    5XFF_A
    129    8KH9_A
    130    4QQJ_A
    131    6VG3_A
    132    7WCX_A
    133    4UXQ_A
    134    6TU9_A
    135    5XFJ_A
    136    7DTZ_A
    137    6JPE_A
    138    5JKG_A
    139    4WUN_A
    140    5A4C_A
    141    5AM7_A
    142    4RWI_A
    143    4ZSA_A
    144    4F63_A
    145    3RHX_A
    146    4QQT_A
    147    1AGW_A
    148    3JS2_A
    149    3C4F_A
    150    6LVM_A
    151    5ZV2_A
    152    5VND_A
    153    5A46_A
    154    4TYE_A
    155    4QQ5_A
    156    8W5C_A
    157    5NUD_A
    158    3TT0_A
    159    6YI8_A
    160    7VJL_A
    161    7F3M_A
    162    8Y22_A
    163    6NVL_A
    164    6IUO_A
    165    4QQC_A
    166    7WCL_A
    167    6MZW_A
    168    7AAY_A
    169    3KXX_A
    170    2PZP_A
    171    2PWL_A
    172    2PZ5_A
    173    6FEK_A
    174    3GQI_A
    175    6XRG_A
    176    2PZR_A
    177    6LVL_A
    178    4J98_A
    179    8E1X_A
    180    4J97_A
    181    3RI1_A
    182    7KIA_A
    183    9U7E_A
    184    8STG_A
    185    8SWE_A
    186    1GJO_A
    187  7OZY_AAA
    188    2PVY_A
    189    9U3N_A
    190    9BHI_A
    191    4J99_A
    192    5UHN_A
    193    2Q0B_A
    194    4J96_A
    195    8W1L_A
    196    5U6C_A
    197    2I0V_A
    198    2PY3_A
    199    7AAZ_A
    200    2Z60_A
    201    3OY3_A
    202    7CQE_A
    203    3BEA_A
    204    3B2T_A
    205    2PSQ_A
    206    6LVK_A
    207    2PVF_A
    208    7OAM_A
    209    2P0C_A
    210    5UGL_A
    211    7DXL_A
    212    5AMN_A
    213    3CLY_A
    214    2QOH_A
    215    5TC0_A
    216    1FPU_A
    217    4TWP_A
    218    3OXZ_A
    219    2IVS_A
    220    5EG3_A
    221    7TNH_A
    222    8W3D_A
    223    7AAX_A
    224    2G1T_A
    225    5TD2_A
    226    8H75_A
    227    4WA9_A
    228    3QRJ_A
    229    5UI0_A
    230    2I1M_A
    231    6XR6_A
    232    2HIW_A
    233    7M5Z_A
    234    3QUP_A
    235    4ZOG_A
    236    2E2B_A
    237    6WXJ_A
    238    8W3B_A
    239    2G2F_A
    240    5HU9_A
    241    3QRI_A
    242    8W2X_A
    243    3LCD_A
    244    6BL8_A
    245    6I82_A
    246    5UGX_A
    247    3PYY_A
    248    2HZI_A
    249    8W38_A
    250    2HYY_A
    251    3DK3_A
    252    7N9G_A
    253    2F4J_A
    254    3DK7_A
    255    7CC2_A
    256    3DK6_A
    257    4HW7_A
    258    6V6Q_A
    259    2OGV_A
    260    2HZ0_A
    261    6I83_A
    262    2V7A_A
    263    8JQI_B
    264    2IVT_A
    265    4XEY_A
    266    2IVV_A
    267    2QOC_A
    268    6IN0_A
    269    7W7Y_A
    270    2QOB_A
    271    6AGX_A
    272    4HVS_A
    273    2QOK_A
    274    2QOO_A
    275    8H7F_A
    276    6T2W_A
    277    2QOD_A
    278    2GQG_A
    279    8SSN_A
    280    3DZQ_A
    281    7W7X_A
    282    6VHG_A
    283    8CGC_A
    284    5I9U_A
    285    8XPV_A
    286    2QOI_A
    287    5MO4_A
    288    2GSF_A
    289    3LCO_A
    290    3FXX_A
    291    2QO7_A
    292    1OPK_A
    293    7RUN_A
    294    2QOL_A
    295    1MQB_A
    296    8FLN_A
    297    5FM2_A
    298    2QOF_A
    299    6NJA_A
    300    4OTF_A
    301    7KJA_A
    302    7KJC_A
    303    4NWM_A
    304    7KJB_A
    305    8JOT_A
    306    2FO0_A
    307    6NZM_A
    308    4XLI_A
    309    4YHF_A
    310    6W7O_A
    311    5P9F_A
    312    2QON_A
    313    4OT5_A
    314    3GEN_A
    315    6BIK_A
    316    5ZZ4_A
    317    6TFP_A
    318    6J6M_A
    319    5FBN_C
    320    5J87_A
    321    3OCT_A
    322    7KXQ_A
    323    5XYZ_A
    324    6S90_A
    325    3P08_A
    326    8YVV_A
    327    4Z3V_A
    328    4ZLY_A
    329    3PIX_A
    330    8FLL_A
    331    3OCS_A
    332    7KHK_A
    333    6O8I_A
    334    7KHJ_A
    335    5BPY_A
    336    6NFI_A
    337    6VXQ_A
    338    6AUB_A
    339    4RX5_A
    340    2XYN_A
    341    3ZFX_A
    342    6E4F_A
    343    1OPL_A
    344    8PQG_A
    345    6NE7_A
    346    6XE4_A
    347    4CKI_A
    348    9ZLJ_A
    349    5MJA_A
    350    6MNY_A
    351    4Y95_A
    352    6UMW_A
    353    1K2P_A
    354    9KS5_A
    355    6GQK_A
    356    6GQJ_A
    357    8PQ9_A
    358    6JQR_A
    359    6A32_A
    360    4XUF_A
    361    8FD9_A
    362    1RJB_A
    363    8XB1_A
    364    7KPL_A
    365    5X02_A
    366    6AUA_A
    367    8GC8_A
    368    8XRR_A
    369    8PQH_A
    370    9GZH_A
    371    6JOI_A
    372    5GRN_A
    373    4P2K_A
    374    3K54_A
    375    6IL3_A
    376    5EK7_A
    377    8PQJ_A
    378    8S9F_A
    379    4XI2_A
    380    5MJB_A
    381    4EBV_A
    382    7NX0_B
    383    4TRL_A
    384    3MIY_A
    385    6FER_A
    386    4Y93_A
    387    8E4T_A
    388    3QGW_A
    389    3V5J_A
    390    1SM2_A
    391    4HCT_A
    392    2XYU_A
    393    1MP8_A
    394    2WD1_A
    395    2ETM_A
    396    4GU9_A
    397    6I8Z_A
    398    2Y6M_A
    399    3PXK_A
    400    3BZ3_A
    401    4R1V_A
    402    9SDI_A
    403    8AN8_A
    404    7B3Q_A
    405    3T9T_A
    406  7PI4_DDD
    407    3ZZW_A
    408    6SD9_A
    409    4KNB_A
    410    2J0M_B
    411    8S93_A
    412    3I5N_A
    413    3Q6U_A
    414    3LQ8_A
    415    3F66_A
    416    2RFN_A
    417    4GT4_A
    418    2JKM_A
    419    5UAB_A
    420    2G15_A
    421    4GG5_A
    422    2WGJ_A
    423    2R2P_A
    424    4EEV_A
    425    2JKK_A
    426    3BYS_A
    427    2OG8_A
    428    2OFV_A
    429    3VW8_A
    430    2OF2_A
    431    2PL0_A
    432    8VI1_A
    433    9SZJ_A
    434    9C1R_A
    435    5HLW_A
    436    8AW1_A
    437    4KIO_A
    438    3MPM_A
    439    2HEL_A
    440    8AU5_A
    441    6HH1_A
    442    2DQ7_X
    443    3Q6W_A
    444    4IWD_A
    445    8AU3_A
    446    8ANS_A
    447    6SDC_A
    448    8GMB_A
    449    3SXR_A
    450    6I99_A
    451    3BYO_A
    452    3BYM_A
    453    3KXZ_A
    454    3ZFM_A
    455    1QPC_A
    456    2ZM1_A
    457    2OFU_A
    458    5XY1_A
    459    3CE3_A
    460    6PDJ_A
    461    3A4O_X
    462    3KMM_A
    463    3DKC_A
    464    1R0P_A
    465    3QTI_A
    466    1QPD_A
    467    3A4P_A
    468    7EEF_A
    469    2ZV7_A
    470    3CC6_A
    471    5TO8_A
    472    3ET7_A
    473    1JPA_A
    474    4H1J_A
    475    7EEC_A
    476    5HOA_A
    477    1FVR_A
    478    1T46_A
    479    4U0I_A
    480    2OO8_X
    481    3C1X_A
    482    6MOB_A
    483    2J0L_A
    484    7ZW8_A
    485    7EED_A
    486    2REI_A
    487    1T45_A
    488    3G0E_A
    489    5HOR_A
    490    3PLS_A
    491    2HEN_A
    492    6CZ3_A
    493    7AYM_A
    494    2WQB_A
    495    8X2A_A
    496    3DKG_A
    497    4X3J_A
    498    3CJF_A
    499    6ITV_A
    500    1PKG_A
    501    5DA3_A
    502    5D7V_A
    503    5H2U_A
    504    4AW5_A
    505    2HK5_A
    506    5ZJ6_A
    507    3G0F_A
    508    3CJG_A
    509    3WZD_A
    510    2YN8_A
    511    6TY3_A
    512    2J0K_A
    513    3ZEW_A
    514    2J0J_A
    515    6FNI_A
    516    3VNT_A
    517    7FEH_A
    518    4MXY_A
    519    6CZ2_A
    520    3GEQ_A
    521    5SAU_A
    522    2XIR_A
    523    3EWH_A
    524    2VWU_A
    525    3U6J_A
    526    6GQO_A
    527    3D7T_A
    528    3ZOS_A
    529    2BDF_A
    530    4AGC_A
    531    5BVK_A
    532    8JF3_A
    533    7NG7_A
    534    3G6H_A
    535    8HAQ_A
    536    5FDP_A
    537    4MXO_A
    538    6E6E_A
    539    7OTE_A
    540    3D7U_A
    541    6BRJ_A
    542    1BYG_A
    543    4MXX_A
    544    7MO7_B
    545    6Y23_A
    546    2OIQ_A
    547    3D7U_B
    548    3OEZ_A
    549    2QI8_A
    550    3SVV_A
    551    3U4W_A
    552    9NS1_A
    553    3ZFY_A
    554    1VR2_A
    555    1YOL_A
    556    1QCF_A
    557    9BYJ_A
    558    4MCV_A
    559    3C7Q_A
    560    4LGH_A
    561    2HWO_A
    562    5T0P_A
    563    9NS0_A
    564    5SWH_A
    565    3DQW_A
    566    7ZVS_A
    567    9BT8_C
    568    1YOJ_A
    569    9IRL_A
    570    1FMK_A
    571    1Y57_A
    572    8JN8_A
    573    2P2I_A
    574    2H8H_A
    575    2OH4_A
    576    4K11_A
    577    1YWN_A
    578    1YI6_A
    579    2P2H_A
    580    1KSW_A
    581    1K9A_A
    582    8XN8_A
    583    6F3F_A
    584    2PTK_A
    585    4LGG_A
    586    1AD5_A
    587    3KUL_A
    588    6TUA_A
    589    1U59_A
    590    3KUL_B
    591    7UY0_A
    592    7UY0_B
    593    2OZO_A
    594    4K2R_A
    595    7KP6_A
    596    8FE9_A
    597    4DFL_A
    598    4RX7_A
    599    4HZR_A
    600    4RX9_A
    601    4PV0_A
    602    3EMG_A
    603    6VQM_A
    604    6VOV_A
    605    3EQP_A
    606    1U46_A
    607    5ZXB_A
    608    4F4P_A
    609    4ID7_A
    610    8X5K_A
    611    4PX6_A
    612    5TR6_A
    613    5Y5T_A
    614    4RSS_A
    615    3SRV_B
    616    1XBA_A
    617    4YJO_A
    618    3TUB_A
    619    3TUC_A
    620    4HZS_A
    621    7JXH_A
    622    3PP0_A
    623    7PCD_A
    624    3SRV_A
    625    1U54_A
    626    4EWH_A
    627    8HV4_A
    628    9S3X_A
    629    6LUB_A
    630    6HM6_A
    631    9D3V_A
    632    5XGN_A
    633    8WD4_A
    634    8H7X_A
    635    2R4B_A
    636    5GNK_A
    637    9XU9_A
    638    5GMP_A
    639    8HY7_A
    640    4RJ4_A
    641    4G5P_A
    642    9JQ1_A
    643    5CNN_A
    644    6S9B_A
    645    4I24_A
    646    3IKA_A
    647    5Y9T_A
    648    5ZWJ_A
    649    6S9C_A
    650    5FEE_A
    651    2JIU_A
    652    2JIT_A
    653    4WKQ_A
    654    2J5E_A
    655    4ZSE_A
    656    6TFU_A
    657    5J9Z_A
    658    5J9Y_A
    659    3BBT_B
    660    6V5N_A
    661    8RRQ_A
    662    4YJQ_A
    663    6P1D_A
    664    4ZJV_A
    665    4TKS_A
    666    5CAV_A
    667    3VJO_A
    668    7AEM_A
    669    8HV2_A
    670    2RFD_A
    671    4LI5_A
    672    1M14_A
    673    4G5J_A
    674    5FED_A
    675    4I23_A
    676    2GS2_A
    677    2ITW_A
    678    9FZR_A
    679    4I21_A
    680    4LL0_A
    681    9KLW_A
    682    5C26_A
    683    6JZ0_A
    684    3HNG_A
    685    7UKV_A
    686    4JQ7_A
    687    8A27_A
    688    9H42_A
    689    2RGP_A
    690    9N6G_A
    691    4FL2_A
    692    8PO3_A
    693    3LZB_A
    694    8PO4_A
    695    9BY4_A
    696    8KFQ_A
    697    7OXB_A
    698    4RIW_B
    699    4FL3_A
    700  9QXN_AAA
    701    3W2O_A
    702    5Y25_A
    703    4I1Z_A
    704    1XKK_A
    705    2GS7_A
    706    3UG1_A
    707    8VB5_A
    708    5XDL_A
    709    8D73_A
    710    6JWL_A
    711    4HJO_A
    712    4LQM_A
    713    2EB3_A
    714    2ITT_A
    715    4R3P_A
    716    8U8X_A
    717    7K1H_A
    718    4I20_A
    719    2EB2_A
    720    8A2B_A
    721    2ITN_A
    722    4RT7_A
    724    9QBG_A
    725    9QBF_A
    726    7MN5_B
    727    7MN6_B
    728    3GOP_A
    729    9U8C_A
    730    6JRJ_A
    731    8DSW_A
    732    9DF2_A
    733    6S89_A
    734    4LRM_A
    735    8PO0_A
    736    9DF3_A
    737    8PO1_A
    738    7LGS_A
    739    9FQP_A
    740    7TVD_A
    741    9P9U_A
    742    9P9U_A
    743    6JRK_A
    744    3VHE_A
    745    3VID_A
    746    3VHK_A
    747    1Y6A_A
    748    6SEQ_A
    749    7SYD_A
    750    7SZ0_A
    751    5WNO_A
    752    8DFQ_A
    753    8DFM_A
    754    8DFP_A
    755    5TQ5_A
    756    3UGC_A
    757    4BBE_A
    758    6TPD_A
    759    8G6Z_A
    760    7LL5_A
    761    4RIY_A
    762    7RN6_A
    763    7LL4_A
    764    7TEU_A
    765    5USY_A
    766    6VGL_A
    767    4E6D_A
    768    3KRR_A
    769    4ZIM_A
    770    4YTC_A
    771    5TQ4_A
    772    5HEZ_A
    773    8G8O_A
    774    4GL9_A
    775    3IO7_A
    776    3TJC_A
    777    4E4M_A
    778    5TQ3_A
    779    7Q7I_A
    780    3JY9_A
    781    5TQ6_A
    782    2B7A_A
    783    3Q32_A
    784    4HGE_A
    785    6WTN_A
    786    7UYW_A
    787    4D0W_A
    788    5WEV_A
    789    4RIX_A
    790    3E62_A
    791    3KEX_A
    792    4AQC_A
    793    8BM2_A
    794    6OP9_A
    795    4RIW_A
    796    4UYA_A
    797    8BX6_A
    798    2W1I_A
    799    3LMG_A
    800    3RVG_A
    801    5KHW_A
    802    6AAJ_A
    803    3ZMM_A
    804    2XA4_A
    805    6C7Y_A
    806    5F1Z_A
    807    3NYX_A
    808    4GVJ_A
    809    3NZ0_A
    810    5CEN_A
    811    8DEG_A
    812    4E1Z_A
    813    7UYR_A
    814    4GIH_A
    815    6AAM_A
    816    4E20_A
    817    6N7A_A
    818    6GGH_A
    819    6TPE_A
    820    3EYG_A
    821    4E4L_A
    822    4RIO_A
    823    6ELR_A
    824    4HVD_A
    825    7T6F_A
    827    4OLI_A
    828    5TOZ_A
    829    3PJC_A
    830  7Q6H_AAA
    831    7MN5_A
    832    3LXK_A
    833    4PY1_A
    834    3LXN_A
    835    5LWM_A
    836    4QPS_A
    837    3ZC6_A
    838    5W86_A
    839    7UYV_A
    840    7C3N_A
    841    6HZV_A
    842    8GW3_A
    843    3DTC_A
    844    4YHT_A
    845    4FK3_A
    846    8C7Y_A
    847    1YVJ_A
    848    4Z16_A
    849    4UY9_A
    850    4V0G_B
    851    6V34_A
    852    4WO5_A
    853    4CQE_A
    854    4XV1_A
    855    4V0G_A
    856    5JRQ_A
    857    6P3D_A
    858    3OG7_A
    859    4RZV_A
    860    5CSW_A
    861    6XFP_A
    862    7P3V_A
    863    6U2H_C
    864    4JVG_A
    865    5GJD_A
    866    4GS6_A
    867    4XV9_A
    868    4L52_A
    869    2EVA_A
    870    4O91_A
    871    3C4C_A
    872    9FPD_A
    873    8F7O_A
    874    3PPZ_A
    875    5HI2_A
    876    5ITA_A
    877    3P86_A
    878    5X5O_A
    879    5HES_A
    880   9RPV_N1
    881    4YZM_A
    882    8C0A_A
    883    6G3C_A
    884    6D2I_A
    885    5WIJ_A
    886    5I4N_A
    887    4FVP_A
    888    8B8N_A
    889  8ATB_AAA
    890    8C08_A
    891  8ATL_AAA
    892    4FVR_A
    893    5NXD_A
    894    7F7W_A
    895    4TPT_A
    896    8EX2_A
    897    8C09_A
    898    4F0F_A
    899  8ATL_BBB
    900    9ND3_A
    901    9ND5_A
    902    4F1O_A
    903    9GB9_A
    904    4F1M_A
    905    9F32_A
    906    8P5G_A
    907    6MNH_A
    908    4WNO_A
    909    6QAS_A
    910    8SV9_A
    911    4L00_A
    912    5EBZ_A
    913    6EG9_A
    914    4L01_A
    915    6THW_A
    916    8P5H_A
    917    6F3E_A
    918    2NRY_A
    919    3A7F_A
    920    7B30_A
    921    6O8U_A
    922    5UIS_A
    923    7QG3_A
    924    4QML_A
    925    6MOM_A
    926    6THX_A
    927    5W84_A
    928    4RMZ_A
    929    6LXY_A
    930    4U8Z_A
    931    4W8E_A
    932    9NA2_A
    933    4Y73_A
    934    6O94_A
    935    5K72_A
    936    9PSU_A
    937    7C2V_A
    938    2NRU_A
    939    2OIB_A
    940  8BR5_AAA
    941    6N8G_A
    942    5UIQ_A
    943    5UIT_A
    944    6F3D_A
    945    6F3G_A
    946    7C2W_A
    947    6F3I_A
    948    8V1O_A
    949    8SCV_A
    950    6CTH_A
    951    4U97_A
    952    6EGD_A
    953    8DKS_A
    954    8WTF_A
    826    7T6F_A
    955    1U5Q_A
    956    7Z4V_A
    957    2GCD_A
    958    3S95_A
    959    3CKX_A
    960    3ZHP_C
    961    3CKW_A
    962    4O27_B
    963    9V70_A
    964    2XIK_A
    965    6C4D_A
    966    9LBG_A
    967    9V71_A
    968    6GR8_A
    969    6C3E_A
    970    9HY8_A
    971    7FCZ_A
    972    5XD6_A
    973    6NYH_A
    974    2O8Y_A
    975    5HVJ_A
    976    5HX6_A
    977    5HVK_A
    978    4NZW_B
    979    6NW2_A
    980    9WYR_A
    981    9GTG_A
    982    9MZY_A
    983    9MZZ_A
    984    9D51_A
    985    9MZX_A
    986    6VPJ_A
    987    6QAT_A
    988    9LBF_A
    989    4ITH_A
    990    2WTW_A
    991    9M41_A
    992    2C6E_A
    993    6BDN_A
    994    4J8M_A
    995    4ZJI_A
    996    2BMC_A
    997    3NRM_A
    998    3W10_A
    999    3R21_A
    1000   3H0Y_A
    1001   6VPI_A
    1002   2J4Z_A
    1003   4ZLO_A
    1004   3FDN_A
    1005   5OBJ_A
    1006   5EW9_A
    1007   4NEU_A
    1008   2J50_A
    1009   3UNZ_A
    1010   5DN3_A
    1011   1MUO_A
    1012   3COH_A
    1013   4C3P_A
    1014   8C1M_A
    1015   6C83_A
    1016   4BN1_A
    1017   1MQ4_A
    1018   2DWB_A
    1019   6I2U_A
    1020   3W16_A
    1021   4PRJ_A
    1022   3E5A_A
    1023   5ZAN_A
    1024   1OL5_A
    1025   2XNG_A
    1026   3EFW_A
    1027   2C6D_A
    1028   7O2V_A
    1029 9ESA_AAA
    1030   4JAI_A
    1031   8SSP_A
    1032   2XRU_A
    1033   3HA6_A
    1034   3LAU_A
    1035   3FXZ_A
    1036   2X6D_A
    1037   4UZD_A
    1038   9GFZ_A
    1039   3W2C_A
    1040   5DT3_A
    1041   8JF4_A
    1042   2W1D_A
    1043   5DT4_A
    1044   6XKA_A
    1045   5DOS_A
    1046   6VPL_A
    1047   4EQC_A
    1048   6VPG_A
    1049   2W1C_A
    1050   3Q52_A
    1051   4ZY4_A
    1052   1F3M_C
    1053   7VTO_A
    1054   3DXN_A
    1055   1YHV_A
    1056   8X5Z_A
    1057   4O0R_A
    1058   9D4X_A
    1059   1OL6_A
    1060   5DEW_A
    1061   2WTV_A
    1062   2WQE_A
    1063   2XNE_A
    1064   7ZTL_A
    1065   3RZF_A
    1066   2BFY_A
    1067   9KS6_A
    1068   3QA8_A
    1069   4O0W_A
    1070   4P90_A
    1071   10SL_A
    1072   3GGF_A
    1073   5KBQ_A
    1074   5K3Y_A
    1075   3Q4Z_A
    1076   3IS5_A
    1077   4KS7_A
    1078   9Z8K_B
    1079   5AAD_A
    1080   4CEG_A
    1081   9BZG_A
    1082   10JU_B
    1083   5LXM_A
    1084   5OS2_A
    1085   9KDS_A
    1086   5ORL_A
    1087   10BL_A
    1088   4O0U_A
    1089   4IEB_A
    1090   2C30_A
    1091   6FD3_A
    1092   5OS5_A
    1093   9Z8K_A
    1094   10JU_A
    1095   8C1K_A
    1096   5OSD_A
    1097   8GUW_A
    1098   8C15_A
    1099   4KIK_A
    1100   6VBZ_A
    1101   6VPH_A
    1102   4B8L_A
    1103   4C2V_A
    1104   4B8M_A
    1105   2VRX_A
    1106   3DAJ_A
    1107   2BFX_A
    1108   4M68_A
    1109   3D14_A
    1110   3HZT_A
    1111   9N48_A
    1112   4FZA_B
    1113   4C2W_A
    1114   5ODT_A
    1115   4KIK_B
    1116   3QBN_A
    1117   8OMV_A
    1118   7JUW_B
    1119   8BW9_D
    1120   3HX4_A
    1121   4E3C_A
    1122   6HJJ_A
    1123   3KU2_A
    1124   8OF5_A
    1125   5DVR_A
    1126   4YGA_A
    1127   3DFA_A
    1128   2WEI_A
    1129   2JAM_A
    1130   5EYK_A
    1131   4BTF_A
    1132   9AXH_C
    1133   2QKW_B
    1134   3HGK_A
    1135   9D8S_A
    1136   3IGO_A
    1137   8PR7_A
    1138   6VC0_A
    1139   3MA6_A
    1140   4AF3_A
    1141   4M97_A
    1142 8C12_AAA
    1143   2F57_A
    1144   3I79_A
    1145   3LM0_A
    1146   2Y4I_B
    1147   3I7C_A
    1148   5KKR_B
    1149   8PAV_A
    1150   3COM_A
    1151   6YAT_A
    1152   7JUQ_B
    1153  9FQR_Er
    1154   5FG8_A
    1155   9IIC_A
    1156   2CN5_A
    1157   2YCR_A
    1158   2W0J_A
    1159   2YCF_A
    1160   2XK9_A
    1161   5WNI_A
    1162   8A66_A
    1163   2W4O_A
    1164   5DH3_A
    723    4RT7_A
    1165   8A5J_A
    1166   3LIJ_A
    1167   4JDJ_A
    1168   8A66_B
    1169   5VED_A
    1170 9R1W_AAA
    1171   3I6U_A
    1172   4FIE_A
    1173   8YHK_A
    1174   8AHG_A
    1175   4FIF_A
    1176   3I6W_A
    1177   5UPL_A
    1178   4MVF_A
    1179   2CDZ_A
    1180   2X4Z_A
    1181   4XBR_A
    1182   4O0V_A
    1183   2Q0N_A
    1184   5XVA_A
    1185   2V5Q_A
    1186   5XVF_A
    1187   4XBU_A
    1188   2BVA_A
    1189   4LG4_A
    1190   3KB7_A
    1191   2YAC_A
    1192   2OU7_A
    1193   3THB_A
    1194   2V7O_A
    1195   4LGD_A
    1196   4J52_A
    1197   2RKU_A
    1198   5TA6_A
    1199   5IG1_A
    1200   2WEL_A
    1201   3KN5_A
    1202   5VLO_A
    1203   7S46_A
    1204   6AO5_A
    1205   9BLH_A
    1206   2VN9_A
    1207   8USO_A
    1208   7S47_A
    1209   9P6A_A
    1210   3FHR_A
    1211   3R1N_A
    1212   2JC6_A
    1213   3BHH_A
    1214 6T28_AAA
    1215   8E05_A
    1216   3MDY_A
    1217   8E04_A
    1218   6QP5_A
    1219   8FAC_A
    1220   7MX3_A
    1221   8T6K_A
    1222   4YSJ_A
    1223   2KUP_B
    1224   6BWK_A
    1225   9LFU_A
    1226   1A06_A
    1227   6LBA_A
    1228   6W4O_A
    1229   7UJR_A
    1230   6O5Z_A
    1231   8SLZ_A
    1232   5KNJ_A
    1233   2VZ6_A
    1234   5U6Y_A
    1235   4MWI_A
    1236   4M67_A
    1237   7MON_B
    1238   7B55_B
    1239   3MFR_A
    1240   6LK6_A
    1241   6BXI_A
    1242   4TXC_A
    1243   3MY0_A
    1244   4FG7_A
    1245   3RP9_A
    1246   4FG8_A
    1247   4FG9_A
    1248   6LK5_A
    1249   9D5I_A
    1250   3MTF_A
    1251   9D5H_A
    1252   2W4J_A
    1253   1WVW_A
    1254   4PF4_A
    1255   9RDA_A
    1256   3H9R_A
    1257   2Y4P_A
    1258   4TL0_A
    1259   6FHB_A
    1260   4UV0_A
    1261   5AUT_A
    1262   1P4F_A
    1263   1IG1_A
    1264   3F5U_A
    1265   3DFC_B
    1266   3GU4_A
    1267   6FHA_A
    1268   8UWR_A
    1269   3KMW_A
    1270   2W4K_A
    1271   9MIU_A
    1272   6EIX_A
    1273   2XZS_A
    1274   6QMO_A
    1275   6QN4_A
    1276   8FX4_D
    1277   2X0G_A
    1278   4B4L_A
    1279   2Y0A_A
    1280   9D8Z_A
    1281   2XUU_A
    1282   9IWX_A
    1283   9D8F_A
    1284   6UNR_A
    1285   6UNQ_A
    1286   2JBO_A
    1287   3GOK_A
    1288   3R2B_A
    1289   6TCA_A
    1290   2PZY_A
    1291   2OZA_A
    1292   6JUX_A
    1293   4TYH_A
    1294   2ONL_C
    1295   4M66_A
    1296   3FPM_A
    1297   1KWP_A
    1298   2P3G_X
    1299   4DYM_A
    1300   3R2Y_A
    1301   3KA0_A
    1302   6T8X_A
    1303   6MIB_A
    1304   6KA4_A
    1305   8XU4_A
    1306   9R59_A
    1307   4M69_A
    1308   1NXK_A
    1309   7UP4_A
    1310   2KUQ_A
    1311   3GU8_A
    1312   3D5V_A
    1313   5YV8_A
    1314   2ZV2_A
    1315   3D5W_A
    1316   3D5X_A
    1317   3D5U_A
    1318   6CMJ_A
    1319   5UY6_A
    1320   5YKS_A
    1321   3KGA_A
    1322   8H59_A
    1323   8ZTC_A
    1324   5Z33_A
    1325   7KPV_A
    1326   6FYP_A
    1327   2EU9_A
    1328   6FT7_A
    1329   2WU6_A
    1330   2EXE_A
    1331   3KMU_A
    1332   6YTY_A
    1333   3N9X_A
    1334   4HNI_A
    1335   9B3S_A
    1336   7LIR_A
    1337   8VXF_A
    1338   6KHF_A
    1339   3NIE_A
    1340   5X17_A
    1341   5MQV_A
    1342   3UYS_A
    1343   4KB8_A
    1344   6RCG_A
    1345   4TN6_A
    1346   5IH4_A
    1347   8VXD_A
    1348   8D7M_A
    1349   4JJR_A
    1350   4TW9_A
    1351   8IZC_A
    1352   1CKI_A
    1353   6PXN_A
    1354   6PXP_A
    1355   9BCV_A
    1356   9BCL_A
    1357   9DZH_A
    1358   5OKT_A
    1359   7P7F_A
    1360   5CZO_A
    1361   5CYZ_A
    1362   4XH0_A
    1363   4XHL_A
    1364   9CWM_A
    1365   4LQS_A
    1366   4LQP_A
    1367   7T4S_F
    1368   9I3V_A
    1369   3SV0_A
    1370  9Y9Z_20

    $raw
               queryid subjectids identity alignmentlength mismatches gapopens
    1    Query_2244025     7NX3_A  100.000             383          0        0
    2    Query_2244025     7N00_A  100.000             378          0        0
    3    Query_2244025     4FOB_A   99.717             353          1        0
    4    Query_2244025     7LS0_A   99.718             354          1        0
    5    Query_2244025     7MZW_A  100.000             353          0        0
    6    Query_2244025     3AOX_A  100.000             343          0        0
    7    Query_2244025     9GBE_A   99.417             343          2        0
    8    Query_2244025     3L9P_A   99.125             343          3        0
    9    Query_2244025     3LCS_A   99.125             343          3        0
    10   Query_2244025     4Z55_A   99.705             339          1        0
    11   Query_2244025     4DCE_A   99.700             333          1        0
    12   Query_2244025     7NWZ_A   98.555             346          3        1
    13   Query_2244025     4FNZ_A   99.694             327          1        0
    14   Query_2244025     4FNX_A   99.388             327          2        0
    15   Query_2244025     4FNW_A   99.388             327          2        0
    16   Query_2244025     2XP2_A   99.688             320          1        0
    17   Query_2244025     2YFX_A   99.375             320          2        0
    18   Query_2244025     8ARJ_A  100.000             319          0        0
    19   Query_2244025     5AA9_A   99.375             320          2        0
    20   Query_2244025     2YHV_A   99.687             319          1        0
    21   Query_2244025     4ANL_A   99.687             319          1        0
    22   Query_2244025     4ANS_A   99.373             319          2        0
    23   Query_2244025     6E0R_A  100.000             317          0        0
    24   Query_2244025     2YJR_A   99.687             319          1        0
    25   Query_2244025     5A9U_A   99.375             320          2        0
    26   Query_2244025     2YJS_A   99.687             319          1        0
    27   Query_2244025     7BTT_A   99.686             318          1        0
    28   Query_2244025     5AA8_A   99.062             320          3        0
    29   Query_2244025     4TT7_A   99.685             317          1        0
    30   Query_2244025     2XB7_A  100.000             314          0        0
    31   Query_2244025     6MX8_A  100.000             307          0        0
    32   Query_2244025     7MZY_A  100.000             314          0        0
    33   Query_2244025     7LRZ_A   99.677             310          1        0
    34   Query_2244025     3ZBF_A   49.147             293        143        3
    35   Query_2244025     7Z5W_A   49.470             283        140        2
    36   Query_2244025     9QEK_A   49.296             284        141        2
    37   Query_2244025   8PYI_AAA   44.816             299        158        3
    38   Query_2244025     3LVP_A   43.974             307        165        3
    39   Query_2244025     1P4O_A   44.816             299        158        3
    40   Query_2244025     1M7N_A   44.816             299        158        3
    41   Query_2244025     5FXQ_A   44.828             290        154        2
    42   Query_2244025     5FXR_A   44.828             290        154        2
    43   Query_2244025     1JQH_A   44.828             290        154        2
    44   Query_2244025     3QQU_A   45.775             284        148        2
    45   Query_2244025     2OJ9_A   45.583             283        148        2
    46   Query_2244025     3LW0_A   45.583             283        148        2
    47   Query_2244025     3O23_A   45.583             283        148        2
    48   Query_2244025     4D2R_A   45.583             283        148        2
    49   Query_2244025     3I81_A   45.583             283        148        2
    50   Query_2244025     5FXS_A   44.483             290        155        2
    51   Query_2244025     3D94_A   45.583             283        148        2
    52   Query_2244025     2ZM3_A   43.793             290        157        2
    53   Query_2244025     1K3A_A   44.523             283        151        2
    54   Query_2244025     3ETA_A   43.648             307        158        5
    55   Query_2244025     1I44_A   45.714             280        144        3
    56   Query_2244025     1IRK_A   45.714             280        144        3
    57   Query_2244025     4IBM_A   45.714             280        144        3
    58   Query_2244025     5E1S_A   45.357             280        145        3
    59   Query_2244025     5HHW_A   45.357             280        145        3
    60   Query_2244025     3EKK_A   45.357             280        145        3
    61   Query_2244025     1P14_A   45.357             280        145        3
    62   Query_2244025     9OYZ_B   40.244             410        225        7
    63   Query_2244025     8EYR_A   40.548             365        186        6
    64   Query_2244025     6JK8_A   40.278             360        189        5
    65   Query_2244025     8DWN_A   45.000             280        146        3
    66   Query_2244025     2Z8C_A   44.643             280        147        3
    67   Query_2244025     1GAG_A   44.643             280        147        3
    68   Query_2244025     1RQQ_A   44.643             280        147        3
    69   Query_2244025     6PYH_A   40.000             365        188        6
    70   Query_2244025     4XLV_A   44.643             280        147        3
    71   Query_2244025     7TYJ_A   43.464             306        166        3
    72   Query_2244025     7SL1_A   41.573             356        182        8
    73   Query_2244025     8DTL_A   41.573             356        182        8
    74   Query_2244025     8EYX_A   41.573             356        182        8
    75   Query_2244025     8U4B_A   41.573             356        182        8
    76   Query_2244025     7BW7_A   41.573             356        182        8
    77   Query_2244025     8VJB_A   41.573             356        182        8
    78   Query_2244025     7VKO_A   40.836             311        172        3
    79   Query_2244025     7PG0_A   41.573             356        182        8
    80   Query_2244025     4ASZ_A   42.182             275        149        3
    81   Query_2244025     8J5W_A   40.895             313        167        4
    82   Query_2244025     6PXV_A   42.059             340        175        7
    83   Query_2244025     4YNE_A   40.850             306        169        3
    84   Query_2244025     6IQN_A   41.275             298        163        3
    85   Query_2244025     4AOJ_A   40.575             313        168        4
    86   Query_2244025     7VKM_A   40.514             311        173        3
    87   Query_2244025     6NSP_A   41.275             298        163        3
    88   Query_2244025     6D1Y_A   40.575             313        168        4
    89   Query_2244025     5H3Q_A   40.575             313        168        4
    90   Query_2244025     4F0I_A   41.275             298        163        3
    91   Query_2244025     7XAF_A   41.275             298        163        3
    92   Query_2244025     5KMI_A   40.575             313        168        4
    93   Query_2244025     5KML_A   40.575             313        168        4
    94   Query_2244025     6PL1_A   40.575             313        168        4
    95   Query_2244025     5JFS_A   41.275             298        163        3
    96   Query_2244025     5WR7_A   40.909             308        164        4
    97   Query_2244025     6D22_A   41.275             298        163        3
    98   Query_2244025     6NPT_A   40.575             313        168        4
    99   Query_2244025     4GT5_A   41.275             298        163        3
    100  Query_2244025     6NSS_A   40.575             313        168        4
    101  Query_2244025     4PMM_A   41.522             289        157        3
    102  Query_2244025     8J5X_A   40.940             298        164        3
    103  Query_2244025     3V5Q_A   40.614             293        157        5
    104  Query_2244025     5I8A_A   42.049             283        152        3
    105  Query_2244025     5KVT_A   42.049             283        152        3
    106  Query_2244025     4YMJ_A   40.614             293        157        5
    107  Query_2244025     1LUF_A   40.972             288        148        5
    108  Query_2244025     4CSV_A   43.885             278        140        5
    109  Query_2244025     9EF1_A   39.032             310        168        3
    110  Query_2244025     5U6B_A   40.214             281        154        5
    111  Query_2244025     6PNX_A   40.070             287        157        5
    112  Query_2244025     6JMF_A   42.804             271        141        3
    113  Query_2244025     8XKP_A   42.804             271        141        3
    114  Query_2244025     8UDV_A   40.288             278        157        4
    115  Query_2244025     3BKB_A   42.804             271        141        3
    116  Query_2244025     8UDT_A   40.288             278        157        4
    117  Query_2244025     6KZC_A   39.130             299        151        6
    118  Query_2244025     9CD7_A   39.721             287        158        5
    119  Query_2244025     8S9P_C   35.356             379        212        9
    120  Query_2244025     4K33_A   39.721             287        158        5
    121  Query_2244025     3CD3_A   42.435             271        142        3
    122  Query_2244025     8YKI_A   38.235             306        171        7
    123  Query_2244025     4XCU_A   41.135             282        156        5
    124  Query_2244025     5FLF_A   39.721             287        158        6
    125  Query_2244025     9KFU_A   39.236             288        158        5
    126  Query_2244025     3GQL_A   38.235             306        171        7
    127  Query_2244025     7WCW_A   41.237             291        152        7
    128  Query_2244025     5XFF_A   40.816             294        155        7
    129  Query_2244025     8KH9_A   40.476             294        156        7
    130  Query_2244025     4QQJ_A   41.237             291        152        7
    131  Query_2244025     6VG3_A   37.102             283        170        5
    132  Query_2244025     7WCX_A   40.893             291        153        7
    133  Query_2244025     4UXQ_A   40.893             291        153        7
    134  Query_2244025     6TU9_A   39.931             288        159        3
    135  Query_2244025     5XFJ_A   40.476             294        156        7
    136  Query_2244025     7DTZ_A   40.893             291        153        7
    137  Query_2244025     6JPE_A   40.893             291        153        7
    138  Query_2244025     5JKG_A   40.893             291        153        7
    139  Query_2244025     4WUN_A   39.373             287        159        6
    140  Query_2244025     5A4C_A   39.373             287        159        6
    141  Query_2244025     5AM7_A   39.373             287        159        6
    142  Query_2244025     4RWI_A   39.373             287        159        6
    143  Query_2244025     4ZSA_A   39.373             287        159        6
    144  Query_2244025     4F63_A   39.373             287        159        6
    145  Query_2244025     3RHX_A   39.373             287        159        6
    146  Query_2244025     4QQT_A   40.893             291        153        7
    147  Query_2244025     1AGW_A   39.373             287        159        6
    148  Query_2244025     3JS2_A   39.373             287        159        6
    149  Query_2244025     3C4F_A   39.373             287        159        6
    150  Query_2244025     6LVM_A   38.889             288        159        5
    151  Query_2244025     5ZV2_A   39.373             287        159        6
    152  Query_2244025     5VND_A   39.373             287        159        6
    153  Query_2244025     5A46_A   38.065             310        173        8
    154  Query_2244025     4TYE_A   40.550             291        154        7
    155  Query_2244025     4QQ5_A   40.893             291        153        7
    156  Query_2244025     8W5C_A   40.550             291        154        7
    157  Query_2244025     5NUD_A   40.550             291        154        7
    158  Query_2244025     3TT0_A   37.864             309        170        7
    159  Query_2244025     6YI8_A   40.550             291        154        7
    160  Query_2244025     7VJL_A   40.550             291        154        7
    161  Query_2244025     7F3M_A   40.550             291        154        7
    162  Query_2244025     8Y22_A   39.024             287        160        6
    163  Query_2244025     6NVL_A   39.024             287        160        6
    164  Query_2244025     6IUO_A   40.550             291        154        7
    165  Query_2244025     4QQC_A   40.550             291        154        7
    166  Query_2244025     7WCL_A   39.024             287        160        6
    167  Query_2244025     6MZW_A   39.024             287        160        6
    168  Query_2244025     7AAY_A   37.544             285        169        6
    169  Query_2244025     3KXX_A   39.024             287        160        6
    170  Query_2244025     2PZP_A   37.979             287        163        4
    171  Query_2244025     2PWL_A   37.979             287        163        4
    172  Query_2244025     2PZ5_A   37.979             287        163        4
    173  Query_2244025     6FEK_A   39.209             278        162        3
    174  Query_2244025     3GQI_A   37.582             306        173        7
    175  Query_2244025     6XRG_A   39.510             286        157        5
    176  Query_2244025     2PZR_A   37.631             287        164        4
    177  Query_2244025     6LVL_A   37.631             287        164        4
    178  Query_2244025     4J98_A   37.631             287        164        4
    179  Query_2244025     8E1X_A   37.979             287        163        4
    180  Query_2244025     4J97_A   37.631             287        164        4
    181  Query_2244025     3RI1_A   37.631             287        164        4
    182  Query_2244025     7KIA_A   37.631             287        164        4
    183  Query_2244025     9U7E_A   37.631             287        164        4
    184  Query_2244025     8STG_A   37.631             287        164        4
    185  Query_2244025     8SWE_A   37.631             287        164        4
    186  Query_2244025     1GJO_A   37.631             287        164        4
    187  Query_2244025   7OZY_AAA   37.631             287        164        4
    188  Query_2244025     2PVY_A   37.631             287        164        4
    189  Query_2244025     9U3N_A   37.631             287        164        4
    190  Query_2244025     9BHI_A   37.884             293        169        7
    191  Query_2244025     4J99_A   37.631             287        164        4
    192  Query_2244025     5UHN_A   37.631             287        164        4
    193  Query_2244025     2Q0B_A   37.631             287        164        4
    194  Query_2244025     4J96_A   37.631             287        164        4
    195  Query_2244025     8W1L_A   38.415             328        184        7
    196  Query_2244025     5U6C_A   37.459             307        177        8
    197  Query_2244025     2I0V_A   38.415             328        184        7
    198  Query_2244025     2PY3_A   37.631             287        164        4
    199  Query_2244025     7AAZ_A   37.716             289        167        7
    200  Query_2244025     2Z60_A   39.161             286        158        5
    201  Query_2244025     3OY3_A   39.161             286        158        5
    202  Query_2244025     7CQE_A   37.716             289        167        7
    203  Query_2244025     3BEA_A   38.344             326        185        7
    204  Query_2244025     3B2T_A   37.282             287        165        4
    205  Query_2244025     2PSQ_A   37.631             287        164        4
    206  Query_2244025     6LVK_A   37.631             287        164        4
    207  Query_2244025     2PVF_A   36.601             306        176        5
    208  Query_2244025     7OAM_A   37.716             289        167        7
    209  Query_2244025     2P0C_A   37.716             289        167        7
    210  Query_2244025     5UGL_A   37.631             287        164        4
    211  Query_2244025     7DXL_A   37.716             289        167        7
    212  Query_2244025     5AMN_A   38.849             278        164        2
    213  Query_2244025     3CLY_A   36.601             306        176        5
    214  Query_2244025     2QOH_A   39.161             286        158        5
    215  Query_2244025     5TC0_A   37.716             289        167        7
    216  Query_2244025     1FPU_A   39.161             286        158        5
    217  Query_2244025     4TWP_A   39.161             286        158        5
    218  Query_2244025     3OXZ_A   39.161             286        158        5
    219  Query_2244025     2IVS_A   37.543             293        161        3
    220  Query_2244025     5EG3_A   35.948             306        178        5
    221  Query_2244025     7TNH_A   39.365             315        175        7
    222  Query_2244025     8W3D_A   37.282             287        165        4
    223  Query_2244025     7AAX_A   38.686             274        156        6
    224  Query_2244025     2G1T_A   38.908             293        163        5
    225  Query_2244025     5TD2_A   37.857             280        162        6
    226  Query_2244025     8H75_A   37.282             287        165        4
    227  Query_2244025     4WA9_A   39.161             286        158        5
    228  Query_2244025     3QRJ_A   39.576             283        155        5
    229  Query_2244025     5UI0_A   37.282             287        165        4
    230  Query_2244025     2I1M_A   38.650             326        184        7
    231  Query_2244025     6XR6_A   39.161             286        158        5
    232  Query_2244025     2HIW_A   38.333             300        159        6
    233  Query_2244025     7M5Z_A   38.686             274        156        6
    234  Query_2244025     3QUP_A   36.545             301        169        6
    235  Query_2244025     4ZOG_A   39.161             286        158        5
    236  Query_2244025     2E2B_A   39.161             286        158        5
    237  Query_2244025     6WXJ_A   38.110             328        185        7
    238  Query_2244025     8W3B_A   37.282             287        165        4
    239  Query_2244025     2G2F_A   38.908             293        163        5
    240  Query_2244025     5HU9_A   39.576             283        155        5
    241  Query_2244025     3QRI_A   39.576             283        155        5
    242  Query_2244025     8W2X_A   37.282             287        165        4
    243  Query_2244025     3LCD_A   38.199             322        187        6
    244  Query_2244025     6BL8_A   38.811             286        159        5
    245  Query_2244025     6I82_A   37.543             293        161        3
    246  Query_2244025     5UGX_A   37.282             287        165        4
    247  Query_2244025     3PYY_A   39.161             286        158        5
    248  Query_2244025     2HZI_A   38.796             299        157        6
    249  Query_2244025     8W38_A   37.282             287        165        4
    250  Query_2244025     2HYY_A   39.576             283        155        5
    251  Query_2244025     3DK3_A   38.811             286        159        5
    252  Query_2244025     7N9G_A   39.576             283        155        5
    253  Query_2244025     2F4J_A   39.161             286        158        5
    254  Query_2244025     3DK7_A   38.811             286        159        5
    255  Query_2244025     7CC2_A   39.161             286        158        5
    256  Query_2244025     3DK6_A   39.161             286        158        5
    257  Query_2244025     4HW7_A   37.015             335        186        6
    258  Query_2244025     6V6Q_A   36.452             310        178        6
    259  Query_2244025     2OGV_A   39.159             309        178        6
    260  Query_2244025     2HZ0_A   39.928             278        151        5
    261  Query_2244025     6I83_A   37.201             293        162        3
    262  Query_2244025     2V7A_A   38.811             286        159        5
    263  Query_2244025     8JQI_B   38.065             310        173        8
    264  Query_2244025     2IVT_A   37.201             293        162        3
    265  Query_2244025     4XEY_A   39.161             286        158        5
    266  Query_2244025     2IVV_A   37.201             293        162        3
    267  Query_2244025     2QOC_A   37.288             295        168        7
    268  Query_2244025     6IN0_A   37.895             285        161        6
    269  Query_2244025     7W7Y_A   38.811             286        159        5
    270  Query_2244025     2QOB_A   37.288             295        168        7
    271  Query_2244025     6AGX_A   36.585             287        167        4
    272  Query_2244025     4HVS_A   37.500             304        173        6
    273  Query_2244025     2QOK_A   37.124             299        171        7
    274  Query_2244025     2QOO_A   37.124             299        171        7
    275  Query_2244025     8H7F_A   39.223             283        156        5
    276  Query_2244025     6T2W_A   37.015             335        186        6
    277  Query_2244025     2QOD_A   36.709             316        177        8
    278  Query_2244025     2GQG_A   39.223             283        156        5
    279  Query_2244025     8SSN_A   39.161             286        158        5
    280  Query_2244025     3DZQ_A   37.288             295        168        7
    281  Query_2244025     7W7X_A   39.223             283        156        5
    282  Query_2244025     6VHG_A   37.201             293        162        3
    283  Query_2244025     8CGC_A   37.015             335        186        6
    284  Query_2244025     5I9U_A   38.112             286        156        6
    285  Query_2244025     8XPV_A   38.112             286        156        6
    286  Query_2244025     2QOI_A   36.789             299        172        7
    287  Query_2244025     5MO4_A   38.811             286        159        5
    288  Query_2244025     2GSF_A   36.392             316        178        8
    289  Query_2244025     3LCO_A   37.888             322        177        6
    290  Query_2244025     3FXX_A   36.392             316        178        8
    291  Query_2244025     2QO7_A   36.392             316        178        8
    292  Query_2244025     1OPK_A   38.811             286        159        5
    293  Query_2244025     7RUN_A   37.201             293        162        3
    294  Query_2244025     2QOL_A   36.789             299        172        7
    295  Query_2244025     1MQB_A   38.112             286        156        6
    296  Query_2244025     8FLN_A   38.321             274        151        5
    297  Query_2244025     5FM2_A   37.201             293        162        3
    298  Query_2244025     2QOF_A   37.895             285        161        6
    299  Query_2244025     6NJA_A   36.860             293        163        3
    300  Query_2244025     4OTF_A   38.321             274        151        5
    301  Query_2244025     7KJA_A   36.646             322        172        8
    302  Query_2244025     7KJC_A   36.646             322        172        8
    303  Query_2244025     4NWM_A   38.321             274        151        5
    304  Query_2244025     7KJB_A   36.646             322        172        8
    305  Query_2244025     8JOT_A   35.838             346        186        6
    306  Query_2244025     2FO0_A   38.811             286        159        5
    307  Query_2244025     6NZM_A   38.321             274        151        5
    308  Query_2244025     4XLI_A   39.576             283        155        6
    309  Query_2244025     4YHF_A   38.321             274        151        5
    310  Query_2244025     6W7O_A   38.321             274        151        5
    311  Query_2244025     5P9F_A   38.321             274        151        5
    312  Query_2244025     2QON_A   36.789             299        172        7
    313  Query_2244025     4OT5_A   37.956             274        152        5
    314  Query_2244025     3GEN_A   38.321             274        151        5
    315  Query_2244025     6BIK_A   38.321             274        151        5
    316  Query_2244025     5ZZ4_A   38.321             274        151        5
    317  Query_2244025     6TFP_A   38.321             274        151        5
    318  Query_2244025     6J6M_A   38.321             274        151        5
    319  Query_2244025     5FBN_C   38.321             274        151        5
    320  Query_2244025     5J87_A   38.321             274        151        5
    321  Query_2244025     3OCT_A   38.321             274        151        5
    322  Query_2244025     7KXQ_A   38.321             274        151        5
    323  Query_2244025     5XYZ_A   38.321             274        151        5
    324  Query_2244025     6S90_A   38.321             274        151        5
    325  Query_2244025     3P08_A   38.321             274        151        5
    326  Query_2244025     8YVV_A   38.321             274        151        5
    327  Query_2244025     4Z3V_A   38.321             274        151        5
    328  Query_2244025     4ZLY_A   38.321             274        151        5
    329  Query_2244025     3PIX_A   38.321             274        151        5
    330  Query_2244025     8FLL_A   38.321             274        151        5
    331  Query_2244025     3OCS_A   38.321             274        151        5
    332  Query_2244025     7KHK_A   37.171             304        174        6
    333  Query_2244025     6O8I_A   38.321             274        151        5
    334  Query_2244025     7KHJ_A   37.171             304        174        6
    335  Query_2244025     5BPY_A   38.321             274        151        5
    336  Query_2244025     6NFI_A   38.321             274        151        5
    337  Query_2244025     6VXQ_A   38.321             274        151        5
    338  Query_2244025     6AUB_A   38.321             274        151        5
    339  Query_2244025     4RX5_A   38.321             274        151        5
    340  Query_2244025     2XYN_A   38.869             283        157        5
    341  Query_2244025     3ZFX_A   36.054             294        174        5
    342  Query_2244025     6E4F_A   38.321             274        151        5
    343  Query_2244025     1OPL_A   38.811             286        159        5
    344  Query_2244025     8PQG_A   36.755             302        176        5
    345  Query_2244025     6NE7_A   36.519             293        164        3
    346  Query_2244025     6XE4_A   38.321             274        151        5
    347  Query_2244025     4CKI_A   36.519             293        164        3
    348  Query_2244025     9ZLJ_A   38.321             274        151        5
    349  Query_2244025     5MJA_A   35.374             294        176        5
    350  Query_2244025     6MNY_A   38.321             274        151        5
    351  Query_2244025     4Y95_A   38.686             274        150        5
    352  Query_2244025     6UMW_A   36.054             294        174        5
    353  Query_2244025     1K2P_A   38.519             270        148        5
    354  Query_2244025     9KS5_A   38.869             283        157        5
    355  Query_2244025     6GQK_A   36.755             302        176        5
    356  Query_2244025     6GQJ_A   36.755             302        176        5
    357  Query_2244025     8PQ9_A   36.755             302        176        5
    358  Query_2244025     6JQR_A   36.508             315        178        5
    359  Query_2244025     6A32_A   35.417             336        191        7
    360  Query_2244025     4XUF_A   38.754             289        155        5
    361  Query_2244025     8FD9_A   38.321             274        151        5
    362  Query_2244025     1RJB_A   36.508             315        178        5
    363  Query_2244025     8XB1_A   36.508             315        178        5
    364  Query_2244025     7KPL_A   36.491             285        167        5
    365  Query_2244025     5X02_A   36.508             315        178        5
    366  Query_2244025     6AUA_A   37.956             274        152        5
    367  Query_2244025     8GC8_A   37.956             274        152        5
    368  Query_2244025     8XRR_A   35.417             336        191        7
    369  Query_2244025     8PQH_A   37.500             296        161        5
    370  Query_2244025     9GZH_A   37.500             296        161        5
    371  Query_2244025     6JOI_A   35.417             336        191        7
    372  Query_2244025     5GRN_A   35.417             336        191        7
    373  Query_2244025     4P2K_A   39.114             271        144        6
    374  Query_2244025     3K54_A   37.956             274        152        5
    375  Query_2244025     6IL3_A   36.508             315        178        5
    376  Query_2244025     5EK7_A   38.545             275        148        6
    377  Query_2244025     8PQJ_A   37.500             296        161        5
    378  Query_2244025     8S9F_A   37.956             274        152        5
    379  Query_2244025     4XI2_A   38.321             274        151        5
    380  Query_2244025     5MJB_A   35.034             294        177        5
    381  Query_2244025     4EBV_A   37.809             283        163        6
    382  Query_2244025     7NX0_B   54.019             311        134        2
    383  Query_2244025     4TRL_A   38.745             271        145        6
    384  Query_2244025     3MIY_A   39.033             269        146        6
    385  Query_2244025     6FER_A   37.415             294        159        7
    386  Query_2244025     4Y93_A   38.686             274        150        5
    387  Query_2244025     8E4T_A   36.620             284        166        5
    388  Query_2244025     3QGW_A   39.033             269        146        6
    389  Query_2244025     3V5J_A   39.033             269        146        6
    390  Query_2244025     1SM2_A   39.033             269        146        6
    391  Query_2244025     4HCT_A   39.033             269        146        6
    392  Query_2244025     2XYU_A   35.664             286        168        6
    393  Query_2244025     1MP8_A   38.433             268        152        6
    394  Query_2244025     2WD1_A   37.594             266        150        6
    395  Query_2244025     2ETM_A   38.433             268        152        6
    396  Query_2244025     4GU9_A   38.433             268        152        6
    397  Query_2244025     6I8Z_A   38.433             268        152        6
    398  Query_2244025     2Y6M_A   35.664             286        168        6
    399  Query_2244025     3PXK_A   38.433             268        152        6
    400  Query_2244025     3BZ3_A   38.433             268        152        6
    401  Query_2244025     4R1V_A   37.594             266        150        6
    402  Query_2244025     9SDI_A   38.433             268        152        6
    403  Query_2244025     8AN8_A   37.594             266        150        6
    404  Query_2244025     7B3Q_A   37.594             266        150        6
    405  Query_2244025     3T9T_A   39.033             269        146        6
    406  Query_2244025   7PI4_DDD   38.433             268        152        6
    407  Query_2244025     3ZZW_A   34.737             285        174        2
    408  Query_2244025     6SD9_A   37.594             266        150        6
    409  Query_2244025     4KNB_A   37.594             266        150        6
    410  Query_2244025     2J0M_B   38.433             268        152        6
    411  Query_2244025     8S93_A   38.321             274        151        5
    412  Query_2244025     3I5N_A   37.594             266        150        6
    413  Query_2244025     3Q6U_A   37.594             266        150        6
    414  Query_2244025     3LQ8_A   37.594             266        150        6
    415  Query_2244025     3F66_A   37.594             266        150        6
    416  Query_2244025     2RFN_A   37.594             266        150        6
    417  Query_2244025     4GT4_A   34.495             287        176        2
    418  Query_2244025     2JKM_A   38.060             268        153        6
    419  Query_2244025     5UAB_A   37.594             266        150        6
    420  Query_2244025     2G15_A   37.594             266        150        6
    421  Query_2244025     4GG5_A   37.594             266        150        6
    422  Query_2244025     2WGJ_A   37.594             266        150        6
    423  Query_2244025     2R2P_A   36.140             285        166        6
    424  Query_2244025     4EEV_A   37.594             266        150        6
    425  Query_2244025     2JKK_A   38.060             268        153        6
    426  Query_2244025     3BYS_A   40.000             285        141        8
    427  Query_2244025     2OG8_A   41.026             273        131        8
    428  Query_2244025     2OFV_A   40.000             285        141        8
    429  Query_2244025     3VW8_A   37.594             266        150        6
    430  Query_2244025     2OF2_A   40.000             285        141        8
    431  Query_2244025     2PL0_A   40.000             285        141        8
    432  Query_2244025     8VI1_A   37.218             266        151        6
    433  Query_2244025     9SZJ_A   37.218             266        151        6
    434  Query_2244025     9C1R_A   37.218             266        151        6
    435  Query_2244025     5HLW_A   37.218             266        151        6
    436  Query_2244025     8AW1_A   37.218             266        151        6
    437  Query_2244025     4KIO_A   38.662             269        147        6
    438  Query_2244025     3MPM_A   39.858             281        139        8
    439  Query_2244025     2HEL_A   35.664             286        168        6
    440  Query_2244025     8AU5_A   37.218             266        151        6
    441  Query_2244025     6HH1_A   38.206             301        171        6
    442  Query_2244025     2DQ7_X   38.571             280        152        7
    443  Query_2244025     3Q6W_A   37.218             266        151        6
    444  Query_2244025     4IWD_A   37.218             266        151        6
    445  Query_2244025     8AU3_A   37.218             266        151        6
    446  Query_2244025     8ANS_A   37.218             266        151        6
    447  Query_2244025     6SDC_A   37.218             266        151        6
    448  Query_2244025     8GMB_A   38.321             274        151        5
    449  Query_2244025     3SXR_A   38.182             275        152        5
    450  Query_2244025     6I99_A   38.182             275        152        5
    451  Query_2244025     3BYO_A   39.649             285        142        8
    452  Query_2244025     3BYM_A   39.649             285        142        8
    453  Query_2244025     3KXZ_A   39.649             285        142        8
    454  Query_2244025     3ZFM_A   32.993             294        183        5
    455  Query_2244025     1QPC_A   39.649             285        142        8
    456  Query_2244025     2ZM1_A   39.649             285        142        8
    457  Query_2244025     2OFU_A   39.649             285        142        8
    458  Query_2244025     5XY1_A   38.433             268        146        6
    459  Query_2244025     3CE3_A   36.466             266        153        6
    460  Query_2244025     6PDJ_A   39.649             285        142        8
    461  Query_2244025     3A4O_X   38.235             272        149        6
    462  Query_2244025     3KMM_A   39.649             285        142        8
    463  Query_2244025     3DKC_A   36.466             266        153        6
    464  Query_2244025     1R0P_A   36.466             266        153        6
    465  Query_2244025     3QTI_A   36.466             266        153        6
    466  Query_2244025     1QPD_A   39.649             285        142        8
    467  Query_2244025     3A4P_A   36.466             266        153        6
    468  Query_2244025     7EEF_A   35.664             286        168        6
    469  Query_2244025     2ZV7_A   38.060             268        147        6
    470  Query_2244025     3CC6_A   36.704             267        156        5
    471  Query_2244025     5TO8_A   36.704             267        156        5
    472  Query_2244025     3ET7_A   36.704             267        156        5
    473  Query_2244025     1JPA_A   32.993             294        183        5
    474  Query_2244025     4H1J_A   36.704             267        156        5
    475  Query_2244025     7EEC_A   35.664             286        168        6
    476  Query_2244025     5HOA_A   36.090             266        154        6
    477  Query_2244025     1FVR_A   36.237             287        163        6
    478  Query_2244025     1T46_A   36.184             304        177        6
    479  Query_2244025     4U0I_A   36.184             304        177        6
    480  Query_2244025     2OO8_X   35.714             294        169        6
    481  Query_2244025     3C1X_A   36.466             266        153        6
    482  Query_2244025     6MOB_A   36.721             305        174        7
    483  Query_2244025     2J0L_A   37.687             268        154        6
    484  Query_2244025     7ZW8_A   36.721             305        174        7
    485  Query_2244025     7EED_A   35.664             286        168        6
    486  Query_2244025     2REI_A   35.664             286        168        6
    487  Query_2244025     1T45_A   35.780             327        188        8
    488  Query_2244025     3G0E_A   35.780             327        188        8
    489  Query_2244025     5HOR_A   36.090             266        154        6
    490  Query_2244025     3PLS_A   37.175             269        153        6
    491  Query_2244025     2HEN_A   32.653             294        184        5
    492  Query_2244025     6CZ3_A   39.427             279        150        6
    493  Query_2244025     7AYM_A   35.548             301        160        7
    494  Query_2244025     2WQB_A   35.889             287        164        6
    495  Query_2244025     8X2A_A   37.455             275        154        5
    496  Query_2244025     3DKG_A   36.090             266        154        6
    497  Query_2244025     4X3J_A   35.889             287        164        6
    498  Query_2244025     3CJF_A   36.170             282        169        5
    499  Query_2244025     6ITV_A   35.780             327        188        8
    500  Query_2244025     1PKG_A   36.458             288        167        5
    501  Query_2244025     5DA3_A   39.273             275        148        6
    502  Query_2244025     5D7V_A   39.273             275        148        6
    503  Query_2244025     5H2U_A   39.273             275        148        6
    504  Query_2244025     4AW5_A   34.483             290        176        4
    505  Query_2244025     2HK5_A   38.545             275        149        7
    506  Query_2244025     5ZJ6_A   38.545             275        149        7
    507  Query_2244025     3G0F_A   35.474             327        189        8
    508  Query_2244025     3CJG_A   36.879             282        167        6
    509  Query_2244025     3WZD_A   36.014             286        168        5
    510  Query_2244025     2YN8_A   34.737             285        172        4
    511  Query_2244025     6TY3_A   38.060             268        153        6
    512  Query_2244025     2J0K_A   38.060             268        153        6
    513  Query_2244025     3ZEW_A   34.386             285        173        4
    514  Query_2244025     2J0J_A   38.060             268        153        6
    515  Query_2244025     6FNI_A   34.737             285        172        4
    516  Query_2244025     3VNT_A   37.063             286        165        7
    517  Query_2244025     7FEH_A   36.271             295        156        8
    518  Query_2244025     4MXY_A   38.434             281        151        8
    519  Query_2244025     6CZ2_A   39.068             279        151        6
    520  Query_2244025     3GEQ_A   38.214             280        153        7
    521  Query_2244025     5SAU_A   36.271             295        156        8
    522  Query_2244025     2XIR_A   36.014             286        168        5
    523  Query_2244025     3EWH_A   36.014             286        168        5
    524  Query_2244025     2VWU_A   34.386             285        173        4
    525  Query_2244025     3U6J_A   36.014             286        168        5
    526  Query_2244025     6GQO_A   36.014             286        168        5
    527  Query_2244025     3D7T_A   38.095             273        145        8
    528  Query_2244025     3ZOS_A   36.000             300        156        8
    529  Query_2244025     2BDF_A   38.434             281        151        8
    530  Query_2244025     4AGC_A   36.014             286        168        5
    531  Query_2244025     5BVK_A   36.000             300        156        8
    532  Query_2244025     8JF3_A   38.434             281        151        8
    533  Query_2244025     7NG7_A   37.857             280        154        7
    534  Query_2244025     3G6H_A   37.857             280        154        7
    535  Query_2244025     8HAQ_A   38.434             281        151        8
    536  Query_2244025     5FDP_A   36.000             300        156        8
    537  Query_2244025     4MXO_A   37.857             280        154        7
    538  Query_2244025     6E6E_A   38.571             280        150        8
    539  Query_2244025     7OTE_A   37.857             280        154        7
    540  Query_2244025     3D7U_A   38.095             273        145        8
    541  Query_2244025     6BRJ_A   36.000             300        156        8
    542  Query_2244025     1BYG_A   38.095             273        145        8
    543  Query_2244025     4MXX_A   37.857             280        154        7
    544  Query_2244025     7MO7_B   37.594             266        150        6
    545  Query_2244025     6Y23_A   36.000             300        156        8
    546  Query_2244025     2OIQ_A   37.857             280        154        7
    547  Query_2244025     3D7U_B   37.857             280        154        7
    548  Query_2244025     3OEZ_A   37.857             280        154        7
    549  Query_2244025     2QI8_A   37.857             280        154        7
    550  Query_2244025     3SVV_A   37.857             280        154        7
    551  Query_2244025     3U4W_A   38.043             276        151        7
    552  Query_2244025     9NS1_A   38.078             281        152        8
    553  Query_2244025     3ZFY_A   35.088             285        171        5
    554  Query_2244025     1VR2_A   35.664             286        169        5
    555  Query_2244025     1YOL_A   38.078             281        152        8
    556  Query_2244025     1QCF_A   38.686             274        148        7
    557  Query_2244025     9BYJ_A   38.686             274        148        7
    558  Query_2244025     4MCV_A   37.857             280        154        7
    559  Query_2244025     3C7Q_A   35.915             284        169        6
    560  Query_2244025     4LGH_A   37.857             280        154        7
    561  Query_2244025     2HWO_A   37.857             280        154        7
    562  Query_2244025     5T0P_A   37.857             280        154        7
    563  Query_2244025     9NS0_A   38.078             281        152        8
    564  Query_2244025     5SWH_A   37.500             280        155        7
    565  Query_2244025     3DQW_A   37.500             280        155        7
    566  Query_2244025     7ZVS_A   36.770             291        162        8
    567  Query_2244025     9BT8_C   37.993             279        153        7
    568  Query_2244025     1YOJ_A   37.722             281        153        8
    569  Query_2244025     9IRL_A   37.993             279        153        7
    570  Query_2244025     1FMK_A   37.993             279        153        7
    571  Query_2244025     1Y57_A   37.993             279        153        7
    572  Query_2244025     8JN8_A   37.993             279        153        7
    573  Query_2244025     2P2I_A   35.315             286        170        5
    574  Query_2244025     2H8H_A   37.993             279        153        7
    575  Query_2244025     2OH4_A   35.439             285        170        5
    576  Query_2244025     4K11_A   37.993             279        153        7
    577  Query_2244025     1YWN_A   35.315             286        170        5
    578  Query_2244025     1YI6_A   38.214             280        151        8
    579  Query_2244025     2P2H_A   35.315             286        170        5
    580  Query_2244025     1KSW_A   37.993             279        153        7
    581  Query_2244025     1K9A_A   38.095             273        145        8
    582  Query_2244025     8XN8_A   37.634             279        154        7
    583  Query_2244025     6F3F_A   37.634             279        154        7
    584  Query_2244025     2PTK_A   36.972             284        149        7
    585  Query_2244025     4LGG_A   37.729             273        150        7
    586  Query_2244025     1AD5_A   37.591             274        141        7
    587  Query_2244025     3KUL_A   32.095             296        181        6
    588  Query_2244025     6TUA_A   32.042             284        184        4
    589  Query_2244025     1U59_A   36.842             266        154        8
    590  Query_2244025     3KUL_B   31.757             296        182        6
    591  Query_2244025     7UY0_A   37.500             280        155        7
    592  Query_2244025     7UY0_B   37.500             280        155        7
    593  Query_2244025     2OZO_A   35.495             293        167        9
    594  Query_2244025     4K2R_A   35.495             293        167        9
    595  Query_2244025     7KP6_A   35.252             278        154       10
    596  Query_2244025     8FE9_A   35.252             278        154       10
    597  Query_2244025     4DFL_A   35.036             274        161        8
    598  Query_2244025     4RX7_A   35.036             274        161        8
    599  Query_2244025     4HZR_A   35.252             278        154       10
    600  Query_2244025     4RX9_A   35.036             274        161        8
    601  Query_2244025     4PV0_A   35.036             274        161        8
    602  Query_2244025     3EMG_A   33.798             287        171        8
    603  Query_2244025     6VQM_A   35.636             275        151       10
    604  Query_2244025     6VOV_A   35.036             274        161        8
    605  Query_2244025     3EQP_A   35.636             275        151       10
    606  Query_2244025     1U46_A   35.636             275        151       10
    607  Query_2244025     5ZXB_A   35.636             275        151       10
    608  Query_2244025     4F4P_A   35.036             274        161        8
    609  Query_2244025     4ID7_A   35.636             275        151       10
    610  Query_2244025     8X5K_A   35.036             274        161        8
    611  Query_2244025     4PX6_A   35.036             274        161        8
    612  Query_2244025     5TR6_A   35.036             274        161        8
    613  Query_2244025     5Y5T_A   35.036             274        161        8
    614  Query_2244025     4RSS_A   35.036             274        161        8
    615  Query_2244025     3SRV_B   35.036             274        161        8
    616  Query_2244025     1XBA_A   35.036             274        161        8
    617  Query_2244025     4YJO_A   35.036             274        161        8
    618  Query_2244025     3TUB_A   35.036             274        161        8
    619  Query_2244025     3TUC_A   35.036             274        161        8
    620  Query_2244025     4HZS_A   35.636             275        151       10
    621  Query_2244025     7JXH_A   34.909             275        162        7
    622  Query_2244025     3PP0_A   33.916             286        172        7
    623  Query_2244025     7PCD_A   33.916             286        172        7
    624  Query_2244025     3SRV_A   33.449             287        172        8
    625  Query_2244025     1U54_A   35.273             275        152       10
    626  Query_2244025     4EWH_A   35.273             275        152       10
    627  Query_2244025     8HV4_A   33.217             286        171        8
    628  Query_2244025     9S3X_A   33.217             286        171        8
    629  Query_2244025     6LUB_A   33.217             286        171        8
    630  Query_2244025     6HM6_A   34.672             274        162        8
    631  Query_2244025     9D3V_A   33.217             286        171        8
    632  Query_2244025     5XGN_A   32.867             286        172        8
    633  Query_2244025     8WD4_A   33.217             286        171        8
    634  Query_2244025     8H7X_A   32.867             286        172        8
    635  Query_2244025     2R4B_A   31.293             294        187        6
    636  Query_2244025     5GNK_A   32.867             286        172        8
    637  Query_2244025     9XU9_A   32.867             286        172        8
    638  Query_2244025     5GMP_A   32.867             286        172        8
    639  Query_2244025     8HY7_A   33.217             286        171        8
    640  Query_2244025     4RJ4_A   33.217             286        171        8
    641  Query_2244025     4G5P_A   32.867             286        172        8
    642  Query_2244025     9JQ1_A   32.867             286        172        8
    643  Query_2244025     5CNN_A   31.818             286        178        7
    644  Query_2244025     6S9B_A   33.217             286        171        8
    645  Query_2244025     4I24_A   32.867             286        172        8
    646  Query_2244025     3IKA_A   32.867             286        172        8
    647  Query_2244025     5Y9T_A   32.867             286        172        8
    648  Query_2244025     5ZWJ_A   32.867             286        172        8
    649  Query_2244025     6S9C_A   33.217             286        171        8
    650  Query_2244025     5FEE_A   32.867             286        172        8
    651  Query_2244025     2JIU_A   32.867             286        172        8
    652  Query_2244025     2JIT_A   32.867             286        172        8
    653  Query_2244025     4WKQ_A   32.867             286        172        8
    654  Query_2244025     2J5E_A   32.867             286        172        8
    655  Query_2244025     4ZSE_A   32.867             286        172        8
    656  Query_2244025     6TFU_A   32.867             286        172        8
    657  Query_2244025     5J9Z_A   32.867             286        172        8
    658  Query_2244025     5J9Y_A   32.867             286        172        8
    659  Query_2244025     3BBT_B   31.399             293        186        6
    660  Query_2244025     6V5N_A   32.867             286        172        8
    661  Query_2244025     8RRQ_A   32.867             286        175        7
    662  Query_2244025     4YJQ_A   32.867             286        175        7
    663  Query_2244025     6P1D_A   32.867             286        172        8
    664  Query_2244025     4ZJV_A   32.867             286        172        8
    665  Query_2244025     4TKS_A   32.867             286        172        8
    666  Query_2244025     5CAV_A   32.867             286        172        8
    667  Query_2244025     3VJO_A   32.867             286        172        8
    668  Query_2244025     7AEM_A   32.867             286        172        8
    669  Query_2244025     8HV2_A   32.867             286        172        8
    670  Query_2244025     2RFD_A   32.313             294        179        8
    671  Query_2244025     4LI5_A   32.867             286        172        8
    672  Query_2244025     1M14_A   32.867             286        172        8
    673  Query_2244025     4G5J_A   32.867             286        172        8
    674  Query_2244025     5FED_A   32.867             286        172        8
    675  Query_2244025     4I23_A   32.867             286        172        8
    676  Query_2244025     2GS2_A   32.867             286        172        8
    677  Query_2244025     2ITW_A   32.867             286        172        8
    678  Query_2244025     9FZR_A   32.867             286        172        8
    679  Query_2244025     4I21_A   32.867             286        172        8
    680  Query_2244025     4LL0_A   32.867             286        172        8
    681  Query_2244025     9KLW_A   32.867             286        172        8
    682  Query_2244025     5C26_A   32.867             286        175        7
    683  Query_2244025     6JZ0_A   32.867             286        172        8
    684  Query_2244025     3HNG_A   42.683             164         90        2
    685  Query_2244025     7UKV_A   32.867             286        172        8
    686  Query_2244025     4JQ7_A   32.867             286        172        8
    687  Query_2244025     8A27_A   32.867             286        172        8
    688  Query_2244025     9H42_A   32.867             286        172        8
    689  Query_2244025     2RGP_A   32.867             286        172        8
    690  Query_2244025     9N6G_A   32.867             286        172        8
    691  Query_2244025     4FL2_A   33.798             287        171        8
    692  Query_2244025     8PO3_A   32.867             286        172        8
    693  Query_2244025     3LZB_A   32.867             286        172        8
    694  Query_2244025     8PO4_A   32.867             286        172        8
    695  Query_2244025     9BY4_A   32.867             286        172        8
    696  Query_2244025     8KFQ_A   32.867             286        172        8
    697  Query_2244025     7OXB_A   32.867             286        172        8
    698  Query_2244025     4RIW_B   32.867             286        172        8
    699  Query_2244025     4FL3_A   33.798             287        171        8
    700  Query_2244025   9QXN_AAA   32.867             286        172        8
    701  Query_2244025     3W2O_A   32.867             286        172        8
    702  Query_2244025     5Y25_A   32.867             286        172        8
    703  Query_2244025     4I1Z_A   32.867             286        172        8
    704  Query_2244025     1XKK_A   32.867             286        172        8
    705  Query_2244025     2GS7_A   32.867             286        172        8
    706  Query_2244025     3UG1_A   32.517             286        173        8
    707  Query_2244025     8VB5_A   33.448             290        172        8
    708  Query_2244025     5XDL_A   32.867             286        172        8
    709  Query_2244025     8D73_A   32.867             286        172        8
    710  Query_2244025     6JWL_A   32.867             286        172        8
    711  Query_2244025     4HJO_A   32.867             286        172        8
    712  Query_2244025     4LQM_A   32.867             286        172        8
    713  Query_2244025     2EB3_A   32.867             286        172        8
    714  Query_2244025     2ITT_A   32.867             286        172        8
    715  Query_2244025     4R3P_A   32.867             286        172        8
    716  Query_2244025     8U8X_A   32.441             299        181        8
    717  Query_2244025     7K1H_A   32.867             286        172        8
    718  Query_2244025     4I20_A   32.867             286        172        8
    719  Query_2244025     2EB2_A   32.517             286        173        8
    720  Query_2244025     8A2B_A   32.867             286        172        8
    721  Query_2244025     2ITN_A   32.517             286        173        8
    722  Query_2244025     4RT7_A   45.029             171         87        3
    723  Query_2244025     4RT7_A   29.412             136         94        2
    724  Query_2244025     9QBG_A   30.829             386        232       11
    725  Query_2244025     9QBF_A   30.829             386        232       11
    726  Query_2244025     7MN5_B   30.075             399        244       11
    727  Query_2244025     7MN6_B   30.075             399        244       11
    728  Query_2244025     3GOP_A   32.517             286        173        8
    729  Query_2244025     9U8C_A   31.104             299        186        8
    730  Query_2244025     6JRJ_A   33.217             286        171        8
    731  Query_2244025     8DSW_A   32.414             290        172        9
    732  Query_2244025     9DF2_A   32.526             289        172        9
    733  Query_2244025     6S89_A   33.217             286        171        8
    734  Query_2244025     4LRM_A   32.526             289        172        9
    735  Query_2244025     8PO0_A   32.526             289        172        9
    736  Query_2244025     9DF3_A   32.526             289        172        9
    737  Query_2244025     8PO1_A   32.526             289        172        9
    738  Query_2244025     7LGS_A   32.526             289        172        9
    739  Query_2244025     9FQP_A   32.526             289        172        9
    740  Query_2244025     7TVD_A   32.517             286        170        9
    741  Query_2244025     9P9U_A   32.867             286        172        8
    742  Query_2244025     9P9U_A   32.867             286        172        8
    743  Query_2244025     6JRK_A   33.217             286        171        8
    744  Query_2244025     3VHE_A   41.143             175         99        2
    745  Query_2244025     3VID_A   41.143             175         99        2
    746  Query_2244025     3VHK_A   41.143             175         99        2
    747  Query_2244025     1Y6A_A   41.143             175         99        2
    748  Query_2244025     6SEQ_A   31.597             288        175        8
    749  Query_2244025     7SYD_A   32.867             286        172        8
    750  Query_2244025     7SZ0_A   32.867             286        172        8
    751  Query_2244025     5WNO_A   30.000             270        177        4
    752  Query_2244025     8DFQ_A   45.098             153         80        2
    753  Query_2244025     8DFM_A   45.098             153         80        2
    754  Query_2244025     8DFP_A   45.098             153         80        2
    755  Query_2244025     5TQ5_A   29.000             300        184        9
    756  Query_2244025     3UGC_A   28.620             297        183        9
    757  Query_2244025     4BBE_A   28.716             296        182        9
    758  Query_2244025     6TPD_A   28.328             293        181        9
    759  Query_2244025     8G6Z_A   28.667             300        185        9
    760  Query_2244025     7LL5_A   28.716             296        182        9
    761  Query_2244025     4RIY_A   31.769             277        168        6
    762  Query_2244025     7RN6_A   28.716             296        182        9
    763  Query_2244025     7LL4_A   28.716             296        182        9
    764  Query_2244025     7TEU_A   28.378             296        183        9
    765  Query_2244025     5USY_A   28.716             296        182        9
    766  Query_2244025     6VGL_A   28.716             296        182        9
    767  Query_2244025     4E6D_A   29.054             296        181        9
    768  Query_2244025     3KRR_A   28.956             297        182        9
    769  Query_2244025     4ZIM_A   28.667             300        185        9
    770  Query_2244025     4YTC_A   28.378             296        183        9
    771  Query_2244025     5TQ4_A   28.667             300        185        9
    772  Query_2244025     5HEZ_A   28.716             296        182        9
    773  Query_2244025     8G8O_A   28.667             300        185        9
    774  Query_2244025     4GL9_A   29.054             296        181        9
    775  Query_2244025     3IO7_A   28.378             296        183        9
    776  Query_2244025     3TJC_A   28.667             300        185        9
    777  Query_2244025     4E4M_A   28.716             296        182        9
    778  Query_2244025     5TQ3_A   28.716             296        182        9
    779  Query_2244025     7Q7I_A   28.571             308        186       10
    780  Query_2244025     3JY9_A   28.378             296        183        9
    781  Query_2244025     5TQ6_A   28.716             296        182        9
    782  Query_2244025     2B7A_A   28.716             296        182        9
    783  Query_2244025     3Q32_A   28.523             298        184        9
    784  Query_2244025     4HGE_A   28.716             296        182        9
    785  Query_2244025     6WTN_A   28.716             296        182        9
    786  Query_2244025     7UYW_A   28.669             293        180        9
    787  Query_2244025     4D0W_A   28.716             296        182        9
    788  Query_2244025     5WEV_A   28.716             296        182        9
    789  Query_2244025     4RIX_A   31.408             277        169        6
    790  Query_2244025     3E62_A   28.716             296        182        9
    791  Query_2244025     3KEX_A   31.408             277        169        6
    792  Query_2244025     4AQC_A   28.716             296        182        9
    793  Query_2244025     8BM2_A   28.716             296        182        9
    794  Query_2244025     6OP9_A   31.408             277        169        6
    795  Query_2244025     4RIW_A   31.408             277        169        6
    796  Query_2244025     4UYA_A   30.721             319        180       10
    797  Query_2244025     8BX6_A   28.716             296        182        9
    798  Query_2244025     2W1I_A   28.617             311        190       10
    799  Query_2244025     3LMG_A   31.408             277        169        6
    800  Query_2244025     3RVG_A   28.716             296        182        9
    801  Query_2244025     5KHW_A   29.283             321        200        7
    802  Query_2244025     6AAJ_A   28.378             296        183        9
    803  Query_2244025     3ZMM_A   28.378             296        183        9
    804  Query_2244025     2XA4_A   28.378             296        183        9
    805  Query_2244025     6C7Y_A   30.796             289        173        7
    806  Query_2244025     5F1Z_A   31.000             300        168        8
    807  Query_2244025     3NYX_A   31.000             300        168        8
    808  Query_2244025     4GVJ_A   31.419             296        164        8
    809  Query_2244025     3NZ0_A   31.419             296        164        8
    810  Query_2244025     5CEN_A   31.068             309        181       10
    811  Query_2244025     8DEG_A   31.068             309        181       10
    812  Query_2244025     4E1Z_A   30.952             294        162        8
    813  Query_2244025     7UYR_A   31.250             288        155        9
    814  Query_2244025     4GIH_A   31.081             296        165        8
    815  Query_2244025     6AAM_A   31.119             286        158        8
    816  Query_2244025     4E20_A   31.010             287        157        8
    817  Query_2244025     6N7A_A   30.450             289        174        7
    818  Query_2244025     6GGH_A   30.450             289        174        7
    819  Query_2244025     6TPE_A   30.450             289        174        7
    820  Query_2244025     3EYG_A   30.450             289        174        7
    821  Query_2244025     4E4L_A   30.450             289        174        7
    822  Query_2244025     4RIO_A   31.034             290        158        9
    823  Query_2244025     6ELR_A   30.450             289        174        7
    824  Query_2244025     4HVD_A   31.034             290        158        9
    825  Query_2244025     7T6F_A   29.154             319        199        7
    826  Query_2244025     7T6F_A   26.174             298        196       11
    827  Query_2244025     4OLI_A   30.000             330        190       10
    828  Query_2244025     5TOZ_A   31.034             290        158        9
    829  Query_2244025     3PJC_A   31.034             290        158        9
    830  Query_2244025   7Q6H_AAA   31.034             290        158        9
    831  Query_2244025     7MN5_A   28.571             364        221       10
    832  Query_2244025     3LXK_A   31.034             290        158        9
    833  Query_2244025     4PY1_A   31.119             286        158        8
    834  Query_2244025     3LXN_A   31.119             286        158        8
    835  Query_2244025     5LWM_A   30.333             300        167        9
    836  Query_2244025     4QPS_A   30.690             290        159        9
    837  Query_2244025     3ZC6_A   30.822             292        156       10
    838  Query_2244025     5W86_A   30.822             292        156       10
    839  Query_2244025     7UYV_A   30.822             292        156       10
    840  Query_2244025     7C3N_A   30.822             292        156       10
    841  Query_2244025     6HZV_A   30.822             292        156       10
    842  Query_2244025     8GW3_A   30.249             281        173        8
    843  Query_2244025     3DTC_A   29.825             285        174        8
    844  Query_2244025     4YHT_A   29.123             285        172        9
    845  Query_2244025     4FK3_A   28.571             294        180        9
    846  Query_2244025     8C7Y_A   29.066             289        175        9
    847  Query_2244025     1YVJ_A   30.345             290        160       10
    848  Query_2244025     4Z16_A   30.345             290        160       10
    849  Query_2244025     4UY9_A   29.825             285        174        8
    850  Query_2244025     4V0G_B   30.479             292        157       10
    851  Query_2244025     6V34_A   28.231             294        181        9
    852  Query_2244025     4WO5_A   29.293             297        178       10
    853  Query_2244025     4CQE_A   28.276             290        178        9
    854  Query_2244025     4XV1_A   28.276             290        178        9
    855  Query_2244025     4V0G_A   30.479             292        157       10
    856  Query_2244025     5JRQ_A   28.772             285        173        9
    857  Query_2244025     6P3D_A   28.276             290        178        9
    858  Query_2244025     3OG7_A   28.772             285        173        9
    859  Query_2244025     4RZV_A   29.066             289        175        9
    860  Query_2244025     5CSW_A   29.066             289        175        9
    861  Query_2244025     6XFP_A   29.066             289        175        9
    862  Query_2244025     7P3V_A   28.772             285        173        9
    863  Query_2244025     6U2H_C   28.571             294        180        9
    864  Query_2244025     4JVG_A   29.066             289        175        9
    865  Query_2244025     5GJD_A   30.435             276        169        8
    866  Query_2244025     4GS6_A   30.435             276        169        8
    867  Query_2244025     4XV9_A   29.066             289        175        9
    868  Query_2244025     4L52_A   30.435             276        169        8
    869  Query_2244025     2EVA_A   30.435             276        169        8
    870  Query_2244025     4O91_A   30.435             276        169        8
    871  Query_2244025     3C4C_A   29.066             289        175        9
    872  Query_2244025     9FPD_A   30.108             279        172        8
    873  Query_2244025     8F7O_A   28.720             289        176        9
    874  Query_2244025     3PPZ_A   28.904             301        187       10
    875  Query_2244025     5HI2_A   29.167             288        171        9
    876  Query_2244025     5ITA_A   28.276             290        178        9
    877  Query_2244025     3P86_A   28.571             301        188       10
    878  Query_2244025     5X5O_A   27.597             308        183       11
    879  Query_2244025     5HES_A   27.852             298        175       11
    880  Query_2244025    9RPV_N1   27.458             295        180        9
    881  Query_2244025     4YZM_A   27.055             292        181       13
    882  Query_2244025     8C0A_A   23.944             284        193        7
    883  Query_2244025     6G3C_A   24.113             282        191        7
    884  Query_2244025     6D2I_A   24.113             282        191        7
    885  Query_2244025     5WIJ_A   23.944             284        193        7
    886  Query_2244025     5I4N_A   23.944             284        193        7
    887  Query_2244025     4FVP_A   24.113             282        191        7
    888  Query_2244025     8B8N_A   23.944             284        193        7
    889  Query_2244025   8ATB_AAA   27.305             282        174        7
    890  Query_2244025     8C08_A   24.199             281        190        7
    891  Query_2244025   8ATL_AAA   27.305             282        174        7
    892  Query_2244025     4FVR_A   23.944             284        193        7
    893  Query_2244025     5NXD_A   26.316             285        175        7
    894  Query_2244025     7F7W_A   23.944             284        193        7
    895  Query_2244025     4TPT_A   26.316             285        175        7
    896  Query_2244025     8EX2_A   23.592             284        194        7
    897  Query_2244025     8C09_A   23.944             284        193        7
    898  Query_2244025     4F0F_A   26.370             292        183       13
    899  Query_2244025   8ATL_BBB   27.305             282        174        7
    900  Query_2244025     9ND3_A   23.944             284        193        7
    901  Query_2244025     9ND5_A   23.944             284        193        7
    902  Query_2244025     4F1O_A   26.370             292        183       13
    903  Query_2244025     9GB9_A   29.577             213        127        6
    904  Query_2244025     4F1M_A   27.551             294        177       15
    905  Query_2244025     9F32_A   26.182             275        175        8
    906  Query_2244025     8P5G_A   26.182             275        175        8
    907  Query_2244025     6MNH_A   26.182             275        175        8
    908  Query_2244025     4WNO_A   26.182             275        175        8
    909  Query_2244025     6QAS_A   26.182             275        175        8
    910  Query_2244025     8SV9_A   26.182             275        175        8
    911  Query_2244025     4L00_A   25.676             296        192       11
    912  Query_2244025     5EBZ_A   28.571             217        131        7
    913  Query_2244025     6EG9_A   33.010             206        120        6
    914  Query_2244025     4L01_A   25.676             296        192       11
    915  Query_2244025     6THW_A   33.010             206        120        6
    916  Query_2244025     8P5H_A   26.182             275        175        8
    917  Query_2244025     6F3E_A   33.010             206        120        6
    918  Query_2244025     2NRY_A   33.010             206        120        6
    919  Query_2244025     3A7F_A   26.786             280        180        9
    920  Query_2244025     7B30_A   26.882             279        179        9
    921  Query_2244025     6O8U_A   33.010             206        120        6
    922  Query_2244025     5UIS_A   33.010             206        120        6
    923  Query_2244025     7QG3_A   33.010             206        120        6
    924  Query_2244025     4QML_A   26.690             281        181        9
    925  Query_2244025     6MOM_A   33.010             206        120        6
    926  Query_2244025     6THX_A   33.010             206        120        6
    927  Query_2244025     5W84_A   33.010             206        120        6
    928  Query_2244025     4RMZ_A   33.010             206        120        6
    929  Query_2244025     6LXY_A   33.010             206        120        6
    930  Query_2244025     4U8Z_A   26.786             280        180        9
    931  Query_2244025     4W8E_A   26.786             280        180        9
    932  Query_2244025     9NA2_A   33.010             206        120        6
    933  Query_2244025     4Y73_A   33.010             206        120        6
    934  Query_2244025     6O94_A   33.010             206        120        6
    935  Query_2244025     5K72_A   33.010             206        120        6
    936  Query_2244025     9PSU_A   33.010             206        120        6
    937  Query_2244025     7C2V_A   33.010             206        120        6
    938  Query_2244025     2NRU_A   33.010             206        120        6
    939  Query_2244025     2OIB_A   33.010             206        120        6
    940  Query_2244025   8BR5_AAA   33.010             206        120        6
    941  Query_2244025     6N8G_A   33.010             206        120        6
    942  Query_2244025     5UIQ_A   33.010             206        120        6
    943  Query_2244025     5UIT_A   33.010             206        120        6
    944  Query_2244025     6F3D_A   33.010             206        120        6
    945  Query_2244025     6F3G_A   33.010             206        120        6
    946  Query_2244025     7C2W_A   33.010             206        120        6
    947  Query_2244025     6F3I_A   33.010             206        120        6
    948  Query_2244025     8V1O_A   33.010             206        120        6
    949  Query_2244025     8SCV_A   31.163             215        112        6
    950  Query_2244025     6CTH_A   31.696             224        133        8
    951  Query_2244025     4U97_A   32.524             206        121        6
    952  Query_2244025     6EGD_A   32.524             206        121        6
    953  Query_2244025     8DKS_A   33.010             206        120        6
    954  Query_2244025     8WTF_A   32.524             206        121        6
    955  Query_2244025     1U5Q_A   26.246             301        175       10
    956  Query_2244025     7Z4V_A   27.622             286        167       10
    957  Query_2244025     2GCD_A   26.573             286        170        9
    958  Query_2244025     3S95_A   26.882             279        166        9
    959  Query_2244025     3CKX_A   26.740             273        175        9
    960  Query_2244025     3ZHP_C   26.966             267        170        9
    961  Query_2244025     3CKW_A   26.740             273        175        9
    962  Query_2244025     4O27_B   26.966             267        170        9
    963  Query_2244025     9V70_A   28.986             207        123        7
    964  Query_2244025     2XIK_A   27.622             286        167       10
    965  Query_2244025     6C4D_A   25.794             252        156       10
    966  Query_2244025     9LBG_A   25.253             297        193       11
    967  Query_2244025     9V71_A   28.986             207        123        7
    968  Query_2244025     6GR8_A   27.273             264        169        8
    969  Query_2244025     6C3E_A   25.794             252        156       10
    970  Query_2244025     9HY8_A   25.794             252        156       10
    971  Query_2244025     7FCZ_A   25.794             252        156       10
    972  Query_2244025     5XD6_A   25.352             284        179        9
    973  Query_2244025     6NYH_A   25.794             252        156       10
    974  Query_2244025     2O8Y_A   30.841             214        112        6
    975  Query_2244025     5HVJ_A   26.523             279        167        9
    976  Query_2244025     5HX6_A   25.794             252        156       10
    977  Query_2244025     5HVK_A   26.855             283        161       10
    978  Query_2244025     4NZW_B   26.923             286        169        9
    979  Query_2244025     6NW2_A   25.794             252        156       10
    980  Query_2244025     9WYR_A   28.502             207        124        7
    981  Query_2244025     9GTG_A   25.794             252        156       10
    982  Query_2244025     9MZY_A   25.820             244        152        9
    983  Query_2244025     9MZZ_A   25.820             244        152        9
    984  Query_2244025     9D51_A   25.283             265        174       10
    985  Query_2244025     9MZX_A   25.820             244        152        9
    986  Query_2244025     6VPJ_A   27.273             275        155        9
    987  Query_2244025     6QAT_A   26.415             265        168       10
    988  Query_2244025     9LBF_A   24.916             297        194       11
    989  Query_2244025     4ITH_A   25.820             244        152        9
    990  Query_2244025     2WTW_A   27.273             275        155        9
    991  Query_2244025     9M41_A   24.916             297        194       11
    992  Query_2244025     2C6E_A   26.370             292        170        9
    993  Query_2244025     6BDN_A   26.159             302        182       11
    994  Query_2244025     4J8M_A   27.273             275        155        9
    995  Query_2244025     4ZJI_A   25.379             264        175        8
    996  Query_2244025     2BMC_A   27.273             275        155        9
    997  Query_2244025     3NRM_A   27.273             275        155        9
    998  Query_2244025     3W10_A   27.273             275        155        9
    999  Query_2244025     3R21_A   27.273             275        155        9
    1000 Query_2244025     3H0Y_A   27.273             275        155        9
    1001 Query_2244025     6VPI_A   26.909             275        156        9
    1002 Query_2244025     2J4Z_A   27.273             275        155        9
    1003 Query_2244025     4ZLO_A   25.379             264        175        8
    1004 Query_2244025     3FDN_A   27.273             275        155        9
    1005 Query_2244025     5OBJ_A   27.273             275        155        9
    1006 Query_2244025     5EW9_A   27.273             275        155        9
    1007 Query_2244025     4NEU_A   25.820             244        152        9
    1008 Query_2244025     2J50_A   27.273             275        155        9
    1009 Query_2244025     3UNZ_A   27.273             275        155        9
    1010 Query_2244025     5DN3_A   27.273             275        155        9
    1011 Query_2244025     1MUO_A   27.273             275        155        9
    1012 Query_2244025     3COH_A   27.273             275        155        9
    1013 Query_2244025     4C3P_A   27.273             275        155        9
    1014 Query_2244025     8C1M_A   27.273             275        155        9
    1015 Query_2244025     6C83_A   27.273             275        155        9
    1016 Query_2244025     4BN1_A   26.909             275        156        9
    1017 Query_2244025     1MQ4_A   27.273             275        155        9
    1018 Query_2244025     2DWB_A   27.273             275        155        9
    1019 Query_2244025     6I2U_A   27.273             275        155        9
    1020 Query_2244025     3W16_A   27.273             275        155        9
    1021 Query_2244025     4PRJ_A   27.273             275        155        9
    1022 Query_2244025     3E5A_A   27.273             275        155        9
    1023 Query_2244025     5ZAN_A   27.273             275        155        9
    1024 Query_2244025     1OL5_A   27.273             275        155        9
    1025 Query_2244025     2XNG_A   27.273             275        155        9
    1026 Query_2244025     3EFW_A   27.273             275        155        9
    1027 Query_2244025     2C6D_A   27.273             275        155        9
    1028 Query_2244025     7O2V_A   27.273             275        155        9
    1029 Query_2244025   9ESA_AAA   26.515             264        171        8
    1030 Query_2244025     4JAI_A   27.273             275        155        9
    1031 Query_2244025     8SSP_A   27.273             275        155        9
    1032 Query_2244025     2XRU_A   27.273             275        155        9
    1033 Query_2244025     3HA6_A   27.273             275        155        9
    1034 Query_2244025     3LAU_A   27.273             275        155        9
    1035 Query_2244025     3FXZ_A   25.000             264        176        8
    1036 Query_2244025     2X6D_A   27.273             275        155        9
    1037 Query_2244025     4UZD_A   27.273             275        155        9
    1038 Query_2244025     9GFZ_A   27.397             219        123        7
    1039 Query_2244025     3W2C_A   27.273             275        155        9
    1040 Query_2244025     5DT3_A   27.273             275        155        9
    1041 Query_2244025     8JF4_A   27.273             275        155        9
    1042 Query_2244025     2W1D_A   27.273             275        155        9
    1043 Query_2244025     5DT4_A   27.273             275        155        9
    1044 Query_2244025     6XKA_A   27.273             275        155        9
    1045 Query_2244025     5DOS_A   27.273             275        155        9
    1046 Query_2244025     6VPL_A   27.273             275        155        9
    1047 Query_2244025     4EQC_A   25.000             264        176        8
    1048 Query_2244025     6VPG_A   27.273             275        155        9
    1049 Query_2244025     2W1C_A   27.273             275        155        9
    1050 Query_2244025     3Q52_A   25.000             264        176        8
    1051 Query_2244025     4ZY4_A   25.000             264        176        8
    1052 Query_2244025     1F3M_C   25.000             264        176        8
    1053 Query_2244025     7VTO_A   25.000             264        176        8
    1054 Query_2244025     3DXN_A   24.691             243        149       10
    1055 Query_2244025     1YHV_A   25.000             264        176        8
    1056 Query_2244025     8X5Z_A   25.000             264        176        8
    1057 Query_2244025     4O0R_A   25.000             264        176        8
    1058 Query_2244025     9D4X_A   25.000             264        176        8
    1059 Query_2244025     1OL6_A   26.909             275        156        9
    1060 Query_2244025     5DEW_A   25.000             264        176        8
    1061 Query_2244025     2WTV_A   26.909             275        156        9
    1062 Query_2244025     2WQE_A   26.909             275        156        9
    1063 Query_2244025     2XNE_A   26.909             275        156        9
    1064 Query_2244025     7ZTL_A   26.129             310        178       11
    1065 Query_2244025     3RZF_A   29.358             218        129       10
    1066 Query_2244025     2BFY_A   27.372             274        172        8
    1067 Query_2244025     9KS6_A   26.909             275        156        9
    1068 Query_2244025     3QA8_A   29.358             218        129       10
    1069 Query_2244025     4O0W_A   26.909             275        156        9
    1070 Query_2244025     4P90_A   25.000             264        176        8
    1071 Query_2244025     10SL_A   25.514             243        156        8
    1072 Query_2244025     3GGF_A   27.803             223        139        7
    1073 Query_2244025     5KBQ_A   25.000             264        176        8
    1074 Query_2244025     5K3Y_A   27.372             274        172        8
    1075 Query_2244025     3Q4Z_A   24.621             264        177        8
    1076 Query_2244025     3IS5_A   25.746             268        174       10
    1077 Query_2244025     4KS7_A   27.068             266        164       11
    1078 Query_2244025     9Z8K_B   24.583             240        162        7
    1079 Query_2244025     5AAD_A   26.909             275        156        9
    1080 Query_2244025     4CEG_A   26.909             275        156        9
    1081 Query_2244025     9BZG_A   26.909             275        156        9
    1082 Query_2244025     10JU_B   24.583             240        162        7
    1083 Query_2244025     5LXM_A   26.909             275        156        9
    1084 Query_2244025     5OS2_A   26.909             275        156        9
    1085 Query_2244025     9KDS_A   26.909             275        156        9
    1086 Query_2244025     5ORL_A   26.909             275        156        9
    1087 Query_2244025     10BL_A   25.514             243        156        8
    1088 Query_2244025     4O0U_A   26.909             275        156        9
    1089 Query_2244025     4IEB_A   26.087             230        147        9
    1090 Query_2244025     2C30_A   27.068             266        164       11
    1091 Query_2244025     6FD3_A   25.000             264        176        8
    1092 Query_2244025     5OS5_A   26.909             275        156        9
    1093 Query_2244025     9Z8K_A   24.583             240        162        7
    1094 Query_2244025     10JU_A   24.583             240        162        7
    1095 Query_2244025     8C1K_A   26.909             275        156        9
    1096 Query_2244025     5OSD_A   26.909             275        156        9
    1097 Query_2244025     8GUW_A   26.909             275        156        9
    1098 Query_2244025     8C15_A   26.909             275        156        9
    1099 Query_2244025     4KIK_A   27.189             217        135        7
    1100 Query_2244025     6VBZ_A   24.653             288        188       13
    1101 Query_2244025     6VPH_A   26.909             275        156        9
    1102 Query_2244025     4B8L_A   27.372             274        172        8
    1103 Query_2244025     4C2V_A   27.372             274        172        8
    1104 Query_2244025     4B8M_A   27.372             274        172        8
    1105 Query_2244025     2VRX_A   27.372             274        172        8
    1106 Query_2244025     3DAJ_A   26.909             275        156        9
    1107 Query_2244025     2BFX_A   27.372             274        172        8
    1108 Query_2244025     4M68_A   25.210             238        156       10
    1109 Query_2244025     3D14_A   26.909             275        156        9
    1110 Query_2244025     3HZT_A   24.691             243        149       10
    1111 Query_2244025     9N48_A   24.621             264        177        8
    1112 Query_2244025     4FZA_B   27.014             211        136        5
    1113 Query_2244025     4C2W_A   27.372             274        172        8
    1114 Query_2244025     5ODT_A   26.545             275        157        9
    1115 Query_2244025     4KIK_B   26.728             217        136        7
    1116 Query_2244025     3QBN_A   26.909             275        156        9
    1117 Query_2244025     8OMV_A   26.728             217        136        7
    1118 Query_2244025     7JUW_B   22.408             299        203       10
    1119 Query_2244025     8BW9_D   25.743             303        184       14
    1120 Query_2244025     3HX4_A   26.087             230        147        9
    1121 Query_2244025     4E3C_A   26.728             217        136        7
    1122 Query_2244025     6HJJ_A   26.545             275        157        9
    1123 Query_2244025     3KU2_A   26.087             230        147        9
    1124 Query_2244025     8OF5_A   26.545             275        157        9
    1125 Query_2244025     5DVR_A   26.087             230        147        9
    1126 Query_2244025     4YGA_A   26.087             230        147        9
    1127 Query_2244025     3DFA_A   26.809             235        150        9
    1128 Query_2244025     2WEI_A   26.809             235        150        9
    1129 Query_2244025     2JAM_A   23.404             235        158        7
    1130 Query_2244025     5EYK_A   26.838             272        172        8
    1131 Query_2244025     4BTF_A   25.210             238        156       10
    1132 Query_2244025     9AXH_C   22.222             288        195       10
    1133 Query_2244025     2QKW_B   26.042             288        173       10
    1134 Query_2244025     3HGK_A   26.042             288        173       10
    1135 Query_2244025     9D8S_A   26.087             253        160       10
    1136 Query_2244025     3IGO_A   26.809             235        150        9
    1137 Query_2244025     8PR7_A   26.182             275        158        9
    1138 Query_2244025     6VC0_A   23.368             291        192       13
    1139 Query_2244025     3MA6_A   26.087             230        147        9
    1140 Query_2244025     4AF3_A   26.562             256        165        8
    1141 Query_2244025     4M97_A   26.087             230        147        9
    1142 Query_2244025   8C12_AAA   29.189             185        116        7
    1143 Query_2244025     2F57_A   29.189             185        116        7
    1144 Query_2244025     3I79_A   26.087             230        147        9
    1145 Query_2244025     3LM0_A   27.083             192        126        5
    1146 Query_2244025     2Y4I_B   21.192             302        201       11
    1147 Query_2244025     3I7C_A   26.087             230        147        9
    1148 Query_2244025     5KKR_B   21.192             302        201       11
    1149 Query_2244025     8PAV_A   23.711             291        170       10
    1150 Query_2244025     3COM_A   23.711             291        170       10
    1151 Query_2244025     6YAT_A   23.711             291        170       10
    1152 Query_2244025     7JUQ_B   21.192             302        201       11
    1153 Query_2244025    9FQR_Er   25.210             238        151        8
    1154 Query_2244025     5FG8_A   23.629             237        165        7
    1155 Query_2244025     9IIC_A   23.158             285        179       10
    1156 Query_2244025     2CN5_A   27.200             250        149       11
    1157 Query_2244025     2YCR_A   27.200             250        149       11
    1158 Query_2244025     2W0J_A   27.200             250        149       11
    1159 Query_2244025     2YCF_A   27.200             250        149       11
    1160 Query_2244025     2XK9_A   27.200             250        149       11
    1161 Query_2244025     5WNI_A   24.026             308        202       12
    1162 Query_2244025     8A66_A   24.762             210        139        6
    1163 Query_2244025     2W4O_A   24.206             252        154        8
    1164 Query_2244025     5DH3_A   24.651             215        143        6
    1165 Query_2244025     8A5J_A   23.636             275        170        9
    1166 Query_2244025     3LIJ_A   23.552             259        177        9
    1167 Query_2244025     4JDJ_A   29.570             186        112        7
    1168 Query_2244025     8A66_B   24.762             210        139        5
    1169 Query_2244025     5VED_A   29.570             186        112        7
    1170 Query_2244025   9R1W_AAA   25.581             215        146        6
    1171 Query_2244025     3I6U_A   26.071             280        171       12
    1172 Query_2244025     4FIE_A   29.570             186        112        7
    1173 Query_2244025     8YHK_A   29.570             186        112        7
    1174 Query_2244025     8AHG_A   28.507             221        134        8
    1175 Query_2244025     4FIF_A   29.570             186        112        7
    1176 Query_2244025     3I6W_A   26.071             280        171       12
    1177 Query_2244025     5UPL_A   29.570             186        112        7
    1178 Query_2244025     4MVF_A   24.891             229        144        9
    1179 Query_2244025     2CDZ_A   29.570             186        112        7
    1180 Query_2244025     2X4Z_A   28.507             221        134        8
    1181 Query_2244025     4XBR_A   28.507             221        134        8
    1182 Query_2244025     4O0V_A   29.570             186        112        7
    1183 Query_2244025     2Q0N_A   29.570             186        112        7
    1184 Query_2244025     5XVA_A   29.570             186        112        7
    1185 Query_2244025     2V5Q_A   25.581             215        146        6
    1186 Query_2244025     5XVF_A   28.507             221        134        8
    1187 Query_2244025     4XBU_A   29.570             186        112        7
    1188 Query_2244025     2BVA_A   28.507             221        134        8
    1189 Query_2244025     4LG4_A   24.286             210        140        6
    1190 Query_2244025     3KB7_A   25.581             215        146        6
    1191 Query_2244025     2YAC_A   25.581             215        146        6
    1192 Query_2244025     2OU7_A   25.581             215        146        6
    1193 Query_2244025     3THB_A   25.581             215        146        6
    1194 Query_2244025     2V7O_A   23.077             234        162        7
    1195 Query_2244025     4LGD_A   24.424             217        145        6
    1196 Query_2244025     4J52_A   25.581             215        146        6
    1197 Query_2244025     2RKU_A   25.581             215        146        6
    1198 Query_2244025     5TA6_A   25.581             215        146        6
    1199 Query_2244025     5IG1_A   24.473             237        160        7
    1200 Query_2244025     2WEL_A   24.138             232        156        8
    1201 Query_2244025     3KN5_A   27.389             157        104        3
    1202 Query_2244025     5VLO_A   24.138             232        156        8
    1203 Query_2244025     7S46_A   29.032             186        113        7
    1204 Query_2244025     6AO5_A   24.286             210        140        6
    1205 Query_2244025     9BLH_A   24.138             232        156        8
    1206 Query_2244025     2VN9_A   24.138             232        156        8
    1207 Query_2244025     8USO_A   24.138             232        156        8
    1208 Query_2244025     7S47_A   29.032             186        113        7
    1209 Query_2244025     9P6A_A   28.000             225        124        8
    1210 Query_2244025     3FHR_A   27.397             146         96        5
    1211 Query_2244025     3R1N_A   27.397             146         96        5
    1212 Query_2244025     2JC6_A   22.358             246        161        6
    1213 Query_2244025     3BHH_A   22.944             231        160        7
    1214 Query_2244025   6T28_AAA   22.764             246        160        6
    1215 Query_2244025     8E05_A   26.484             219        144        8
    1216 Query_2244025     3MDY_A   23.779             307        160       14
    1217 Query_2244025     8E04_A   26.484             219        144        8
    1218 Query_2244025     6QP5_A   22.269             238        155        6
    1219 Query_2244025     8FAC_A   26.484             219        144        8
    1220 Query_2244025     7MX3_A   23.345             287        175       10
    1221 Query_2244025     8T6K_A   22.944             231        160        7
    1222 Query_2244025     4YSJ_A   26.840             231        144        9
    1223 Query_2244025     2KUP_B  100.000              19          0        0
    1224 Query_2244025     6BWK_A   23.276             232        154       10
    1225 Query_2244025     9LFU_A   23.693             287        174       11
    1226 Query_2244025     1A06_A   21.862             247        167        6
    1227 Query_2244025     6LBA_A   27.230             213        132       10
    1228 Query_2244025     6W4O_A   23.377             231        159        7
    1229 Query_2244025     7UJR_A   23.377             231        159        7
    1230 Query_2244025     6O5Z_A   23.276             232        154       10
    1231 Query_2244025     8SLZ_A   23.276             232        154       10
    1232 Query_2244025     5KNJ_A   24.895             237        144       11
    1233 Query_2244025     2VZ6_A   23.377             231        159        7
    1234 Query_2244025     5U6Y_A   23.377             231        159        7
    1235 Query_2244025     4MWI_A   21.595             301        192       13
    1236 Query_2244025     4M67_A   21.595             301        192       13
    1237 Query_2244025     7MON_B   23.345             287        175       11
    1238 Query_2244025     7B55_B   23.377             231        159        7
    1239 Query_2244025     3MFR_A   27.513             189        129        7
    1240 Query_2244025     6LK6_A   21.595             301        192       13
    1241 Query_2244025     6BXI_A   22.264             265        147       10
    1242 Query_2244025     4TXC_A   27.027             185        119        7
    1243 Query_2244025     3MY0_A   26.840             231        125        9
    1244 Query_2244025     4FG7_A   22.374             219        154        5
    1245 Query_2244025     3RP9_A   22.131             244        126       12
    1246 Query_2244025     4FG8_A   22.374             219        154        5
    1247 Query_2244025     4FG9_A   22.374             219        154        5
    1248 Query_2244025     6LK5_A   21.595             301        192       13
    1249 Query_2244025     9D5I_A   24.823             282        176       14
    1250 Query_2244025     3MTF_A   26.180             233        124       11
    1251 Query_2244025     9D5H_A   24.823             282        176       14
    1252 Query_2244025     2W4J_A   27.027             185        119        6
    1253 Query_2244025     1WVW_A   27.027             185        119        6
    1254 Query_2244025     4PF4_A   27.027             185        119        6
    1255 Query_2244025     9RDA_A   25.287             261        146       12
    1256 Query_2244025     3H9R_A   25.287             261        146       12
    1257 Query_2244025     2Y4P_A   27.027             185        119        6
    1258 Query_2244025     4TL0_A   27.027             185        119        7
    1259 Query_2244025     6FHB_A   27.027             185        119        7
    1260 Query_2244025     4UV0_A   27.027             185        119        7
    1261 Query_2244025     5AUT_A   27.027             185        119        6
    1262 Query_2244025     1P4F_A   27.027             185        119        6
    1263 Query_2244025     1IG1_A   27.027             185        119        6
    1264 Query_2244025     3F5U_A   27.027             185        119        6
    1265 Query_2244025     3DFC_B   27.027             185        119        6
    1266 Query_2244025     3GU4_A   27.027             185        119        6
    1267 Query_2244025     6FHA_A   27.027             185        119        7
    1268 Query_2244025     8UWR_A   25.523             239        130       11
    1269 Query_2244025     3KMW_A   24.823             282        176       14
    1270 Query_2244025     2W4K_A   27.027             185        119        6
    1271 Query_2244025     9MIU_A   27.027             185        119        6
    1272 Query_2244025     6EIX_A   25.287             261        146       12
    1273 Query_2244025     2XZS_A   27.027             185        119        6
    1274 Query_2244025     6QMO_A   27.027             185        119        6
    1275 Query_2244025     6QN4_A   27.027             185        119        6
    1276 Query_2244025     8FX4_D   23.111             225        134        8
    1277 Query_2244025     2X0G_A   27.027             185        119        7
    1278 Query_2244025     4B4L_A   27.568             185        118        7
    1279 Query_2244025     2Y0A_A   27.027             185        119        6
    1280 Query_2244025     9D8Z_A   25.287             261        146       12
    1281 Query_2244025     2XUU_A   27.807             187        115        7
    1282 Query_2244025     9IWX_A   22.222             288        179       12
    1283 Query_2244025     9D8F_A   26.180             233        124       11
    1284 Query_2244025     6UNR_A   26.180             233        124       11
    1285 Query_2244025     6UNQ_A   26.180             233        124       11
    1286 Query_2244025     2JBO_A   27.143             140         93        5
    1287 Query_2244025     3GOK_A   27.143             140         93        5
    1288 Query_2244025     3R2B_A   27.143             140         93        5
    1289 Query_2244025     6TCA_A   27.143             140         93        5
    1290 Query_2244025     2PZY_A   27.143             140         93        5
    1291 Query_2244025     2OZA_A   27.143             140         93        5
    1292 Query_2244025     6JUX_A   26.407             231        122       11
    1293 Query_2244025     4TYH_A   27.143             140         93        5
    1294 Query_2244025     2ONL_C   27.143             140         93        5
    1295 Query_2244025     4M66_A   22.222             288        179       12
    1296 Query_2244025     3FPM_A   27.143             140         93        5
    1297 Query_2244025     1KWP_A   27.143             140         93        5
    1298 Query_2244025     2P3G_X   27.143             140         93        5
    1299 Query_2244025     4DYM_A   26.407             231        122       11
    1300 Query_2244025     3R2Y_A   27.143             140         93        5
    1301 Query_2244025     3KA0_A   27.143             140         93        5
    1302 Query_2244025     6T8X_A   27.143             140         93        5
    1303 Query_2244025     6MIB_A   24.823             282        176       14
    1304 Query_2244025     6KA4_A   23.707             232        154        9
    1305 Query_2244025     8XU4_A   25.714             140         95        4
    1306 Query_2244025     9R59_A   25.714             140         95        4
    1307 Query_2244025     4M69_A   23.024             291        173       13
    1308 Query_2244025     1NXK_A   27.143             140         93        5
    1309 Query_2244025     7UP4_A   24.841             157         88        4
    1310 Query_2244025     2KUQ_A  100.000              19          0        0
    1311 Query_2244025     3GU8_A   26.486             185        120        6
    1312 Query_2244025     3D5V_A   24.473             237        157        9
    1313 Query_2244025     5YV8_A   27.461             193        103       10
    1314 Query_2244025     2ZV2_A   27.461             193        103       10
    1315 Query_2244025     3D5W_A   24.473             237        157        9
    1316 Query_2244025     3D5X_A   24.268             239        159        9
    1317 Query_2244025     3D5U_A   24.473             237        157        9
    1318 Query_2244025     6CMJ_A   24.706             255        151       12
    1319 Query_2244025     5UY6_A   27.461             193        103       10
    1320 Query_2244025     5YKS_A   22.789             294        178       14
    1321 Query_2244025     3KGA_A   25.000             140         75        4
    1322 Query_2244025     8H59_A   25.225             222        141        9
    1323 Query_2244025     8ZTC_A   25.225             222        141        9
    1324 Query_2244025     5Z33_A   25.225             222        141        9
    1325 Query_2244025     7KPV_A   29.348              92         60        2
    1326 Query_2244025     6FYP_A   22.041             245        149       11
    1327 Query_2244025     2EU9_A   22.041             245        149       11
    1328 Query_2244025     6FT7_A   22.041             245        149       11
    1329 Query_2244025     2WU6_A   22.041             245        149       11
    1330 Query_2244025     2EXE_A   22.041             245        149       11
    1331 Query_2244025     3KMU_A   24.113             282        178       14
    1332 Query_2244025     6YTY_A   22.041             245        149       11
    1333 Query_2244025     3N9X_A   22.121             330        193       14
    1334 Query_2244025     4HNI_A   24.028             283        166       16
    1335 Query_2244025     9B3S_A   22.989             174        115        8
    1336 Query_2244025     7LIR_A   33.000             100         60        2
    1337 Query_2244025     8VXF_A   22.857             175        116        8
    1338 Query_2244025     6KHF_A   21.600             250        154       11
    1339 Query_2244025     3NIE_A   23.109             238        129       12
    1340 Query_2244025     5X17_A   21.264             174        120        6
    1341 Query_2244025     5MQV_A   21.264             174        120        6
    1342 Query_2244025     3UYS_A   22.857             175        116        8
    1343 Query_2244025     4KB8_A   21.387             173        119        6
    1344 Query_2244025     6RCG_A   22.857             175        116        8
    1345 Query_2244025     4TN6_A   22.857             175        116        8
    1346 Query_2244025     5IH4_A   22.857             175        116        8
    1347 Query_2244025     8VXD_A   22.857             175        116        8
    1348 Query_2244025     8D7M_A   22.857             175        116        8
    1349 Query_2244025     4JJR_A   22.857             175        116        8
    1350 Query_2244025     4TW9_A   22.857             175        116        8
    1351 Query_2244025     8IZC_A   22.857             175        116        8
    1352 Query_2244025     1CKI_A   22.857             175        116        8
    1353 Query_2244025     6PXN_A   21.387             173        119        6
    1354 Query_2244025     6PXP_A   22.857             175        116        8
    1355 Query_2244025     9BCV_A   23.176             233        145       10
    1356 Query_2244025     9BCL_A   23.176             233        145       10
    1357 Query_2244025     9DZH_A   23.176             233        145       10
    1358 Query_2244025     5OKT_A   21.264             174        120        6
    1359 Query_2244025     7P7F_A   22.857             175        116        8
    1360 Query_2244025     5CZO_A   24.242             165         91        7
    1361 Query_2244025     5CYZ_A   24.242             165         91        7
    1362 Query_2244025     4XH0_A   22.973             222        126       10
    1363 Query_2244025     4XHL_A   24.118             170         94        8
    1364 Query_2244025     9CWM_A   34.483              58         23        2
    1365 Query_2244025     4LQS_A   21.637             171        116        5
    1366 Query_2244025     4LQP_A   21.637             171        116        5
    1367 Query_2244025     7T4S_F   23.958             192        122       11
    1368 Query_2244025     9I3V_A   34.483              58         23        2
    1369 Query_2244025     3SV0_A   27.711             166         90        9
    1370 Query_2244025    9Y9Z_20   25.166             151         79        5
         q.start q.end s.start s.end   evalue bitscore positives
    1        648  1030       1   383 0.00e+00    793.0    100.00
    2        648  1025       2   379 0.00e+00    782.0    100.00
    3       1058  1410       1   353 0.00e+00    739.0     99.72
    4        677  1030      15   368 0.00e+00    731.0     99.72
    5        673  1025       1   353 0.00e+00    730.0    100.00
    6       1069  1411       2   344 0.00e+00    719.0    100.00
    7       1069  1411       2   344 0.00e+00    716.0     99.71
    8       1068  1410      25   367 0.00e+00    712.0     99.13
    9       1068  1410       2   344 0.00e+00    711.0     99.13
    10      1072  1410       1   339 0.00e+00    709.0     99.71
    11      1078  1410       1   333 0.00e+00    697.0     99.70
    12       648   993       1   344 0.00e+00    694.0     98.55
    13      1084  1410       1   327 0.00e+00    685.0     99.69
    14      1084  1410       1   327 0.00e+00    683.0     99.69
    15      1084  1410       1   327 0.00e+00    682.0     99.39
    16      1092  1411       8   327 0.00e+00    671.0    100.00
    17      1092  1411       8   327 0.00e+00    671.0    100.00
    18      1093  1411       3   321 0.00e+00    671.0    100.00
    19      1092  1411       8   327 0.00e+00    670.0     99.69
    20      1093  1411      24   342 0.00e+00    670.0    100.00
    21      1093  1411      24   342 0.00e+00    669.0     99.69
    22      1093  1411      24   342 0.00e+00    668.0     99.69
    23      1090  1406       6   322 0.00e+00    668.0    100.00
    24      1093  1411      24   342 0.00e+00    668.0     99.69
    25      1092  1411       8   327 0.00e+00    667.0     99.69
    26      1093  1411      24   342 0.00e+00    667.0     99.69
    27      1093  1410       3   320 0.00e+00    666.0     99.69
    28      1092  1411       8   327 0.00e+00    666.0     99.38
    29      1095  1411       2   318 0.00e+00    664.0    100.00
    30      1094  1407       2   315 0.00e+00    660.0    100.00
    31      1094  1400       1   307 0.00e+00    646.0    100.00
    32       673   986       2   315 0.00e+00    642.0    100.00
    33       677   986       2   311 0.00e+00    633.0     99.68
    34      1095  1384      17   306 5.49e-88    291.0     70.65
    35      1105  1384       7   289 1.74e-87    290.0     71.73
    36      1104  1384       2   285 4.13e-87    288.0     71.48
    37      1089  1384       1   295 6.31e-83    277.0     62.21
    38      1081  1384      15   317 8.48e-83    277.0     61.56
    39      1089  1384       1   295 9.68e-83    276.0     62.54
    40      1089  1384       1   295 1.10e-82    276.0     62.21
    41      1098  1384       3   289 1.45e-81    272.0     62.76
    42      1098  1384       3   289 1.48e-81    272.0     62.76
    43      1098  1384       3   289 1.50e-81    272.0     62.76
    44      1104  1384       2   282 1.55e-81    272.0     63.73
    45      1105  1384       9   288 4.53e-81    271.0     63.60
    46      1105  1384       6   285 5.49e-81    270.0     63.96
    47      1105  1384       7   286 6.07e-81    270.0     63.60
    48      1105  1384       4   283 7.65e-81    270.0     63.60
    49      1105  1384       9   288 7.68e-81    270.0     63.60
    50      1098  1384       3   289 2.56e-80    269.0     62.41
    51      1105  1384       3   282 7.82e-80    267.0     62.90
    52      1098  1384       3   289 4.79e-78    262.0     61.72
    53      1105  1384       1   280 5.15e-77    259.0     62.19
    54      1110  1412      12   307 5.70e-77    259.0     60.59
    55      1105  1380       8   283 5.74e-77    259.0     63.21
    56      1105  1380       8   283 7.45e-77    259.0     62.86
    57      1105  1380       8   283 1.81e-76    258.0     62.50
    58      1105  1380      10   285 3.24e-76    257.0     62.86
    59      1105  1380       9   284 3.70e-76    257.0     62.86
    60      1105  1380       9   284 5.19e-76    256.0     62.50
    61      1105  1380       8   283 5.87e-76    256.0     62.50
    62      1043  1435    1879  2285 6.00e-76    282.0     58.78
    63      1026  1384     904  1243 5.40e-75    276.0     57.26
    64      1028  1384     931  1267 8.99e-75    276.0     57.22
    65      1105  1380       8   283 1.62e-74    252.0     62.14
    66      1105  1380       5   280 1.36e-73    249.0     61.79
    67      1105  1380       8   283 2.23e-73    249.0     61.79
    68      1105  1380       8   283 2.73e-73    248.0     61.43
    69      1026  1384     900  1239 3.28e-73    271.0     56.99
    70      1105  1380      30   305 6.51e-73    248.0     61.43
    71      1082  1384     946  1247 2.08e-71    265.0     61.76
    72      1093  1434     986  1329 2.27e-70    262.0     57.58
    73      1093  1434     959  1302 2.43e-70    262.0     57.58
    74      1093  1434     959  1302 2.63e-70    262.0     57.58
    75      1093  1434     996  1339 9.87e-70    260.0     57.58
    76      1093  1434     969  1312 1.13e-69    260.0     57.58
    77      1093  1434     984  1327 1.18e-69    260.0     57.58
    78      1095  1397      19   325 1.29e-69    239.0     55.31
    79      1093  1434     984  1327 1.45e-69    260.0     57.58
    80      1108  1376       7   277 1.63e-69    237.0     59.27
    81      1093  1397      10   312 6.59e-69    236.0     55.59
    82      1105  1434     973  1300 6.83e-69    258.0     58.82
    83      1100  1397       1   302 1.13e-68    235.0     55.56
    84      1108  1397       2   295 1.28e-68    234.0     56.38
    85      1093  1397      26   328 1.33e-68    236.0     55.27
    86      1095  1397      19   325 1.35e-68    236.0     54.98
    87      1108  1397       3   296 1.56e-68    234.0     56.38
    88      1093  1397      17   319 1.57e-68    235.0     55.27
    89      1093  1397      21   323 1.60e-68    235.0     55.27
    90      1108  1397       6   299 1.65e-68    234.0     56.38
    91      1108  1397       5   298 1.85e-68    234.0     56.38
    92      1093  1397      20   322 2.01e-68    235.0     55.27
    93      1093  1397      21   323 2.07e-68    235.0     55.27
    94      1093  1397       9   311 2.15e-68    234.0     55.27
    95      1108  1397      14   307 2.18e-68    234.0     56.38
    96      1093  1392       5   302 2.18e-68    234.0     55.84
    97      1108  1397      13   306 2.26e-68    234.0     56.38
    98      1093  1397       3   305 2.27e-68    234.0     55.27
    99      1108  1397      12   305 2.34e-68    234.0     56.38
    100     1093  1397       9   311 2.53e-68    234.0     55.27
    101     1108  1388       2   286 7.62e-68    232.0     57.09
    102     1108  1397       5   298 1.88e-67    231.0     56.04
    103     1100  1381       1   287 6.31e-67    230.0     57.34
    104     1108  1382       5   283 6.42e-67    230.0     57.24
    105     1108  1382       2   280 9.19e-67    229.0     57.24
    106     1100  1381       1   287 9.23e-67    229.0     57.34
    107     1110  1379      43   326 1.03e-65    228.0     58.33
    108     1107  1384       4   265 1.44e-64    222.0     56.83
    109     1090  1384    1348  1651 1.96e-64    244.0     59.03
    110     1111  1384      20   293 2.64e-63    220.0     58.36
    111     1110  1384      31   314 4.11e-63    220.0     56.79
    112     1114  1384     112   368 4.66e-63    221.0     60.15
    113     1114  1384     112   368 5.28e-63    221.0     60.15
    114     1110  1384      13   284 5.29e-63    218.0     57.19
    115     1114  1384     114   370 5.98e-63    221.0     60.15
    116     1110  1384      13   284 6.60e-63    218.0     57.19
    117     1108  1381       3   295 7.36e-63    219.0     55.52
    118     1110  1384      19   302 1.19e-62    218.0     56.79
    119     1029  1383     490   859 1.94e-62    233.0     54.09
    120     1110  1384      32   315 1.95e-62    218.0     56.79
    121     1114  1384     114   370 7.07e-62    218.0     59.78
    122     1110  1400      15   317 8.19e-62    216.0     56.54
    123     1108  1384      11   287 1.07e-61    215.0     57.80
    124     1110  1384      17   300 1.07e-61    215.0     57.14
    125     1110  1384      19   302 1.29e-61    215.0     55.90
    126     1110  1400      24   326 1.60e-61    215.0     56.54
    127     1108  1384      15   300 2.70e-61    214.0     57.04
    128     1105  1384      14   302 3.58e-61    214.0     56.80
    129     1105  1384       3   291 4.41e-61    213.0     56.80
    130     1108  1384      29   314 4.87e-61    214.0     57.04
    131     1100  1379       7   284 5.37e-61    213.0     60.07
    132     1108  1384      15   300 5.67e-61    213.0     57.04
    133     1108  1384      15   300 5.84e-61    213.0     57.04
    134     1106  1383      11   294 5.87e-61    213.0     56.25
    135     1105  1384      14   302 6.19e-61    213.0     56.80
    136     1108  1384      15   300 6.49e-61    213.0     57.04
    137     1108  1384      17   302 7.30e-61    213.0     57.04
    138     1108  1384      17   302 8.27e-61    213.0     57.04
    139     1110  1384      18   301 8.43e-61    213.0     56.79
    140     1110  1384      14   297 8.64e-61    213.0     56.79
    141     1110  1384      17   300 8.92e-61    213.0     56.79
    142     1110  1384      24   307 9.06e-61    213.0     56.79
    143     1110  1384      15   298 1.03e-60    212.0     56.79
    144     1110  1384      16   299 1.10e-60    212.0     56.79
    145     1110  1384      13   296 1.15e-60    212.0     56.79
    146     1108  1384      29   314 1.18e-60    213.0     57.04
    147     1110  1384      17   300 1.20e-60    212.0     56.79
    148     1110  1384      24   307 1.26e-60    213.0     56.79
    149     1110  1384       9   292 1.31e-60    212.0     56.79
    150     1110  1384      20   303 1.35e-60    212.0     55.56
    151     1110  1384      13   296 1.42e-60    212.0     56.79
    152     1110  1384      16   299 1.43e-60    212.0     56.79
    153     1110  1403      36   342 1.98e-60    214.0     56.13
    154     1108  1384      17   302 2.55e-60    211.0     56.70
    155     1108  1384      29   314 2.62e-60    212.0     56.70
    156     1108  1384       7   292 3.39e-60    211.0     56.70
    157     1108  1384      13   298 3.42e-60    211.0     56.70
    158     1095  1384      43   348 3.74e-60    213.0     55.34
    159     1108  1384      13   298 3.76e-60    211.0     56.70
    160     1108  1384       7   292 3.88e-60    210.0     56.70
    161     1108  1384      17   302 4.20e-60    211.0     56.70
    162     1110  1384      15   298 5.53e-60    210.0     56.45
    163     1110  1384      16   299 5.65e-60    210.0     56.45
    164     1108  1384      28   313 5.65e-60    211.0     56.70
    165     1108  1384      29   314 5.76e-60    211.0     56.70
    166     1110  1384      17   300 6.47e-60    210.0     56.45
    167     1110  1384      18   301 6.54e-60    210.0     56.45
    168     1111  1392      16   294 6.60e-60    209.0     58.95
    169     1110  1384      24   307 7.66e-60    210.0     56.45
    170     1110  1384      31   314 8.07e-60    210.0     55.05
    171     1110  1384      31   314 9.14e-60    210.0     55.05
    172     1110  1384      31   314 1.22e-59    210.0     55.05
    173     1110  1384      19   292 1.77e-59    208.0     56.83
    174     1110  1400      24   326 1.90e-59    209.0     55.88
    175     1107  1392       5   274 1.94e-59    208.0     56.29
    176     1110  1384      31   314 2.15e-59    209.0     55.05
    177     1110  1384      20   303 2.85e-59    208.0     54.70
    178     1110  1384      31   314 2.90e-59    209.0     55.05
    179     1110  1384      37   320 3.22e-59    209.0     54.70
    180     1110  1384      31   314 3.25e-59    209.0     55.05
    181     1110  1384      20   303 3.36e-59    208.0     54.70
    182     1110  1384      15   298 3.37e-59    208.0     54.36
    183     1110  1384      11   294 3.49e-59    208.0     54.70
    184     1110  1384      23   306 3.50e-59    208.0     54.70
    185     1110  1384      23   306 3.56e-59    208.0     54.70
    186     1110  1384      23   306 3.88e-59    208.0     54.70
    187     1110  1384      15   298 4.07e-59    207.0     54.70
    188     1110  1384      31   314 4.09e-59    208.0     54.70
    189     1110  1384      18   301 4.43e-59    207.0     54.36
    190     1111  1396      33   319 5.10e-59    208.0     58.02
    191     1110  1384      31   314 5.46e-59    208.0     54.70
    192     1110  1384      31   314 6.18e-59    208.0     54.70
    193     1110  1384      31   314 6.43e-59    207.0     54.70
    194     1110  1384      31   314 8.66e-59    207.0     54.70
    195     1074  1389       6   327 9.10e-59    207.0     52.13
    196     1095  1392      15   315 1.01e-58    207.0     56.68
    197     1074  1389       8   329 1.06e-58    207.0     52.13
    198     1110  1384      31   314 1.09e-58    207.0     54.70
    199     1111  1392      14   296 1.10e-58    206.0     58.13
    200     1107  1392       6   275 1.27e-58    206.0     56.64
    201     1107  1392       6   275 1.29e-58    205.0     56.64
    202     1111  1392      12   294 1.29e-58    206.0     58.13
    203     1074  1389       8   327 1.30e-58    207.0     53.37
    204     1110  1384      18   301 1.32e-58    206.0     54.36
    205     1110  1384      77   360 1.36e-58    208.0     54.70
    206     1110  1384      20   303 1.37e-58    206.0     54.36
    207     1110  1400      31   333 1.46e-58    207.0     53.92
    208     1111  1392      14   296 1.57e-58    206.0     58.13
    209     1111  1392      31   313 1.65e-58    206.0     58.13
    210     1110  1384      31   314 1.88e-58    206.0     54.70
    211     1111  1392      14   296 2.18e-58    205.0     58.13
    212     1110  1384      19   293 2.25e-58    205.0     55.76
    213     1110  1400      31   333 2.33e-58    206.0     53.92
    214     1107  1392       6   275 2.51e-58    205.0     56.29
    215     1111  1392      32   314 3.00e-58    206.0     58.13
    216     1107  1392      11   280 3.13e-58    204.0     56.29
    217     1107  1392       1   270 3.18e-58    204.0     56.29
    218     1107  1392       6   275 3.34e-58    204.0     56.29
    219     1110  1384      19   307 3.71e-58    205.0     53.92
    220     1110  1400      31   333 3.77e-58    206.0     54.25
    221     1088  1389      21   332 3.99e-58    206.0     52.38
    222     1110  1384      31   314 4.02e-58    206.0     54.70
    223     1111  1378      16   283 4.16e-58    204.0     58.39
    224     1100  1392       1   277 4.26e-58    204.0     55.29
    225     1111  1384       6   279 4.29e-58    204.0     58.57
    226     1110  1384      19   302 4.63e-58    205.0     54.36
    227     1107  1392       7   276 4.69e-58    204.0     55.94
    228     1107  1389      11   277 4.95e-58    203.0     56.54
    229     1110  1384      31   314 5.07e-58    205.0     54.36
    230     1074  1389       8   327 5.91e-58    205.0     52.76
    231     1107  1392       5   274 5.92e-58    204.0     55.94
    232     1093  1392       4   277 6.03e-58    204.0     54.67
    233     1111  1378      31   298 6.60e-58    204.0     58.39
    234     1111  1395      20   314 7.23e-58    205.0     54.15
    235     1107  1392       5   274 7.56e-58    203.0     55.94
    236     1107  1392      11   280 7.65e-58    203.0     55.94
    237     1074  1389       5   326 7.74e-58    205.0     51.83
    238     1110  1384      31   314 8.51e-58    204.0     54.36
    239     1100  1392       1   277 9.48e-58    203.0     55.29
    240     1107  1389      10   276 9.71e-58    202.0     56.18
    241     1107  1389      11   277 1.00e-57    202.0     56.18
    242     1110  1384      31   314 1.03e-57    204.0     54.36
    243     1074  1389       8   323 1.04e-57    204.0     52.17
    244     1107  1392       1   270 1.11e-57    202.0     56.29
    245     1110  1384      19   307 1.12e-57    204.0     53.58
    246     1110  1384      31   314 1.21e-57    204.0     54.36
    247     1107  1392      19   288 1.22e-57    203.0     55.94
    248     1091  1389       4   276 1.31e-57    202.0     54.85
    249     1110  1384      31   314 1.39e-57    204.0     54.36
    250     1107  1389       6   272 1.39e-57    202.0     56.18
    251     1107  1392       4   273 1.42e-57    202.0     56.29
    252     1107  1389       5   271 1.44e-57    202.0     56.18
    253     1107  1392       7   276 1.58e-57    202.0     55.94
    254     1107  1392       4   273 1.63e-57    202.0     56.29
    255     1107  1392      33   302 1.69e-57    203.0     55.94
    256     1107  1392       4   273 2.27e-57    202.0     55.94
    257     1074  1389      12   340 2.63e-57    204.0     50.45
    258     1110  1403      65   371 2.81e-57    206.0     53.87
    259     1088  1389      10   315 3.08e-57    202.0     52.43
    260     1107  1384       6   267 3.17e-57    201.0     56.47
    261     1110  1384      19   307 3.38e-57    202.0     53.58
    262     1107  1392       7   276 4.21e-57    201.0     55.94
    263     1110  1403     472   778 4.26e-57    216.0     56.13
    264     1110  1384      19   307 5.07e-57    202.0     53.58
    265     1107  1392     118   387 5.37e-57    205.0     55.94
    266     1110  1384      19   307 5.47e-57    202.0     53.58
    267     1100  1390       1   282 8.24e-57    202.0     57.97
    268     1109  1390       3   274 9.96e-57    201.0     58.25
    269     1107  1392       5   274 9.98e-57    199.0     55.59
    270     1100  1390       1   282 1.01e-56    202.0     57.97
    271     1110  1384       9   292 1.02e-56    201.0     53.66
    272     1095  1384      26   326 1.12e-56    202.0     52.30
    273     1096  1390      26   311 1.16e-56    203.0     57.53
    274     1096  1390      26   311 1.25e-56    203.0     57.53
    275     1107  1389      10   276 1.33e-56    199.0     55.83
    276     1074  1389       1   329 1.38e-56    201.0     50.45
    277     1079  1390      15   311 1.39e-56    202.0     56.33
    278     1107  1389      11   277 1.43e-56    199.0     55.83
    279     1107  1392     171   440 1.43e-56    205.0     55.94
    280     1100  1390      18   299 1.46e-56    202.0     57.97
    281     1107  1389       5   271 1.49e-56    199.0     55.83
    282     1110  1384      16   304 1.68e-56    200.0     53.24
    283     1074  1389      12   340 1.77e-56    201.0     50.45
    284     1116  1395      19   289 2.64e-56    199.0     56.64
    285     1116  1395      18   288 2.82e-56    199.0     56.64
    286     1096  1390      26   311 3.29e-56    202.0     57.53
    287     1107  1392     213   482 3.77e-56    205.0     56.29
    288     1079  1390      15   311 3.80e-56    201.0     56.33
    289     1088  1389       3   321 3.85e-56    200.0     50.62
    290     1079  1390      13   309 4.07e-56    201.0     56.33
    291     1079  1390      15   311 4.30e-56    201.0     56.33
    292     1107  1392     213   482 4.47e-56    205.0     56.29
    293     1110  1384      39   327 4.52e-56    200.0     53.24
    294     1096  1390      26   311 5.21e-56    201.0     57.19
    295     1116  1395      46   316 5.69e-56    199.0     56.64
    296     1110  1383      10   265 6.08e-56    197.0     55.11
    297     1110  1384      60   348 6.53e-56    200.0     53.24
    298     1109  1390      40   311 6.74e-56    201.0     58.25
    299     1110  1384      19   307 7.25e-56    199.0     53.24
    300     1110  1383       5   260 7.56e-56    197.0     55.11
    301     1116  1428      27   325 8.35e-56    201.0     54.66
    302     1116  1428      27   325 8.68e-56    201.0     54.66
    303     1110  1383       2   257 8.79e-56    196.0     55.11
    304     1116  1428      27   325 9.73e-56    201.0     54.97
    305     1074  1389      12   351 1.18e-55    199.0     48.84
    306     1107  1392     210   479 1.24e-55    204.0     55.94
    307     1110  1383      17   272 1.31e-55    196.0     55.11
    308     1107  1389       1   267 1.38e-55    196.0     55.83
    309     1110  1383      15   270 1.43e-55    196.0     55.11
    310     1110  1383      14   269 1.48e-55    196.0     55.11
    311     1110  1383      16   271 1.51e-55    196.0     55.11
    312     1096  1390      26   311 1.56e-55    200.0     57.19
    313     1110  1383      20   275 1.60e-55    196.0     55.11
    314     1110  1383      20   275 1.71e-55    196.0     55.11
    315     1110  1383       5   260 1.73e-55    196.0     55.11
    316     1110  1383       8   263 1.76e-55    196.0     55.11
    317     1110  1383      13   268 1.76e-55    196.0     55.11
    318     1110  1383       6   261 1.79e-55    196.0     55.11
    319     1110  1383       8   263 1.82e-55    196.0     55.11
    320     1110  1383      12   267 1.82e-55    196.0     55.11
    321     1110  1383       5   260 1.84e-55    196.0     55.11
    322     1110  1383       7   262 1.85e-55    196.0     55.11
    323     1110  1383       5   260 1.91e-55    196.0     55.11
    324     1110  1383       4   259 1.91e-55    196.0     55.11
    325     1110  1383       4   259 1.95e-55    196.0     55.11
    326     1110  1383       3   258 1.99e-55    196.0     55.11
    327     1110  1383      20   275 1.99e-55    196.0     55.11
    328     1110  1383       8   263 2.00e-55    196.0     55.11
    329     1110  1383      11   266 2.01e-55    196.0     55.11
    330     1110  1383      10   265 2.12e-55    196.0     55.11
    331     1110  1383       5   260 2.18e-55    196.0     55.11
    332     1095  1384      26   326 2.20e-55    198.0     51.97
    333     1110  1383       6   261 2.22e-55    196.0     55.11
    334     1095  1384      26   326 2.29e-55    198.0     51.97
    335     1110  1383       4   259 2.32e-55    195.0     55.11
    336     1110  1383       5   260 2.32e-55    195.0     55.11
    337     1110  1383      30   285 2.34e-55    196.0     55.11
    338     1110  1383       2   257 2.35e-55    195.0     55.11
    339     1110  1383       5   260 2.54e-55    195.0     55.11
    340     1107  1389      25   291 2.84e-55    196.0     54.77
    341     1109  1399      14   296 3.20e-55    196.0     54.42
    342     1110  1383      27   282 3.31e-55    196.0     55.11
    343     1107  1392     252   521 3.44e-55    204.0     55.94
    344     1095  1384      20   318 3.67e-55    197.0     50.99
    345     1110  1384      19   307 3.75e-55    196.0     52.90
    346     1110  1383       5   260 4.07e-55    195.0     55.11
    347     1110  1384      19   307 4.17e-55    196.0     52.90
    348     1110  1383      15   270 4.28e-55    195.0     55.47
    349     1109  1399      21   303 4.28e-55    196.0     55.44
    350     1110  1383      13   268 4.52e-55    195.0     55.47
    351     1110  1383       3   258 4.64e-55    194.0     54.01
    352     1109  1399      17   299 4.70e-55    196.0     54.42
    353     1114  1383       4   255 5.38e-55    194.0     55.19
    354     1107  1389       5   271 6.68e-55    194.0     55.12
    355     1095  1384      21   319 8.06e-55    196.0     50.66
    356     1095  1384      21   319 8.06e-55    196.0     50.66
    357     1095  1384      20   318 8.06e-55    196.0     50.66
    358     1081  1376       4   315 9.12e-55    196.0     51.75
    359     1071  1384       3   334 9.79e-55    197.0     50.60
    360     1107  1376       1   286 9.94e-55    195.0     53.63
    361     1110  1383       2   257 1.05e-54    194.0     54.74
    362     1081  1376      11   322 1.24e-54    196.0     51.75
    363     1081  1376      13   324 1.28e-54    196.0     51.75
    364     1109  1390       2   275 1.31e-54    194.0     55.09
    365     1081  1376      14   325 1.48e-54    196.0     51.75
    366     1110  1383       3   258 1.48e-54    193.0     54.74
    367     1110  1383       8   263 1.60e-54    193.0     54.74
    368     1071  1384       3   334 1.71e-54    196.0     50.30
    369     1110  1384      38   330 1.72e-54    196.0     52.70
    370     1110  1384      41   333 1.79e-54    196.0     52.70
    371     1071  1384      22   353 2.64e-54    196.0     50.60
    372     1071  1384       3   334 2.73e-54    196.0     50.30
    373     1116  1380      36   291 2.84e-54    193.0     57.20
    374     1110  1383      20   275 3.28e-54    192.0     54.74
    375     1081  1376      37   348 3.42e-54    196.0     51.75
    376     1116  1384      45   304 3.51e-54    193.0     57.09
    377     1110  1384      38   330 4.38e-54    195.0     52.36
    378     1110  1383      16   271 7.33e-54    191.0     55.11
    379     1110  1383     183   438 8.53e-54    197.0     55.47
    380     1109  1399      21   303 9.35e-54    192.0     55.10
    381     1095  1377      19   288 3.02e-53    191.0     56.54
    382      683   984       6   316 3.04e-53    191.0     65.92
    383     1116  1380      36   291 3.80e-53    190.0     56.83
    384     1115  1383       8   258 3.97e-53    189.0     56.88
    385     1108  1379       3   293 5.12e-53    190.0     53.74
    386     1110  1383     184   439 5.97e-53    194.0     54.38
    387     1109  1392       8   277 7.54e-53    189.0     58.10
    388     1115  1383      28   278 7.63e-53    189.0     57.25
    389     1115  1383       8   258 9.00e-53    188.0     56.88
    390     1115  1383       6   256 9.61e-53    188.0     56.88
    391     1115  1383      11   261 1.16e-52    187.0     56.88
    392     1109  1391       3   275 1.18e-52    188.0     56.64
    393     1110  1377      11   265 1.54e-52    188.0     57.84
    394     1122  1383      30   283 1.64e-52    188.0     56.77
    395     1110  1377       8   262 1.64e-52    187.0     57.84
    396     1110  1377       9   263 1.67e-52    187.0     57.84
    397     1110  1377       8   262 1.71e-52    187.0     57.84
    398     1109  1391       9   281 1.73e-52    188.0     56.64
    399     1110  1377       9   263 1.74e-52    187.0     57.84
    400     1110  1377       3   257 1.77e-52    187.0     57.84
    401     1122  1383      30   283 1.78e-52    188.0     56.77
    402     1110  1377       7   261 1.82e-52    187.0     57.84
    403     1122  1383      34   287 1.87e-52    188.0     56.77
    404     1122  1383      37   290 1.87e-52    188.0     56.77
    405     1115  1383       9   259 1.91e-52    187.0     56.88
    406     1110  1377       2   256 1.92e-52    187.0     57.84
    407     1108  1383       3   284 1.92e-52    188.0     52.63
    408     1122  1383      47   300 1.93e-52    189.0     56.77
    409     1122  1383      25   278 2.02e-52    187.0     56.77
    410     1110  1377       6   260 2.10e-52    187.0     57.84
    411     1110  1383     194   449 2.25e-52    193.0     54.74
    412     1122  1383      37   290 2.47e-52    188.0     56.77
    413     1122  1383      38   291 2.50e-52    188.0     56.77
    414     1122  1383      36   289 2.57e-52    188.0     56.77
    415     1122  1383      33   286 2.60e-52    188.0     56.77
    416     1122  1383      38   291 2.85e-52    188.0     56.77
    417     1106  1383      18   301 3.33e-52    188.0     52.61
    418     1110  1377       6   260 3.47e-52    187.0     57.84
    419     1122  1383      67   320 3.49e-52    189.0     56.77
    420     1122  1383      56   309 3.65e-52    188.0     56.77
    421     1122  1383      57   310 3.72e-52    188.0     56.77
    422     1122  1383      35   288 3.74e-52    187.0     56.77
    423     1109  1390      17   288 3.74e-52    187.0     56.49
    424     1122  1383      55   308 3.87e-52    188.0     56.77
    425     1110  1377       6   260 4.08e-52    186.0     57.84
    426     1106  1384      11   271 4.41e-52    186.0     54.39
    427     1110  1376       4   252 4.58e-52    186.0     55.31
    428     1106  1384      10   270 4.81e-52    186.0     54.39
    429     1122  1383      60   313 4.92e-52    188.0     56.77
    430     1106  1384       5   265 5.02e-52    186.0     54.39
    431     1106  1384      15   275 6.40e-52    186.0     54.39
    432     1122  1383      47   300 8.70e-52    187.0     56.77
    433     1122  1383      47   300 1.03e-51    186.0     56.77
    434     1122  1383      38   291 1.04e-51    186.0     56.77
    435     1122  1383      28   281 1.07e-51    186.0     56.77
    436     1122  1383      34   287 1.37e-51    186.0     56.77
    437     1115  1383       8   258 1.62e-51    184.0     56.51
    438     1110  1384       5   261 1.95e-51    184.0     54.80
    439     1109  1391      24   296 1.99e-51    186.0     56.29
    440     1122  1383      34   287 2.01e-51    185.0     56.39
    441     1095  1384       3   299 2.19e-51    185.0     52.82
    442     1106  1384       1   261 2.55e-51    184.0     57.50
    443     1122  1383      37   290 3.27e-51    185.0     56.77
    444     1122  1383      38   291 3.44e-51    185.0     56.77
    445     1122  1383      34   287 3.51e-51    184.0     56.77
    446     1122  1383      34   287 3.54e-51    184.0     56.39
    447     1122  1383      47   300 3.74e-51    185.0     56.39
    448     1110  1383     396   651 3.93e-51    194.0     54.74
    449     1110  1384       4   260 5.15e-51    183.0     52.73
    450     1110  1384      14   270 5.44e-51    183.0     52.73
    451     1106  1384       5   265 6.44e-51    183.0     54.04
    452     1106  1384       6   266 7.03e-51    182.0     54.04
    453     1106  1384      13   273 7.14e-51    183.0     54.04
    454     1109  1399      14   296 7.21e-51    184.0     53.40
    455     1106  1384       5   265 8.39e-51    182.0     54.04
    456     1106  1384      11   271 8.82e-51    183.0     54.04
    457     1106  1384       7   267 9.03e-51    182.0     54.04
    458     1110  1376       8   257 9.32e-51    182.0     55.97
    459     1122  1383      38   291 1.01e-50    184.0     56.77
    460     1106  1384      14   274 1.04e-50    183.0     54.04
    461     1106  1376       5   258 1.05e-50    182.0     55.51
    462     1106  1384      14   274 1.08e-50    182.0     54.04
    463     1122  1383      39   292 1.19e-50    184.0     56.77
    464     1122  1383      36   289 1.23e-50    183.0     56.77
    465     1122  1383      38   291 1.30e-50    183.0     56.77
    466     1106  1384       5   265 1.32e-50    182.0     54.04
    467     1122  1383      43   296 1.55e-50    183.0     56.77
    468     1109  1391      28   300 1.71e-50    182.0     56.29
    469     1110  1376       8   257 1.76e-50    182.0     55.97
    470     1111  1377       9   262 1.99e-50    182.0     55.81
    471     1111  1377      10   263 2.05e-50    182.0     55.81
    472     1111  1377       5   258 2.11e-50    181.0     55.81
    473     1109  1399      28   310 2.43e-50    182.0     53.40
    474     1111  1377      21   274 2.61e-50    182.0     55.81
    475     1109  1391      28   300 2.84e-50    182.0     55.94
    476     1122  1383      36   289 3.27e-50    182.0     56.77
    477     1122  1397      33   310 3.47e-50    182.0     53.31
    478     1095  1384       3   303 3.63e-50    182.0     50.66
    479     1095  1384       5   305 3.80e-50    182.0     50.66
    480     1115  1397      16   300 3.86e-50    182.0     52.72
    481     1122  1383      97   350 3.97e-50    184.0     56.77
    482     1095  1384       2   302 4.07e-50    182.0     51.48
    483     1110  1377       6   260 4.47e-50    181.0     56.72
    484     1095  1384      17   317 4.59e-50    182.0     51.80
    485     1109  1391      28   300 4.86e-50    181.0     55.59
    486     1109  1391      38   310 5.30e-50    182.0     55.94
    487     1073  1384       2   321 5.85e-50    182.0     50.46
    488     1073  1384       7   326 6.33e-50    182.0     50.46
    489     1122  1383      36   289 8.94e-50    181.0     56.39
    490     1120  1384      27   283 9.10e-50    180.0     54.65
    491     1109  1399       2   284 9.39e-50    180.0     53.06
    492     1106  1383       2   262 1.23e-49    179.0     53.76
    493     1110  1379      28   325 1.25e-49    181.0     51.83
    494     1122  1397      30   307 1.31e-49    181.0     53.31
    495     1110  1384       2   258 1.37e-49    179.0     52.00
    496     1122  1383      39   292 1.45e-49    181.0     56.39
    497     1122  1397      29   306 1.75e-49    180.0     53.31
    498     1110  1383      23   301 2.34e-49    179.0     52.48
    499     1073  1384       2   321 2.41e-49    180.0     50.15
    500     1110  1384      35   319 2.85e-49    180.0     51.39
    501     1110  1383       2   258 3.13e-49    177.0     53.82
    502     1110  1383       2   258 3.29e-49    178.0     53.82
    503     1110  1383       2   258 3.42e-49    177.0     53.82
    504     1104  1390       4   282 3.47e-49    178.0     52.41
    505     1106  1379       7   262 4.48e-49    177.0     54.91
    506     1106  1379      18   273 4.58e-49    178.0     54.91
    507     1073  1384       7   326 5.45e-49    179.0     50.15
    508     1110  1383      23   301 8.79e-49    178.0     52.84
    509     1110  1383      15   297 9.05e-49    178.0     51.75
    510     1109  1390      14   287 9.85e-49    177.0     52.98
    511     1110  1377     388   642 1.02e-48    187.0     57.84
    512     1110  1377     386   640 1.13e-48    187.0     57.84
    513     1109  1390      14   287 1.25e-48    177.0     52.98
    514     1110  1377     386   640 1.34e-48    187.0     57.84
    515     1109  1390      13   286 1.41e-48    177.0     52.98
    516     1110  1383      25   307 1.45e-48    177.0     52.45
    517     1110  1377      17   306 1.56e-48    177.0     51.86
    518     1106  1384      10   270 1.57e-48    176.0     55.87
    519     1106  1383       2   262 1.59e-48    176.0     53.41
    520     1106  1384      10   270 1.65e-48    176.0     55.00
    521     1110  1377      12   301 1.66e-48    177.0     51.86
    522     1110  1383      23   305 1.79e-48    177.0     51.75
    523     1110  1383      14   296 2.01e-48    177.0     51.40
    524     1109  1390      11   284 2.12e-48    177.0     52.98
    525     1110  1383      14   296 2.32e-48    177.0     51.40
    526     1110  1383      23   305 2.37e-48    177.0     51.75
    527     1114  1385      12   261 2.66e-48    175.0     56.41
    528     1110  1377       6   301 2.89e-48    177.0     51.67
    529     1106  1384       3   263 3.69e-48    175.0     55.52
    530     1110  1383      60   342 3.95e-48    177.0     51.75
    531     1110  1377      15   310 4.04e-48    176.0     51.67
    532     1106  1384       7   267 4.18e-48    175.0     55.52
    533     1106  1384      11   271 4.22e-48    175.0     55.36
    534     1106  1384      10   270 4.30e-48    175.0     55.00
    535     1106  1384       1   261 4.43e-48    175.0     55.52
    536     1110  1377      28   323 4.73e-48    177.0     51.67
    537     1106  1384      10   270 4.73e-48    175.0     55.36
    538     1107  1384       1   260 4.83e-48    175.0     55.71
    539     1106  1384      17   277 5.00e-48    175.0     55.36
    540     1114  1385       6   255 5.95e-48    174.0     56.41
    541     1110  1377      42   337 6.90e-48    177.0     51.67
    542     1114  1385      21   270 7.31e-48    174.0     56.41
    543     1106  1384      10   270 7.44e-48    174.0     55.36
    544     1122  1383    1084  1337 7.68e-48    190.0     56.77
    545     1110  1377      41   336 9.04e-48    176.0     51.67
    546     1106  1384      10   270 9.46e-48    174.0     54.64
    547     1106  1384       1   261 9.56e-48    174.0     54.64
    548     1106  1384      10   270 1.18e-47    174.0     54.64
    549     1106  1384      10   270 1.19e-47    174.0     55.00
    550     1106  1384      10   270 1.20e-47    174.0     54.64
    551     1110  1384       3   259 1.64e-47    173.0     55.07
    552     1106  1384      10   270 1.87e-47    173.0     55.16
    553     1109  1390      14   287 2.02e-47    174.0     52.63
    554     1110  1383      23   305 2.34e-47    174.0     51.40
    555     1106  1384       7   267 2.36e-47    173.0     55.16
    556     1107  1379     181   435 2.36e-47    178.0     55.11
    557     1107  1379     181   435 2.55e-47    178.0     55.11
    558     1106  1384       2   262 2.60e-47    172.0     54.64
    559     1110  1383      25   305 2.62e-47    174.0     52.11
    560     1106  1384       1   261 2.73e-47    172.0     54.64
    561     1106  1384      10   270 2.99e-47    173.0     54.64
    562     1106  1384      10   270 3.56e-47    172.0     54.29
    563     1106  1384      10   270 4.31e-47    172.0     55.16
    564     1106  1384      10   270 4.61e-47    172.0     54.29
    565     1106  1384      10   270 5.28e-47    172.0     54.64
    566     1098  1375      13   294 6.88e-47    174.0     53.26
    567     1107  1384     202   461 9.09e-47    177.0     55.56
    568     1106  1384       7   267 9.68e-47    171.0     55.16
    569     1107  1384     176   435 9.74e-47    176.0     55.56
    570     1107  1384     177   436 9.96e-47    176.0     55.56
    571     1107  1384     177   436 1.09e-46    176.0     55.56
    572     1107  1384     261   520 1.45e-46    178.0     55.56
    573     1110  1383      14   296 1.47e-46    172.0     51.05
    574     1107  1384     260   519 1.56e-46    178.0     55.56
    575     1110  1383      24   305 1.90e-46    171.0     51.23
    576     1107  1384     175   434 2.60e-46    175.0     55.56
    577     1110  1383      23   305 2.87e-46    171.0     51.05
    578     1107  1384       1   260 2.87e-46    169.0     55.00
    579     1110  1383      14   296 3.02e-46    171.0     50.70
    580     1107  1384     177   436 3.06e-46    175.0     55.56
    581     1114  1385     193   442 5.36e-46    174.0     56.04
    582     1107  1384     176   435 5.53e-46    174.0     55.20
    583     1107  1384     180   439 6.62e-46    174.0     55.20
    584     1107  1384     178   437 2.08e-45    172.0     53.17
    585     1113  1384       1   254 3.21e-45    166.0     54.58
    586     1107  1379     175   419 7.63e-45    171.0     53.65
    587     1109  1399      44   324 9.01e-45    167.0     52.36
    588     1100  1381      28   304 2.73e-44    165.0     52.11
    589     1122  1386      18   270 4.86e-44    164.0     54.14
    590     1109  1399      44   324 1.10e-43    164.0     52.03
    591     1106  1384     182   442 1.30e-41    161.0     52.14
    592     1106  1384     182   442 1.33e-41    161.0     52.14
    593     1103  1386     317   596 3.30e-41    164.0     52.56
    594     1103  1386     317   596 5.53e-41    163.0     52.56
    595     1111  1379      17   277 1.39e-40    154.0     52.16
    596     1111  1379      17   277 1.43e-40    154.0     52.16
    597     1113  1383       5   264 1.64e-40    153.0     53.28
    598     1113  1383      15   274 1.65e-40    153.0     53.28
    599     1111  1379       9   269 1.68e-40    153.0     51.80
    600     1113  1383      15   274 1.69e-40    153.0     53.28
    601     1113  1383       5   264 1.75e-40    153.0     53.28
    602     1111  1394      21   291 1.80e-40    153.0     51.92
    603     1114  1379      18   275 1.94e-40    153.0     52.36
    604     1113  1383       5   264 2.06e-40    153.0     53.28
    605     1114  1379       8   265 2.31e-40    152.0     52.00
    606     1114  1379      18   275 2.34e-40    153.0     52.36
    607     1114  1379       8   265 2.36e-40    152.0     52.00
    608     1113  1383       3   262 2.36e-40    152.0     53.28
    609     1114  1379       8   265 2.46e-40    152.0     52.00
    610     1113  1383      12   271 2.48e-40    152.0     53.28
    611     1113  1383      15   274 2.57e-40    153.0     53.28
    612     1113  1383      15   274 2.66e-40    153.0     53.28
    613     1113  1383      15   274 2.71e-40    153.0     53.28
    614     1113  1383      12   271 3.15e-40    152.0     53.28
    615     1113  1383       9   268 3.32e-40    152.0     53.28
    616     1113  1383      15   274 4.07e-40    152.0     53.28
    617     1113  1383      13   272 4.23e-40    152.0     53.28
    618     1113  1383      25   284 5.78e-40    152.0     53.28
    619     1113  1383      25   284 6.77e-40    152.0     53.28
    620     1114  1379      12   269 7.10e-40    153.0     52.00
    621     1119  1390      25   285 8.13e-40    152.0     51.64
    622     1108  1390      11   282 8.78e-40    153.0     51.05
    623     1108  1390      10   281 8.83e-40    152.0     51.05
    624     1111  1394       7   277 1.60e-39    150.0     51.57
    625     1114  1379      18   275 2.74e-39    150.0     52.00
    626     1114  1379       8   265 2.88e-39    149.0     51.64
    627     1108  1390      14   282 3.40e-39    151.0     52.10
    628     1108  1390      12   280 3.49e-39    150.0     52.10
    629     1108  1390      14   282 3.56e-39    151.0     52.10
    630     1113  1383       8   267 3.59e-39    149.0     52.92
    631     1108  1390      15   283 3.72e-39    150.0     52.10
    632     1108  1390      16   284 4.07e-39    150.0     52.10
    633     1108  1390      14   282 4.18e-39    150.0     52.10
    634     1108  1390      15   283 4.41e-39    150.0     52.10
    635     1099  1390      23   303 4.75e-39    150.0     50.00
    636     1108  1390      16   284 5.58e-39    149.0     52.10
    637     1108  1390      16   284 1.02e-38    149.0     51.75
    638     1108  1390      16   284 1.11e-38    149.0     52.10
    639     1108  1390      13   281 1.14e-38    149.0     52.10
    640     1108  1390      14   282 1.18e-38    149.0     52.10
    641     1108  1390      15   283 1.21e-38    149.0     52.10
    642     1108  1390      16   284 1.24e-38    149.0     51.75
    643     1108  1390      12   283 1.25e-38    150.0     51.75
    644     1108  1390      11   279 1.28e-38    149.0     52.10
    645     1108  1390      14   282 1.33e-38    149.0     52.10
    646     1108  1390      16   284 1.34e-38    149.0     52.10
    647     1108  1390      18   286 1.39e-38    149.0     52.10
    648     1108  1390      34   302 1.42e-38    150.0     52.10
    649     1108  1390      14   282 1.43e-38    149.0     52.10
    650     1108  1390      13   281 1.45e-38    149.0     52.10
    651     1108  1390      13   281 1.48e-38    149.0     52.10
    652     1108  1390      12   280 1.57e-38    149.0     52.10
    653     1108  1390      15   283 1.63e-38    149.0     51.75
    654     1108  1390      12   280 1.63e-38    149.0     51.75
    655     1108  1390      16   284 1.70e-38    149.0     52.10
    656     1108  1390      18   286 1.70e-38    149.0     52.10
    657     1108  1390      12   280 1.79e-38    149.0     52.10
    658     1108  1390      11   279 1.90e-38    149.0     52.10
    659     1100  1390       1   280 2.00e-38    149.0     49.83
    660     1108  1390      13   281 2.14e-38    149.0     52.10
    661     1111  1394      12   282 2.21e-38    147.0     50.35
    662     1111  1394      11   281 2.35e-38    147.0     50.35
    663     1108  1390      12   280 2.44e-38    148.0     52.10
    664     1108  1390      16   284 2.56e-38    148.0     51.75
    665     1108  1390      17   285 2.83e-38    148.0     51.75
    666     1108  1390      14   282 3.10e-38    148.0     51.75
    667     1108  1390      19   287 3.21e-38    148.0     51.75
    668     1108  1390      31   299 3.27e-38    149.0     51.75
    669     1108  1390      16   284 3.28e-38    148.0     51.75
    670     1100  1390       1   277 3.28e-38    148.0     51.36
    671     1108  1390      15   283 3.32e-38    148.0     51.75
    672     1108  1390      18   286 3.34e-38    148.0     51.75
    673     1108  1390      15   283 3.39e-38    148.0     51.75
    674     1108  1390      13   281 3.62e-38    148.0     51.75
    675     1108  1390      14   282 3.67e-38    148.0     51.75
    676     1108  1390      15   283 3.73e-38    148.0     51.75
    677     1108  1390      12   280 3.85e-38    148.0     51.75
    678     1108  1390      14   282 3.89e-38    148.0     51.75
    679     1108  1390      14   282 3.93e-38    148.0     51.75
    680     1108  1390      16   284 4.01e-38    148.0     51.75
    681     1108  1390      15   283 4.06e-38    148.0     51.75
    682     1111  1394      23   293 4.09e-38    147.0     50.35
    683     1108  1390      12   280 4.21e-38    147.0     51.75
    684     1221  1383     196   356 4.23e-38    149.0     62.80
    685     1108  1390      13   281 4.25e-38    147.0     51.75
    686     1108  1390      14   282 4.30e-38    147.0     51.75
    687     1108  1390      11   279 4.41e-38    147.0     51.75
    688     1108  1390      13   281 4.46e-38    147.0     51.75
    689     1108  1390       6   274 4.52e-38    147.0     51.75
    690     1108  1390      12   280 4.66e-38    147.0     51.75
    691     1111  1394     366   636 4.83e-38    154.0     51.92
    692     1108  1390      15   283 5.01e-38    147.0     51.75
    693     1108  1390      12   280 5.22e-38    147.0     51.75
    694     1108  1390      13   281 5.56e-38    147.0     51.75
    695     1108  1390      23   291 5.62e-38    147.0     51.75
    696     1108  1390      11   279 5.80e-38    147.0     51.75
    697     1108  1390      13   281 5.93e-38    147.0     51.75
    698     1108  1390      30   298 5.98e-38    148.0     51.75
    699     1111  1394     365   635 5.99e-38    154.0     51.92
    700     1108  1390      31   299 6.01e-38    148.0     51.75
    701     1108  1390      16   284 6.21e-38    147.0     51.75
    702     1108  1390      17   285 6.30e-38    147.0     51.75
    703     1108  1390      14   282 6.38e-38    147.0     51.75
    704     1108  1390      37   305 6.53e-38    148.0     51.75
    705     1108  1390      15   283 6.66e-38    147.0     51.75
    706     1108  1390      19   287 8.79e-38    147.0     51.75
    707     1108  1390      11   286 8.88e-38    147.0     50.34
    708     1108  1390      16   284 9.26e-38    147.0     51.40
    709     1108  1390      33   301 9.38e-38    147.0     51.75
    710     1108  1390      16   284 9.43e-38    147.0     51.40
    711     1108  1390      22   290 9.53e-38    147.0     51.75
    712     1108  1390      16   284 1.04e-37    147.0     51.40
    713     1108  1390      19   287 1.08e-37    147.0     51.40
    714     1108  1390      12   280 1.17e-37    146.0     51.40
    715     1108  1390      12   280 1.22e-37    146.0     51.40
    716     1099  1390      12   296 1.45e-37    147.0     50.17
    717     1108  1390      16   284 1.49e-37    146.0     51.40
    718     1108  1390      14   282 1.61e-37    146.0     51.40
    719     1108  1390      19   287 1.97e-37    146.0     51.40
    720     1108  1390      11   279 1.99e-37    145.0     51.40
    721     1108  1390      12   280 2.40e-37    145.0     51.40
    722     1210  1376     226   393 3.71e-37    147.0     58.48
    723     1081  1214      31   166 1.66e-09     63.9     48.53
    724     1008  1390     664  1017 3.99e-37    155.0     48.45
    725     1008  1390     664  1017 3.99e-37    155.0     48.45
    726     1008  1403     630   996 6.23e-37    154.0     47.62
    727     1008  1403     630   996 6.50e-37    154.0     47.62
    728     1108  1390      46   314 7.03e-37    145.0     51.40
    729     1098  1390       7   291 8.21e-37    144.0     50.84
    730     1108  1390      16   284 1.49e-36    143.0     52.45
    731     1108  1390      16   288 1.67e-36    143.0     51.03
    732     1108  1390      15   286 1.69e-36    143.0     51.21
    733     1108  1390      18   286 1.70e-36    143.0     52.45
    734     1108  1390      16   287 2.09e-36    143.0     51.21
    735     1108  1390      14   285 2.30e-36    143.0     51.21
    736     1108  1390      15   286 2.59e-36    142.0     50.87
    737     1108  1390      14   285 3.17e-36    142.0     51.21
    738     1108  1390      13   284 3.82e-36    142.0     51.21
    739     1108  1390      14   285 4.67e-36    142.0     51.21
    740     1108  1390      23   288 4.70e-36    142.0     51.40
    741     1108  1390      12   280 9.89e-36    148.0     51.75
    742     1108  1390     363   631 9.89e-36    148.0     51.75
    743     1108  1390      16   284 1.50e-35    140.0     52.10
    744     1210  1383     179   350 2.50e-35    140.0     56.57
    745     1210  1383     177   348 2.60e-35    140.0     56.57
    746     1210  1383     186   357 3.01e-35    140.0     56.57
    747     1210  1383     184   355 3.26e-35    140.0     56.57
    748     1113  1385     130   410 7.28e-35    147.0     51.39
    749     1108  1390     707   975 8.68e-35    147.0     51.75
    750     1108  1390     707   975 2.35e-34    145.0     51.40
    751     1118  1386      26   284 3.31e-34    136.0     47.78
    752     1233  1384     770   919 3.23e-33    142.0     60.13
    753     1233  1384     772   921 3.66e-33    141.0     60.13
    754     1233  1384     774   923 3.90e-33    141.0     60.13
    755     1103  1384       2   290 2.35e-32    130.0     47.67
    756     1106  1384       2   287 1.56e-31    127.0     48.15
    757     1107  1384       4   288 2.40e-31    127.0     47.97
    758     1110  1384       2   283 4.40e-31    126.0     48.12
    759     1103  1384      22   310 5.20e-31    127.0     47.33
    760     1107  1384       1   285 6.50e-31    125.0     47.64
    761     1119  1390      18   278 6.82e-31    127.0     47.29
    762     1107  1384       6   290 7.04e-31    125.0     47.64
    763     1107  1384       5   289 8.00e-31    125.0     47.64
    764     1107  1384      25   309 8.98e-31    126.0     47.97
    765     1107  1384      24   308 1.01e-30    126.0     47.64
    766     1107  1384      16   300 1.11e-30    125.0     47.64
    767     1107  1384       6   290 1.27e-30    125.0     47.64
    768     1106  1384       2   287 1.43e-30    125.0     47.81
    769     1103  1384      19   307 2.26e-30    125.0     47.67
    770     1107  1384       4   288 2.72e-30    124.0     47.97
    771     1103  1384       2   290 2.93e-30    124.0     47.33
    772     1107  1384      10   294 4.15e-30    124.0     47.64
    773     1103  1384      22   310 4.18e-30    124.0     47.33
    774     1107  1384       5   289 4.23e-30    123.0     47.64
    775     1107  1384      21   305 4.32e-30    124.0     47.97
    776     1103  1384       2   290 4.33e-30    123.0     47.33
    777     1107  1384      10   294 4.52e-30    124.0     47.64
    778     1107  1384      12   296 4.83e-30    124.0     47.64
    779     1095  1384      17   308 4.84e-30    124.0     47.08
    780     1107  1384      21   305 5.09e-30    124.0     47.97
    781     1107  1384      12   296 5.56e-30    123.0     47.64
    782     1107  1384       1   285 5.92e-30    123.0     47.64
    783     1105  1384       1   287 6.17e-30    123.0     47.65
    784     1107  1384       8   292 6.20e-30    123.0     47.64
    785     1107  1384       7   291 6.41e-30    123.0     47.64
    786     1110  1384       2   283 6.51e-30    123.0     47.78
    787     1107  1384       6   290 7.03e-30    123.0     47.64
    788     1107  1384      27   311 7.07e-30    123.0     47.64
    789     1119  1390      18   278 7.48e-30    124.0     46.93
    790     1107  1384       2   286 7.87e-30    122.0     47.64
    791     1119  1390      18   278 7.89e-30    123.0     46.93
    792     1107  1384       9   293 8.05e-30    123.0     47.64
    793     1107  1384      25   309 8.17e-30    123.0     47.64
    794     1119  1390      39   299 8.18e-30    124.0     46.93
    795     1119  1390      18   278 8.22e-30    123.0     46.93
    796     1111  1414      23   315 8.31e-30    124.0     44.51
    797     1107  1384      24   308 9.05e-30    123.0     47.64
    798     1095  1384      19   318 9.38e-30    123.0     46.62
    799     1119  1390      36   296 1.11e-29    124.0     46.93
    800     1107  1384       7   291 1.16e-29    122.0     47.64
    801     1081  1384       2   312 1.51e-29    122.0     43.30
    802     1107  1384       7   291 3.62e-29    121.0     46.96
    803     1107  1384       6   290 3.78e-29    120.0     46.96
    804     1107  1384       6   290 3.85e-29    120.0     46.96
    805     1113  1384       5   283 4.32e-29    120.0     44.29
    806     1103  1380       3   285 6.03e-29    120.0     44.67
    807     1103  1380       3   285 6.59e-29    120.0     44.67
    808     1103  1376       3   281 7.18e-29    120.0     44.26
    809     1103  1376       3   281 7.89e-29    120.0     44.59
    810     1107  1414       5   282 1.03e-28    119.0     46.60
    811     1107  1414      27   304 1.79e-28    119.0     46.60
    812     1106  1376       1   276 2.49e-28    118.0     43.54
    813     1113  1376       6   274 2.74e-28    118.0     45.49
    814     1103  1376       3   281 3.18e-28    118.0     44.26
    815     1113  1376      10   278 3.23e-28    118.0     44.76
    816     1113  1376       7   275 3.46e-28    117.0     43.90
    817     1113  1384      22   300 4.64e-28    118.0     43.94
    818     1113  1384      10   288 5.93e-28    117.0     43.94
    819     1113  1384       9   287 6.50e-28    117.0     43.94
    820     1113  1384       8   286 6.66e-28    117.0     43.94
    821     1113  1384      20   298 7.13e-28    117.0     43.94
    822     1114  1379      13   284 7.55e-28    117.0     46.21
    823     1113  1384      19   297 8.51e-28    117.0     43.94
    824     1114  1379      10   281 9.41e-28    117.0     46.21
    825     1083  1384     841  1149 9.72e-28    124.0     43.89
    826     1111  1398     577   860 4.55e-16     86.3     42.95
    827     1074  1380     313   624 9.98e-28    122.0     44.24
    828     1114  1379      17   288 1.15e-27    117.0     46.21
    829     1114  1379      11   282 1.32e-27    117.0     46.21
    830     1114  1379      23   294 1.41e-27    117.0     46.21
    831     1033  1390     642   972 1.59e-27    123.0     45.60
    832     1114  1379      23   294 1.78e-27    117.0     46.21
    833     1113  1376      30   298 1.80e-27    116.0     44.41
    834     1113  1376      30   298 2.02e-27    116.0     44.41
    835     1104  1379       1   282 5.30e-27    114.0     45.33
    836     1114  1379      10   281 1.04e-26    113.0     45.86
    837     1114  1379       8   279 1.48e-26    113.0     46.58
    838     1114  1379       7   278 1.59e-26    113.0     46.23
    839     1114  1379      11   282 1.96e-26    112.0     46.58
    840     1114  1379      11   282 2.24e-26    113.0     46.58
    841     1114  1379       6   277 2.44e-26    112.0     46.23
    842     1103  1381       9   268 2.71e-26    113.0     46.98
    843     1108  1383       1   268 3.53e-26    111.0     44.21
    844     1110  1384       3   267 4.77e-26    111.0     47.37
    845     1106  1389      16   289 1.04e-25    110.0     47.28
    846     1106  1384       6   274 1.34e-25    110.0     47.40
    847     1114  1379       7   278 1.55e-25    110.0     45.86
    848     1114  1379      12   283 1.62e-25    110.0     46.21
    849     1108  1383       3   270 1.85e-25    110.0     44.21
    850     1114  1379       5   276 1.92e-25    109.0     46.23
    851     1106  1389       7   280 2.37e-25    109.0     47.28
    852     1098  1384      18   292 2.59e-25    109.0     47.14
    853     1110  1389       6   275 2.85e-25    108.0     47.24
    854     1110  1389      20   289 2.88e-25    109.0     47.24
    855     1114  1379       5   276 2.89e-25    109.0     46.23
    856     1110  1384       8   272 3.28e-25    108.0     47.37
    857     1110  1389      25   294 3.58e-25    109.0     47.24
    858     1110  1384      20   284 3.59e-25    109.0     47.37
    859     1106  1384       5   273 4.25e-25    108.0     47.40
    860     1106  1384       6   274 4.26e-25    108.0     47.06
    861     1106  1384      12   280 4.29e-25    108.0     47.06
    862     1110  1384       5   269 4.59e-25    108.0     47.37
    863     1106  1389       2   275 4.74e-25    108.0     46.94
    864     1106  1384       8   276 4.75e-25    108.0     47.06
    865     1108  1381       3   257 4.98e-25    109.0     46.38
    866     1108  1381       3   257 5.17e-25    109.0     46.38
    867     1106  1384      16   284 5.28e-25    108.0     47.06
    868     1108  1381       3   257 5.37e-25    108.0     46.38
    869     1108  1381       2   256 5.47e-25    108.0     46.38
    870     1108  1381       2   256 6.06e-25    108.0     46.38
    871     1106  1384       4   272 6.07e-25    108.0     47.06
    872     1105  1381       1   258 7.00e-25    108.0     46.24
    873     1106  1384       7   275 9.75e-25    107.0     47.06
    874     1089  1381      10   291 1.24e-24    108.0     47.18
    875     1106  1384      12   275 1.33e-24    107.0     47.22
    876     1110  1389      25   294 1.41e-24    107.0     46.90
    877     1089  1381      10   291 4.33e-24    106.0     47.18
    878     1100  1397       1   278 5.99e-23    103.0     43.83
    879     1110  1397       8   275 1.16e-22    102.0     44.30
    880     1110  1397      10   277 4.61e-22    105.0     43.73
    881     1106  1383      11   284 2.31e-19     92.0     47.95
    882     1108  1383       2   270 2.89e-19     91.7     45.07
    883     1110  1383       3   269 5.35e-19     90.5     45.04
    884     1110  1383       4   270 6.11e-19     90.5     45.04
    885     1108  1383       2   270 6.47e-19     90.5     45.07
    886     1108  1383       3   271 6.99e-19     90.9     44.72
    887     1110  1383       4   270 7.06e-19     90.9     45.39
    888     1108  1383       2   270 7.54e-19     90.5     44.72
    889     1122  1387      30   296 9.61e-19     90.5     42.91
    890     1111  1383       5   270 1.05e-18     90.1     45.20
    891     1122  1387      30   296 1.30e-18     90.1     42.91
    892     1108  1383       2   270 1.34e-18     89.7     44.72
    893     1122  1384       4   275 1.37e-18     90.1     42.11
    894     1108  1383       2   270 1.48e-18     89.4     44.72
    895     1122  1384       2   273 1.55e-18     90.1     42.11
    896     1108  1383       2   270 1.80e-18     89.4     45.07
    897     1108  1383       2   270 2.00e-18     89.4     44.72
    898     1106  1383      11   284 2.12e-18     89.4     47.26
    899     1122  1387      30   296 2.71e-18     89.4     42.91
    900     1108  1383       2   270 3.16e-18     88.6     45.07
    901     1108  1383       2   270 3.35e-18     88.6     45.07
    902     1106  1383      11   284 4.93e-18     88.2     46.92
    903     1115  1324      20   212 7.75e-18     87.8     49.30
    904     1106  1383      11   284 1.28e-17     87.0     47.96
    905     1110  1376      17   271 1.82e-17     86.3     43.27
    906     1110  1376      16   270 2.02e-17     86.3     43.27
    907     1110  1376      12   266 2.57e-17     85.9     43.27
    908     1110  1376      19   273 2.61e-17     85.9     43.27
    909     1110  1376      19   273 3.09e-17     85.9     43.27
    910     1110  1376      15   269 4.05e-17     85.5     43.27
    911     1111  1394      22   301 5.40e-17     85.5     43.24
    912     1122  1330      16   216 5.55e-17     88.6     47.00
    913     1122  1324      44   234 5.93e-17     85.5     47.57
    914     1111  1394      22   301 6.44e-17     85.1     42.91
    915     1122  1324      40   230 6.66e-17     85.1     47.57
    916     1110  1376      16   270 6.96e-17     84.7     42.91
    917     1122  1324      29   219 7.60e-17     84.7     47.57
    918     1122  1324      39   229 7.61e-17     85.1     47.57
    919     1105  1381      13   270 7.93e-17     85.1     44.29
    920     1106  1381      24   280 8.07e-17     85.1     44.44
    921     1122  1324      34   224 8.17e-17     85.1     47.57
    922     1122  1324      55   245 8.22e-17     85.1     47.57
    923     1122  1324      40   230 8.24e-17     85.1     47.57
    924     1105  1382      20   278 8.50e-17     85.1     44.13
    925     1122  1324      35   225 9.11e-17     84.7     47.57
    926     1122  1324      40   230 9.13e-17     84.7     47.57
    927     1122  1324      37   227 9.14e-17     84.7     47.57
    928     1122  1324      39   229 9.42e-17     84.7     47.57
    929     1122  1324      37   227 9.75e-17     84.7     47.57
    930     1105  1381       5   262 9.80e-17     84.3     44.29
    931     1105  1381       5   262 9.87e-17     84.3     44.29
    932     1122  1324      36   226 9.88e-17     84.7     47.57
    933     1122  1324      34   224 9.94e-17     84.7     47.57
    934     1122  1324      49   239 1.03e-16     84.7     47.57
    935     1122  1324      33   223 1.03e-16     84.7     47.57
    936     1122  1324      36   226 1.05e-16     84.7     47.57
    937     1122  1324      32   222 1.07e-16     84.3     47.57
    938     1122  1324      39   229 1.07e-16     84.7     47.57
    939     1122  1324      33   223 1.07e-16     84.3     47.57
    940     1122  1324      31   221 1.09e-16     84.3     47.57
    941     1122  1324      29   219 1.12e-16     84.3     47.57
    942     1122  1324      55   245 1.16e-16     84.7     47.57
    943     1122  1324      55   245 1.20e-16     84.7     47.57
    944     1122  1324      29   219 1.21e-16     84.3     47.57
    945     1122  1324      29   219 1.21e-16     84.3     47.57
    946     1122  1324      30   220 1.25e-16     84.3     47.57
    947     1122  1324      54   244 1.53e-16     84.3     47.57
    948     1122  1324      59   249 1.54e-16     84.3     47.57
    949     1122  1324      37   227 1.94e-16     84.0     45.58
    950     1104  1324       6   212 2.02e-16     84.0     47.77
    951     1122  1324      44   234 2.74e-16     83.6     47.57
    952     1122  1324      34   224 2.76e-16     83.2     47.57
    953     1122  1324     192   382 2.89e-16     85.5     47.57
    954     1122  1324      29   219 3.39e-16     82.8     47.57
    955     1100  1381      33   305 5.53e-16     83.2     42.19
    956     1098  1375       9   262 7.19e-16     82.0     41.61
    957     1108  1381       9   266 7.83e-16     82.0     42.66
    958     1118  1377      12   271 7.87e-16     82.0     41.22
    959     1112  1381       5   255 8.06e-16     82.0     43.96
    960     1112  1375      25   269 8.12e-16     81.6     43.82
    961     1112  1381       5   255 8.44e-16     82.0     43.96
    962     1112  1375       4   248 9.51e-16     81.3     43.45
    963     1122  1324      55   241 1.08e-15     82.0     47.83
    964     1098  1375       8   261 1.18e-15     81.3     41.61
    965     1156  1388      56   295 1.33e-15     81.3     44.44
    966     1080  1373     160   430 1.36e-15     83.2     41.75
    967     1122  1324      28   214 1.51e-15     81.3     47.83
    968     1120  1381      16   258 1.57e-15     80.5     44.70
    969     1156  1388      56   295 1.60e-15     80.9     44.44
    970     1156  1388      56   295 1.66e-15     80.9     44.44
    971     1156  1388      56   295 1.77e-15     80.9     44.44
    972     1122  1384      30   301 1.78e-15     80.9     43.66
    973     1156  1388      55   294 1.85e-15     80.9     44.44
    974     1123  1324      31   220 1.85e-15     80.9     44.39
    975     1118  1377      16   275 2.11e-15     80.9     41.22
    976     1156  1388      62   301 2.48e-15     80.5     44.44
    977     1118  1377      16   275 2.80e-15     80.5     40.28
    978     1098  1375       9   262 3.00e-15     80.1     41.61
    979     1156  1388      69   308 3.36e-15     80.1     44.44
    980     1122  1324      28   214 3.72e-15     80.1     47.83
    981     1156  1388      72   311 4.02e-15     80.1     44.44
    982     1156  1382      46   277 6.87e-15     79.0     44.67
    983     1156  1382      47   278 7.11e-15     79.0     44.67
    984     1112  1373      18   261 7.54e-15     79.0     42.64
    985     1156  1382      48   279 7.56e-15     78.6     44.67
    986     1120  1381      40   282 8.05e-15     78.6     40.73
    987     1122  1376      19   266 9.21e-15     78.2     44.15
    988     1080  1373     173   443 1.02e-14     80.5     41.75
    989     1156  1382      53   284 1.05e-14     78.6     44.67
    990     1120  1381      19   261 1.09e-14     78.2     40.36
    991     1080  1373     241   511 1.39e-14     80.5     41.41
    992     1103  1381       2   261 2.05e-14     77.4     40.41
    993     1101  1389      11   284 2.58e-14     77.8     39.74
    994     1120  1381      15   257 3.07e-14     76.6     40.00
    995     1112  1373      20   263 3.23e-14     77.0     40.91
    996     1120  1381      40   282 3.35e-14     77.0     40.00
    997     1120  1381      17   259 3.36e-14     76.6     40.00
    998     1120  1381      12   254 3.38e-14     76.6     40.00
    999     1120  1381      17   259 3.39e-14     76.6     40.00
    1000    1120  1381      14   256 3.42e-14     76.3     40.00
    1001    1120  1381      40   282 3.46e-14     77.0     40.73
    1002    1120  1381      40   282 3.48e-14     77.0     40.00
    1003    1112  1373      18   261 3.85e-14     76.6     40.91
    1004    1120  1381      15   257 3.95e-14     76.3     40.00
    1005    1120  1381      18   260 4.23e-14     76.3     40.00
    1006    1120  1381      18   260 4.25e-14     76.3     40.00
    1007    1156  1382      62   293 4.30e-14     77.4     44.26
    1008    1120  1381      14   256 4.32e-14     76.3     40.00
    1009    1120  1381      15   257 4.34e-14     76.3     40.00
    1010    1120  1381      18   260 4.40e-14     76.3     40.00
    1011    1120  1381      31   273 4.42e-14     76.6     40.00
    1012    1120  1381      14   256 4.49e-14     75.9     40.00
    1013    1120  1381      16   258 4.66e-14     76.3     40.00
    1014    1120  1381      19   261 4.77e-14     75.9     40.00
    1015    1120  1381      19   261 4.83e-14     76.3     40.00
    1016    1120  1381      19   261 4.88e-14     76.3     40.73
    1017    1120  1381      18   260 4.92e-14     75.9     40.00
    1018    1120  1381      19   261 4.92e-14     76.3     39.64
    1019    1120  1381      19   261 4.92e-14     76.3     40.00
    1020    1120  1381      12   254 4.96e-14     76.3     40.00
    1021    1120  1381      15   257 4.96e-14     75.9     40.00
    1022    1120  1381      14   256 4.97e-14     75.9     40.00
    1023    1120  1381      15   257 5.00e-14     76.3     40.00
    1024    1120  1381      16   258 5.02e-14     76.3     40.00
    1025    1120  1381      17   259 5.20e-14     76.3     40.00
    1026    1120  1381      13   255 5.23e-14     75.9     40.00
    1027    1120  1381      14   256 5.25e-14     75.9     40.00
    1028    1120  1381      33   275 5.31e-14     76.3     40.00
    1029    1120  1381      41   283 5.45e-14     76.3     43.94
    1030    1120  1381      25   267 5.52e-14     76.3     40.00
    1031    1120  1381      18   260 5.52e-14     76.3     40.00
    1032    1120  1381      14   256 5.66e-14     75.9     40.00
    1033    1120  1381      14   256 5.67e-14     75.9     40.00
    1034    1120  1381      14   256 5.72e-14     76.3     40.00
    1035    1112  1373      18   261 5.78e-14     76.3     40.53
    1036    1120  1381      19   261 5.82e-14     75.9     40.00
    1037    1120  1381      14   256 5.99e-14     75.9     40.00
    1038    1115  1324      20   211 6.31e-14     76.3     46.58
    1039    1120  1381      10   252 6.34e-14     75.5     40.00
    1040    1120  1381      14   256 6.36e-14     75.9     40.00
    1041    1120  1381      11   253 6.43e-14     75.5     40.00
    1042    1120  1381      17   259 6.44e-14     75.9     40.00
    1043    1120  1381      14   256 6.54e-14     75.5     40.00
    1044    1120  1381      40   282 6.80e-14     75.9     40.00
    1045    1120  1381      14   256 6.98e-14     75.5     40.00
    1046    1120  1381      40   282 6.99e-14     75.9     40.00
    1047    1112  1373      22   265 7.61e-14     75.9     40.53
    1048    1120  1381      40   282 7.95e-14     75.9     40.00
    1049    1120  1381      17   259 8.20e-14     75.5     40.00
    1050    1112  1373      19   262 9.33e-14     75.9     40.53
    1051    1112  1373      19   262 1.14e-13     75.5     40.91
    1052    1112  1373      18   261 1.16e-13     75.5     40.15
    1053    1112  1373      19   262 1.28e-13     75.5     40.91
    1054    1119  1351      26   244 1.30e-13     75.1     47.33
    1055    1112  1373      18   261 1.33e-13     75.1     40.15
    1056    1112  1373      18   261 1.38e-13     75.1     40.15
    1057    1112  1373      18   261 1.82e-13     74.7     40.91
    1058    1112  1373      17   260 1.93e-13     74.7     40.91
    1059    1120  1381      16   258 2.02e-13     74.3     40.00
    1060    1112  1373      18   261 2.11e-13     74.7     40.91
    1061    1120  1381      19   261 2.19e-13     74.3     40.00
    1062    1120  1381      11   253 2.34e-13     73.9     39.64
    1063    1120  1381      17   259 2.37e-13     73.9     40.00
    1064    1089  1381      10   285 2.64e-13     74.3     39.68
    1065    1122  1330      23   224 3.06e-13     76.6     46.33
    1066    1108  1374       3   256 3.07e-13     73.9     40.51
    1067    1120  1381      11   253 3.13e-13     73.6     39.64
    1068    1122  1330      22   223 3.24e-13     76.6     46.33
    1069    1120  1381      16   258 3.25e-13     73.6     40.00
    1070    1112  1373      18   261 3.40e-13     73.9     40.53
    1071    1108  1340       1   228 3.53e-13     74.7     44.86
    1072    1100  1322      13   213 3.79e-13     73.9     45.29
    1073    1112  1373      13   256 3.85e-13     73.6     40.53
    1074    1108  1374       4   257 3.87e-13     73.6     40.51
    1075    1112  1373      19   262 3.92e-13     73.9     40.53
    1076    1120  1380      28   277 3.97e-13     73.6     45.15
    1077    1146  1406      50   290 4.20e-13     73.6     43.23
    1078    1108  1340       1   228 4.55e-13     74.3     43.75
    1079    1120  1381      19   261 4.64e-13     73.2     39.64
    1080    1120  1381      19   261 4.68e-13     73.2     39.64
    1081    1120  1381      19   261 5.00e-13     73.2     39.64
    1082    1108  1340       1   228 5.16e-13     74.3     43.75
    1083    1120  1381      17   259 5.64e-13     73.2     39.64
    1084    1120  1381      11   253 5.89e-13     72.8     39.64
    1085    1120  1381      12   254 5.93e-13     72.8     39.64
    1086    1120  1381      11   253 6.29e-13     72.4     39.64
    1087    1108  1340       1   228 6.29e-13     73.9     44.44
    1088    1120  1381      16   258 6.33e-13     72.8     39.64
    1089    1120  1345      55   265 6.46e-13     75.1     47.83
    1090    1146  1406      72   312 6.50e-13     73.6     43.23
    1091    1112  1373      20   263 6.87e-13     73.2     40.53
    1092    1120  1381      13   255 6.96e-13     72.4     39.64
    1093    1108  1340       1   228 7.07e-13     73.9     43.33
    1094    1108  1340       1   228 7.27e-13     73.9     43.33
    1095    1120  1381      14   256 7.71e-13     72.4     39.64
    1096    1120  1381      13   255 7.81e-13     72.4     39.64
    1097    1120  1381      38   280 7.98e-13     72.8     39.64
    1098    1120  1381      14   256 8.17e-13     72.4     39.64
    1099    1122  1330      27   228 9.37e-13     75.1     45.16
    1100    1108  1383      14   284 9.49e-13     72.4     45.83
    1101    1120  1381      40   282 9.74e-13     72.4     39.64
    1102    1108  1374       4   257 1.31e-12     72.0     40.15
    1103    1108  1374       5   258 1.52e-12     71.6     40.15
    1104    1108  1374       4   257 1.54e-12     71.6     40.15
    1105    1108  1374       4   257 1.56e-12     71.6     40.15
    1106    1120  1381      18   260 1.66e-12     71.6     39.64
    1107    1108  1374       3   256 1.75e-12     71.6     40.15
    1108    1164  1391      55   280 1.76e-12     71.6     46.64
    1109    1120  1381      18   260 1.79e-12     71.2     39.64
    1110    1119  1351       9   227 1.79e-12     73.6     47.74
    1111    1112  1373     255   498 1.89e-12     73.6     41.29
    1112    1112  1322       6   198 1.91e-12     71.6     45.02
    1113    1108  1374       3   256 1.97e-12     71.2     40.15
    1114    1120  1381      17   259 2.12e-12     71.2     39.64
    1115    1122  1330      27   228 2.20e-12     73.9     44.70
    1116    1120  1381      15   257 2.65e-12     70.9     39.27
    1117    1122  1330      23   224 2.88e-12     73.6     44.70
    1118    1099  1384      31   313 2.92e-12     71.6     45.48
    1119    1101  1385      13   292 2.96e-12     71.2     43.23
    1120    1120  1345      56   266 3.41e-12     72.8     47.39
    1121    1122  1330      21   222 3.58e-12     73.2     44.70
    1122    1120  1381      19   261 3.65e-12     70.5     39.27
    1123    1120  1345      55   265 3.77e-12     72.8     47.39
    1124    1120  1381      19   261 4.00e-12     70.5     39.27
    1125    1120  1345      73   283 4.28e-12     72.4     47.39
    1126    1120  1345      56   266 4.56e-12     72.4     47.39
    1127    1113  1345      23   237 5.39e-12     70.1     48.94
    1128    1113  1345      23   237 5.46e-12     70.1     48.94
    1129    1113  1345       8   222 6.06e-12     70.5     44.26
    1130    1110  1374       2   253 6.53e-12     69.7     41.18
    1131    1164  1391     241   466 7.48e-12     71.6     46.22
    1132    1110  1384       8   279 7.72e-12     69.7     45.83
    1133    1122  1388      47   315 9.40e-12     70.1     43.40
    1134    1122  1388      47   315 1.03e-11     70.1     43.40
    1135    1095  1345      16   243 1.87e-11     70.5     47.83
    1136    1113  1345      23   237 2.13e-11     70.1     48.94
    1137    1120  1381      17   259 2.33e-11     68.2     39.27
    1138    1108  1383       8   282 2.35e-11     68.2     47.77
    1139    1120  1345      38   248 3.17e-11     68.2     46.52
    1140    1120  1373      29   263 3.72e-11     67.8     42.19
    1141    1120  1345      33   243 7.11e-11     68.6     46.52
    1142    1146  1330      50   219 7.65e-11     67.0     46.49
    1143    1146  1330      72   241 8.07e-11     67.0     46.49
    1144    1120  1345      32   242 9.86e-11     68.2     46.52
    1145    1193  1380     105   286 1.65e-10     66.2     44.79
    1146    1099  1384      18   298 3.31e-10     65.1     44.37
    1147    1120  1345      32   242 3.49e-10     66.2     46.52
    1148    1099  1384      18   298 4.08e-10     65.1     44.37
    1149    1108  1381      23   278 4.23e-10     64.7     39.52
    1150    1108  1381      23   278 4.35e-10     64.7     39.52
    1151    1108  1381      23   278 4.43e-10     64.7     39.52
    1152    1099  1384      41   321 5.18e-10     64.7     44.37
    1153    1094  1330      30   241 5.22e-10     65.5     39.92
    1154    1115  1350      15   236 5.67e-10     63.9     40.93
    1155    1108  1381      13   268 5.79e-10     64.3     40.70
    1156    1113  1349      15   244 6.14e-10     64.3     41.60
    1157    1113  1349       9   238 7.26e-10     64.3     41.60
    1158    1113  1349       9   238 7.52e-10     64.3     41.60
    1159    1113  1349       9   238 7.53e-10     64.3     41.60
    1160    1113  1349       8   237 7.53e-10     64.3     41.60
    1161    1122  1416      28   316 8.03e-10     64.3     41.23
    1162    1108  1317       5   195 1.33e-09     63.2     43.81
    1163    1094  1339      39   259 1.43e-09     63.5     39.68
    1164    1108  1322      21   216 1.57e-09     63.2     43.26
    1165    1118  1381       5   250 1.99e-09     62.4     40.00
    1166    1119  1373      42   283 2.32e-09     63.5     42.86
    1167    1147  1330     102   270 2.59e-09     62.8     45.16
    1168    1108  1317       5   195 2.63e-09     62.0     42.86
    1169    1147  1330      75   243 2.81e-09     62.4     44.62
    1170    1166  1380      85   285 2.87e-09     62.4     40.00
    1171    1086  1349     104   363 2.91e-09     63.2     40.36
    1172    1147  1330     179   347 3.14e-09     63.2     44.62
    1173    1147  1330      57   225 3.16e-09     62.0     44.62
    1174    1112  1330      23   221 3.19e-09     62.0     42.53
    1175    1147  1330     102   270 3.32e-09     62.4     44.62
    1176    1086  1349     118   377 3.41e-09     62.8     40.36
    1177    1147  1330     209   377 3.64e-09     62.8     44.62
    1178    1122  1345      65   270 4.10e-09     62.8     44.10
    1179    1147  1330      59   227 4.15e-09     61.6     44.62
    1180    1112  1330      22   220 4.42e-09     61.6     42.53
    1181    1112  1330      92   290 4.55e-09     62.0     42.53
    1182    1147  1330      49   217 4.66e-09     61.2     44.62
    1183    1147  1330      57   225 4.71e-09     61.6     44.62
    1184    1147  1330      49   217 5.06e-09     61.2     44.62
    1185    1166  1380      70   270 5.07e-09     61.6     40.00
    1186    1112  1330      19   217 5.10e-09     61.2     42.53
    1187    1147  1330      82   250 5.13e-09     61.6     44.62
    1188    1112  1330      18   216 5.39e-09     61.2     42.53
    1189    1108  1317       5   195 5.39e-09     61.2     43.81
    1190    1166  1380      66   266 5.42e-09     61.2     40.00
    1191    1166  1380      66   266 5.67e-09     61.2     40.00
    1192    1166  1380      90   290 8.86e-09     60.8     40.00
    1193    1166  1380      88   288 9.56e-09     60.8     40.00
    1194    1115  1346      32   249 1.01e-08     60.8     41.45
    1195    1101  1317      13   210 1.07e-08     60.8     43.32
    1196    1166  1380      63   263 1.10e-08     60.1     40.00
    1197    1166  1380      64   264 1.10e-08     60.1     40.00
    1198    1166  1380     113   313 1.11e-08     60.8     40.00
    1199    1103  1338       8   226 1.13e-08     60.8     43.04
    1200    1118  1346       8   222 1.32e-08     60.5     41.38
    1201    1176  1332      65   211 1.34e-08     60.5     43.95
    1202    1118  1346      17   231 1.60e-08     59.7     41.38
    1203    1147  1330     102   270 1.61e-08     60.1     44.62
    1204    1108  1317       4   194 1.61e-08     60.5     43.81
    1205    1118  1346       7   221 1.75e-08     59.7     41.38
    1206    1118  1346       8   222 1.78e-08     59.7     41.38
    1207    1118  1346      17   231 2.68e-08     60.1     41.38
    1208    1147  1330     139   307 2.68e-08     59.7     44.62
    1209    1115  1324      35   236 3.64e-08     58.5     36.89
    1210    1193  1338     102   237 3.75e-08     58.9     46.58
    1211    1193  1338      83   218 3.78e-08     58.9     46.58
    1212    1102  1340      10   232 6.84e-08     58.2     40.65
    1213    1118  1346       8   222 7.44e-08     57.8     41.56
    1214    1102  1340       9   231 7.55e-08     58.5     40.65
    1215    1163  1374    1304  1512 9.63e-08     59.3     42.92
    1216    1114  1373      37   316 9.94e-08     57.8     38.44
    1217    1163  1374    1284  1492 1.01e-07     59.3     42.92
    1218    1110  1340      10   224 1.06e-07     57.4     40.76
    1219    1163  1374    1336  1544 1.07e-07     58.9     42.92
    1220    1122  1388      31   292 1.29e-07     57.4     40.07
    1221    1118  1346     289   503 1.41e-07     58.5     41.56
    1222    1120  1345      36   246 1.50e-07     57.8     46.32
    1223    1571  1589       1    19 1.70e-07     50.4    100.00
    1224    1164  1383      63   282 2.29e-07     56.2     45.26
    1225    1122  1388      58   319 2.38e-07     56.6     40.42
    1226    1094  1340       8   228 2.43e-07     56.6     40.49
    1227    1193  1388     307   513 2.48e-07     57.4     44.13
    1228    1118  1346      10   224 2.62e-07     57.0     40.69
    1229    1118  1346       9   223 2.89e-07     55.5     40.69
    1230    1164  1383      63   282 2.90e-07     55.8     45.26
    1231    1164  1383      63   282 2.93e-07     55.8     45.26
    1232    1164  1383      59   278 3.02e-07     55.8     44.30
    1233    1118  1346      26   240 3.18e-07     55.8     40.69
    1234    1118  1346       4   218 3.32e-07     56.6     40.69
    1235    1108  1383       8   289 3.64e-07     55.5     43.19
    1236    1108  1383       7   288 3.95e-07     55.5     43.19
    1237    1122  1388      27   288 4.01e-07     55.8     40.42
    1238    1118  1346      17   231 4.11e-07     55.5     40.69
    1239    1163  1350      72   253 4.81e-07     55.8     41.80
    1240    1108  1383       7   288 5.08e-07     55.1     43.19
    1241    1119  1344      11   255 5.73e-07     55.5     40.38
    1242    1163  1344      79   250 1.00e-06     54.3     43.24
    1243    1114  1322       8   216 1.05e-06     54.3     38.96
    1244    1122  1340      26   228 1.14e-06     53.9     42.01
    1245    1122  1325      61   280 1.20e-06     54.7     40.98
    1246    1122  1340      26   228 1.32e-06     53.9     42.01
    1247    1122  1340      26   228 1.36e-06     53.9     42.01
    1248    1108  1383     185   466 1.42e-06     54.7     43.19
    1249    1114  1384      10   266 2.39e-06     52.8     40.78
    1250    1114  1322       8   216 2.40e-06     53.1     41.63
    1251    1114  1384      10   266 2.44e-06     52.8     40.78
    1252    1163  1344      60   231 2.58e-06     52.8     42.16
    1253    1163  1344      60   231 2.60e-06     52.8     42.16
    1254    1163  1344      61   232 2.60e-06     52.8     42.16
    1255    1087  1322      10   246 2.61e-06     53.1     41.00
    1256    1087  1322       9   245 2.73e-06     53.1     41.00
    1257    1163  1344      60   231 2.74e-06     52.8     42.16
    1258    1163  1344      62   233 2.76e-06     53.1     43.24
    1259    1163  1344      63   234 2.82e-06     53.1     43.24
    1260    1163  1344      62   233 2.83e-06     53.1     43.24
    1261    1163  1344      60   231 2.90e-06     52.8     42.16
    1262    1163  1344      59   230 2.90e-06     52.8     42.16
    1263    1163  1344      59   230 2.92e-06     52.8     42.16
    1264    1163  1344      60   231 2.94e-06     52.8     42.16
    1265    1163  1344      60   231 2.94e-06     52.8     42.16
    1266    1163  1344      60   231 2.94e-06     52.8     42.16
    1267    1163  1344      63   234 2.95e-06     53.1     43.24
    1268    1108  1322      24   238 2.95e-06     53.1     41.42
    1269    1114  1384      10   266 2.97e-06     52.4     40.78
    1270    1163  1344      60   231 3.08e-06     52.8     42.16
    1271    1163  1344      59   230 3.11e-06     52.8     42.16
    1272    1087  1322       9   245 3.24e-06     53.1     41.00
    1273    1163  1344      60   231 3.26e-06     52.8     42.16
    1274    1163  1344      63   234 3.28e-06     52.8     42.16
    1275    1163  1344      63   234 3.28e-06     52.8     42.16
    1276    1173  1379     172   375 3.45e-06     53.9     38.67
    1277    1163  1344      60   231 3.50e-06     52.8     43.24
    1278    1163  1344      62   233 3.50e-06     52.8     42.70
    1279    1163  1344      60   231 3.52e-06     52.8     42.16
    1280    1087  1322       1   237 3.85e-06     52.8     41.00
    1281    1163  1344      60   231 3.86e-06     52.8     42.25
    1282    1111  1376      17   281 4.61e-06     52.4     39.58
    1283    1114  1322      14   222 4.62e-06     52.4     41.20
    1284    1114  1322      37   245 5.68e-06     52.0     41.20
    1285    1114  1322      37   245 5.68e-06     52.0     41.20
    1286    1193  1332      97   227 5.83e-06     52.0     45.00
    1287    1193  1332     105   235 5.89e-06     52.0     45.00
    1288    1193  1332      89   219 6.17e-06     52.0     45.00
    1289    1193  1332      97   227 6.22e-06     52.4     45.00
    1290    1193  1332      95   225 6.59e-06     52.0     45.00
    1291    1193  1332      91   221 6.62e-06     52.0     45.00
    1292    1116  1322       8   214 6.86e-06     51.6     41.13
    1293    1193  1332      85   215 6.88e-06     52.0     45.00
    1294    1193  1332     141   271 6.88e-06     52.4     45.00
    1295    1111  1376      17   281 6.92e-06     52.0     39.24
    1296    1193  1332      96   226 6.92e-06     52.0     45.00
    1297    1193  1332     135   265 7.02e-06     52.4     45.00
    1298    1193  1332      91   221 7.17e-06     52.0     45.00
    1299    1116  1322      10   216 7.26e-06     51.6     41.13
    1300    1193  1332      90   220 7.53e-06     51.6     45.00
    1301    1193  1332      89   219 7.92e-06     51.6     45.00
    1302    1193  1332     116   246 8.09e-06     51.6     45.00
    1303    1114  1384      10   266 9.36e-06     50.8     40.43
    1304    1174  1385     281   509 1.02e-05     52.4     41.38
    1305    1193  1332      89   219 1.42e-05     50.8     44.29
    1306    1193  1332      91   221 1.46e-05     50.8     44.29
    1307    1111  1376      17   281 1.57e-05     50.8     39.52
    1308    1193  1332     135   265 1.67e-05     50.8     43.57
    1309    1176  1332      66   192 2.06e-05     50.1     40.76
    1310    1571  1589     135   153 2.08e-05     48.1    100.00
    1311    1163  1344      60   231 3.02e-05     49.7     41.62
    1312    1105  1337      31   249 3.45e-05     49.7     40.08
    1313    1167  1341      86   259 3.61e-05     49.3     41.45
    1314    1167  1341      86   259 3.87e-05     49.3     41.45
    1315    1105  1337      31   249 4.04e-05     49.3     40.08
    1316    1103  1337      13   233 4.08e-05     49.3     39.75
    1317    1105  1337      31   249 4.11e-05     49.3     40.08
    1318    1095  1330      14   246 4.86e-05     49.3     41.18
    1319    1167  1341      78   251 4.87e-05     48.9     41.45
    1320    1117  1384      15   285 9.43e-05     48.5     38.78
    1321    1193  1332      91   200 3.16e-04     46.6     39.29
    1322    1117  1330      20   224 4.68e-04     46.2     39.19
    1323    1117  1330      35   239 4.92e-04     46.2     39.19
    1324    1117  1330      34   238 5.54e-04     46.2     39.19
    1325    1236  1325     273   361 6.29e-04     46.2     43.48
    1326    1118  1339      34   259 3.00e-03     43.9     40.41
    1327    1118  1339      23   248 3.00e-03     43.5     40.41
    1328    1118  1339      34   259 3.00e-03     43.5     40.41
    1329    1118  1339      55   280 3.00e-03     43.9     40.41
    1330    1118  1339      32   257 3.00e-03     43.5     40.41
    1331    1114  1384      10   266 4.00e-03     43.1     38.30
    1332    1118  1339      34   259 7.00e-03     42.4     40.41
    1333    1122  1418      34   332 8.00e-03     42.4     38.79
    1334    1120  1379      15   271 2.60e-02     40.4     43.46
    1335    1221  1379     100   269 3.70e-02     40.0     44.25
    1336     684   783       8   100 4.70e-02     39.7     39.00
    1337    1220  1379     100   270 5.00e-02     39.7     44.00
    1338    1113  1339     153   383 5.20e-02     40.0     40.80
    1339    1122  1325      36   253 5.50e-02     39.7     41.60
    1340    1220  1379     101   271 5.60e-02     39.3     43.10
    1341    1220  1379     119   289 5.70e-02     39.3     43.10
    1342    1220  1379     101   271 5.80e-02     39.3     44.00
    1343    1221  1379     114   283 6.10e-02     39.3     43.35
    1344    1220  1379     101   271 6.10e-02     39.3     44.00
    1345    1220  1379      99   269 6.30e-02     39.3     44.00
    1346    1220  1379      99   269 6.40e-02     39.3     44.00
    1347    1220  1379     100   270 6.40e-02     39.3     44.00
    1348    1220  1379     106   276 6.50e-02     39.3     44.00
    1349    1220  1379      99   269 6.70e-02     39.3     44.00
    1350    1220  1379      99   269 6.90e-02     39.3     44.00
    1351    1220  1379      96   266 6.90e-02     39.3     44.00
    1352    1220  1379      99   269 7.20e-02     39.3     44.00
    1353    1221  1379     100   269 8.40e-02     39.3     42.77
    1354    1220  1379      99   269 8.50e-02     38.9     44.00
    1355    1165  1379     549   765 9.80e-02     39.3     41.20
    1356    1165  1379     560   776 9.80e-02     39.3     41.20
    1357    1165  1379     551   767 9.90e-02     39.3     41.20
    1358    1220  1379     119   289 1.10e-01     38.5     42.53
    1359    1220  1379     101   271 1.20e-01     38.5     43.43
    1360    1120  1274      14   154 1.20e-01     38.5     41.82
    1361    1120  1274      14   154 1.40e-01     38.5     41.82
    1362    1120  1328      13   202 2.40e-01     37.7     41.44
    1363    1120  1279      13   157 3.30e-01     37.4     42.35
    1364     439   481    2744  2801 6.50e-01     37.0     46.55
    1365    1119  1285     107   263 6.60e-01     36.6     40.94
    1366    1119  1285     107   263 7.00e-01     36.2     40.94
    1367     450   636     625   797 7.30e-01     36.6     43.23
    1368     439   481    2744  2801 7.70e-01     36.6     46.55
    1369    1118  1275      11   154 8.60e-01     35.8     45.18
    1370     917  1037       3   149 8.90e+00     32.3     39.07

    $url
                                                                                                                                                                              V628A9VW016 
    "https://blast.ncbi.nlm.nih.gov/Blast.cgi?CMD=Get&FORMAT_OBJECT=Alignment&ALIGNMENT_VIEW=Tabular&RESULTS_FILE=on&FORMAT_TYPE=CSV&ALIGNMENTS=20000&DESCRIPTIONS=20000&RID=V628A9VW016" 

    attr(,"class")
    [1] "blast"

> Q2. \[6pts\] What are the tumor specific mutations in this particular
> case ( e.g. A130V)?

``` r
which(conserv(ngs) < 1)
```

    [1] 1145 1233 1242 1312

V1145L, E1233I, R1242E, Y1312T

> Q3. \[1pts\] Do your mutations cluster to any particular domain and if
> so give the name and PFAM id of this domain? Alternately note whether
> your protein is single domain and provide it’s PFAM id/accession and
> name (e.g. PF00613 and PI3Ka).

Yes, the mutations are found between the ~1100 and ~1400 bp areas. This
domain corresponds to the Pkindase_Tyr domain and the protein is not a
single domain, but rather composed of multiple ones.

PFAM ID: PF07714 Name: Protein tyrosine and serine/threonine kinase

> Q4. \[2pts\] Using the NCI-GDC list the observed top 2 missense
> mutations in this protein (amino acid substitutions)?

The top 2 missense mutations in this protein are R1275Q and F1174L

> Q5. \[2pts\] What two TCGA projects have the most cases affected by
> mutations of this gene? (Give the TCGA “code” and “Project Name” for
> example “TCGA-BRCA” and “Breast Invasive Carcinoma”).

Code: TCGA-UCEC Project Name: Uterine Corpus Endometrial Carcinoma Code:
TCGA-SKCM Project Name: Skin Cutaneous Melanoma

> Q6. \[3pts\] List one RCSB PDB identifier with 100% identity to the
> wt_healthy sequence and detail the percent coverage of your query
> sequence for this known structure? Alternately,provide the most
> similar in sequence PDB structure along with it’s percent identity,
> coverageand E-value. Does this structure “cover” (i.e. include or span
> the amino acid residue positions) of your previously identified tumor
> specific mutations?

RCSB PDB: 7NX3_A Percentage Coverage: 100% E-Value: 0.0

No, this structure does not “cover” the previously identified tumor
specific mutations. It only ranges from 648 to 1030, which is out of the
range of where the mutations were at.
