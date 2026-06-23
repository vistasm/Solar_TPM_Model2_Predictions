# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-23 UTC
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
|    FRESH |   42 |   13.0 | 9.5% | 0.433 | 0.1 |       39 | 100.0% |  23.5% | 2.3× | 0.0% |   0.4359 |
|       OK |   25 |   37.4 | 4.0% | 0.389 | 0.0 |       24 | 100.0% |  33.3% | 8.0× | 0.0% |   0.1250 |
| DEGRADED |   39 |  120.7 | 0.0% | 0.365 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.2564 |
|      ALL |  106 |   58.4 | 4.7% | 0.397 | 0.1 |      102 | 100.0% |  16.7% | 3.4× | 0.0% |   0.2941 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   13.0 | 0.0% | 0.426 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.1282 |
|       OK |   25 |   37.4 | 0.0% | 0.323 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   39 |  120.7 | 0.0% | 0.317 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |  106 |   58.4 | 0.0% | 0.361 | 0.0 |      102 |    - |   0.0% |    - | 0.0% |   0.0784 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   13.0 | 7.1% | 0.587 | 0.1 |       39 | 0.0% |   0.0% |    - | 8.3% |   0.0769 |
|       OK |   25 |   37.4 | 4.0% | 0.541 | 0.0 |       24 | 0.0% |      - |    - | 4.2% |   0.0000 |
| DEGRADED |   39 |  120.7 | 0.0% | 0.473 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.0256 |
|      ALL |  106 |   58.4 | 3.8% | 0.534 | 0.0 |      102 | 0.0% |   0.0% |    - | 4.1% |   0.0392 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.1 | 0.0% | 0.408 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.2222 |
|       OK |    7 |   41.6 | 0.0% | 0.422 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  100.6 | 0.0% | 0.389 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.3333 |
|      ALL |   31 |   53.4 | 0.0% | 0.404 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.1 | 0.0% | 0.417 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    7 |   41.6 | 0.0% | 0.318 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  100.6 | 0.0% | 0.343 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   31 |   53.4 | 0.0% | 0.366 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.1 | 8.3% | 0.578 | 0.1 |        9 | 0.0% |   0.0% |    - | 12.5% |   0.1111 |
|       OK |    7 |   41.6 | 0.0% | 0.575 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  100.6 | 0.0% | 0.503 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   53.4 | 3.2% | 0.548 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available