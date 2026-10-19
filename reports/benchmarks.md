# Benchmark Report

> Generated on 2026-10-19 at 12:11:01 UTC
>
> System: linux | AMD EPYC 7763 64-Core Processor (4 cores) | 16GB RAM | Bun 1.4.3
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
| libpdf          |    52.2 |  19.15ms |  24.54ms | ±3.61% |      27 |
| @cantoo/pdf-lib |     4.6 | 218.88ms | 245.10ms | ±3.47% |      10 |
| pdf-lib         |     4.6 | 219.37ms | 229.56ms | ±1.29% |      10 |

- **libpdf** is 11.43x faster than @cantoo/pdf-lib
- **libpdf** is 11.46x faster than pdf-lib

### Create blank PDF

| Benchmark       | ops/sec |  Mean |    p99 |    RME | Samples |
| :-------------- | ------: | ----: | -----: | -----: | ------: |
| libpdf          |   12.4K |  80us |  184us | ±3.25% |   6,223 |
| pdf-lib         |    2.6K | 385us | 1.56ms | ±3.59% |   1,300 |
| @cantoo/pdf-lib |    2.2K | 461us | 1.82ms | ±3.10% |   1,085 |

- **libpdf** is 4.79x faster than pdf-lib
- **libpdf** is 5.74x faster than @cantoo/pdf-lib

### Add 10 pages

| Benchmark       | ops/sec |  Mean |    p99 |    RME | Samples |
| :-------------- | ------: | ----: | -----: | -----: | ------: |
| libpdf          |    8.0K | 126us |  237us | ±1.39% |   3,979 |
| @cantoo/pdf-lib |    2.1K | 471us | 2.96ms | ±4.96% |   1,061 |
| pdf-lib         |    2.1K | 477us | 2.38ms | ±4.55% |   1,049 |

- **libpdf** is 3.75x faster than @cantoo/pdf-lib
- **libpdf** is 3.79x faster than pdf-lib

### Draw 50 rectangles

| Benchmark       | ops/sec |   Mean |    p99 |    RME | Samples |
| :-------------- | ------: | -----: | -----: | -----: | ------: |
| libpdf          |    2.7K |  366us | 1.14ms | ±1.98% |   1,365 |
| pdf-lib         |   697.7 | 1.43ms | 6.57ms | ±7.66% |     349 |
| @cantoo/pdf-lib |   606.6 | 1.65ms | 4.63ms | ±6.20% |     304 |

- **libpdf** is 3.91x faster than pdf-lib
- **libpdf** is 4.50x faster than @cantoo/pdf-lib

### Load and save PDF

| Benchmark       | ops/sec |     Mean |      p99 |    RME | Samples |
| :-------------- | ------: | -------: | -------: | -----: | ------: |
| libpdf          |    51.8 |  19.29ms |  28.45ms | ±4.71% |      26 |
| pdf-lib         |     3.1 | 322.65ms | 332.18ms | ±1.00% |      10 |
| @cantoo/pdf-lib |     1.9 | 530.85ms | 547.95ms | ±1.16% |      10 |

- **libpdf** is 16.72x faster than pdf-lib
- **libpdf** is 27.51x faster than @cantoo/pdf-lib

### Load, modify, and save PDF

| Benchmark       | ops/sec |     Mean |      p99 |    RME | Samples |
| :-------------- | ------: | -------: | -------: | -----: | ------: |
| pdf-lib         |     3.2 | 315.11ms | 329.53ms | ±1.38% |      10 |
| libpdf          |     2.9 | 339.34ms | 353.57ms | ±1.17% |      10 |
| @cantoo/pdf-lib |     1.9 | 529.01ms | 554.70ms | ±1.44% |      10 |

- **pdf-lib** is 1.08x faster than libpdf
- **pdf-lib** is 1.68x faster than @cantoo/pdf-lib

### Extract single page from 100-page PDF

