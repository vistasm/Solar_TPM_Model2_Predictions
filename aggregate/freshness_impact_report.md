# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-08 UTC
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
|    FRESH |   25 |   12.6 | 16.0% | 0.453 | 0.2 |       24 | 100.0% |  28.6% | 1.7× | 0.0% |   0.5833 |
|       OK |   13 |   35.5 | 7.7% | 0.404 | 0.1 |       12 | 100.0% |  33.3% | 4.0× | 0.0% |   0.2500 |
| DEGRADED |   22 |  144.0 | 0.0% | 0.341 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.1500 |
|      ALL |   60 |   65.7 | 8.3% | 0.401 | 0.1 |       56 | 100.0% |  25.0% | 2.8× | 0.0% |   0.3571 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   25 |   12.6 | 0.0% | 0.460 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |   13 |   35.5 | 0.0% | 0.372 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   22 |  144.0 | 0.0% | 0.308 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.0500 |
|      ALL |   60 |   65.7 | 0.0% | 0.385 | 0.0 |       56 |    - |   0.0% |    - | 0.0% |   0.0893 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   25 |   12.6 | 8.0% | 0.600 | 0.1 |       24 | 0.0% |   0.0% |    - | 9.1% |   0.0833 |
|       OK |   13 |   35.5 | 7.7% | 0.523 | 0.1 |       12 | 0.0% |      - |    - | 8.3% |   0.0000 |
| DEGRADED |   22 |  144.0 | 0.0% | 0.439 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.0500 |
|      ALL |   60 |   65.7 | 5.0% | 0.524 | 0.1 |       56 | 0.0% |   0.0% |    - | 5.7% |   0.0536 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.7 | 40.0% | 0.611 | 0.5 |        9 | 100.0% |  66.7% | 1.5× | 0.0% |   0.6667 |
|       OK |    4 |   35.7 | 25.0% | 0.469 | 0.2 |        3 | 100.0% | 100.0% | 3.0× | 0.0% |   0.3333 |
| DEGRADED |   17 |  162.9 | 0.0% | 0.345 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|      ALL |   31 |   97.7 | 16.1% | 0.447 | 0.2 |       27 | 100.0% |  55.6% | 3.0× | 0.0% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.7 | 0.0% | 0.561 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.2222 |
|       OK |    4 |   35.7 | 0.0% | 0.338 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  162.9 | 0.0% | 0.301 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   31 |   97.7 | 0.0% | 0.390 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.7 | 20.0% | 0.700 | 0.2 |        9 | 0.0% |   0.0% |    - | 25.0% |   0.1111 |
|       OK |    4 |   35.7 | 0.0% | 0.490 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  162.9 | 0.0% | 0.431 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   31 |   97.7 | 6.5% | 0.525 | 0.1 |       27 | 0.0% |   0.0% |    - | 8.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available