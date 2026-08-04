# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-04 UTC
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
|    FRESH |   62 |   12.6 | 19.4% | 0.505 | 0.3 |       62 | 83.3% |  34.5% | 1.8× | 6.1% |   0.4677 |
|       OK |   32 |   36.8 | 6.2% | 0.396 | 0.1 |       31 | 100.0% |  25.0% | 7.8× | 0.0% |   0.1290 |
| DEGRADED |   54 |  114.7 | 1.8% | 0.403 | 0.0 |       51 | 0.0% |   0.0% |    - | 2.7% |   0.2745 |
|      ALL |  148 |   55.1 | 10.1% | 0.444 | 0.1 |      144 | 78.6% |  23.4% | 2.4× | 3.1% |   0.3264 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.6 | 8.1% | 0.499 | 0.1 |       62 | 60.0% |  27.3% | 3.4× | 3.9% |   0.1774 |
|       OK |   32 |   36.8 | 0.0% | 0.329 | 0.0 |       31 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   54 |  114.7 | 0.0% | 0.350 | 0.0 |       51 |    - |   0.0% |    - | 0.0% |   0.0588 |
|      ALL |  148 |   55.1 | 3.4% | 0.408 | 0.0 |      144 | 60.0% |  21.4% | 6.2× | 1.5% |   0.0972 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.6 | 14.5% | 0.608 | 0.1 |       62 | 11.1% |  20.0% | 1.4× | 14.0% |   0.0806 |
|       OK |   32 |   36.8 | 3.1% | 0.527 | 0.0 |       31 | 0.0% |      - |    - | 3.2% |   0.0000 |
| DEGRADED |   54 |  114.7 | 0.0% | 0.491 | 0.0 |       51 |    - |   0.0% |    - | 0.0% |   0.0196 |
|      ALL |  148 |   55.1 | 6.8% | 0.548 | 0.1 |      144 | 10.0% |  16.7% | 2.4× | 6.5% |   0.0417 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.7 | 26.7% | 0.576 | 0.4 |       15 | 50.0% |  40.0% | 1.5× | 20.0% |   0.3333 |
|       OK |    7 |   34.9 | 14.3% | 0.420 | 0.1 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
| DEGRADED |    9 |   86.2 | 0.0% | 0.393 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.5000 |
|      ALL |   31 |   39.5 | 16.1% | 0.488 | 0.2 |       27 | 50.0% |  22.2% | 1.5× | 11.1% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.7 | 13.3% | 0.565 | 0.1 |       15 | 50.0% | 100.0% | 7.5× | 7.1% |   0.0667 |
|       OK |    7 |   34.9 | 0.0% | 0.353 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |   86.2 | 0.0% | 0.346 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   39.5 | 6.5% | 0.453 | 0.1 |       27 | 50.0% | 100.0% | 13.5× | 3.9% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.7 | 13.3% | 0.559 | 0.1 |       15 | 0.0% |      - |    - | 13.3% |   0.0000 |
|       OK |    7 |   34.9 | 0.0% | 0.479 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |   86.2 | 0.0% | 0.443 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   39.5 | 6.5% | 0.507 | 0.1 |       27 | 0.0% |      - |    - | 7.4% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available