---
layout: default
title: requirements
nav_order: 1
parent: Component Implementation
---
{% raw %}
| FDD    | ID  | Source         | Function                                                | Line(s)                | Status    | Comment    |
|--------|-----|----------------|---------------------------------------------------------|------------------------|-----------|------------|
|        |     | .SwFileName    | .SwFuncName                                             | .SwLines               | .SwStatus | .SwComment |
| SF051A | 216 | SnsrOffsLrng.c | RstHwTq_Oper                                            | 517-548                | I         |            |
| SF051A | 217 | SnsrOffsLrng.c | GetYawRateOffs_Oper                                     | 468-471                | I         |            |
| SF051A | 214 | SnsrOffsLrng.c | GetHwAgOffs_Oper                                        | 404-407                | I         |            |
| SF051A | 215 | SnsrOffsLrng.c | SetHwAgOffs_Oper                                        | 646-664                | I         |            |
| SF051A | 212 | SnsrOffsLrng.c | GetHwTqOffs_Oper                                        | 436-439                | I         |            |
| SF051A | 213 | SnsrOffsLrng.c | SetHwTqOffs_Oper                                        | 710-746                | I         |            |
| SF051A | 210 | SnsrOffsLrng.c | SnsrOffsLrngInit1                                       | 841-963                | I         |            |
| SF051A | 211 | SnsrOffsLrng.c | RstYawAndAg_Oper                                        | 587-607                | I         |            |
| SF051A | 218 | SnsrOffsLrng.c | SetYawRateOffs_Oper                                     | 786                    | I         |            |
| SF051A | 164 | SnsrOffsLrng.c | EnableYOC_Cnt_T_logl                                    | 1711-1859              | I         |            |
| SF051A | 136 | SnsrOffsLrng.c | EnableYOC_Cnt_T_logl                                    | 1588                   | I         |            |
| SF051A | 135 | SnsrOffsLrng.c | EnableYOC_Cnt_T_logl                                    | 1588                   | I         |            |
| SF051A | 134 | SnsrOffsLrng.c | EnableYOC_Cnt_T_logl                                    | 1600                   | I         |            |
| SF051A | 139 | SnsrOffsLrng.c | LearnHwAg                                               | 1528                   | I         |            |
| SF051A | 166 | SnsrOffsLrng.c | EnableYOC_Cnt_T_logl                                    | 1732                   | I         |            |
| SF051A | 26  | SnsrOffsLrng.c | SnsrOffsLrngInit1,SnsrOffsLrngPer2,EnableYOC_Cnt_T_logl | 889-955,1292,1700-1888 | I         |            |
| SF051A | 160 | SnsrOffsLrng.c | SnsrOffsLrngPer1                                        | 1045-1050              | I         |            |
| SF051A | 28  | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1298,1318              | I         |            |
| SF051A | 29  | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1303                   | I         |            |
| SF051A | 97  | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1338                   | I         |            |
| SF051A | 163 | SnsrOffsLrng.c | SnsrOffsLrngPer1                                        | 1044                   | I         |            |
| SF051A | 120 | SnsrOffsLrng.c | LearnHwAg                                               | 1449,1464              | I         |            |
| SF051A | 122 | SnsrOffsLrng.c | LearnHwAg                                               | 1465                   | I         |            |
| SF051A | 123 | SnsrOffsLrng.c | LearnHwAg                                               | 1448                   | I         |            |
| SF051A | 125 | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1384-1401              | I         |            |
| SF051A | 126 | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1383                   | I         |            |
| SF051A | 127 | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1404                   | I         |            |
| SF051A | 58  | SnsrOffsLrng.c | SetYawRateOffs_Oper                                     | 785-797                | I         |            |
| SF051A | 195 | SnsrOffsLrng.c | SnsrOffsLrngPer1                                        | 1159-1181              | I         |            |
| SF051A | 194 | SnsrOffsLrng.c | SnsrOffsLrngPer1                                        | 1159-1181              | I         |            |
| SF051A | 191 | SnsrOffsLrng.c | SnsrOffsLrngPer1                                        | 1152                   | I         |            |
| SF051A | 190 | SnsrOffsLrng.c | KVect_Uls_T_f32                                         | 2057                   | I         |            |
| SF051A | 115 | SnsrOffsLrng.c | LearnHwAg                                               | 1477                   | I         |            |
| SF051A | 88  | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1313                   | I         |            |
| SF051A | 89  | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1307                   | I         |            |
| SF051A | 111 | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1326                   | I         |            |
| SF051A | 112 | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1326                   | I         |            |
| SF051A | 80  | SnsrOffsLrng.c | SnsrOffsLrngInit1                                       | 960                    | I         |            |
| SF051A | 81  | SnsrOffsLrng.c | SnsrOffsLrngInit1                                       | 900-931                | I         |            |
| SF051A | 86  | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1295                   | I         |            |
| SF051A | 87  | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1313                   | I         |            |
| SF051A | 165 | SnsrOffsLrng.c | EnableYOC_Cnt_T_logl                                    | 1703-1882              | I         |            |
| SF051A | 140 | SnsrOffsLrng.c | LearnHwAg                                               | 1523                   | I         |            |
| SF051A | 245 | SnsrOffsLrng.c | SnsrOffsLrngInit1                                       | 889-955                | I         |            |
| SF051A | 244 | SnsrOffsLrng.c | SnsrOffsLrngInit1                                       | 889-955                | I         |            |
| SF051A | 240 | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1364                   | I         |            |
| SF051A | 243 | SnsrOffsLrng.c | SnsrOffsLrngPer1,KVect_Uls_T_f32                        | 1081-1114,1982         | I         |            |
| SF051A | 242 | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1326                   | I         |            |
| SF051A | 106 | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1365                   | I         |            |
| SF051A | 107 | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1361                   | I         |            |
| SF051A | 104 | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1364                   | I         |            |
| SF051A | 105 | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1364                   | I         |            |
| SF051A | 32  | SnsrOffsLrng.c | EnableYOC_Cnt_T_logl                                    | 1577                   | I         |            |
| SF051A | 31  | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1324                   | I         |            |
| SF051A | 60  | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1372                   | I         |            |
| SF051A | 178 | SnsrOffsLrng.c | SnsrOffsLrngPer1                                        | 1074-1078              | I         |            |
| SF051A | 177 | SnsrOffsLrng.c | SnsrOffsLrngPer1                                        | 1076                   | I         |            |
| SF051A | 176 | SnsrOffsLrng.c | SnsrOffsLrngPer1                                        | 1123                   | I         |            |
| SF051A | 174 | SnsrOffsLrng.c | SnsrOffsLrngPer1,KVect_Uls_T_f32                        | 1138,2035              | I         |            |
| SF051A | 173 | SnsrOffsLrng.c | SnsrOffsLrngPer1,KVect_Uls_T_f32                        | 1138,2035              | I         |            |
| SF051A | 172 | SnsrOffsLrng.c | EnableYOC_Cnt_T_logl                                    | 1692,1700-1888         | I         |            |
| SF051A | 171 | SnsrOffsLrng.c | EnableYOC_Cnt_T_logl                                    | 1696                   | I         |            |
| SF051A | 183 | SnsrOffsLrng.c | SnsrOffsLrngPer1                                        | 1116,1123              | I         |            |
| SF051A | 180 | SnsrOffsLrng.c | SnsrOffsLrngPer1                                        | 1074-1078              | I         |            |
| SF051A | 186 | SnsrOffsLrng.c | SnsrOffsLrngPer1                                        | 1159-1181              | I         |            |
| SF051A | 187 | SnsrOffsLrng.c | SnsrOffsLrngPer1                                        | 1152                   | I         |            |
| SF051A | 188 | SnsrOffsLrng.c | SnsrOffsLrngPer1                                        | 1184                   | I         |            |
| SF051A | 98  | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1324                   | I         |            |
| SF051A | 169 | SnsrOffsLrng.c | EnableYOC_Cnt_T_logl                                    | 1693                   | I         |            |
| SF051A | 229 | SnsrOffsLrng.c | GetYawRateOffs_Oper                                     | 468-471                | I         |            |
| SF051A | 91  | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1353,1355,1364         | I         |            |
| SF051A | 90  | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1352                   | I         |            |
| SF051A | 93  | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1361                   | I         |            |
| SF051A | 95  | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1350                   | I         |            |
| SF051A | 94  | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1349                   | I         |            |
| SF051A | 162 | SnsrOffsLrng.c | SnsrOffsLrngPer1                                        | 1041                   | I         |            |
| SF051A | 96  | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1338                   | I         |            |
| SF051A | 12  | SnsrOffsLrng.c | SnsrOffsLrngPer1,SnsrOffsLrngPer2                       | 1034,1383-1401         | I         |            |
| SF051A | 16  | SnsrOffsLrng.c | SnsrOffsLrngInit1                                       | 961                    | I         |            |
| SF051A | 117 | SnsrOffsLrng.c | LearnHwAg                                               | 1465                   | I         |            |
| SF051A | 116 | SnsrOffsLrng.c | LearnHwAg                                               | 1454                   | I         |            |
| SF051A | 150 | SnsrOffsLrng.c | SnsrOffsLrngPer1                                        | 1014-1212              | I         |            |
| SF051A | 153 | SnsrOffsLrng.c | SnsrOffsLrngPer1,EnableYOC_Cnt_T_logl                   | 1069,1711-1728         | I         |            |
| SF051A | 154 | SnsrOffsLrng.c | SnsrOffsLrngPer1                                        | 1052                   | I         |            |
| SF051A | 157 | SnsrOffsLrng.c | SnsrOffsLrngPer1                                        | 1052                   | I         |            |
| SF051A | 156 | SnsrOffsLrng.c | SnsrOffsLrngPer1                                        | 1208                   | I         |            |
| SF051A | 158 | SnsrOffsLrng.c | SnsrOffsLrngPer1                                        | 1045-1050              | I         |            |
| SF051A | 238 | SnsrOffsLrng.c | SetHwTqOffs_Oper                                        | 710-746                | I         |            |
| SF051A | 234 | SnsrOffsLrng.c | RstYawAndAg_Oper                                        | 587-607                | I         |            |
| SF051A | 235 | SnsrOffsLrng.c | RstHwTq_Oper                                            | 517-548                | I         |            |
| SF051A | 236 | SnsrOffsLrng.c | SetHwAgOffs_Oper                                        | 646-664                | I         |            |
| SF051A | 237 | SnsrOffsLrng.c | SetYawRateOffs_Oper                                     | 785-797                | I         |            |
| SF051A | 230 | SnsrOffsLrng.c | SetHwAgOffs_Oper                                        | 647                    | I         |            |
| SF051A | 231 | SnsrOffsLrng.c | GetHwAgOffs_Oper                                        | 404-407                | I         |            |
| SF051A | 232 | SnsrOffsLrng.c | SetHwTqOffs_Oper                                        | 711                    | I         |            |
| SF051A | 233 | SnsrOffsLrng.c | GetHwTqOffs_Oper                                        | 436-439                | I         |            |
| SF051A | 46  | SnsrOffsLrng.c | SnsrOffsLrngInit1                                       | 841,935-953            | I         |            |
| SF051A | 119 | SnsrOffsLrng.c | LearnHwAg                                               | 1464                   | I         |            |
| SF051A | 45  | SnsrOffsLrng.c | SnsrOffsLrngInit1                                       | 889-955                | I         |            |
| SF051A | 118 | SnsrOffsLrng.c | LearnHwAg                                               | 1459,1464              | I         |            |
| SF051A | 146 | SnsrOffsLrng.c | LearnHwAg                                               | 1481                   | I         |            |
| SF051A | 144 | SnsrOffsLrng.c | LearnHwAg                                               | 1489                   | I         |            |
| SF051A | 145 | SnsrOffsLrng.c | LearnHwAg                                               | 1485                   | I         |            |
| SF051A | 142 | SnsrOffsLrng.c | LearnHwAg                                               | 1497                   | I         |            |
| SF051A | 143 | SnsrOffsLrng.c | LearnHwAg                                               | 1493                   | I         |            |
| SF051A | 207 | SnsrOffsLrng.c | SnsrOffsLrngPer1                                        | 1014-1212              | I         |            |
| SF051A | 141 | SnsrOffsLrng.c | LearnHwAg                                               | 1519                   | I         |            |
| SF051A | 209 | SnsrOffsLrng.c | SnsrOffsLrngInit1                                       | 887,900-931            | I         |            |
| SF051A | 149 | SnsrOffsLrng.c | EnableYOC_Cnt_T_logl                                    | 1700-1888              | I         |            |
| SF051A | 77  | SnsrOffsLrng.c | EnableYOC_Cnt_T_logl                                    | 1565                   | I         |            |
| SF051A | 74  | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1288                   | I         |            |
| SF051A | 72  | SnsrOffsLrng.c | EnableYOC_Cnt_T_logl                                    | 1695                   | I         |            |
| SF051A | 71  | SnsrOffsLrng.c | SnsrOffsLrngPer1,EnableYOC_Cnt_T_logl                   | 1033,1697              | I         |            |
| SF051A | 79  | SnsrOffsLrng.c | SnsrOffsLrngInit1                                       | 962                    | I         |            |
| SF051A | 78  | SnsrOffsLrng.c | SnsrOffsLrngPer2                                        | 1286                   | I         |            |

{% endraw %}