| Benchmark       | ops/sec |   Mean |     p99 |    RME | Samples |
| :-------------- | ------: | -----: | ------: | -----: | ------: |
| libpdf          |   275.9 | 3.62ms |  4.57ms | ±1.09% |     138 |
| pdf-lib         |   111.4 | 8.98ms | 11.29ms | ±2.22% |      56 |
| @cantoo/pdf-lib |   108.7 | 9.20ms | 11.05ms | ±1.97% |      55 |

- **libpdf** is 2.48x faster than pdf-lib
- **libpdf** is 2.54x faster than @cantoo/pdf-lib

### Split 100-page PDF into single-page PDFs

| Benchmark       | ops/sec |    Mean |     p99 |    RME | Samples |
| :-------------- | ------: | ------: | ------: | -----: | ------: |
| libpdf          |    24.9 | 40.09ms | 44.75ms | ±2.30% |      13 |
| pdf-lib         |    13.6 | 73.34ms | 78.74ms | ±4.06% |       7 |
| @cantoo/pdf-lib |    12.7 | 78.96ms | 95.53ms | ±9.03% |       7 |

- **libpdf** is 1.83x faster than pdf-lib
- **libpdf** is 1.97x faster than @cantoo/pdf-lib

### Split 2000-page PDF into single-page PDFs (0.9MB)

| Benchmark       | ops/sec |     Mean |      p99 |    RME | Samples |
| :-------------- | ------: | -------: | -------: | -----: | ------: |
| libpdf          |     1.3 | 751.41ms | 751.41ms | ±0.00% |       1 |
| pdf-lib         |   0.754 |    1.33s |    1.33s | ±0.00% |       1 |
| @cantoo/pdf-lib |   0.694 |    1.44s |    1.44s | ±0.00% |       1 |

- **libpdf** is 1.77x faster than pdf-lib
- **libpdf** is 1.92x faster than @cantoo/pdf-lib

### Copy 10 pages between documents

| Benchmark       | ops/sec |    Mean |     p99 |    RME | Samples |
| :-------------- | ------: | ------: | ------: | -----: | ------: |
| libpdf          |   216.0 |  4.63ms |  5.51ms | ±1.28% |     108 |
| pdf-lib         |    87.1 | 11.48ms | 12.47ms | ±1.32% |      44 |
| @cantoo/pdf-lib |    72.9 | 13.72ms | 22.29ms | ±4.26% |      37 |

- **libpdf** is 2.48x faster than pdf-lib
- **libpdf** is 2.96x faster than @cantoo/pdf-lib

### Merge 2 x 100-page PDFs

| Benchmark       | ops/sec |    Mean |     p99 |    RME | Samples |
| :-------------- | ------: | ------: | ------: | -----: | ------: |
| libpdf          |    64.0 | 15.64ms | 17.33ms | ±1.42% |      32 |
| pdf-lib         |    18.9 | 52.80ms | 53.65ms | ±0.83% |      10 |
| @cantoo/pdf-lib |    15.7 | 63.62ms | 64.74ms | ±0.98% |       8 |

- **libpdf** is 3.38x faster than pdf-lib
- **libpdf** is 4.07x faster than @cantoo/pdf-lib

### Fill FINTRAC form fields

| Benchmark       | ops/sec |    Mean |     p99 |    RME | Samples |
| :-------------- | ------: | ------: | ------: | -----: | ------: |
| libpdf          |    48.2 | 20.75ms | 25.98ms | ±3.83% |      25 |
| pdf-lib         |    36.4 | 27.46ms | 35.97ms | ±4.69% |      19 |
| @cantoo/pdf-lib |    35.7 | 27.99ms | 44.42ms | ±7.82% |      18 |

- **libpdf** is 1.32x faster than pdf-lib
- **libpdf** is 1.35x faster than @cantoo/pdf-lib

### Fill and flatten FINTRAC form

| Benchmark       | ops/sec |    Mean |     p99 |    RME | Samples |
| :-------------- | ------: | ------: | ------: | -----: | ------: |
| libpdf          |    56.2 | 17.80ms | 23.21ms | ±3.48% |      29 |
| pdf-lib         |  FAILED |       - |       - |      - |       0 |
| @cantoo/pdf-lib |    32.7 | 30.53ms | 35.56ms | ±3.18% |      17 |

