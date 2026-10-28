# Raw profile of the 63 sheets that touch Aomori (whole sheets, before any cutting)

Source: G空間情報センター dataset `mesh_10` (全国森林資源メッシュ, zone X), sheets chosen by intersecting the sheet index with the Aomori boundary (KSJ N03). Run 2026-10-29; sha256 of each archive is in data/raw/20261029/MANIFEST.json (kept in the Hugging Face repo).

These counts cover the whole sheets, so they include cells of neighbouring prefectures and of the sea. The Aomori-only figures are in docs/aomori_profile.md.

- sheets: 63; rows: 29,837,059; layers: 63 geometry layers, one per file, named like the file; geometry type ids: {6: 29837059} (6 = MultiPolygon); invalid geometries: 0
- CRS: EPSG:6678; plane bbox x -113180 to 80000, y 15000 to 172800
- column sets: 1 distinct (林種, 森林簿樹種1, 森林簿樹種2, 森林簿樹種3, 林齢, 森林簿年月日, 樹冠高, レーザ解析樹種, 立木密度, 平均標高, 計測年月日, plus the GeoPackage fid)

| column | NULL rows | share of rows |
| --- | ---: | ---: |
| 林種 | 8,368,077 | 28.0% |
| 森林簿樹種1 | 8,363,528 | 28.0% |
| 森林簿樹種2 | 19,918,377 | 66.8% |
| 森林簿樹種3 | 25,829,732 | 86.6% |
| 林齢 | 8,368,077 | 28.0% |
| 森林簿年月日 | 8,363,423 | 28.0% |
| 樹冠高 | 29,837,059 | 100.0% |
| レーザ解析樹種 | 29,837,059 | 100.0% |
| 立木密度 | 29,837,059 | 100.0% |
| 平均標高 | 29,837,059 | 100.0% |
| 計測年月日 | 29,837,059 | 100.0% |

## Unique values of the text columns (all 63 sheets)

### 林種

| value | rows |
| --- | ---: |
| 天然林 | 11,436,207 |
| 人工林 | 9,248,495 |
| <NULL> | 8,368,077 |
| その他 | 395,577 |
| 伐採跡地 | 301,628 |
| 未立木地 | 87,075 |

### 森林簿樹種1

| value | rows |
| --- | ---: |
| 広葉樹 | 9,101,684 |
| <NULL> | 8,363,528 |
| スギ | 6,876,879 |
| マツ類 | 2,038,510 |
| ヒバ | 1,648,307 |
| カラマツ | 854,039 |
| その他 | 468,248 |
| 伐採跡地 | 289,269 |
| その他針葉樹 | 175,489 |
| #N/A | 15,597 |
| ヒノキ類 | 5,437 |
| エゾマツ | 72 |

### 森林簿樹種2

| value | rows |
| --- | ---: |
| <NULL> | 19,918,377 |
| 広葉樹 | 7,647,008 |
| マツ類 | 682,636 |
| ヒバ | 613,058 |
| スギ | 559,852 |
| カラマツ | 387,927 |
| その他針葉樹 | 24,652 |
| ヒノキ類 | 3,481 |
| エゾマツ | 68 |

### 森林簿樹種3

| value | rows |
| --- | ---: |
| <NULL> | 25,829,732 |
| 広葉樹 | 3,016,172 |
| ヒバ | 488,812 |
| マツ類 | 203,510 |
| スギ | 169,917 |
| その他針葉樹 | 66,073 |
| カラマツ | 60,868 |
| ヒノキ類 | 1,975 |

### レーザ解析樹種

| value | rows |
| --- | ---: |
| <NULL> | 29,837,059 |

### 森林簿年月日

| value | rows |
| --- | ---: |
| <NULL> | 8,363,423 |
| 2023/4/1 | 7,647,015 |
| 2022/4/1 | 4,049,455 |
| 2024/4/1 | 2,702,377 |
| 2019/4/1 | 2,511,709 |
| 2020/4/1 | 2,023,405 |
| 2021/4/1 | 1,728,650 |
| 2024/3/31 | 811,025 |

## Other findings

- 計測年月日 values other than NULL: {}
- The literal text `#N/A` as a value: 森林簿樹種1 15,597 rows, 森林簿樹種2 0 rows; kept as in the source.
- 林齢 is 0 in 768,092 rows besides the NULLs (8,368,077); whether 0 means an age of zero or an unknown age is not stated in the definition.
- 森林簿年月日 holds 7 dates, as text: 2019/4/1, 2020/4/1, 2021/4/1, 2022/4/1, 2023/4/1, 2024/3/31, 2024/4/1.
- No column separates 国有林 from 民有林 in the mesh; that attribute (民国別) is in the 森林計画対象森林レイヤ of Aomori (downloaded as well).
