# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-02 UTC
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
|    FRESH |   22 |   13.0 | 18.2% | 0.466 | 0.2 |       21 | 100.0% |  30.8% | 1.6× | 0.0% |   0.6190 |
|       OK |   12 |   36.1 | 8.3% | 0.413 | 0.1 |       11 | 100.0% |  33.3% | 3.7× | 0.0% |   0.2727 |
| DEGRADED |   20 |  152.0 | 0.0% | 0.351 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   54 |   69.6 | 9.3% | 0.412 | 0.1 |       50 | 100.0% |  26.3% | 2.6× | 0.0% |   0.3800 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   22 |   13.0 | 0.0% | 0.482 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.1905 |
|       OK |   12 |   36.1 | 0.0% | 0.384 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   20 |  152.0 | 0.0% | 0.320 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   54 |   69.6 | 0.0% | 0.400 | 0.0 |       50 |    - |   0.0% |    - | 0.0% |   0.1000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   22 |   13.0 | 9.1% | 0.609 | 0.1 |       21 | 0.0% |   0.0% |    - | 10.5% |   0.0952 |
|       OK |   12 |   36.1 | 8.3% | 0.522 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   20 |  152.0 | 0.0% | 0.429 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   54 |   69.6 | 5.6% | 0.523 | 0.1 |       50 | 0.0% |   0.0% |    - | 6.4% |   0.0600 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   10.5 | 36.4% | 0.611 | 0.5 |       10 | 100.0% |  50.0% | 1.2× | 0.0% |   0.8000 |
|       OK |    4 |   36.4 | 25.0% | 0.515 | 0.2 |        3 | 100.0% | 100.0% | 3.0× | 0.0% |   0.3333 |
| DEGRADED |   16 |  168.5 | 0.0% | 0.358 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|      ALL |   31 |   95.4 | 16.1% | 0.468 | 0.2 |       27 | 100.0% |  45.5% | 2.5× | 0.0% |   0.4074 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   10.5 | 0.0% | 0.577 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.3000 |
|       OK |    4 |   36.4 | 0.0% | 0.392 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  168.5 | 0.0% | 0.315 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   95.4 | 0.0% | 0.418 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   10.5 | 18.2% | 0.684 | 0.2 |       10 | 0.0% |   0.0% |    - | 22.2% |   0.1000 |
|       OK |    4 |   36.4 | 0.0% | 0.463 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  168.5 | 0.0% | 0.422 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   95.4 | 6.5% | 0.520 | 0.1 |       27 | 0.0% |   0.0% |    - | 8.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available