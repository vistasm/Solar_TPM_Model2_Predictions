# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-12 UTC
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
|    FRESH |   26 |   12.7 | 15.4% | 0.464 | 0.2 |       25 | 100.0% |  28.6% | 1.8× | 0.0% |   0.5600 |
|       OK |   15 |   36.0 | 6.7% | 0.409 | 0.1 |       13 | 100.0% |  33.3% | 4.3× | 0.0% |   0.2308 |
| DEGRADED |   23 |  140.5 | 0.0% | 0.343 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.1818 |
|      ALL |   64 |   64.1 | 7.8% | 0.407 | 0.1 |       60 | 100.0% |  23.8% | 2.9× | 0.0% |   0.3500 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   26 |   12.7 | 0.0% | 0.465 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.1600 |
|       OK |   15 |   36.0 | 0.0% | 0.364 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   23 |  140.5 | 0.0% | 0.313 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |
|      ALL |   64 |   64.1 | 0.0% | 0.387 | 0.0 |       60 |    - |   0.0% |    - | 0.0% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   26 |   12.7 | 7.7% | 0.600 | 0.1 |       25 | 0.0% |   0.0% |    - | 8.7% |   0.0800 |
|       OK |   15 |   36.0 | 6.7% | 0.527 | 0.1 |       13 | 0.0% |      - |    - | 7.7% |   0.0000 |
| DEGRADED |   23 |  140.5 | 0.0% | 0.444 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |
|      ALL |   64 |   64.1 | 4.7% | 0.527 | 0.1 |       60 | 0.0% |   0.0% |    - | 5.3% |   0.0500 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.2 | 40.0% | 0.658 | 0.5 |        9 | 100.0% |  66.7% | 1.5× | 0.0% |   0.6667 |
|       OK |    4 |   36.5 | 0.0% | 0.421 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  161.9 | 0.0% | 0.351 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1875 |
|      ALL |   31 |   97.1 | 12.9% | 0.460 | 0.2 |       27 | 100.0% |  44.4% | 3.0× | 0.0% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.2 | 0.0% | 0.609 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.2222 |
|       OK |    4 |   36.5 | 0.0% | 0.300 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  161.9 | 0.0% | 0.315 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   31 |   97.1 | 0.0% | 0.408 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.2 | 20.0% | 0.711 | 0.2 |        9 | 0.0% |   0.0% |    - | 25.0% |   0.1111 |
|       OK |    4 |   36.5 | 0.0% | 0.542 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  161.9 | 0.0% | 0.434 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   31 |   97.1 | 6.5% | 0.537 | 0.1 |       27 | 0.0% |   0.0% |    - | 8.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available