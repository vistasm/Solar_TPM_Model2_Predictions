# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-10 UTC
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
| DEGRADED |   23 |  140.5 | 0.0% | 0.343 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.1429 |
|      ALL |   62 |   65.2 | 8.1% | 0.398 | 0.1 |       58 | 100.0% |  25.0% | 2.9× | 0.0% |   0.3448 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   25 |   12.6 | 0.0% | 0.460 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |   14 |   35.7 | 0.0% | 0.358 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   23 |  140.5 | 0.0% | 0.313 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.0476 |
|      ALL |   62 |   65.2 | 0.0% | 0.383 | 0.0 |       58 |    - |   0.0% |    - | 0.0% |   0.0862 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   25 |   12.6 | 8.0% | 0.600 | 0.1 |       24 | 0.0% |   0.0% |    - | 9.1% |   0.0833 |
|       OK |   14 |   35.7 | 7.1% | 0.523 | 0.1 |       13 | 0.0% |      - |    - | 7.7% |   0.0000 |
| DEGRADED |   23 |  140.5 | 0.0% | 0.444 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.0476 |
|      ALL |   62 |   65.2 | 4.8% | 0.525 | 0.1 |       58 | 0.0% |   0.0% |    - | 5.5% |   0.0517 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.7 | 40.0% | 0.611 | 0.5 |        9 | 100.0% |  66.7% | 1.5× | 0.0% |   0.6667 |
|       OK |    4 |   37.8 | 0.0% | 0.315 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  161.9 | 0.0% | 0.351 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|      ALL |   31 |   97.4 | 12.9% | 0.430 | 0.2 |       27 | 100.0% |  50.0% | 3.4× | 0.0% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.7 | 0.0% | 0.561 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.2222 |
|       OK |    4 |   37.8 | 0.0% | 0.252 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  161.9 | 0.0% | 0.315 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   31 |   97.4 | 0.0% | 0.386 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.7 | 20.0% | 0.700 | 0.2 |        9 | 0.0% |   0.0% |    - | 25.0% |   0.1111 |
|       OK |    4 |   37.8 | 0.0% | 0.479 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  161.9 | 0.0% | 0.434 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   31 |   97.4 | 6.5% | 0.525 | 0.1 |       27 | 0.0% |   0.0% |    - | 8.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available