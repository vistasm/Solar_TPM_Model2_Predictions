# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-09 UTC
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
|       OK |   14 |   35.7 | 7.1% | 0.390 | 0.1 |       13 | 100.0% |  33.3% | 4.3× | 0.0% |   0.2308 |
| DEGRADED |   22 |  144.0 | 0.0% | 0.341 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.1500 |
|      ALL |   61 |   65.3 | 8.2% | 0.398 | 0.1 |       57 | 100.0% |  25.0% | 2.9× | 0.0% |   0.3509 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   25 |   12.6 | 0.0% | 0.460 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |   14 |   35.7 | 0.0% | 0.358 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   22 |  144.0 | 0.0% | 0.308 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.0500 |
|      ALL |   61 |   65.3 | 0.0% | 0.382 | 0.0 |       57 |    - |   0.0% |    - | 0.0% |   0.0877 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   25 |   12.6 | 8.0% | 0.600 | 0.1 |       24 | 0.0% |   0.0% |    - | 9.1% |   0.0833 |
|       OK |   14 |   35.7 | 7.1% | 0.523 | 0.1 |       13 | 0.0% |      - |    - | 7.7% |   0.0000 |
| DEGRADED |   22 |  144.0 | 0.0% | 0.439 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.0500 |
|      ALL |   61 |   65.3 | 4.9% | 0.524 | 0.1 |       57 | 0.0% |   0.0% |    - | 5.6% |   0.0526 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.7 | 40.0% | 0.611 | 0.5 |        9 | 100.0% |  66.7% | 1.5× | 0.0% |   0.6667 |
|       OK |    5 |   36.3 | 20.0% | 0.415 | 0.2 |        4 | 100.0% | 100.0% | 4.0× | 0.0% |   0.2500 |
| DEGRADED |   16 |  168.1 | 0.0% | 0.349 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|      ALL |   31 |   96.4 | 16.1% | 0.444 | 0.2 |       27 | 100.0% |  55.6% | 3.0× | 0.0% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.7 | 0.0% | 0.561 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.2222 |
|       OK |    5 |   36.3 | 0.0% | 0.307 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  168.1 | 0.0% | 0.308 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   96.4 | 0.0% | 0.390 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.7 | 20.0% | 0.700 | 0.2 |        9 | 0.0% |   0.0% |    - | 25.0% |   0.1111 |
|       OK |    5 |   36.3 | 0.0% | 0.496 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  168.1 | 0.0% | 0.426 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   96.4 | 6.5% | 0.526 | 0.1 |       27 | 0.0% |   0.0% |    - | 8.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available