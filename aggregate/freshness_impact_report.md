# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-21 UTC
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
|       OK |   42 |   37.0 | 7.1% | 0.419 | 0.1 |       41 | 33.3% |  20.0% | 2.7× | 5.6% |   0.1220 |
| DEGRADED |   72 |  122.7 | 1.4% | 0.378 | 0.0 |       70 | 0.0% |   0.0% |    - | 1.8% |   0.2143 |
|      ALL |  195 |   58.6 | 9.7% | 0.438 | 0.1 |      191 | 68.4% |  23.2% | 2.3× | 4.4% |   0.2932 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 6.2% | 0.487 | 0.1 |       80 | 60.0% |  23.1% | 3.7× | 3.0% |   0.1625 |
|       OK |   42 |   37.0 | 0.0% | 0.358 | 0.0 |       41 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   72 |  122.7 | 0.0% | 0.320 | 0.0 |       70 |    - |   0.0% |    - | 0.0% |   0.0429 |
|      ALL |  195 |   58.6 | 2.6% | 0.398 | 0.0 |      191 | 60.0% |  18.8% | 7.2× | 1.1% |   0.0838 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 11.1% | 0.597 | 0.1 |       80 | 11.1% |  20.0% | 1.8× | 10.7% |   0.0625 |
|       OK |   42 |   37.0 | 2.4% | 0.535 | 0.0 |       41 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |   72 |  122.7 | 0.0% | 0.499 | 0.0 |       70 |    - |   0.0% |    - | 0.0% |   0.0143 |
|      ALL |  195 |   58.6 | 5.1% | 0.548 | 0.1 |      191 | 10.0% |  16.7% | 3.2× | 4.9% |   0.0314 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   13.7 | 23.1% | 0.471 | 0.3 |       12 | 66.7% |  40.0% | 1.6× | 14.3% |   0.4167 |
|       OK |    7 |   36.2 | 0.0% | 0.428 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  133.2 | 0.0% | 0.298 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|      ALL |   30 |   58.7 | 10.0% | 0.403 | 0.1 |       26 | 66.7% |  33.3% | 2.9× | 5.0% |   0.2308 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   13.7 | 0.0% | 0.429 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|       OK |    7 |   36.2 | 0.0% | 0.366 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  133.2 | 0.0% | 0.217 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   58.7 | 0.0% | 0.344 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0385 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   13.7 | 0.0% | 0.564 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   36.2 | 0.0% | 0.556 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  133.2 | 0.0% | 0.532 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   58.7 | 0.0% | 0.551 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available