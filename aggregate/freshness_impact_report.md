# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-05 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M+**: FRESH alert rate (18.8%) is 2.0× the overall rate (9.3%) — score distribution shift detected
🟡 **M5+**: FRESH alert rate (8.3%) is 2.5× the overall rate (3.4%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (16.7%) is 2.2× the overall rate (7.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   12.1 | 18.8% | 0.492 | 0.3 |       44 | 100.0% |  23.8% | 2.1× | 0.0% |   0.4773 |
|       OK |   25 |   37.4 | 4.0% | 0.389 | 0.0 |       25 | 100.0% |  33.3% | 8.3× | 0.0% |   0.1200 |
| DEGRADED |   45 |  120.4 | 2.2% | 0.405 | 0.0 |       45 | 0.0% |   0.0% |    - | 2.9% |   0.2444 |
|      ALL |  118 |   58.7 | 9.3% | 0.437 | 0.1 |      114 | 85.7% |  17.1% | 2.8× | 1.3% |   0.3070 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   12.1 | 8.3% | 0.488 | 0.1 |       44 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |   25 |   37.4 | 0.0% | 0.323 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   45 |  120.4 | 0.0% | 0.351 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |  118 |   58.7 | 3.4% | 0.401 | 0.0 |      114 |    - |   0.0% |    - | 0.0% |   0.0965 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   12.1 | 16.7% | 0.632 | 0.2 |       44 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |   25 |   37.4 | 4.0% | 0.541 | 0.0 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |
| DEGRADED |   45 |  120.4 | 0.0% | 0.500 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0222 |
|      ALL |  118 |   58.7 | 7.6% | 0.562 | 0.1 |      114 | 0.0% |   0.0% |    - | 4.6% |   0.0439 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |    9.7 | 33.3% | 0.606 | 0.7 |       11 | 100.0% |  20.0% | 2.2× | 0.0% |   0.4545 |
|       OK |    5 |   40.4 | 0.0% | 0.371 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.8 | 9.1% | 0.522 | 0.1 |       11 | 0.0% |   0.0% |    - | 11.1% |   0.1818 |
|      ALL |   31 |   49.1 | 19.4% | 0.538 | 0.4 |       27 | 50.0% |  14.3% | 1.9× | 5.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |    9.7 | 26.7% | 0.628 | 0.3 |       11 |    - |   0.0% |    - | 0.0% |   0.2727 |
|       OK |    5 |   40.4 | 0.0% | 0.283 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.8 | 0.0% | 0.474 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   49.1 | 12.9% | 0.518 | 0.1 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |    9.7 | 33.3% | 0.708 | 0.3 |       11 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |    5 |   40.4 | 0.0% | 0.577 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.8 | 0.0% | 0.547 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   49.1 | 16.1% | 0.630 | 0.2 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available