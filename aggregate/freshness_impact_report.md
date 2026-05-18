# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-18 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (14.3%) is 2.0× the overall rate (7.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   28 |   12.5 | 14.3% | 0.458 | 0.2 |       26 | 100.0% |  28.6% | 1.9× | 0.0% |   0.5385 |
|       OK |   17 |   35.3 | 5.9% | 0.386 | 0.1 |       15 | 100.0% |  33.3% | 5.0× | 0.0% |   0.2000 |
| DEGRADED |   25 |  135.3 | 0.0% | 0.355 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.2000 |
|      ALL |   70 |   61.9 | 7.1% | 0.404 | 0.1 |       66 | 100.0% |  22.7% | 3.0× | 0.0% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   28 |   12.5 | 0.0% | 0.452 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.1538 |
|       OK |   17 |   35.3 | 0.0% | 0.336 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   25 |  135.3 | 0.0% | 0.312 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0800 |
|      ALL |   70 |   61.9 | 0.0% | 0.374 | 0.0 |       66 |    - |   0.0% |    - | 0.0% |   0.0909 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   28 |   12.5 | 7.1% | 0.596 | 0.1 |       26 | 0.0% |   0.0% |    - | 8.3% |   0.0769 |
|       OK |   17 |   35.3 | 5.9% | 0.528 | 0.1 |       15 | 0.0% |      - |    - | 6.7% |   0.0000 |
| DEGRADED |   25 |  135.3 | 0.0% | 0.455 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0400 |
|      ALL |   70 |   61.9 | 4.3% | 0.529 | 0.0 |       66 | 0.0% |   0.0% |    - | 4.8% |   0.0455 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   11.0 | 33.3% | 0.614 | 0.4 |       10 | 100.0% |  66.7% | 1.7× | 0.0% |   0.6000 |
|       OK |    6 |   34.3 | 0.0% | 0.353 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  163.9 | 0.0% | 0.374 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.3077 |
|      ALL |   31 |   79.6 | 12.9% | 0.463 | 0.2 |       27 | 100.0% |  40.0% | 2.7× | 0.0% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   11.0 | 0.0% | 0.555 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.2000 |
|       OK |    6 |   34.3 | 0.0% | 0.242 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  163.9 | 0.0% | 0.314 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|      ALL |   31 |   79.6 | 0.0% | 0.394 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   11.0 | 16.7% | 0.682 | 0.2 |       10 | 0.0% |   0.0% |    - | 22.2% |   0.1000 |
|       OK |    6 |   34.3 | 0.0% | 0.539 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  163.9 | 0.0% | 0.493 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   31 |   79.6 | 6.5% | 0.575 | 0.1 |       27 | 0.0% |   0.0% |    - | 8.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available