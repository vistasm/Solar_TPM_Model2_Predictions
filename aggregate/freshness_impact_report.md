# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-14 UTC
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
|    FRESH |   39 |   13.3 | 10.3% | 0.436 | 0.1 |       36 | 100.0% |  23.5% | 2.1× | 0.0% |   0.4722 |
|       OK |   23 |   37.4 | 4.3% | 0.386 | 0.0 |       22 | 100.0% |  33.3% | 7.3× | 0.0% |   0.1364 |
| DEGRADED |   35 |  123.0 | 0.0% | 0.377 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.2571 |
|      ALL |   97 |   58.6 | 5.1% | 0.403 | 0.1 |       93 | 100.0% |  17.2% | 3.2× | 0.0% |   0.3118 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.3 | 0.0% | 0.438 | 0.0 |       36 |    - |   0.0% |    - | 0.0% |   0.1389 |
|       OK |   23 |   37.4 | 0.0% | 0.329 | 0.0 |       22 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   35 |  123.0 | 0.0% | 0.321 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.0857 |
|      ALL |   97 |   58.6 | 0.0% | 0.370 | 0.0 |       93 |    - |   0.0% |    - | 0.0% |   0.0860 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.3 | 7.7% | 0.596 | 0.1 |       36 | 0.0% |   0.0% |    - | 9.1% |   0.0833 |
|       OK |   23 |   37.4 | 4.3% | 0.544 | 0.0 |       22 | 0.0% |      - |    - | 4.5% |   0.0000 |
| DEGRADED |   35 |  123.0 | 0.0% | 0.487 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.0286 |
|      ALL |   97 |   58.6 | 4.1% | 0.544 | 0.0 |       93 | 0.0% |   0.0% |    - | 4.5% |   0.0430 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.4 | 0.0% | 0.381 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.3000 |
|       OK |    8 |   40.0 | 0.0% | 0.342 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   92.2 | 0.0% | 0.430 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.4000 |
|      ALL |   31 |   46.1 | 0.0% | 0.387 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.4 | 0.0% | 0.383 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    8 |   40.0 | 0.0% | 0.264 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   92.2 | 0.0% | 0.342 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|      ALL |   31 |   46.1 | 0.0% | 0.339 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.4 | 7.7% | 0.588 | 0.1 |       10 | 0.0% |   0.0% |    - | 11.1% |   0.1000 |
|       OK |    8 |   40.0 | 0.0% | 0.576 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   92.2 | 0.0% | 0.568 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.1 | 3.2% | 0.578 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available