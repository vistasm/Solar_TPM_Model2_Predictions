# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-07 UTC
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
|    FRESH |   24 |   12.5 | 16.7% | 0.463 | 0.2 |       23 | 100.0% |  28.6% | 1.6× | 0.0% |   0.6087 |
|       OK |   13 |   35.5 | 7.7% | 0.404 | 0.1 |       12 | 100.0% |  33.3% | 4.0× | 0.0% |   0.2500 |
| DEGRADED |   22 |  144.0 | 0.0% | 0.341 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.1500 |
|      ALL |   59 |   66.6 | 8.5% | 0.405 | 0.1 |       55 | 100.0% |  25.0% | 2.8× | 0.0% |   0.3636 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.5 | 0.0% | 0.472 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.1739 |
|       OK |   13 |   35.5 | 0.0% | 0.372 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   22 |  144.0 | 0.0% | 0.308 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.0500 |
|      ALL |   59 |   66.6 | 0.0% | 0.389 | 0.0 |       55 |    - |   0.0% |    - | 0.0% |   0.0909 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.5 | 8.3% | 0.604 | 0.1 |       23 | 0.0% |   0.0% |    - | 9.5% |   0.0870 |
|       OK |   13 |   35.5 | 7.7% | 0.523 | 0.1 |       12 | 0.0% |      - |    - | 8.3% |   0.0000 |
| DEGRADED |   22 |  144.0 | 0.0% | 0.439 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.0500 |
|      ALL |   59 |   66.6 | 5.1% | 0.524 | 0.1 |       55 | 0.0% |   0.0% |    - | 5.8% |   0.0545 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.4 | 44.4% | 0.657 | 0.6 |        8 | 100.0% |  66.7% | 1.3× | 0.0% |   0.7500 |
|       OK |    4 |   35.7 | 25.0% | 0.469 | 0.2 |        3 | 100.0% | 100.0% | 3.0× | 0.0% |   0.3333 |
| DEGRADED |   18 |  156.9 | 0.0% | 0.345 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |
|      ALL |   31 |   99.0 | 16.1% | 0.452 | 0.2 |       27 | 100.0% |  55.6% | 3.0× | 0.0% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.4 | 0.0% | 0.605 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|       OK |    4 |   35.7 | 0.0% | 0.338 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  156.9 | 0.0% | 0.301 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   31 |   99.0 | 0.0% | 0.394 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.4 | 22.2% | 0.720 | 0.2 |        8 | 0.0% |   0.0% |    - | 28.6% |   0.1250 |
|       OK |    4 |   35.7 | 0.0% | 0.490 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  156.9 | 0.0% | 0.435 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   31 |   99.0 | 6.5% | 0.524 | 0.1 |       27 | 0.0% |   0.0% |    - | 8.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available