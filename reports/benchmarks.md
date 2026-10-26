# Benchmark Report

> Generated on 2026-10-26 at 12:18:01 UTC
>
> System: linux | AMD EPYC 7763 64-Core Processor (4 cores) | 16GB RAM | Bun 1.4.4
>
> Libraries: @libpdf/core 0.5.3 (this repo), pdf-lib 1.17.1, @cantoo/pdf-lib 2.9.1

---

## Contents

- [Comparison](#comparison)
- [Copying](#copying)
- [Drawing](#drawing)
- [Forms](#forms)
- [Loading](#loading)
- [Saving](#saving)
- [Splitting](#splitting)

## Comparison

### Load PDF

| Benchmark       | ops/sec |     Mean |      p99 |    RME | Samples |
| :-------------- | ------: | -------: | -------: | -----: | ------: |
| libpdf          |    51.1 |  19.57ms |  25.64ms | ±2.97% |      26 |
| @cantoo/pdf-lib |     4.6 | 219.24ms | 220.95ms | ±0.51% |      10 |
| pdf-lib         |     4.3 | 234.65ms | 320.20ms | ±9.23% |      10 |

- **libpdf** is 11.20x faster than @cantoo/pdf-lib
- **libpdf** is 11.99x faster than pdf-lib

### Create blank PDF

| Benchmark       | ops/sec |  Mean |    p99 |    RME | Samples |
| :-------------- | ------: | ----: | -----: | -----: | ------: |
| libpdf          |   13.4K |  74us |  164us | ±2.31% |   6,715 |
| pdf-lib         |    2.8K | 354us | 1.48ms | ±2.77% |   1,414 |
| @cantoo/pdf-lib |    2.5K | 406us | 1.94ms | ±3.68% |   1,232 |

- **libpdf** is 4.75x faster than pdf-lib
- **libpdf** is 5.45x faster than @cantoo/pdf-lib

### Add 10 pages

| Benchmark       | ops/sec |  Mean |    p99 |    RME | Samples |
| :-------------- | ------: | ----: | -----: | -----: | ------: |
| libpdf          |    8.0K | 125us |  195us | ±1.35% |   3,993 |
| @cantoo/pdf-lib |    2.2K | 462us | 2.41ms | ±5.09% |   1,082 |
| pdf-lib         |    2.0K | 490us | 2.19ms | ±5.31% |   1,021 |

- **libpdf** is 3.69x faster than @cantoo/pdf-lib
- **libpdf** is 3.91x faster than pdf-lib

### Draw 50 rectangles

| Benchmark       | ops/sec |   Mean |    p99 |    RME | Samples |
| :-------------- | ------: | -----: | -----: | -----: | ------: |
| libpdf          |    2.8K |  362us |  946us | ±1.56% |   1,382 |
| pdf-lib         |   577.8 | 1.73ms | 7.99ms | ±8.61% |     289 |
| @cantoo/pdf-lib |   566.7 | 1.76ms | 5.85ms | ±6.32% |     284 |

- **libpdf** is 4.78x faster than pdf-lib
- **libpdf** is 4.87x faster than @cantoo/pdf-lib

### Load and save PDF

| Benchmark       | ops/sec |     Mean |      p99 |    RME | Samples |
| :-------------- | ------: | -------: | -------: | -----: | ------: |
| libpdf          |    49.2 |  20.32ms |  29.84ms | ±5.03% |      25 |
| pdf-lib         |     3.2 | 316.29ms | 330.76ms | ±1.48% |      10 |
| @cantoo/pdf-lib |     1.6 | 610.77ms | 629.44ms | ±1.01% |      10 |

- **libpdf** is 15.57x faster than pdf-lib
- **libpdf** is 30.06x faster than @cantoo/pdf-lib

### Load, modify, and save PDF

| Benchmark       | ops/sec |     Mean |      p99 |    RME | Samples |
| :-------------- | ------: | -------: | -------: | -----: | ------: |
| pdf-lib         |     3.2 | 312.97ms | 329.84ms | ±1.50% |      10 |
| libpdf          |     2.9 | 341.00ms | 357.99ms | ±2.23% |      10 |
| @cantoo/pdf-lib |     1.7 | 606.06ms | 626.62ms | ±1.19% |      10 |

- **pdf-lib** is 1.09x faster than libpdf
- **pdf-lib** is 1.94x faster than @cantoo/pdf-lib

### Extract single page from 100-page PDF

| Benchmark       | ops/sec |   Mean |     p99 |    RME | Samples |
| :-------------- | ------: | -----: | ------: | -----: | ------: |
| libpdf          |   276.2 | 3.62ms |  4.36ms | ±1.03% |     139 |
| pdf-lib         |   110.9 | 9.02ms | 13.09ms | ±2.65% |      56 |
| @cantoo/pdf-lib |   101.1 | 9.90ms | 15.44ms | ±3.33% |      51 |

- **libpdf** is 2.49x faster than pdf-lib
- **libpdf** is 2.73x faster than @cantoo/pdf-lib

### Split 100-page PDF into single-page PDFs

| Benchmark       | ops/sec |    Mean |     p99 |    RME | Samples |
| :-------------- | ------: | ------: | ------: | -----: | ------: |
| libpdf          |    25.3 | 39.45ms | 42.75ms | ±1.68% |      13 |
| pdf-lib         |    13.8 | 72.62ms | 75.72ms | ±2.69% |       7 |
| @cantoo/pdf-lib |    13.1 | 76.21ms | 79.65ms | ±2.88% |       7 |

- **libpdf** is 1.84x faster than pdf-lib
- **libpdf** is 1.93x faster than @cantoo/pdf-lib

### Split 2000-page PDF into single-page PDFs (0.9MB)

| Benchmark       | ops/sec |     Mean |      p99 |    RME | Samples |
| :-------------- | ------: | -------: | -------: | -----: | ------: |
| libpdf          |     1.3 | 743.79ms | 743.79ms | ±0.00% |       1 |
| pdf-lib         |   0.745 |    1.34s |    1.34s | ±0.00% |       1 |
| @cantoo/pdf-lib |   0.674 |    1.48s |    1.48s | ±0.00% |       1 |

- **libpdf** is 1.80x faster than pdf-lib
- **libpdf** is 2.00x faster than @cantoo/pdf-lib

### Copy 10 pages between documents

| Benchmark       | ops/sec |    Mean |     p99 |    RME | Samples |
| :-------------- | ------: | ------: | ------: | -----: | ------: |
| libpdf          |   219.6 |  4.55ms |  5.23ms | ±0.81% |     110 |
| pdf-lib         |    86.3 | 11.59ms | 13.02ms | ±1.51% |      44 |
| @cantoo/pdf-lib |    77.3 | 12.93ms | 14.51ms | ±1.44% |      39 |

- **libpdf** is 2.55x faster than pdf-lib
- **libpdf** is 2.84x faster than @cantoo/pdf-lib

### Merge 2 x 100-page PDFs

| Benchmark       | ops/sec |    Mean |     p99 |    RME | Samples |
| :-------------- | ------: | ------: | ------: | -----: | ------: |
| libpdf          |    64.9 | 15.42ms | 18.31ms | ±2.03% |      33 |
| pdf-lib         |    19.0 | 52.59ms | 54.45ms | ±1.35% |      10 |
| @cantoo/pdf-lib |    15.8 | 63.36ms | 64.83ms | ±1.16% |       8 |

- **libpdf** is 3.41x faster than pdf-lib
- **libpdf** is 4.11x faster than @cantoo/pdf-lib

### Fill FINTRAC form fields

| Benchmark       | ops/sec |    Mean |     p99 |    RME | Samples |
| :-------------- | ------: | ------: | ------: | -----: | ------: |
| libpdf          |    47.8 | 20.94ms | 25.86ms | ±4.16% |      24 |
| pdf-lib         |    35.9 | 27.88ms | 36.82ms | ±4.81% |      18 |
| @cantoo/pdf-lib |    35.8 | 27.92ms | 37.33ms | ±5.03% |      18 |

- **libpdf** is 1.33x faster than pdf-lib
- **libpdf** is 1.33x faster than @cantoo/pdf-lib

### Fill and flatten FINTRAC form

| Benchmark       | ops/sec |    Mean |     p99 |    RME | Samples |
| :-------------- | ------: | ------: | ------: | -----: | ------: |
| libpdf          |    57.2 | 17.48ms | 21.60ms | ±2.97% |      29 |
| pdf-lib         |  FAILED |       - |       - |      - |       0 |
| @cantoo/pdf-lib |    32.3 | 30.92ms | 48.55ms | ±7.70% |      17 |

- **libpdf** is 1.77x faster than @cantoo/pdf-lib

## Copying

### Copy pages between documents

| Benchmark                       | ops/sec |   Mean |     p99 |    RME | Samples |
| :------------------------------ | ------: | -----: | ------: | -----: | ------: |
| copy 1 page                     |   872.5 | 1.15ms |  2.73ms | ±3.41% |     437 |
| copy 10 pages from 100-page PDF |   215.1 | 4.65ms |  5.66ms | ±1.99% |     108 |
| copy all 100 pages              |   123.9 | 8.07ms | 12.14ms | ±2.66% |      62 |

- **copy 1 page** is 4.06x faster than copy 10 pages from 100-page PDF
- **copy 1 page** is 7.04x faster than copy all 100 pages

### Duplicate pages within same document

| Benchmark                                 | ops/sec |   Mean |    p99 |    RME | Samples |
| :---------------------------------------- | ------: | -----: | -----: | -----: | ------: |
| duplicate all pages (double the document) |    1.0K |  997us | 1.31ms | ±0.58% |     502 |
| duplicate page 0                          |   972.6 | 1.03ms | 1.47ms | ±0.89% |     487 |

- **duplicate all pages (double the document)** is 1.03x faster than duplicate page 0

### Merge PDFs

| Benchmark               | ops/sec |    Mean |     p99 |    RME | Samples |
| :---------------------- | ------: | ------: | ------: | -----: | ------: |
| merge 2 small PDFs      |   640.6 |  1.56ms |  2.02ms | ±1.01% |     321 |
| merge 10 small PDFs     |   122.1 |  8.19ms | 13.66ms | ±2.97% |      62 |
| merge 2 x 100-page PDFs |    67.9 | 14.73ms | 19.13ms | ±2.04% |      34 |

- **merge 2 small PDFs** is 5.25x faster than merge 10 small PDFs
- **merge 2 small PDFs** is 9.43x faster than merge 2 x 100-page PDFs

## Drawing

| Benchmark                           | ops/sec |   Mean |    p99 |    RME | Samples |
| :---------------------------------- | ------: | -----: | -----: | -----: | ------: |
| draw 100 lines                      |    1.7K |  572us | 1.17ms | ±1.27% |     875 |
| draw 100 rectangles                 |    1.6K |  622us | 1.32ms | ±1.71% |     804 |
| draw 100 circles                    |    1.1K |  936us | 1.74ms | ±1.54% |     534 |
| create 10 pages with mixed content  |   678.4 | 1.47ms | 2.82ms | ±2.29% |     340 |
| draw 100 text lines (standard font) |   620.0 | 1.61ms | 2.77ms | ±1.62% |     310 |

- **draw 100 lines** is 1.09x faster than draw 100 rectangles
- **draw 100 lines** is 1.64x faster than draw 100 circles
- **draw 100 lines** is 2.58x faster than create 10 pages with mixed content
- **draw 100 lines** is 2.82x faster than draw 100 text lines (standard font)

## Forms

| Benchmark         | ops/sec |    Mean |     p99 |    RME | Samples |
| :---------------- | ------: | ------: | ------: | -----: | ------: |
| read field values |   345.7 |  2.89ms |  5.22ms | ±2.65% |     173 |
| get form fields   |   313.7 |  3.19ms |  5.46ms | ±2.88% |     157 |
| flatten form      |   124.9 |  8.01ms | 11.58ms | ±2.01% |      63 |
| fill text fields  |    77.4 | 12.91ms | 16.39ms | ±4.53% |      39 |

- **read field values** is 1.10x faster than get form fields
- **read field values** is 2.77x faster than flatten form
- **read field values** is 4.46x faster than fill text fields

## Loading

| Benchmark              | ops/sec |    Mean |     p99 |    RME | Samples |
| :--------------------- | ------: | ------: | ------: | -----: | ------: |
| load small PDF (888B)  |   15.7K |    64us |   181us | ±1.79% |   7,866 |
| load medium PDF (19KB) |   11.0K |    91us |   174us | ±0.60% |   5,481 |
| load form PDF (116KB)  |   796.4 |  1.26ms |  2.40ms | ±1.66% |     399 |
| load heavy PDF (2.0MB) |    57.4 | 17.41ms | 18.51ms | ±1.43% |      29 |

- **load small PDF (888B)** is 1.44x faster than load medium PDF (19KB)
- **load small PDF (888B)** is 19.75x faster than load form PDF (116KB)
- **load small PDF (888B)** is 273.92x faster than load heavy PDF (2.0MB)

## Saving

| Benchmark                          | ops/sec |    Mean |     p99 |    RME | Samples |
| :--------------------------------- | ------: | ------: | ------: | -----: | ------: |
| save unmodified (19KB)             |    8.5K |   117us |   336us | ±3.49% |   4,271 |
| incremental save (19KB)            |    5.4K |   184us |   385us | ±1.31% |   2,714 |
| save with modifications (19KB)     |    1.2K |   860us |  1.62ms | ±1.71% |     582 |
| save heavy PDF (2.0MB)             |    56.3 | 17.77ms | 20.34ms | ±1.39% |      29 |
| incremental save heavy PDF (2.0MB) |    54.7 | 18.30ms | 19.45ms | ±1.19% |      28 |

- **save unmodified (19KB)** is 1.57x faster than incremental save (19KB)
- **save unmodified (19KB)** is 7.35x faster than save with modifications (19KB)
- **save unmodified (19KB)** is 151.79x faster than save heavy PDF (2.0MB)
- **save unmodified (19KB)** is 156.28x faster than incremental save heavy PDF (2.0MB)

## Splitting

### Extract single page

| Benchmark                                | ops/sec |    Mean |     p99 |    RME | Samples |
| :--------------------------------------- | ------: | ------: | ------: | -----: | ------: |
| extractPages (1 page from small PDF)     |   893.2 |  1.12ms |  2.42ms | ±2.86% |     447 |
| extractPages (1 page from 100-page PDF)  |   279.9 |  3.57ms |  5.37ms | ±1.57% |     140 |
| extractPages (1 page from 2000-page PDF) |    17.5 | 57.02ms | 59.78ms | ±1.70% |      10 |

- **extractPages (1 page from small PDF)** is 3.19x faster than extractPages (1 page from 100-page PDF)
- **extractPages (1 page from small PDF)** is 50.93x faster than extractPages (1 page from 2000-page PDF)

### Split into single-page PDFs

| Benchmark                   | ops/sec |     Mean |      p99 |    RME | Samples |
| :-------------------------- | ------: | -------: | -------: | -----: | ------: |
| split 100-page PDF (0.1MB)  |    24.6 |  40.66ms |  43.77ms | ±1.77% |      13 |
| split 2000-page PDF (0.9MB) |     1.4 | 735.55ms | 735.55ms | ±0.00% |       1 |

- **split 100-page PDF (0.1MB)** is 18.09x faster than split 2000-page PDF (0.9MB)

### Batch page extraction

| Benchmark                                              | ops/sec |    Mean |     p99 |    RME | Samples |
| :----------------------------------------------------- | ------: | ------: | ------: | -----: | ------: |
| extract first 10 pages from 2000-page PDF              |    17.4 | 57.46ms | 58.60ms | ±0.95% |       9 |
| extract first 100 pages from 2000-page PDF             |    16.1 | 62.04ms | 65.15ms | ±2.41% |       9 |
| extract every 10th page from 2000-page PDF (200 pages) |    15.2 | 65.64ms | 66.87ms | ±0.95% |       8 |

- **extract first 10 pages from 2000-page PDF** is 1.08x faster than extract first 100 pages from 2000-page PDF
- **extract first 10 pages from 2000-page PDF** is 1.14x faster than extract every 10th page from 2000-page PDF (200 pages)

---

_Results are machine-dependent. Use for relative comparison only._
