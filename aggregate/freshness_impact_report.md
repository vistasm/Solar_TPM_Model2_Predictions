# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-05 UTC
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
🟡 **X+**: FRESH alert rate (14.5%) is 2.2× the overall rate (6.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.6 | 19.4% | 0.505 | 0.3 |       62 | 83.3% |  34.5% | 1.8× | 6.1% |   0.4677 |
|       OK |   32 |   36.8 | 6.2% | 0.396 | 0.1 |       32 | 50.0% |  25.0% | 4.0× | 3.6% |   0.1250 |
| DEGRADED |   55 |  115.0 | 1.8% | 0.404 | 0.0 |       51 | 0.0% |   0.0% |    - | 2.7% |   0.2745 |
|      ALL |  149 |   55.6 | 10.1% | 0.444 | 0.1 |      145 | 73.3% |  23.4% | 2.3× | 4.1% |   0.3241 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.6 | 8.1% | 0.499 | 0.1 |       62 | 60.0% |  27.3% | 3.4× | 3.9% |   0.1774 |
|       OK |   32 |   36.8 | 0.0% | 0.329 | 0.0 |       32 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   55 |  115.0 | 0.0% | 0.352 | 0.0 |       51 |    - |   0.0% |    - | 0.0% |   0.0588 |
|      ALL |  149 |   55.6 | 3.4% | 0.408 | 0.0 |      145 | 60.0% |  21.4% | 6.2× | 1.5% |   0.0966 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.6 | 14.5% | 0.608 | 0.1 |       62 | 11.1% |  20.0% | 1.4× | 14.0% |   0.0806 |
|       OK |   32 |   36.8 | 3.1% | 0.527 | 0.0 |       32 | 0.0% |      - |    - | 3.1% |   0.0000 |
| DEGRADED |   55 |  115.0 | 0.0% | 0.492 | 0.0 |       51 |    - |   0.0% |    - | 0.0% |   0.0196 |
|      ALL |  149 |   55.6 | 6.7% | 0.548 | 0.1 |      145 | 10.0% |  16.7% | 2.4× | 6.5% |   0.0414 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   14.3 | 21.4% | 0.547 | 0.2 |       14 | 33.3% |  25.0% | 1.2× | 20.0% |   0.2857 |
|       OK |    7 |   34.9 | 14.3% | 0.420 | 0.1 |        7 | 0.0% |   0.0% |    - | 16.7% |   0.1429 |
| DEGRADED |   10 |   90.9 | 0.0% | 0.401 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.5000 |
|      ALL |   31 |   43.6 | 12.9% | 0.471 | 0.1 |       27 | 25.0% |  12.5% | 0.8× | 15.8% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   14.3 | 7.1% | 0.535 | 0.1 |       14 | 0.0% |      - |    - | 7.1% |   0.0000 |
|       OK |    7 |   34.9 | 0.0% | 0.353 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   90.9 | 0.0% | 0.356 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   43.6 | 3.2% | 0.436 | 0.0 |       27 | 0.0% |      - |    - | 3.7% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   14.3 | 7.1% | 0.529 | 0.1 |       14 | 0.0% |      - |    - | 7.1% |   0.0000 |
|       OK |    7 |   34.9 | 0.0% | 0.479 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   90.9 | 0.0% | 0.456 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   43.6 | 3.2% | 0.494 | 0.0 |       27 | 0.0% |      - |    - | 3.7% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available