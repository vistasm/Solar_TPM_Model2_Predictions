# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-20 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (80.0%) is 80.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (6.2%) is 2.4× the overall rate (2.6%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (11.1%) is 2.2× the overall rate (5.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 18.5% | 0.501 | 0.3 |       80 | 80.0% |  33.3% | 1.8× | 6.8% |   0.4500 |
|       OK |   41 |   37.1 | 7.3% | 0.414 | 0.1 |       41 | 33.3% |  20.0% | 2.7× | 5.6% |   0.1220 |
| DEGRADED |   72 |  122.7 | 1.4% | 0.378 | 0.0 |       69 | 0.0% |   0.0% |    - | 1.8% |   0.2174 |
|      ALL |  194 |   58.7 | 9.8% | 0.437 | 0.1 |      190 | 68.4% |  23.2% | 2.3× | 4.5% |   0.2947 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 6.2% | 0.487 | 0.1 |       80 | 60.0% |  23.1% | 3.7× | 3.0% |   0.1625 |
|       OK |   41 |   37.1 | 0.0% | 0.354 | 0.0 |       41 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   72 |  122.7 | 0.0% | 0.320 | 0.0 |       69 |    - |   0.0% |    - | 0.0% |   0.0435 |
|      ALL |  194 |   58.7 | 2.6% | 0.397 | 0.0 |      190 | 60.0% |  18.8% | 7.1× | 1.1% |   0.0842 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 11.1% | 0.597 | 0.1 |       80 | 11.1% |  20.0% | 1.8× | 10.7% |   0.0625 |
|       OK |   41 |   37.1 | 2.4% | 0.535 | 0.0 |       41 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |   72 |  122.7 | 0.0% | 0.499 | 0.0 |       69 |    - |   0.0% |    - | 0.0% |   0.0145 |
|      ALL |  194 |   58.7 | 5.1% | 0.548 | 0.1 |      190 | 10.0% |  16.7% | 3.2× | 4.9% |   0.0316 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.7 | 21.4% | 0.489 | 0.3 |       13 | 66.7% |  33.3% | 1.4× | 14.3% |   0.4615 |
|       OK |    6 |   36.3 | 0.0% | 0.401 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  133.2 | 0.0% | 0.298 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|      ALL |   30 |   58.0 | 10.0% | 0.408 | 0.1 |       26 | 66.7% |  28.6% | 2.5× | 5.3% |   0.2692 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.7 | 0.0% | 0.429 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|       OK |    6 |   36.3 | 0.0% | 0.341 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  133.2 | 0.0% | 0.217 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   58.0 | 0.0% | 0.341 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0385 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.7 | 0.0% | 0.566 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.3 | 0.0% | 0.561 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  133.2 | 0.0% | 0.532 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   58.0 | 0.0% | 0.553 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available