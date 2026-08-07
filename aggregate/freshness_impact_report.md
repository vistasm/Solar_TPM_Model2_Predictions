# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-07 UTC
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
🟡 **X+**: FRESH alert rate (14.5%) is 2.2× the overall rate (6.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.6 | 19.4% | 0.505 | 0.3 |       62 | 83.3% |  34.5% | 1.8× | 6.1% |   0.4677 |
|       OK |   32 |   36.8 | 6.2% | 0.396 | 0.1 |       32 | 50.0% |  25.0% | 4.0× | 3.6% |   0.1250 |
| DEGRADED |   57 |  116.9 | 1.8% | 0.400 | 0.0 |       53 | 0.0% |   0.0% |    - | 2.6% |   0.2642 |
|      ALL |  151 |   57.1 | 9.9% | 0.442 | 0.1 |      147 | 73.3% |  23.4% | 2.3× | 4.0% |   0.3197 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.6 | 8.1% | 0.499 | 0.1 |       62 | 60.0% |  27.3% | 3.4× | 3.9% |   0.1774 |
|       OK |   32 |   36.8 | 0.0% | 0.329 | 0.0 |       32 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   57 |  116.9 | 0.0% | 0.346 | 0.0 |       53 |    - |   0.0% |    - | 0.0% |   0.0566 |
|      ALL |  151 |   57.1 | 3.3% | 0.405 | 0.0 |      147 | 60.0% |  21.4% | 6.3× | 1.5% |   0.0952 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.6 | 14.5% | 0.608 | 0.1 |       62 | 11.1% |  20.0% | 1.4× | 14.0% |   0.0806 |
|       OK |   32 |   36.8 | 3.1% | 0.527 | 0.0 |       32 | 0.0% |      - |    - | 3.1% |   0.0000 |
| DEGRADED |   57 |  116.9 | 0.0% | 0.493 | 0.0 |       53 |    - |   0.0% |    - | 0.0% |   0.0189 |
|      ALL |  151 |   57.1 | 6.6% | 0.548 | 0.1 |      147 | 10.0% |  16.7% | 2.5× | 6.4% |   0.0408 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.7 | 15.4% | 0.513 | 0.1 |       13 | 50.0% |  25.0% | 1.6× | 11.1% |   0.3077 |
|       OK |    6 |   36.6 | 16.7% | 0.390 | 0.2 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
| DEGRADED |   12 |  103.8 | 0.0% | 0.382 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.3750 |
|      ALL |   31 |   53.5 | 9.7% | 0.438 | 0.1 |       27 | 33.3% |  14.3% | 1.3× | 10.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.7 | 0.0% | 0.505 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.6 | 0.0% | 0.306 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  103.8 | 0.0% | 0.328 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   53.5 | 0.0% | 0.398 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.7 | 0.0% | 0.495 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.6 | 0.0% | 0.449 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  103.8 | 0.0% | 0.468 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   53.5 | 0.0% | 0.476 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available