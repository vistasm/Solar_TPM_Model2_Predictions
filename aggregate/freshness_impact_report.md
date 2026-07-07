# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-07 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M+**: FRESH alert rate (20.4%) is 2.0× the overall rate (10.0%) — score distribution shift detected
🟡 **M5+**: FRESH alert rate (10.2%) is 2.4× the overall rate (4.2%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (18.4%) is 2.2× the overall rate (8.3%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   12.0 | 20.4% | 0.502 | 0.3 |       46 | 100.0% |  30.4% | 2.0× | 0.0% |   0.5000 |
|       OK |   26 |   36.9 | 3.9% | 0.398 | 0.0 |       25 | 100.0% |  33.3% | 8.3× | 0.0% |   0.1200 |
| DEGRADED |   45 |  120.4 | 2.2% | 0.405 | 0.0 |       45 | 0.0% |   0.0% |    - | 2.9% |   0.2444 |
|      ALL |  120 |   58.0 | 10.0% | 0.443 | 0.2 |      116 | 88.9% |  21.6% | 2.8× | 1.3% |   0.3190 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   12.0 | 10.2% | 0.497 | 0.1 |       46 | 50.0% |  11.1% | 2.6× | 2.7% |   0.1957 |
|       OK |   26 |   36.9 | 0.0% | 0.334 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   45 |  120.4 | 0.0% | 0.351 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |  120 |   58.0 | 4.2% | 0.407 | 0.0 |      116 | 50.0% |   8.3% | 4.8× | 1.0% |   0.1034 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   12.0 | 18.4% | 0.638 | 0.2 |       46 | 0.0% |   0.0% |    - | 14.3% |   0.0870 |
|       OK |   26 |   36.9 | 3.9% | 0.545 | 0.0 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |
| DEGRADED |   45 |  120.4 | 0.0% | 0.500 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0222 |
|      ALL |  120 |   58.0 | 8.3% | 0.566 | 0.1 |      116 | 0.0% |   0.0% |    - | 6.3% |   0.0431 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |    9.2 | 40.0% | 0.643 | 0.8 |       12 | 100.0% |  50.0% | 2.0× | 0.0% |   0.5000 |
|       OK |    5 |   36.8 | 0.0% | 0.401 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.8 | 9.1% | 0.522 | 0.1 |       11 | 0.0% |   0.0% |    - | 11.1% |   0.1818 |
|      ALL |   31 |   48.3 | 22.6% | 0.561 | 0.4 |       27 | 75.0% |  37.5% | 2.5× | 5.3% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |    9.2 | 33.3% | 0.655 | 0.3 |       12 | 50.0% |  25.0% | 1.5× | 12.5% |   0.3333 |
|       OK |    5 |   36.8 | 0.0% | 0.338 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.8 | 0.0% | 0.474 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   48.3 | 16.1% | 0.540 | 0.2 |       27 | 50.0% |  25.0% | 3.4× | 4.3% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |    9.2 | 40.0% | 0.730 | 0.4 |       12 | 0.0% |   0.0% |    - | 27.3% |   0.0833 |
|       OK |    5 |   36.8 | 0.0% | 0.556 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.8 | 0.0% | 0.547 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   48.3 | 19.4% | 0.637 | 0.2 |       27 | 0.0% |   0.0% |    - | 11.5% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available