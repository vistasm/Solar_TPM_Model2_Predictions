# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-23 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

✅ No anomalies detected. Insufficient data or metrics within normal range.

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   13.0 | 13.3% | 0.442 | 0.2 |       28 | 100.0% |  26.7% | 1.9× | 0.0% |   0.5357 |
|       OK |   18 |   35.7 | 5.6% | 0.377 | 0.1 |       17 | 100.0% |  33.3% | 5.7× | 0.0% |   0.1765 |
| DEGRADED |   27 |  129.6 | 0.0% | 0.354 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.1923 |
|      ALL |   75 |   60.4 | 6.7% | 0.395 | 0.1 |       71 | 100.0% |  21.7% | 3.1× | 0.0% |   0.3239 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   13.0 | 0.0% | 0.430 | 0.0 |       28 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |   18 |   35.7 | 0.0% | 0.324 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   27 |  129.6 | 0.0% | 0.305 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   75 |   60.4 | 0.0% | 0.359 | 0.0 |       71 |    - |   0.0% |    - | 0.0% |   0.0845 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   13.0 | 6.7% | 0.590 | 0.1 |       28 | 0.0% |   0.0% |    - | 7.7% |   0.0714 |
|       OK |   18 |   35.7 | 5.6% | 0.527 | 0.1 |       17 | 0.0% |      - |    - | 5.9% |   0.0000 |
| DEGRADED |   27 |  129.6 | 0.0% | 0.460 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0385 |
|      ALL |   75 |   60.4 | 4.0% | 0.528 | 0.0 |       71 | 0.0% |   0.0% |    - | 4.4% |   0.0423 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   12.2 | 28.6% | 0.557 | 0.4 |       12 | 100.0% |  57.1% | 1.7× | 0.0% |   0.5833 |
|       OK |    7 |   35.6 | 0.0% | 0.333 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   94.4 | 0.0% | 0.394 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.3333 |
|      ALL |   31 |   44.0 | 12.9% | 0.454 | 0.2 |       27 | 100.0% |  40.0% | 2.7× | 0.0% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   12.2 | 0.0% | 0.493 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    7 |   35.6 | 0.0% | 0.225 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   94.4 | 0.0% | 0.288 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.2222 |
|      ALL |   31 |   44.0 | 0.0% | 0.366 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   12.2 | 14.3% | 0.658 | 0.1 |       12 | 0.0% |   0.0% |    - | 18.2% |   0.0833 |
|       OK |    7 |   35.6 | 0.0% | 0.536 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   94.4 | 0.0% | 0.545 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|      ALL |   31 |   44.0 | 6.5% | 0.594 | 0.1 |       27 | 0.0% |   0.0% |    - | 8.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available