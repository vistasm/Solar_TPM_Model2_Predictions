# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-01 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (83.3%) is 83.3% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (8.1%) is 2.3× the overall rate (3.5%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (14.5%) is 2.1× the overall rate (6.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.6 | 19.4% | 0.505 | 0.3 |       61 | 83.3% |  34.5% | 1.8× | 6.2% |   0.4754 |
|       OK |   32 |   36.8 | 6.2% | 0.396 | 0.1 |       30 | 100.0% |  25.0% | 7.5× | 0.0% |   0.1333 |
| DEGRADED |   51 |  116.4 | 2.0% | 0.398 | 0.0 |       50 | 0.0% |   0.0% |    - | 2.7% |   0.2600 |
|      ALL |  145 |   54.5 | 10.3% | 0.443 | 0.1 |      141 | 78.6% |  23.9% | 2.4× | 3.2% |   0.3262 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.6 | 8.1% | 0.499 | 0.1 |       61 | 60.0% |  27.3% | 3.3× | 4.0% |   0.1803 |
|       OK |   32 |   36.8 | 0.0% | 0.329 | 0.0 |       30 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   51 |  116.4 | 0.0% | 0.338 | 0.0 |       50 |    - |   0.0% |    - | 0.0% |   0.0600 |
|      ALL |  145 |   54.5 | 3.5% | 0.405 | 0.0 |      141 | 60.0% |  21.4% | 6.0× | 1.6% |   0.0993 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.6 | 14.5% | 0.608 | 0.1 |       61 | 11.1% |  20.0% | 1.4× | 14.3% |   0.0820 |
|       OK |   32 |   36.8 | 3.1% | 0.527 | 0.0 |       30 | 0.0% |      - |    - | 3.3% |   0.0000 |
| DEGRADED |   51 |  116.4 | 0.0% | 0.486 | 0.0 |       50 |    - |   0.0% |    - | 0.0% |   0.0200 |
|      ALL |  145 |   54.5 | 6.9% | 0.547 | 0.1 |      141 | 10.0% |  16.7% | 2.4× | 6.7% |   0.0426 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   12.2 | 38.9% | 0.644 | 0.7 |       17 | 71.4% |  62.5% | 1.5× | 22.2% |   0.4706 |
|       OK |    7 |   34.9 | 14.3% | 0.420 | 0.1 |        5 |    - |   0.0% |    - | 0.0% |   0.2000 |
| DEGRADED |    6 |   87.0 | 0.0% | 0.346 | 0.0 |        5 |    - |   0.0% |    - | 0.0% |   0.4000 |
|      ALL |   31 |   31.8 | 25.8% | 0.536 | 0.5 |       27 | 71.4% |  45.5% | 1.8× | 12.5% |   0.4074 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   12.2 | 27.8% | 0.635 | 0.3 |       17 | 60.0% | 100.0% | 3.4× | 14.3% |   0.1765 |
|       OK |    7 |   34.9 | 0.0% | 0.353 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   87.0 | 0.0% | 0.242 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   31.8 | 16.1% | 0.495 | 0.2 |       27 | 60.0% | 100.0% | 5.4× | 8.3% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   12.2 | 27.8% | 0.631 | 0.3 |       17 | 20.0% | 100.0% | 3.4× | 25.0% |   0.0588 |
|       OK |    7 |   34.9 | 0.0% | 0.479 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   87.0 | 0.0% | 0.382 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   31.8 | 16.1% | 0.548 | 0.2 |       27 | 20.0% | 100.0% | 5.4× | 15.4% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available