# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-03 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (83.3%) is 83.3% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (8.1%) is 2.4× the overall rate (3.4%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (14.5%) is 2.1× the overall rate (6.8%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.6 | 19.4% | 0.505 | 0.3 |       61 | 83.3% |  34.5% | 1.8× | 6.2% |   0.4754 |
|       OK |   32 |   36.8 | 6.2% | 0.396 | 0.1 |       31 | 100.0% |  25.0% | 7.8× | 0.0% |   0.1290 |
| DEGRADED |   53 |  114.8 | 1.9% | 0.402 | 0.0 |       51 | 0.0% |   0.0% |    - | 2.7% |   0.2745 |
|      ALL |  147 |   54.7 | 10.2% | 0.444 | 0.1 |      143 | 78.6% |  23.4% | 2.4× | 3.1% |   0.3287 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.6 | 8.1% | 0.499 | 0.1 |       61 | 60.0% |  27.3% | 3.3× | 4.0% |   0.1803 |
|       OK |   32 |   36.8 | 0.0% | 0.329 | 0.0 |       31 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   53 |  114.8 | 0.0% | 0.346 | 0.0 |       51 |    - |   0.0% |    - | 0.0% |   0.0588 |
|      ALL |  147 |   54.7 | 3.4% | 0.407 | 0.0 |      143 | 60.0% |  21.4% | 6.1× | 1.6% |   0.0979 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.6 | 14.5% | 0.608 | 0.1 |       61 | 11.1% |  20.0% | 1.4× | 14.3% |   0.0820 |
|       OK |   32 |   36.8 | 3.1% | 0.527 | 0.0 |       31 | 0.0% |      - |    - | 3.2% |   0.0000 |
| DEGRADED |   53 |  114.8 | 0.0% | 0.489 | 0.0 |       51 |    - |   0.0% |    - | 0.0% |   0.0196 |
|      ALL |  147 |   54.7 | 6.8% | 0.548 | 0.1 |      143 | 10.0% |  16.7% | 2.4× | 6.6% |   0.0420 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.0 | 31.2% | 0.601 | 0.6 |       15 | 60.0% |  50.0% | 1.5× | 22.2% |   0.4000 |
|       OK |    7 |   34.9 | 14.3% | 0.420 | 0.1 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
| DEGRADED |    8 |   83.4 | 0.0% | 0.384 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.5000 |
|      ALL |   31 |   36.1 | 19.4% | 0.504 | 0.3 |       27 | 60.0% |  30.0% | 1.6× | 11.8% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.0 | 18.8% | 0.592 | 0.2 |       15 | 66.7% | 100.0% | 5.0× | 7.7% |   0.1333 |
|       OK |    7 |   34.9 | 0.0% | 0.353 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |   83.4 | 0.0% | 0.322 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   36.1 | 9.7% | 0.468 | 0.1 |       27 | 66.7% | 100.0% | 9.0× | 4.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.0 | 18.8% | 0.587 | 0.2 |       15 | 33.3% | 100.0% | 5.0× | 14.3% |   0.0667 |
|       OK |    7 |   34.9 | 0.0% | 0.479 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |   83.4 | 0.0% | 0.426 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   36.1 | 9.7% | 0.521 | 0.1 |       27 | 33.3% | 100.0% | 9.0× | 7.7% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available