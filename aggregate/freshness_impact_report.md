# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-25 UTC
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
|    FRESH |   18 |   13.1 | 5.6% | 0.393 | 0.1 |       16 |    - |   0.0% |    - | 0.0% |   0.5000 |
|       OK |   11 |   35.8 | 9.1% | 0.405 | 0.1 |       11 | 100.0% |  33.3% | 3.7× | 0.0% |   0.2727 |
| DEGRADED |   18 |  160.5 | 0.0% | 0.338 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   47 |   74.8 | 4.3% | 0.374 | 0.1 |       43 | 100.0% |   8.3% | 3.6× | 0.0% |   0.2791 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   13.1 | 0.0% | 0.428 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   11 |   35.8 | 0.0% | 0.387 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  160.5 | 0.0% | 0.325 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   47 |   74.8 | 0.0% | 0.379 | 0.0 |       43 |    - |   0.0% |    - | 0.0% |   0.0465 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   13.1 | 5.6% | 0.563 | 0.1 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|       OK |   11 |   35.8 | 9.1% | 0.522 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   18 |  160.5 | 0.0% | 0.416 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   47 |   74.8 | 4.3% | 0.497 | 0.0 |       43 | 0.0% |   0.0% |    - | 2.4% |   0.0233 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   11.7 | 9.1% | 0.437 | 0.2 |        9 |    - |   0.0% |    - | 0.0% |   0.5556 |
|       OK |    6 |   34.8 | 16.7% | 0.478 | 0.2 |        6 | 100.0% |  50.0% | 3.0× | 0.0% |   0.3333 |
| DEGRADED |   14 |  181.7 | 0.0% | 0.342 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   93.0 | 6.5% | 0.402 | 0.1 |       27 | 100.0% |  14.3% | 3.9× | 0.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   11.7 | 0.0% | 0.470 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.2222 |
|       OK |    6 |   34.8 | 0.0% | 0.425 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  181.7 | 0.0% | 0.321 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   93.0 | 0.0% | 0.394 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   11.7 | 9.1% | 0.658 | 0.1 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    6 |   34.8 | 16.7% | 0.609 | 0.2 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
| DEGRADED |   14 |  181.7 | 0.0% | 0.404 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   93.0 | 6.5% | 0.534 | 0.1 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available