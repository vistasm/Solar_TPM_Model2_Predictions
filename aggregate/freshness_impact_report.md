# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-27 UTC
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
|    FRESH |   20 |   12.4 | 15.0% | 0.436 | 0.2 |       16 |    - |   0.0% |    - | 0.0% |   0.5000 |
|       OK |   11 |   35.8 | 9.1% | 0.405 | 0.1 |       11 | 100.0% |  33.3% | 3.7× | 0.0% |   0.2727 |
| DEGRADED |   18 |  160.5 | 0.0% | 0.338 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   49 |   72.0 | 8.2% | 0.393 | 0.1 |       45 | 100.0% |   7.1% | 3.2× | 0.0% |   0.3111 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   20 |   12.4 | 0.0% | 0.459 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   11 |   35.8 | 0.0% | 0.387 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  160.5 | 0.0% | 0.325 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   49 |   72.0 | 0.0% | 0.394 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0667 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   20 |   12.4 | 10.0% | 0.591 | 0.1 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|       OK |   11 |   35.8 | 9.1% | 0.522 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   18 |  160.5 | 0.0% | 0.416 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   49 |   72.0 | 6.1% | 0.511 | 0.1 |       45 | 0.0% |   0.0% |    - | 2.3% |   0.0444 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |    9.7 | 25.0% | 0.500 | 0.3 |        8 |    - |   0.0% |    - | 0.0% |   0.5000 |
|       OK |    5 |   35.9 | 20.0% | 0.514 | 0.2 |        5 | 100.0% | 100.0% | 5.0× | 0.0% |   0.2000 |
| DEGRADED |   14 |  181.7 | 0.0% | 0.342 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|      ALL |   31 |   91.6 | 12.9% | 0.431 | 0.2 |       27 | 100.0% |  14.3% | 3.9× | 0.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |    9.7 | 0.0% | 0.497 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|       OK |    5 |   35.9 | 0.0% | 0.433 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  181.7 | 0.0% | 0.321 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   91.6 | 0.0% | 0.407 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |    9.7 | 16.7% | 0.678 | 0.2 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    5 |   35.9 | 20.0% | 0.607 | 0.2 |        5 | 0.0% |      - |    - | 20.0% |   0.0000 |
| DEGRADED |   14 |  181.7 | 0.0% | 0.404 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   91.6 | 9.7% | 0.543 | 0.1 |       27 | 0.0% |   0.0% |    - | 4.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available