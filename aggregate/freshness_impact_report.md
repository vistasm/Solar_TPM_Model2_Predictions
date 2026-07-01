# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-01 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **X+**: FRESH alert rate (9.1%) is 2.1× the overall rate (4.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   44 |   12.7 | 11.4% | 0.448 | 0.1 |       42 | 100.0% |  21.1% | 2.2× | 0.0% |   0.4524 |
|       OK |   25 |   37.4 | 4.0% | 0.389 | 0.0 |       25 | 100.0% |  33.3% | 8.3× | 0.0% |   0.1200 |
| DEGRADED |   45 |  120.4 | 2.2% | 0.405 | 0.0 |       43 | 0.0% |   0.0% |    - | 3.0% |   0.2326 |
|      ALL |  114 |   60.6 | 6.1% | 0.418 | 0.1 |      110 | 83.3% |  15.6% | 2.9× | 1.3% |   0.2909 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   44 |   12.7 | 0.0% | 0.443 | 0.0 |       42 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |   25 |   37.4 | 0.0% | 0.323 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   45 |  120.4 | 0.0% | 0.351 | 0.0 |       43 |    - |   0.0% |    - | 0.0% |   0.0698 |
|      ALL |  114 |   60.6 | 0.0% | 0.380 | 0.0 |      110 |    - |   0.0% |    - | 0.0% |   0.0818 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   44 |   12.7 | 9.1% | 0.599 | 0.1 |       42 | 0.0% |   0.0% |    - | 7.7% |   0.0714 |
|       OK |   25 |   37.4 | 4.0% | 0.541 | 0.0 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |
| DEGRADED |   45 |  120.4 | 0.0% | 0.500 | 0.0 |       43 |    - |   0.0% |    - | 0.0% |   0.0233 |
|      ALL |  114 |   60.6 | 4.4% | 0.547 | 0.0 |      110 | 0.0% |   0.0% |    - | 3.8% |   0.0364 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.4 | 7.7% | 0.477 | 0.1 |       11 |    - |   0.0% |    - | 0.0% |   0.3636 |
|       OK |    5 |   40.4 | 0.0% | 0.371 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  103.1 | 7.7% | 0.487 | 0.1 |       11 | 0.0% |   0.0% |    - | 12.5% |   0.2727 |
|      ALL |   31 |   54.5 | 6.5% | 0.464 | 0.1 |       27 | 0.0% |   0.0% |    - | 5.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.4 | 0.0% | 0.488 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |    5 |   40.4 | 0.0% | 0.283 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  103.1 | 0.0% | 0.440 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   31 |   54.5 | 0.0% | 0.435 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.4 | 15.4% | 0.621 | 0.1 |       11 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |    5 |   40.4 | 0.0% | 0.577 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  103.1 | 0.0% | 0.550 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   54.5 | 6.5% | 0.584 | 0.1 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available