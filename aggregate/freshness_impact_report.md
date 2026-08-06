# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-06 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (83.3%) is 83.3% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (8.1%) is 2.4× the overall rate (3.3%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (14.5%) is 2.2× the overall rate (6.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.6 | 19.4% | 0.505 | 0.3 |       62 | 83.3% |  34.5% | 1.8× | 6.1% |   0.4677 |
|       OK |   32 |   36.8 | 6.2% | 0.396 | 0.1 |       32 | 50.0% |  25.0% | 4.0× | 3.6% |   0.1250 |
| DEGRADED |   56 |  115.7 | 1.8% | 0.401 | 0.0 |       52 | 0.0% |   0.0% |    - | 2.6% |   0.2692 |
|      ALL |  150 |   56.3 | 10.0% | 0.443 | 0.1 |      146 | 73.3% |  23.4% | 2.3× | 4.0% |   0.3219 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.6 | 8.1% | 0.499 | 0.1 |       62 | 60.0% |  27.3% | 3.4× | 3.9% |   0.1774 |
|       OK |   32 |   36.8 | 0.0% | 0.329 | 0.0 |       32 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   56 |  115.7 | 0.0% | 0.348 | 0.0 |       52 |    - |   0.0% |    - | 0.0% |   0.0577 |
|      ALL |  150 |   56.3 | 3.3% | 0.406 | 0.0 |      146 | 60.0% |  21.4% | 6.3× | 1.5% |   0.0959 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.6 | 14.5% | 0.608 | 0.1 |       62 | 11.1% |  20.0% | 1.4× | 14.0% |   0.0806 |
|       OK |   32 |   36.8 | 3.1% | 0.527 | 0.0 |       32 | 0.0% |      - |    - | 3.1% |   0.0000 |
| DEGRADED |   56 |  115.7 | 0.0% | 0.493 | 0.0 |       52 |    - |   0.0% |    - | 0.0% |   0.0192 |
|      ALL |  150 |   56.3 | 6.7% | 0.548 | 0.1 |      146 | 10.0% |  16.7% | 2.4× | 6.4% |   0.0411 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.7 | 15.4% | 0.513 | 0.1 |       13 | 50.0% |  25.0% | 1.6× | 11.1% |   0.3077 |
|       OK |    7 |   34.9 | 14.3% | 0.420 | 0.1 |        7 | 0.0% |   0.0% |    - | 16.7% |   0.1429 |
| DEGRADED |   11 |   96.9 | 0.0% | 0.381 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.4286 |
|      ALL |   31 |   48.4 | 9.7% | 0.445 | 0.1 |       27 | 33.3% |  12.5% | 1.1× | 10.5% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.7 | 0.0% | 0.505 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   34.9 | 0.0% | 0.353 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |   96.9 | 0.0% | 0.336 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   48.4 | 0.0% | 0.411 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.7 | 0.0% | 0.495 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   34.9 | 0.0% | 0.479 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |   96.9 | 0.0% | 0.464 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   48.4 | 0.0% | 0.480 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available