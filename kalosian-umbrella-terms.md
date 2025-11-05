---
title: Umbrella Terms in Kalosian
date: 2025-10-27
tags:
  - kalosian
  - analysis
author: falnairär
---
<link rel="stylesheet" type="text/css" media="all" href="./style/style.css">

# Umbrella Terms in Kalosian

**Author**: falnairär

**Date**: 2025-10-27

Garbage text is usually found as repeated fragments of text. These fragments seem to form a longer chain of characters from which the pieces are taken. Therefore, a method for statistically detecting garbage text can be to count how many words can be contained within a term. However, longer words can be negatively affected by a simple count. In this case, we'll employ a weighted count, in which the longer the subword token with respect to the longer word, the more it counts. Thus, shorter words with one or two letters, which can be easily found within others (e.g. "a"/"an"), don't affect the results greatly:

$$
score(S) = \frac{1}{|S|} \sum_{s \in W, s \subseteq S} |s|
$$

where $W$ is the set of Kalosian words, $S$ is one largest string, and $s \subseteq S$ are all the words or tokens that are found in $W$ and are contained within $S$. 

## List of Kalosian terms

If a word is contained within another, it won't appear in this list. If the longest word which contains it can be considered garbage text, then the shorter version might also be garbage. Exceptions occur with shorter tokens, but it might hold with longer subwords.

As it can be seen, words with "known" meaning, like <thraex>PQRwNQT DEMLEZ</thraex> (POKeMON CENTER), <thraex>lQDAB</thraex> (MIARE), <thraex>RQFZ</thraex> (CITY), <thraex>JBOM</thraex> (TAXI), and <thraex>DUDLSL</thraex> (MOMIJI) all score exactly $1.0000$ with this method, because the only subwords are themselves. Therefore, terms with a higher score can be considered "garbage text". Words with a score of $1.0000$ can still be "garbage", but it needs to be proven with other methods, like the context of the text and its surrounding words.

