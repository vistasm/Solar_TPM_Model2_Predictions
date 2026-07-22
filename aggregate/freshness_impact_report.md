# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-22 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (90.0%) is 90.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (8.6%) is 2.3× the overall rate (3.7%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (15.5%) is 2.1× the overall rate (7.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   58 |   12.3 | 19.0% | 0.504 | 0.3 |       56 | 90.0% |  33.3% | 1.9× | 3.5% |   0.4821 |
|       OK |   28 |   37.3 | 3.6% | 0.385 | 0.0 |       28 | 100.0% |  25.0% | 7.0× | 0.0% |   0.1429 |
| DEGRADED |   49 |  118.8 | 2.0% | 0.394 | 0.0 |       47 | 0.0% |   0.0% |    - | 2.8% |   0.2340 |
|      ALL |  135 |   56.2 | 9.6% | 0.439 | 0.1 |      131 | 83.3% |  23.8% | 2.6× | 2.2% |   0.3206 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   58 |   12.3 | 8.6% | 0.491 | 0.1 |       56 | 60.0% |  27.3% | 3.0× | 4.4% |   0.1964 |
|       OK |   28 |   37.3 | 0.0% | 0.321 | 0.0 |       28 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   49 |  118.8 | 0.0% | 0.334 | 0.0 |       47 |    - |   0.0% |    - | 0.0% |   0.0638 |
|      ALL |  135 |   56.2 | 3.7% | 0.399 | 0.0 |      131 | 60.0% |  21.4% | 5.6× | 1.7% |   0.1069 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   58 |   12.3 | 15.5% | 0.616 | 0.2 |       56 | 11.1% |  20.0% | 1.2× | 15.7% |   0.0893 |
|       OK |   28 |   37.3 | 3.6% | 0.536 | 0.0 |       28 | 0.0% |      - |    - | 3.6% |   0.0000 |
| DEGRADED |   49 |  118.8 | 0.0% | 0.485 | 0.0 |       47 |    - |   0.0% |    - | 0.0% |   0.0213 |
|      ALL |  135 |   56.2 | 7.4% | 0.552 | 0.1 |      131 | 10.0% |  16.7% | 2.2× | 7.2% |   0.0458 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.5 | 41.2% | 0.691 | 0.8 |       15 | 83.3% |  62.5% | 1.6× | 14.3% |   0.5333 |
|       OK |    4 |   36.3 | 0.0% | 0.441 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
| DEGRADED |   10 |  111.4 | 10.0% | 0.510 | 0.1 |        8 | 0.0% |   0.0% |    - | 14.3% |   0.1250 |
|      ALL |   31 |   46.4 | 25.8% | 0.600 | 0.5 |       27 | 71.4% |  50.0% | 1.9× | 11.8% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.5 | 29.4% | 0.646 | 0.3 |       15 | 60.0% |  60.0% | 1.8× | 20.0% |   0.3333 |
|       OK |    4 |   36.3 | 0.0% | 0.319 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  111.4 | 0.0% | 0.401 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.4 | 16.1% | 0.525 | 0.2 |       27 | 60.0% |  60.0% | 3.2× | 9.1% |   0.1852 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.5 | 35.3% | 0.687 | 0.3 |       15 | 16.7% |  50.0% | 1.2× | 38.5% |   0.1333 |
|       OK |    4 |   36.3 | 0.0% | 0.532 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  111.4 | 0.0% | 0.529 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.4 | 19.4% | 0.616 | 0.2 |       27 | 16.7% |  50.0% | 2.2× | 20.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available