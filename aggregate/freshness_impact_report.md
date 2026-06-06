# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-06 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (11.8%) is 2.1× the overall rate (5.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   34 |   13.2 | 11.8% | 0.441 | 0.1 |       31 | 100.0% |  26.7% | 2.1× | 0.0% |   0.4839 |
|       OK |   21 |   36.9 | 4.8% | 0.397 | 0.1 |       20 | 100.0% |  33.3% | 6.7× | 0.0% |   0.1500 |
| DEGRADED |   34 |  124.7 | 0.0% | 0.368 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.2647 |
|      ALL |   89 |   61.4 | 5.6% | 0.402 | 0.1 |       85 | 100.0% |  18.5% | 3.1× | 0.0% |   0.3176 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   34 |   13.2 | 0.0% | 0.427 | 0.0 |       31 |    - |   0.0% |    - | 0.0% |   0.1290 |
|       OK |   21 |   36.9 | 0.0% | 0.334 | 0.0 |       20 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   34 |  124.7 | 0.0% | 0.311 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0882 |
|      ALL |   89 |   61.4 | 0.0% | 0.361 | 0.0 |       85 |    - |   0.0% |    - | 0.0% |   0.0824 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   34 |   13.2 | 8.8% | 0.598 | 0.1 |       31 | 0.0% |   0.0% |    - | 6.9% |   0.0645 |
|       OK |   21 |   36.9 | 4.8% | 0.543 | 0.1 |       20 | 0.0% |      - |    - | 5.0% |   0.0000 |
| DEGRADED |   34 |  124.7 | 0.0% | 0.485 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0294 |
|      ALL |   89 |   61.4 | 4.5% | 0.542 | 0.0 |       85 | 0.0% |   0.0% |    - | 3.7% |   0.0353 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.8 | 0.0% | 0.387 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    8 |   39.2 | 0.0% | 0.385 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   88.4 | 0.0% | 0.400 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.4615 |
|      ALL |   31 |   51.9 | 0.0% | 0.392 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.8 | 0.0% | 0.320 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   39.2 | 0.0% | 0.271 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   88.4 | 0.0% | 0.301 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|      ALL |   31 |   51.9 | 0.0% | 0.299 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.8 | 10.0% | 0.585 | 0.1 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   39.2 | 0.0% | 0.575 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   88.4 | 0.0% | 0.567 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   51.9 | 3.2% | 0.575 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available