- **libpdf** is 1.72x faster than @cantoo/pdf-lib

## Copying

### Copy pages between documents

| Benchmark                       | ops/sec |   Mean |    p99 |    RME | Samples |
| :------------------------------ | ------: | -----: | -----: | -----: | ------: |
| copy 1 page                     |   903.0 | 1.11ms | 2.18ms | ±2.37% |     452 |
| copy 10 pages from 100-page PDF |   220.9 | 4.53ms | 5.20ms | ±1.02% |     111 |
| copy all 100 pages              |   128.5 | 7.78ms | 9.33ms | ±1.28% |      65 |

- **copy 1 page** is 4.09x faster than copy 10 pages from 100-page PDF
- **copy 1 page** is 7.03x faster than copy all 100 pages

### Duplicate pages within same document

| Benchmark                                 | ops/sec |   Mean |    p99 |    RME | Samples |
| :---------------------------------------- | ------: | -----: | -----: | -----: | ------: |
| duplicate page 0                          |   999.6 | 1.00ms | 1.47ms | ±0.85% |     500 |
| duplicate all pages (double the document) |   997.3 | 1.00ms | 1.46ms | ±0.81% |     499 |

- **duplicate page 0** is 1.00x faster than duplicate all pages (double the document)

### Merge PDFs

| Benchmark               | ops/sec |    Mean |     p99 |    RME | Samples |
| :---------------------- | ------: | ------: | ------: | -----: | ------: |
| merge 2 small PDFs      |   643.3 |  1.55ms |  2.06ms | ±1.21% |     322 |
| merge 10 small PDFs     |   126.4 |  7.91ms | 10.41ms | ±1.34% |      64 |
| merge 2 x 100-page PDFs |    67.4 | 14.84ms | 18.29ms | ±2.62% |      34 |

- **merge 2 small PDFs** is 5.09x faster than merge 10 small PDFs
- **merge 2 small PDFs** is 9.54x faster than merge 2 x 100-page PDFs

## Drawing

| Benchmark                           | ops/sec |   Mean |    p99 |    RME | Samples |
| :---------------------------------- | ------: | -----: | -----: | -----: | ------: |
| draw 100 lines                      |    1.8K |  558us | 1.19ms | ±1.31% |     896 |
| draw 100 rectangles                 |    1.6K |  624us | 1.33ms | ±1.85% |     801 |
| draw 100 circles                    |    1.1K |  932us | 1.81ms | ±1.61% |     537 |
| create 10 pages with mixed content  |   675.5 | 1.48ms | 2.71ms | ±2.26% |     338 |
| draw 100 text lines (standard font) |   601.2 | 1.66ms | 3.04ms | ±2.17% |     301 |

- **draw 100 lines** is 1.12x faster than draw 100 rectangles
- **draw 100 lines** is 1.67x faster than draw 100 circles
- **draw 100 lines** is 2.65x faster than create 10 pages with mixed content
- **draw 100 lines** is 2.98x faster than draw 100 text lines (standard font)

## Forms

| Benchmark         | ops/sec |    Mean |     p99 |    RME | Samples |
| :---------------- | ------: | ------: | ------: | -----: | ------: |
| read field values |   341.8 |  2.93ms |  5.37ms | ±2.44% |     171 |
| get form fields   |   306.8 |  3.26ms |  5.97ms | ±3.49% |     154 |
| flatten form      |   124.5 |  8.03ms | 11.01ms | ±1.61% |      63 |
| fill text fields  |    76.4 | 13.09ms | 23.96ms | ±5.66% |      39 |

- **read field values** is 1.11x faster than get form fields
- **read field values** is 2.74x faster than flatten form
- **read field values** is 4.47x faster than fill text fields

## Loading

