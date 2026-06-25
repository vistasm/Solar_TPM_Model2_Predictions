# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-25 UTC
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
|    FRESH |   42 |   13.0 | 9.5% | 0.433 | 0.1 |       41 | 100.0% |  21.1% | 2.2× | 0.0% |   0.4634 |
|       OK |   25 |   37.4 | 4.0% | 0.389 | 0.0 |       24 | 100.0% |  33.3% | 8.0× | 0.0% |   0.1250 |
| DEGRADED |   41 |  118.2 | 0.0% | 0.377 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.2564 |
|      ALL |  108 |   58.6 | 4.6% | 0.402 | 0.1 |      104 | 100.0% |  15.6% | 3.2× | 0.0% |   0.3077 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   13.0 | 0.0% | 0.426 | 0.0 |       41 |    - |   0.0% |    - | 0.0% |   0.1463 |
|       OK |   25 |   37.4 | 0.0% | 0.323 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   41 |  118.2 | 0.0% | 0.323 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |  108 |   58.6 | 0.0% | 0.363 | 0.0 |      104 |    - |   0.0% |    - | 0.0% |   0.0865 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   42 |   13.0 | 7.1% | 0.587 | 0.1 |       41 | 0.0% |   0.0% |    - | 7.9% |   0.0732 |
|       OK |   25 |   37.4 | 4.0% | 0.541 | 0.0 |       24 | 0.0% |      - |    - | 4.2% |   0.0000 |
| DEGRADED |   41 |  118.2 | 0.0% | 0.476 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.0256 |
|      ALL |  108 |   58.6 | 3.7% | 0.534 | 0.0 |      104 | 0.0% |   0.0% |    - | 4.0% |   0.0385 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.1 | 0.0% | 0.408 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.3636 |
|       OK |    6 |   41.4 | 0.0% | 0.404 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   98.5 | 0.0% | 0.412 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.3636 |
|      ALL |   31 |   54.4 | 0.0% | 0.409 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.1 | 0.0% | 0.417 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |    6 |   41.4 | 0.0% | 0.295 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   98.5 | 0.0% | 0.346 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   31 |   54.4 | 0.0% | 0.363 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.1 | 8.3% | 0.578 | 0.1 |       11 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |    6 |   41.4 | 0.0% | 0.576 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   98.5 | 0.0% | 0.498 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   54.4 | 3.2% | 0.544 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available