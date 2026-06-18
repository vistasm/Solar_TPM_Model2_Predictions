# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-18 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (10.3%) is 2.1× the overall rate (5.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.3 | 10.3% | 0.436 | 0.1 |       39 | 100.0% |  23.5% | 2.3× | 0.0% |   0.4359 |
|       OK |   24 |   37.5 | 4.2% | 0.375 | 0.0 |       23 | 100.0% |  33.3% | 7.7× | 0.0% |   0.1304 |
| DEGRADED |   38 |  120.3 | 0.0% | 0.370 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.2571 |
|      ALL |  101 |   59.3 | 5.0% | 0.397 | 0.1 |       97 | 100.0% |  17.2% | 3.3× | 0.0% |   0.2990 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.3 | 0.0% | 0.438 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.1282 |
|       OK |   24 |   37.5 | 0.0% | 0.321 | 0.0 |       23 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   38 |  120.3 | 0.0% | 0.320 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.0857 |
|      ALL |  101 |   59.3 | 0.0% | 0.366 | 0.0 |       97 |    - |   0.0% |    - | 0.0% |   0.0825 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.3 | 7.7% | 0.596 | 0.1 |       39 | 0.0% |   0.0% |    - | 8.3% |   0.0769 |
|       OK |   24 |   37.5 | 4.2% | 0.536 | 0.0 |       23 | 0.0% |      - |    - | 4.3% |   0.0000 |
| DEGRADED |   38 |  120.3 | 0.0% | 0.477 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.0286 |
|      ALL |  101 |   59.3 | 4.0% | 0.537 | 0.0 |       97 | 0.0% |   0.0% |    - | 4.3% |   0.0412 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   15.2 | 0.0% | 0.379 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |    7 |   42.9 | 0.0% | 0.349 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   91.4 | 0.0% | 0.398 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.4000 |
|      ALL |   31 |   53.4 | 0.0% | 0.380 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   15.2 | 0.0% | 0.401 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|       OK |    7 |   42.9 | 0.0% | 0.285 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   91.4 | 0.0% | 0.335 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|      ALL |   31 |   53.4 | 0.0% | 0.347 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   15.2 | 9.1% | 0.596 | 0.1 |       11 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |    7 |   42.9 | 0.0% | 0.556 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   91.4 | 0.0% | 0.521 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   53.4 | 3.2% | 0.555 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available