| Benchmark              | ops/sec |    Mean |     p99 |    RME | Samples |
| :--------------------- | ------: | ------: | ------: | -----: | ------: |
| load small PDF (888B)  |   16.2K |    62us |   173us | ±1.73% |   8,080 |
| load medium PDF (19KB) |   11.2K |    89us |   118us | ±0.59% |   5,619 |
| load form PDF (116KB)  |   808.7 |  1.24ms |  1.93ms | ±1.18% |     405 |
| load heavy PDF (2.0MB) |    55.7 | 17.96ms | 19.26ms | ±1.46% |      28 |

- **load small PDF (888B)** is 1.44x faster than load medium PDF (19KB)
- **load small PDF (888B)** is 19.98x faster than load form PDF (116KB)
- **load small PDF (888B)** is 290.20x faster than load heavy PDF (2.0MB)

## Saving

| Benchmark                          | ops/sec |    Mean |     p99 |    RME | Samples |
| :--------------------------------- | ------: | ------: | ------: | -----: | ------: |
| save unmodified (19KB)             |    9.0K |   111us |   291us | ±1.48% |   4,501 |
| incremental save (19KB)            |    6.2K |   160us |   334us | ±1.02% |   3,117 |
| save with modifications (19KB)     |    1.2K |   835us |  1.53ms | ±1.55% |     599 |
| save heavy PDF (2.0MB)             |    56.0 | 17.85ms | 21.68ms | ±1.96% |      29 |
| incremental save heavy PDF (2.0MB) |    54.0 | 18.53ms | 19.48ms | ±1.42% |      27 |

- **save unmodified (19KB)** is 1.44x faster than incremental save (19KB)
- **save unmodified (19KB)** is 7.52x faster than save with modifications (19KB)
- **save unmodified (19KB)** is 160.70x faster than save heavy PDF (2.0MB)
- **save unmodified (19KB)** is 166.78x faster than incremental save heavy PDF (2.0MB)

## Splitting

### Extract single page

| Benchmark                                | ops/sec |    Mean |     p99 |    RME | Samples |
| :--------------------------------------- | ------: | ------: | ------: | -----: | ------: |
| extractPages (1 page from small PDF)     |   845.0 |  1.18ms |  2.80ms | ±3.36% |     423 |
| extractPages (1 page from 100-page PDF)  |   279.6 |  3.58ms |  4.20ms | ±1.22% |     140 |
| extractPages (1 page from 2000-page PDF) |    18.1 | 55.14ms | 55.63ms | ±0.63% |      10 |

- **extractPages (1 page from small PDF)** is 3.02x faster than extractPages (1 page from 100-page PDF)
- **extractPages (1 page from small PDF)** is 46.59x faster than extractPages (1 page from 2000-page PDF)

### Split into single-page PDFs

| Benchmark                   | ops/sec |     Mean |      p99 |    RME | Samples |
| :-------------------------- | ------: | -------: | -------: | -----: | ------: |
| split 100-page PDF (0.1MB)  |    23.7 |  42.20ms |  47.02ms | ±3.55% |      12 |
| split 2000-page PDF (0.9MB) |     1.4 | 736.90ms | 736.90ms | ±0.00% |       1 |

- **split 100-page PDF (0.1MB)** is 17.46x faster than split 2000-page PDF (0.9MB)

### Batch page extraction

| Benchmark                                              | ops/sec |    Mean |     p99 |    RME | Samples |
| :----------------------------------------------------- | ------: | ------: | ------: | -----: | ------: |
| extract first 10 pages from 2000-page PDF              |    17.6 | 56.84ms | 59.50ms | ±1.65% |       9 |
| extract first 100 pages from 2000-page PDF             |    16.5 | 60.64ms | 61.63ms | ±1.26% |       9 |
| extract every 10th page from 2000-page PDF (200 pages) |    15.0 | 66.68ms | 68.97ms | ±1.46% |       8 |

- **extract first 10 pages from 2000-page PDF** is 1.07x faster than extract first 100 pages from 2000-page PDF
- **extract first 10 pages from 2000-page PDF** is 1.17x faster than extract every 10th page from 2000-page PDF (200 pages)

---

_Results are machine-dependent. Use for relative comparison only._
