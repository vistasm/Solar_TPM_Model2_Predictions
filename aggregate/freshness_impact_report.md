# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-14 UTC
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
|    FRESH |   16 |   13.7 | 0.0% | 0.342 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.5000 |
|       OK |   11 |   35.8 | 9.1% | 0.405 | 0.1 |       10 | 100.0% |  33.3% | 3.3× | 0.0% |   0.3000 |
| DEGRADED |    9 |   84.1 | 0.0% | 0.337 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   36 |   38.0 | 2.8% | 0.360 | 0.0 |       32 | 100.0% |   8.3% | 2.7× | 0.0% |   0.3750 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.7 | 0.0% | 0.375 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   11 |   35.8 | 0.0% | 0.387 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |   84.1 | 0.0% | 0.316 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   36 |   38.0 | 0.0% | 0.364 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0625 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.7 | 0.0% | 0.531 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|       OK |   11 |   35.8 | 9.1% | 0.522 | 0.1 |       10 | 0.0% |      - |    - | 10.0% |   0.0000 |
| DEGRADED |    9 |   84.1 | 0.0% | 0.427 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   36 |   38.0 | 2.8% | 0.502 | 0.0 |       32 | 0.0% |   0.0% |    - | 3.2% |   0.0312 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.7 | 0.0% | 0.345 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.5714 |
|       OK |    9 |   35.2 | 11.1% | 0.406 | 0.1 |        8 | 100.0% |  33.3% | 2.7× | 0.0% |   0.3750 |
| DEGRADED |    8 |   86.4 | 0.0% | 0.351 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   38.7 | 3.2% | 0.364 | 0.0 |       27 | 100.0% |   9.1% | 2.5× | 0.0% |   0.4074 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.7 | 0.0% | 0.385 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    9 |   35.2 | 0.0% | 0.381 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |   86.4 | 0.0% | 0.325 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   38.7 | 0.0% | 0.368 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   13.7 | 0.0% | 0.545 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|       OK |    9 |   35.2 | 11.1% | 0.530 | 0.1 |        8 | 0.0% |      - |    - | 12.5% |   0.0000 |
| DEGRADED |    8 |   86.4 | 0.0% | 0.419 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   38.7 | 3.2% | 0.508 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available