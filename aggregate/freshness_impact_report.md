# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-26 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (9.5%) is 2.1× the overall rate (4.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   13.0 | 9.5% | 0.433 | 0.1 |       42 | 100.0% |  21.1% | 2.2× | 0.0% |   0.4524 |
|       OK |   25 |   37.4 | 4.0% | 0.389 | 0.0 |       24 | 100.0% |  33.3% | 8.0× | 0.0% |   0.1250 |
| DEGRADED |   42 |  117.9 | 0.0% | 0.386 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.2564 |
|      ALL |  109 |   59.0 | 4.6% | 0.405 | 0.1 |      105 | 100.0% |  15.6% | 3.3× | 0.0% |   0.3048 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   13.0 | 0.0% | 0.426 | 0.0 |       42 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |   25 |   37.4 | 0.0% | 0.323 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   42 |  117.9 | 0.0% | 0.330 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |  109 |   59.0 | 0.0% | 0.365 | 0.0 |      105 |    - |   0.0% |    - | 0.0% |   0.0857 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   13.0 | 7.1% | 0.587 | 0.1 |       42 | 0.0% |   0.0% |    - | 7.7% |   0.0714 |
|       OK |   25 |   37.4 | 4.0% | 0.541 | 0.0 |       24 | 0.0% |      - |    - | 4.2% |   0.0000 |
| DEGRADED |   42 |  117.9 | 0.0% | 0.483 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.0256 |
|      ALL |  109 |   59.0 | 3.7% | 0.536 | 0.0 |      105 | 0.0% |   0.0% |    - | 4.0% |   0.0381 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.1 | 0.0% | 0.408 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.3333 |
|       OK |    6 |   41.4 | 0.0% | 0.404 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   99.6 | 0.0% | 0.439 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.4000 |
|      ALL |   31 |   54.9 | 0.0% | 0.420 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.1 | 0.0% | 0.417 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    6 |   41.4 | 0.0% | 0.295 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   99.6 | 0.0% | 0.367 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|      ALL |   31 |   54.9 | 0.0% | 0.372 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.1 | 8.3% | 0.578 | 0.1 |       12 | 0.0% |   0.0% |    - | 9.1% |   0.0833 |
|       OK |    6 |   41.4 | 0.0% | 0.576 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   99.6 | 0.0% | 0.514 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   54.9 | 3.2% | 0.551 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available