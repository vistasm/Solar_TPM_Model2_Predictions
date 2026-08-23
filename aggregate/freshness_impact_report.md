# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-23 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (83.3%) is 83.3% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (7.2%) is 2.4× the overall rate (3.0%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (13.0%) is 2.2× the overall rate (6.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   69 |   12.8 | 18.8% | 0.512 | 0.3 |       66 | 83.3% |  34.5% | 1.9× | 5.4% |   0.4394 |
|       OK |   36 |   37.4 | 8.3% | 0.425 | 0.1 |       35 | 33.3% |  20.0% | 2.3× | 6.7% |   0.1429 |
| DEGRADED |   62 |  121.0 | 1.6% | 0.390 | 0.0 |       62 | 0.0% |   0.0% |    - | 2.1% |   0.2258 |
|      ALL |  167 |   58.3 | 10.2% | 0.448 | 0.1 |      163 | 68.8% |  22.9% | 2.3× | 4.3% |   0.2945 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   69 |   12.8 | 7.2% | 0.502 | 0.1 |       66 | 60.0% |  27.3% | 3.6× | 3.6% |   0.1667 |
|       OK |   36 |   37.4 | 0.0% | 0.364 | 0.0 |       35 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   62 |  121.0 | 0.0% | 0.337 | 0.0 |       62 |    - |   0.0% |    - | 0.0% |   0.0484 |
|      ALL |  167 |   58.3 | 3.0% | 0.411 | 0.0 |      163 | 60.0% |  21.4% | 7.0× | 1.3% |   0.0859 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   69 |   12.8 | 13.0% | 0.604 | 0.1 |       66 | 11.1% |  20.0% | 1.5× | 13.1% |   0.0758 |
|       OK |   36 |   37.4 | 2.8% | 0.533 | 0.0 |       35 | 0.0% |      - |    - | 2.9% |   0.0000 |
| DEGRADED |   62 |  121.0 | 0.0% | 0.494 | 0.0 |       62 |    - |   0.0% |    - | 0.0% |   0.0161 |
|      ALL |  167 |   58.3 | 6.0% | 0.548 | 0.1 |      163 | 10.0% |  16.7% | 2.7× | 5.7% |   0.0368 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.7 | 10.0% | 0.533 | 0.2 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   37.6 | 25.0% | 0.564 | 0.2 |        7 | 0.0% |   0.0% |    - | 33.3% |   0.1429 |
| DEGRADED |   13 |  129.3 | 0.0% | 0.376 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|      ALL |   31 |   68.7 | 9.7% | 0.475 | 0.1 |       27 | 0.0% |   0.0% |    - | 8.3% |   0.1111 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.7 | 0.0% | 0.524 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   37.6 | 0.0% | 0.514 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  129.3 | 0.0% | 0.346 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   68.7 | 0.0% | 0.447 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.7 | 0.0% | 0.542 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   37.6 | 0.0% | 0.524 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  129.3 | 0.0% | 0.529 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   68.7 | 0.0% | 0.532 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available