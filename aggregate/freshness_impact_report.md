# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-24 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (9.5%) is 2.0× the overall rate (4.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   13.0 | 9.5% | 0.433 | 0.1 |       40 | 100.0% |  22.2% | 2.2× | 0.0% |   0.4500 |
|       OK |   25 |   37.4 | 4.0% | 0.389 | 0.0 |       24 | 100.0% |  33.3% | 8.0× | 0.0% |   0.1250 |
| DEGRADED |   40 |  119.1 | 0.0% | 0.368 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.2564 |
|      ALL |  107 |   58.4 | 4.7% | 0.398 | 0.1 |      103 | 100.0% |  16.1% | 3.3× | 0.0% |   0.3010 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   13.0 | 0.0% | 0.426 | 0.0 |       40 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   25 |   37.4 | 0.0% | 0.323 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   40 |  119.1 | 0.0% | 0.315 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |  107 |   58.4 | 0.0% | 0.360 | 0.0 |      103 |    - |   0.0% |    - | 0.0% |   0.0777 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   13.0 | 7.1% | 0.587 | 0.1 |       40 | 0.0% |   0.0% |    - | 8.1% |   0.0750 |
|       OK |   25 |   37.4 | 4.0% | 0.541 | 0.0 |       24 | 0.0% |      - |    - | 4.2% |   0.0000 |
| DEGRADED |   40 |  119.1 | 0.0% | 0.475 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.0256 |
|      ALL |  107 |   58.4 | 3.7% | 0.534 | 0.0 |      103 | 0.0% |   0.0% |    - | 4.0% |   0.0388 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.1 | 0.0% | 0.408 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.3000 |
|       OK |    6 |   41.4 | 0.0% | 0.404 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   97.3 | 0.0% | 0.398 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.3333 |
|      ALL |   31 |   53.9 | 0.0% | 0.403 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.1 | 0.0% | 0.417 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    6 |   41.4 | 0.0% | 0.295 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   97.3 | 0.0% | 0.335 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   31 |   53.9 | 0.0% | 0.359 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.1 | 8.3% | 0.578 | 0.1 |       10 | 0.0% |   0.0% |    - | 11.1% |   0.1000 |
|       OK |    6 |   41.4 | 0.0% | 0.576 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   97.3 | 0.0% | 0.506 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   53.9 | 3.2% | 0.547 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available