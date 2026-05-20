# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-20 UTC
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
|    FRESH |   29 |   12.8 | 13.8% | 0.447 | 0.2 |       27 | 100.0% |  26.7% | 1.8× | 0.0% |   0.5556 |
|       OK |   17 |   35.3 | 5.9% | 0.386 | 0.1 |       16 | 100.0% |  33.3% | 5.3× | 0.0% |   0.1875 |
| DEGRADED |   26 |  132.0 | 0.0% | 0.351 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.2000 |
|      ALL |   72 |   61.1 | 6.9% | 0.398 | 0.1 |       68 | 100.0% |  21.7% | 3.0× | 0.0% |   0.3382 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   29 |   12.8 | 0.0% | 0.440 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |
|       OK |   17 |   35.3 | 0.0% | 0.336 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   26 |  132.0 | 0.0% | 0.305 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0800 |
|      ALL |   72 |   61.1 | 0.0% | 0.366 | 0.0 |       68 |    - |   0.0% |    - | 0.0% |   0.0882 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   29 |   12.8 | 6.9% | 0.593 | 0.1 |       27 | 0.0% |   0.0% |    - | 8.0% |   0.0741 |
|       OK |   17 |   35.3 | 5.9% | 0.528 | 0.1 |       16 | 0.0% |      - |    - | 6.2% |   0.0000 |
| DEGRADED |   26 |  132.0 | 0.0% | 0.457 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0400 |
|      ALL |   72 |   61.1 | 4.2% | 0.528 | 0.0 |       68 | 0.0% |   0.0% |    - | 4.6% |   0.0441 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.6 | 30.8% | 0.578 | 0.4 |       11 | 100.0% |  57.1% | 1.6× | 0.0% |   0.6364 |
|       OK |    6 |   34.3 | 0.0% | 0.353 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  144.3 | 0.0% | 0.373 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.3636 |
|      ALL |   31 |   67.4 | 12.9% | 0.455 | 0.2 |       27 | 100.0% |  36.4% | 2.5× | 0.0% |   0.4074 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.6 | 0.0% | 0.519 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |    6 |   34.3 | 0.0% | 0.242 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  144.3 | 0.0% | 0.300 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |
|      ALL |   31 |   67.4 | 0.0% | 0.381 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.6 | 15.4% | 0.669 | 0.1 |       11 | 0.0% |   0.0% |    - | 20.0% |   0.0909 |
|       OK |    6 |   34.3 | 0.0% | 0.539 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  144.3 | 0.0% | 0.492 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   31 |   67.4 | 6.5% | 0.576 | 0.1 |       27 | 0.0% |   0.0% |    - | 8.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available