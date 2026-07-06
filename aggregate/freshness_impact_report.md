# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-06 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M+**: FRESH alert rate (20.4%) is 2.0× the overall rate (10.1%) — score distribution shift detected
🟡 **M5+**: FRESH alert rate (10.2%) is 2.4× the overall rate (4.2%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (18.4%) is 2.2× the overall rate (8.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   12.0 | 20.4% | 0.502 | 0.3 |       45 | 100.0% |  27.3% | 2.0× | 0.0% |   0.4889 |
|       OK |   25 |   37.4 | 4.0% | 0.389 | 0.0 |       25 | 100.0% |  33.3% | 8.3× | 0.0% |   0.1200 |
| DEGRADED |   45 |  120.4 | 2.2% | 0.405 | 0.0 |       45 | 0.0% |   0.0% |    - | 2.9% |   0.2444 |
|      ALL |  119 |   58.3 | 10.1% | 0.442 | 0.2 |      115 | 87.5% |  19.4% | 2.8× | 1.3% |   0.3130 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   12.0 | 10.2% | 0.497 | 0.1 |       45 | 0.0% |   0.0% |    - | 2.7% |   0.1778 |
|       OK |   25 |   37.4 | 0.0% | 0.323 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   45 |  120.4 | 0.0% | 0.351 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |  119 |   58.3 | 4.2% | 0.405 | 0.0 |      115 | 0.0% |   0.0% |    - | 1.0% |   0.0957 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   12.0 | 18.4% | 0.638 | 0.2 |       45 | 0.0% |   0.0% |    - | 12.2% |   0.0889 |
|       OK |   25 |   37.4 | 4.0% | 0.541 | 0.0 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |
| DEGRADED |   45 |  120.4 | 0.0% | 0.500 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0222 |
|      ALL |  119 |   58.3 | 8.4% | 0.566 | 0.1 |      115 | 0.0% |   0.0% |    - | 5.5% |   0.0435 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |    9.6 | 37.5% | 0.630 | 0.8 |       12 | 100.0% |  33.3% | 2.0× | 0.0% |   0.5000 |
|       OK |    4 |   39.9 | 0.0% | 0.350 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.8 | 9.1% | 0.522 | 0.1 |       11 | 0.0% |   0.0% |    - | 11.1% |   0.1818 |
|      ALL |   31 |   48.0 | 22.6% | 0.555 | 0.4 |       27 | 66.7% |  25.0% | 2.2× | 5.3% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |    9.6 | 31.2% | 0.647 | 0.3 |       12 | 0.0% |   0.0% |    - | 11.1% |   0.2500 |
|       OK |    4 |   39.9 | 0.0% | 0.265 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.8 | 0.0% | 0.474 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   48.0 | 16.1% | 0.536 | 0.2 |       27 | 0.0% |   0.0% |    - | 4.2% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |    9.6 | 37.5% | 0.724 | 0.4 |       12 | 0.0% |   0.0% |    - | 18.2% |   0.0833 |
|       OK |    4 |   39.9 | 0.0% | 0.530 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.8 | 0.0% | 0.547 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   48.0 | 19.4% | 0.636 | 0.2 |       27 | 0.0% |   0.0% |    - | 7.7% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available