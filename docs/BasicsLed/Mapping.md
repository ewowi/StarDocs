---
title: Mapping
hide:
  # - navigation
  # - toc
---

## Mapping

Text

## Dev

### Mapping table
(LedFixture.cpp - projectAndMap)

Example mapping 1D effect to Rings241 (in2out, 9 rings) with distance from point (0,0)

```
ledV 2 mapping: #ledsP (2): 218 219
ledV 3 mapping: #ledsP (3): 162 164 217 220
ledV 4 mapping: #ledsP (4): 118 161 163 165 215 216 221 222
ledV 5 mapping: #ledsP (5): 80 81 82 116 117 119 120 160 166 214 223
ledV 6 mapping: #ledsP (6): 79 83 115 121 159 167 213 224
ledV 7 mapping: #ledsP (7): 31 51 52 53 78 84 114 122 158 168 212 225
ledV 8 mapping: #ledsP (8): 30 32 49 50 54 55 77 85 113 123 157 169 211 226
ledV 9 mapping: #ledsP (9): 6 16 17 29 33 48 56 76 86 112 124 156 170 210 227
ledV 10 mapping: #ledsP (10): 5 7 14 15 18 19 28 34 47 57 75 87 111 125 155 171 208 209 228 229
ledV 11 mapping: #ledsP (11): 0 4 8 27 35 74 88 110 126 153 154 172 173 207 230
ledV 12 mapping: #ledsP (12): 1 2 3 9 12 13 20 46 58 73 89 108 109 127 128 152 174 206 231
ledV 13 mapping: #ledsP (13): 10 11 21 25 26 36 44 45 59 60 72 90 106 107 129 130 151 175 204 205 232 233
ledV 14 mapping: #ledsP (14): 22 23 24 37 43 70 71 91 92 149 150 176 177 203 234
ledV 15 mapping: #ledsP (15): 38 39 40 41 42 61 62 68 69 104 105 131 132 148 178 200 201 202 235 236 237
ledV 16 mapping: #ledsP (16): 63 64 65 66 67 93 94 98 102 103 146 147 179 180 199 238
ledV 17 mapping: #ledsP (17): 95 96 97 99 100 101 133 134 137 141 144 145 181 196 197 198 239 240
ledV 18 mapping: #ledsP (18): 135 136 138 139 140 142 143 182 183 184 185 192 193 194 195
ledV 19 mapping: #ledsP (19): 186 187 188 189 190 191

projectAndMap [0] V:25 x 1 x 1 -> 20 (v:20 - p:241)

projectAndMap P:18x18x1 -> 241

```

* 1D effect will have a led count of 20 (0..19): virtual leds
* each virtual led is mapped to a number of physical leds. See above: some have 0 phyisical leds, some have more: this results in circles. In total physical 241 leds are mapped
* temporary: virtual leds without a mapping to physical leds are mapped here to led 0. This is a temporary workaround (and as a consequence 252 instead of 241 leds are mapped)
* the mapping table is implemented as: 

```
std::vector<std::vector<unsigned16>> mappingTable;
```

<video width="248" autoplay><source src="https://github.com/ewowi/StarDocs/assets/1737159/637588d2-0f38-46ba-b765-a37acf5fd385" type="video/mp4"></video>
