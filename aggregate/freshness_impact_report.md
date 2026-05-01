# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-01 UTC
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
|    FRESH |   22 |   13.0 | 18.2% | 0.466 | 0.2 |       20 | 100.0% |  25.0% | 1.7× | 0.0% |   0.6000 |
|       OK |   12 |   36.1 | 8.3% | 0.413 | 0.1 |       11 | 100.0% |  33.3% | 3.7× | 0.0% |   0.2727 |
| DEGRADED |   19 |  155.4 | 0.0% | 0.347 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   53 |   69.3 | 9.4% | 0.412 | 0.1 |       49 | 100.0% |  22.2% | 2.7× | 0.0% |   0.3673 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   22 |   13.0 | 0.0% | 0.482 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.2000 |
|       OK |   12 |   36.1 | 0.0% | 0.384 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   19 |  155.4 | 0.0% | 0.323 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   53 |   69.3 | 0.0% | 0.403 | 0.0 |       49 |    - |   0.0% |    - | 0.0% |   0.1020 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   22 |   13.0 | 9.1% | 0.609 | 0.1 |       20 | 0.0% |   0.0% |    - | 11.1% |   0.1000 |
|       OK |   12 |   36.1 | 8.3% | 0.522 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   19 |  155.4 | 0.0% | 0.423 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   53 |   69.3 | 5.7% | 0.522 | 0.1 |       49 | 0.0% |   0.0% |    - | 6.5% |   0.0612 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   11.3 | 33.3% | 0.582 | 0.4 |       10 | 100.0% |  42.9% | 1.4× | 0.0% |   0.7000 |
|       OK |    4 |   36.4 | 25.0% | 0.515 | 0.2 |        3 | 100.0% | 100.0% | 3.0× | 0.0% |   0.3333 |
| DEGRADED |   15 |  173.9 | 0.0% | 0.354 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|      ALL |   31 |   93.2 | 16.1% | 0.463 | 0.2 |       27 | 100.0% |  40.0% | 2.7× | 0.0% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   11.3 | 0.0% | 0.545 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.3000 |
|       OK |    4 |   36.4 | 0.0% | 0.392 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  173.9 | 0.0% | 0.319 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   93.2 | 0.0% | 0.416 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   11.3 | 16.7% | 0.689 | 0.2 |       10 | 0.0% |   0.0% |    - | 22.2% |   0.1000 |
|       OK |    4 |   36.4 | 0.0% | 0.463 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  173.9 | 0.0% | 0.414 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   93.2 | 6.5% | 0.527 | 0.1 |       27 | 0.0% |   0.0% |    - | 8.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available