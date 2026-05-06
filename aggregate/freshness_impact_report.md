# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-06 UTC
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
|    FRESH |   24 |   12.5 | 16.7% | 0.463 | 0.2 |       22 | 100.0% |  30.8% | 1.7× | 0.0% |   0.5909 |
|       OK |   13 |   35.5 | 7.7% | 0.404 | 0.1 |       12 | 100.0% |  33.3% | 4.0× | 0.0% |   0.2500 |
| DEGRADED |   21 |  147.2 | 0.0% | 0.347 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.1500 |
|      ALL |   58 |   66.4 | 8.6% | 0.408 | 0.1 |       54 | 100.0% |  26.3% | 2.8× | 0.0% |   0.3519 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.5 | 0.0% | 0.472 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |   13 |   35.5 | 0.0% | 0.372 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   21 |  147.2 | 0.0% | 0.317 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.0500 |
|      ALL |   58 |   66.4 | 0.0% | 0.394 | 0.0 |       54 |    - |   0.0% |    - | 0.0% |   0.0926 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.5 | 8.3% | 0.604 | 0.1 |       22 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |   13 |   35.5 | 7.7% | 0.523 | 0.1 |       12 | 0.0% |      - |    - | 8.3% |   0.0000 |
| DEGRADED |   21 |  147.2 | 0.0% | 0.434 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.0500 |
|      ALL |   58 |   66.4 | 5.2% | 0.524 | 0.1 |       54 | 0.0% |   0.0% |    - | 5.9% |   0.0556 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.4 | 44.4% | 0.657 | 0.6 |        7 | 100.0% |  80.0% | 1.4× | 0.0% |   0.7143 |
|       OK |    5 |   34.7 | 20.0% | 0.472 | 0.2 |        4 | 100.0% | 100.0% | 4.0× | 0.0% |   0.2500 |
| DEGRADED |   17 |  161.6 | 0.0% | 0.353 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |
|      ALL |   31 |   97.5 | 16.1% | 0.461 | 0.2 |       27 | 100.0% |  62.5% | 3.4× | 0.0% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.4 | 0.0% | 0.605 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.2857 |
|       OK |    5 |   34.7 | 0.0% | 0.360 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  161.6 | 0.0% | 0.312 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   31 |   97.5 | 0.0% | 0.405 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.4 | 22.2% | 0.720 | 0.2 |        7 | 0.0% |   0.0% |    - | 33.3% |   0.1429 |
|       OK |    5 |   34.7 | 0.0% | 0.478 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  161.6 | 0.0% | 0.429 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   31 |   97.5 | 6.5% | 0.521 | 0.1 |       27 | 0.0% |   0.0% |    - | 8.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available