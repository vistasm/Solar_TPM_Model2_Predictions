# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-21 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (9.8%) is 2.0× the overall rate (4.8%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   41 |   13.1 | 9.8% | 0.426 | 0.1 |       39 | 100.0% |  23.5% | 2.3× | 0.0% |   0.4359 |
|       OK |   24 |   37.5 | 4.2% | 0.375 | 0.0 |       24 | 100.0% |  33.3% | 8.0× | 0.0% |   0.1250 |
| DEGRADED |   39 |  120.7 | 0.0% | 0.365 | 0.0 |       37 |    - |   0.0% |    - | 0.0% |   0.2432 |
|      ALL |  104 |   59.1 | 4.8% | 0.391 | 0.1 |      100 | 100.0% |  17.2% | 3.5× | 0.0% |   0.2900 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   41 |   13.1 | 0.0% | 0.427 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.1282 |
|       OK |   24 |   37.5 | 0.0% | 0.321 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   39 |  120.7 | 0.0% | 0.317 | 0.0 |       37 |    - |   0.0% |    - | 0.0% |   0.0811 |
|      ALL |  104 |   59.1 | 0.0% | 0.361 | 0.0 |      100 |    - |   0.0% |    - | 0.0% |   0.0800 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   41 |   13.1 | 7.3% | 0.587 | 0.1 |       39 | 0.0% |   0.0% |    - | 8.3% |   0.0769 |
|       OK |   24 |   37.5 | 4.2% | 0.536 | 0.0 |       24 | 0.0% |      - |    - | 4.2% |   0.0000 |
| DEGRADED |   39 |  120.7 | 0.0% | 0.473 | 0.0 |       37 |    - |   0.0% |    - | 0.0% |   0.0270 |
|      ALL |  104 |   59.1 | 3.9% | 0.533 | 0.0 |      100 | 0.0% |   0.0% |    - | 4.2% |   0.0400 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.9 | 0.0% | 0.374 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.2000 |
|       OK |    6 |   42.9 | 0.0% | 0.371 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   98.0 | 0.0% | 0.392 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.3636 |
|      ALL |   31 |   54.8 | 0.0% | 0.381 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.9 | 0.0% | 0.398 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    6 |   42.9 | 0.0% | 0.312 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   98.0 | 0.0% | 0.340 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   31 |   54.8 | 0.0% | 0.357 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.9 | 8.3% | 0.572 | 0.1 |       10 | 0.0% |   0.0% |    - | 11.1% |   0.1000 |
|       OK |    6 |   42.9 | 0.0% | 0.562 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   98.0 | 0.0% | 0.507 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   54.8 | 3.2% | 0.543 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available