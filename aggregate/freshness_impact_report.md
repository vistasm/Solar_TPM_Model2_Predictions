# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-22 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (80.0%) is 80.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (6.2%) is 2.4× the overall rate (2.5%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (11.1%) is 2.2× the overall rate (5.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 18.5% | 0.501 | 0.3 |       80 | 80.0% |  33.3% | 1.8× | 6.8% |   0.4500 |
|       OK |   42 |   37.0 | 7.1% | 0.419 | 0.1 |       41 | 33.3% |  20.0% | 2.7× | 5.6% |   0.1220 |
| DEGRADED |   73 |  121.8 | 1.4% | 0.379 | 0.0 |       71 | 0.0% |   0.0% |    - | 1.8% |   0.2113 |
|      ALL |  196 |   58.6 | 9.7% | 0.438 | 0.1 |      192 | 68.4% |  23.2% | 2.4× | 4.4% |   0.2917 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 6.2% | 0.487 | 0.1 |       80 | 60.0% |  23.1% | 3.7× | 3.0% |   0.1625 |
|       OK |   42 |   37.0 | 0.0% | 0.358 | 0.0 |       41 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   73 |  121.8 | 0.0% | 0.318 | 0.0 |       71 |    - |   0.0% |    - | 0.0% |   0.0423 |
|      ALL |  196 |   58.6 | 2.5% | 0.396 | 0.0 |      192 | 60.0% |  18.8% | 7.2× | 1.1% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 11.1% | 0.597 | 0.1 |       80 | 11.1% |  20.0% | 1.8× | 10.7% |   0.0625 |
|       OK |   42 |   37.0 | 2.4% | 0.535 | 0.0 |       41 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |   73 |  121.8 | 0.0% | 0.500 | 0.0 |       71 |    - |   0.0% |    - | 0.0% |   0.0141 |
|      ALL |  196 |   58.6 | 5.1% | 0.548 | 0.1 |      192 | 10.0% |  16.7% | 3.2× | 4.8% |   0.0312 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.2 | 16.7% | 0.440 | 0.2 |       11 | 100.0% |  40.0% | 2.2× | 0.0% |   0.4545 |
|       OK |    7 |   36.2 | 0.0% | 0.428 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  126.4 | 0.0% | 0.312 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|      ALL |   30 |   60.1 | 6.7% | 0.390 | 0.1 |       26 | 100.0% |  33.3% | 4.3× | 0.0% |   0.2308 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.2 | 0.0% | 0.402 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|       OK |    7 |   36.2 | 0.0% | 0.366 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  126.4 | 0.0% | 0.213 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   60.1 | 0.0% | 0.325 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0385 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.2 | 0.0% | 0.558 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   36.2 | 0.0% | 0.556 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  126.4 | 0.0% | 0.531 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   60.1 | 0.0% | 0.548 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available