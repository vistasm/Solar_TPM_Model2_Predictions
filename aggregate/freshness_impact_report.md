# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-30 UTC
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
|    FRESH |   22 |   13.0 | 18.2% | 0.466 | 0.2 |       19 | 100.0% |  18.2% | 1.7× | 0.0% |   0.5789 |
|       OK |   12 |   36.1 | 8.3% | 0.413 | 0.1 |       11 | 100.0% |  33.3% | 3.7× | 0.0% |   0.2727 |
| DEGRADED |   18 |  160.5 | 0.0% | 0.338 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   52 |   69.4 | 9.6% | 0.410 | 0.1 |       48 | 100.0% |  17.6% | 2.8× | 0.0% |   0.3542 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   22 |   13.0 | 0.0% | 0.482 | 0.0 |       19 |    - |   0.0% |    - | 0.0% |   0.2105 |
|       OK |   12 |   36.1 | 0.0% | 0.384 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  160.5 | 0.0% | 0.325 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   52 |   69.4 | 0.0% | 0.405 | 0.0 |       48 |    - |   0.0% |    - | 0.0% |   0.1042 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   22 |   13.0 | 9.1% | 0.609 | 0.1 |       19 | 0.0% |   0.0% |    - | 11.8% |   0.1053 |
|       OK |   12 |   36.1 | 8.3% | 0.522 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   18 |  160.5 | 0.0% | 0.416 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   52 |   69.4 | 5.8% | 0.522 | 0.1 |       48 | 0.0% |   0.0% |    - | 6.7% |   0.0625 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   11.3 | 33.3% | 0.582 | 0.4 |        9 | 100.0% |  33.3% | 1.5× | 0.0% |   0.6667 |
|       OK |    5 |   34.4 | 20.0% | 0.544 | 0.2 |        4 | 100.0% | 100.0% | 4.0× | 0.0% |   0.2500 |
| DEGRADED |   14 |  181.7 | 0.0% | 0.342 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|      ALL |   31 |   92.0 | 16.1% | 0.467 | 0.2 |       27 | 100.0% |  33.3% | 3.0× | 0.0% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   11.3 | 0.0% | 0.545 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.3333 |
|       OK |    5 |   34.4 | 0.0% | 0.387 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  181.7 | 0.0% | 0.321 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   92.0 | 0.0% | 0.419 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   11.3 | 16.7% | 0.689 | 0.2 |        9 | 0.0% |   0.0% |    - | 25.0% |   0.1111 |
|       OK |    5 |   34.4 | 20.0% | 0.554 | 0.2 |        4 | 0.0% |      - |    - | 25.0% |   0.0000 |
| DEGRADED |   14 |  181.7 | 0.0% | 0.404 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   92.0 | 9.7% | 0.538 | 0.1 |       27 | 0.0% |   0.0% |    - | 12.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available