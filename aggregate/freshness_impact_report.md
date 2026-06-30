# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-30 UTC
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
|    FRESH |   43 |   12.8 | 9.3% | 0.437 | 0.1 |       42 | 100.0% |  21.1% | 2.2× | 0.0% |   0.4524 |
|       OK |   25 |   37.4 | 4.0% | 0.389 | 0.0 |       25 | 100.0% |  33.3% | 8.3× | 0.0% |   0.1200 |
| DEGRADED |   45 |  120.4 | 2.2% | 0.405 | 0.0 |       42 |    - |   0.0% |    - | 0.0% |   0.2381 |
|      ALL |  113 |   61.1 | 5.3% | 0.414 | 0.1 |      109 | 100.0% |  15.6% | 3.4× | 0.0% |   0.2936 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   43 |   12.8 | 0.0% | 0.434 | 0.0 |       42 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |   25 |   37.4 | 0.0% | 0.323 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   45 |  120.4 | 0.0% | 0.351 | 0.0 |       42 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |  113 |   61.1 | 0.0% | 0.376 | 0.0 |      109 |    - |   0.0% |    - | 0.0% |   0.0826 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   43 |   12.8 | 7.0% | 0.590 | 0.1 |       42 | 0.0% |   0.0% |    - | 7.7% |   0.0714 |
|       OK |   25 |   37.4 | 4.0% | 0.541 | 0.0 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |
| DEGRADED |   45 |  120.4 | 0.0% | 0.500 | 0.0 |       42 |    - |   0.0% |    - | 0.0% |   0.0238 |
|      ALL |  113 |   61.1 | 3.5% | 0.543 | 0.0 |      109 | 0.0% |   0.0% |    - | 3.8% |   0.0367 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   11.6 | 0.0% | 0.440 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.3636 |
|       OK |    6 |   41.4 | 0.0% | 0.404 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  103.1 | 7.7% | 0.487 | 0.1 |       10 |    - |   0.0% |    - | 0.0% |   0.3000 |
|      ALL |   31 |   55.7 | 3.2% | 0.453 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   11.6 | 0.0% | 0.459 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |    6 |   41.4 | 0.0% | 0.295 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  103.1 | 0.0% | 0.440 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|      ALL |   31 |   55.7 | 0.0% | 0.419 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   11.6 | 8.3% | 0.591 | 0.1 |       11 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |    6 |   41.4 | 0.0% | 0.576 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  103.1 | 0.0% | 0.550 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   55.7 | 3.2% | 0.571 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available