|     | pokelatin                 |   subtokens |
|----:|:--------------------------|------------:|
|   0 | <thraex>RELBEQTVEPMsHCsSYCFCJTsZ</thraex>  |      5.5000   |
|   1 | <thraex>TXLSLOFNRSECS</thraex>             |      4.3077 |
|   2 | <thraex>QQLREOLFJHTOOsCLXVSFTsAOT</thraex> |      3.8800  |
|   3 | <thraex>Xcqjoweieajobftbh</thraex>         |      3.1765 |
|   4 | <thraex>NRSECBsASCMBsSVOsR</thraex>        |      3.1667 |
|   5 | <thraex>PsELBRs</thraex>                   |      3.0000     |
|   6 | <thraex>Mbgctefqciboto</thraex>            |      2.7143 |
|   7 | <thraex>Bgcofaiac</thraex>                 |      2.6667 |
|   8 | <thraex>Jbitcaqhrw</thraex>                |      2.6000   |
|   9 | <thraex>RNFSHQ</thraex>                    |      2.5000   |
|  10 | <thraex>sqhct</thraex>                     |      2.4000   |
|  11 | <thraex>Sjqqoctaqfhctacichtaerac</thraex>  |      2.2917 |
|  12 | <thraex>tajraqwc</thraex>                  |      2.1250 |
|  13 | <thraex>Mbgcterqcibotoaeqja</thraex>       |      2.0526 |
|  14 | <thraex>Agfoecqeai</thraex>                |      2.0000     |
|  15 | <thraex>Dawcqe</thraex>                    |      1.8333 |
|  16 | <thraex>UTsOP\~BER\~sVIYD\~B</thraex>         |      1.8235 |
|  17 | <thraex>OPMsHCsSYCBFCJTsZ</thraex>         |      1.8235 |
|  18 | <thraex>Crqot</thraex>                     |      1.8000   |
|  19 | <thraex>Bgcufaiactaqjecag</thraex>         |      1.7647 |
|  20 | <thraex>Drch</thraex>                      |      1.7500  |
|  21 | <thraex>Ribwgjhw</thraex>                  |      1.7500  |
|  22 | <thraex>Mocgawtf</thraex>                  |      1.7500  |
|  23 | <thraex>MBmERBYJOUEQAlFQ</thraex>          |      1.6875 |
|  24 | <thraex>Xocbg</thraex>                     |      1.6000   |
|  25 | <thraex>wrcew</thraex>                     |      1.6000   |
|  26 | <thraex>oewao</thraex>                     |      1.6000   |
|  27 | <thraex>DIsFX</thraex>                     |      1.6000   |
|  28 | <thraex>UTsOP\~OER\~sVIYD\~O</thraex>         |      1.5882 |
|  29 | <thraex>MAOEHSsDL</thraex>                 |      1.5556 |
|  30 | <thraex>lEXBQCSIEIT</thraex>               |      1.5455 |
|  31 | <thraex>ftbahoew</thraex>                  |      1.3750 |
|  32 | <thraex>cagbaqjhoir</thraex>               |      1.3636 |
|  33 | <thraex>raw\~qage\~q</thraex>                |      1.2000   |
|  34 | <thraex>lQDAB</thraex>                     |      1.0000     |
|  35 | <thraex>Veqrehj</thraex>                   |      1.0000     |
|  36 | <thraex>sqbt</thraex>                      |      1.0000     |
|  37 | <thraex>Nehcij</thraex>                    |      1.0000     |
|  38 | <thraex>DHqX</thraex>                      |      1.0000     |
|  39 | <thraex>Ibeo</thraex>                      |      1.0000     |
|  40 | <thraex>Bh</thraex>                        |      1.0000     |
|  41 | <thraex>Tret</thraex>                      |      1.0000     |
|  42 | <thraex>Qewgci</thraex>                    |      1.0000     |
|  43 | <thraex>Vh</thraex>                        |      1.0000     |
|  44 | <thraex>Hcirt</thraex>                     |      1.0000     |
|  45 | <thraex>Lhwtj</thraex>                     |      1.0000     |
|  46 | <thraex>Sogbe</thraex>                     |      1.0000     |
|  47 | <thraex>Oct</thraex>                       |      1.0000     |
|  48 | <thraex>Dfcbw</thraex>                     |      1.0000     |
|  49 | <thraex>wgtieqog</thraex>                  |      1.0000     |
|  50 | <thraex>SCFM</thraex>                      |      1.0000     |
|  51 | <thraex>Riwbr</thraex>                     |      1.0000     |
|  52 | <thraex>Qfcbojicte</thraex>                |      1.0000     |
|  53 | <thraex>qrt</thraex>                       |      1.0000     |
|  54 | <thraex>Jghbt</thraex>                     |      1.0000     |
|  55 | <thraex>Qbe\`qcwoh</thraex>                 |      1.0000     |
|  56 | <thraex>QYEVTJB</thraex>                   |      1.0000     |
|  57 | <thraex>Foewb</thraex>                     |      1.0000     |
|  58 | <thraex>Dbi</thraex>                       |      1.0000     |
|  59 | <thraex>Ze</thraex>                        |      1.0000     |
|  60 | <thraex>qtkonfb</thraex>                   |      1.0000     |
|  61 | <thraex>Ctw</thraex>                       |      1.0000     |
|  62 | <thraex>giq</thraex>                       |      1.0000     |
|  63 | <thraex>BXNegr</thraex>                    |      1.0000     |
|  64 | <thraex>Iefbciww</thraex>                  |      1.0000     |
|  65 | <thraex>DEMLEZ</thraex>                    |      1.0000     |
|  66 | <thraex>lo\~wbqcir</thraex>                 |      1.0000     |
|  67 | <thraex>Fto</thraex>                       |      1.0000     |
|  68 | <thraex>Zwb</thraex>                       |      1.0000     |
|  69 | <thraex>Qofcq</thraex>                     |      1.0000     |
|  70 | <thraex>PQRwNQT</thraex>                   |      1.0000     |
|  71 | <thraex>fcabo</thraex>                     |      1.0000     |
|  72 | <thraex>Xecwbtqc</thraex>                  |      1.0000     |
|  73 | <thraex>RQFZ</thraex>                      |      1.0000     |
|  74 | <thraex>Mbe\~w</thraex>                     |      1.0000     |
|  75 | <thraex>hjc</thraex>                       |      1.0000     |
|  76 | <thraex>Bcbjq</thraex>                     |      1.0000     |
|  77 | <thraex>Pbcwia</thraex>                    |      1.0000     |
|  78 | <thraex>Etiae</thraex>                     |      1.0000     |
|  79 | <thraex>DUDLSL</thraex>                    |      1.0000     |
|  80 | <thraex>rehq</thraex>                      |      1.0000     |
|  81 | <thraex>Xtogwtif</thraex>                  |      1.0000     |
|  82 | <thraex>Meorg</thraex>                     |      1.0000     |
|  83 | <thraex>wbrgq</thraex>                     |      1.0000     |
|  84 | <thraex>Ecgw</thraex>                      |      1.0000     |
|  85 | <thraex>QUJOL\`PlDSl</thraex>               |      1.0000     |
|  86 | <thraex>HiQMf</thraex>                     |      1.0000     |
|  87 | <thraex>rwh\~qg</thraex>                    |      1.0000     |
|  88 | <thraex>LFDEQNC</thraex>                   |      1.0000     |
|  89 | <thraex>eoiw</thraex>                      |      1.0000     |
|  90 | <thraex>\`RBYEZJ\~sQsFLA\`D</thraex>          |      1.0000     |
|  91 | <thraex>mFOQLlVIUJ\`RYlQV</thraex>          |      1.0000     |
|  92 | <thraex>rweZHqVVatS</thraex>               |      1.0000     |
|  93 | <thraex>Qtaoèg</thraex>                    |      1.0000     |
|  94 | <thraex>iègb</thraex>                      |      1.0000     |
|  95 | <thraex>j\`qwe</thraex>                     |      1.0000     |
|  96 | <thraex>toq</thraex>                       |      1.0000     |
|  97 | <thraex>gcofaiactaqje</thraex>             |      1.0000     |
|  98 | <thraex>Dhwcqe</thraex>                    |      1.0000     |
|  99 | <thraex>MBYUSMV</thraex>                   |      1.0000     |
| 100 | <thraex>Zjehq</thraex>                     |      1.0000     |
| 101 | <thraex>Zqb</thraex>                       |      1.0000     |
| 102 | <thraex>Xtogqtif</thraex>                  |      1.0000     |
| 103 | <thraex>Lhqtj</thraex>                     |      1.0000     |
| 104 | <thraex>Foeqb</thraex>                     |      1.0000     |
| 105 | <thraex>QYEVTJO</thraex>                   |      1.0000     |
| 106 | <thraex>qgtieqog</thraex>                  |      1.0000     |
| 107 | <thraex>Xecqbtqc</thraex>                  |      1.0000     |
| 108 | <thraex>MOmEROYJOUEQAlFQ</thraex>          |      1.0000     |
| 109 | <thraex>Riqbr</thraex>                     |      1.0000     |
| 110 | <thraex>Ctq</thraex>                       |      1.0000     |
| 111 | <thraex>Daetrw</thraex>                    |      1.0000     |
| 112 | <thraex>\~BAREFmQ\`DB</thraex>               |      1.0000     |
| 113 | <thraex>IMUOALU</thraex>                   |      1.0000     |
| 114 | <thraex>mjwg</thraex>                      |      1.0000     |
| 115 | <thraex>btotk</thraex>                     |      1.0000     |
| 116 | <thraex>Eoqrègit</thraex>                  |      1.0000     |
| 117 | <thraex>ohqtk\~qbr</thraex>                 |      1.0000     |
| 118 | <thraex>hbgnèib\`q</thraex>                 |      1.0000     |
| 119 | <thraex>Qicwtrg</thraex>                   |      1.0000     |
| 120 | <thraex>Zofhgi</thraex>                    |      1.0000     |
| 121 | <thraex>Tqj</thraex>                       |      1.0000     |
| 122 | <thraex>Xocbj</thraex>                     |      1.0000     |
| 123 | <thraex>Iqite</thraex>                     |      1.0000     |
| 124 | <thraex>Dghbt</thraex>                     |      1.0000     |
| 125 | <thraex>Qtijq</thraex>                     |      1.0000     |
| 126 | <thraex>Bwgib</thraex>                     |      1.0000     |
| 127 | <thraex>\`Rbker</thraex>                    |      1.0000     |
| 128 | <thraex>gaitqhow</thraex>                  |      1.0000     |
| 129 | <thraex>Jfwtwa</thraex>                    |      1.0000     |
| 130 | <thraex>VN\~sEVE</thraex>                   |      1.0000     |
| 131 | <thraex>Ctbgewof</thraex>                  |      1.0000     |
| 132 | <thraex>Oawcortach</thraex>                |      1.0000     |
| 133 | <thraex>Sbrrec</thraex>                    |      1.0000     |
| 134 | <thraex>ibfh</thraex>                      |      1.0000     |
| 135 | <thraex>loqa\`q</thraex>                    |      1.0000     |
| 136 | <thraex>HQD</thraex>                       |      1.0000     |
| 137 | <thraex>XsZI</thraex>                      |      1.0000     |
| 138 | <thraex>swqca</thraex>                     |      1.0000     |
| 139 | <thraex>Xcjq</thraex>                      |      1.0000     |
| 140 | <thraex>fea</thraex>                       |      1.0000     |
| 141 | <thraex>Cw</thraex>                        |      1.0000     |
| 142 | <thraex>Vqciapje</thraex>                  |      1.0000     |
| 143 | <thraex>Aqroj</thraex>                     |      1.0000     |
| 144 | <thraex>Dfcbp</thraex>                     |      1.0000     |
| 145 | <thraex>XCNSsJ</thraex>                    |      1.0000     |
| 146 | <thraex>GCACUJZsF</thraex>                 |      1.0000     |
| 147 | <thraex>Riwcr</thraex>                     |      1.0000     |
| 148 | <thraex>Ctp</thraex>                       |      1.0000     |
| 149 | <thraex>NQTSLOZ</thraex>                   |      1.0000     |
| 150 | <thraex>BrFF</thraex>                      |      1.0000     |
| 151 | <thraex>GAFAZ</thraex>                     |      1.0000     |
| 152 | <thraex>UEBMCJ</thraex>                    |      1.0000     |
| 153 | <thraex>VJSSQE</thraex>                    |      1.0000     |
| 154 | <thraex>RsTY</thraex>                      |      1.0000     |
| 155 | <thraex>HBYUSMV</thraex>                   |      1.0000     |
| 156 | <thraex>LXVSgT</thraex>                    |      1.0000     |
| 157 | <thraex>QLRO</thraex>                      |      1.0000     |
| 158 | <thraex>UMTRhoO</thraex>                   |      1.0000     |
| 159 | <thraex>bokq</thraex>                      |      1.0000     |
| 160 | <thraex>swqba</thraex>                     |      1.0000     |
| 161 | <thraex>Fk</thraex>                        |      1.0000     |
| 162 | <thraex>PYC</thraex>                       |      1.0000     |
| 163 | <thraex>PBCZ</thraex>                      |      1.0000     |
| 164 | <thraex>VwZLQR</thraex>                    |      1.0000     |
| 165 | <thraex>HTOW</thraex>                      |      1.0000     |
| 166 | <thraex>BQFDEB</thraex>                    |      1.0000     |
| 167 | <thraex>Mncgaw</thraex>                    |      1.0000     |
| 168 | <thraex>ehqajq</thraex>                    |      1.0000     |
| 169 | <thraex>aogor</thraex>                     |      1.0000     |
| 170 | <thraex>Bchqag</thraex>                    |      1.0000     |
| 171 | <thraex>TYCR</thraex>                      |      1.0000     |
| 172 | <thraex>PHVHOPsN</thraex>                  |      1.0000     |
| 173 | <thraex>QLREBLFJHT</thraex>                |      1.0000     |
| 174 | <thraex>brn\`qa</thraex>                    |      1.0000     |
| 175 | <thraex>o\`qobètkf</thraex>                 |      1.0000     |
| 176 | <thraex>bna</thraex>                       |      1.0000     |
| 177 | <thraex>Uohteri</thraex>                   |      1.0000     |
| 178 | <thraex>\~Bgc</thraex>                      |      1.0000     |
| 179 | <thraex>Mrtwbè</thraex>                    |      1.0000     |
| 180 | <thraex>Htk</thraex>                       |      1.0000     |
| 181 | <thraex>\`qtg</thraex>                      |      1.0000     |
| 182 | <thraex>Yfq</thraex>                       |      1.0000     |
| 183 | <thraex>j\`qwfe</thraex>                    |      1.0000     |
| 184 | <thraex>QoQog</thraex>                     |      1.0000     |
| 185 | <thraex>Jgbt</thraex>                      |      1.0000     |
| 186 | <thraex>bpkq</thraex>                      |      1.0000     |
| 187 | <thraex>Jtwh</thraex>                      |      1.0000     |
| 188 | <thraex>JBOM</thraex>                      |      1.0000     |
| 189 | <thraex>Btah</thraex>                      |      1.0000     |
| 190 | <thraex>Vqciaqje</thraex>                  |      1.0000     |
| 191 | <thraex>DMS</thraex>                       |      1.0000     |
| 192 | <thraex>\`RbkeA</thraex>                    |      1.0000     |
