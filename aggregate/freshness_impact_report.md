# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-12 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (80.0%) is 80.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (6.2%) is 2.3× the overall rate (2.7%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (11.2%) is 2.1× the overall rate (5.3%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   80 |   12.9 | 18.8% | 0.506 | 0.3 |       78 | 80.0% |  33.3% | 1.7× | 7.1% |   0.4615 |
|       OK |   41 |   37.1 | 7.3% | 0.414 | 0.1 |       40 | 33.3% |  20.0% | 2.7× | 5.7% |   0.1250 |
| DEGRADED |   66 |  117.8 | 1.5% | 0.390 | 0.0 |       65 | 0.0% |   0.0% |    - | 2.0% |   0.2308 |
|      ALL |  187 |   55.2 | 10.2% | 0.445 | 0.1 |      183 | 68.4% |  23.2% | 2.2× | 4.7% |   0.3060 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   80 |   12.9 | 6.2% | 0.493 | 0.1 |       78 | 60.0% |  23.1% | 3.6× | 3.1% |   0.1667 |
|       OK |   41 |   37.1 | 0.0% | 0.354 | 0.0 |       40 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   66 |  117.8 | 0.0% | 0.336 | 0.0 |       65 |    - |   0.0% |    - | 0.0% |   0.0462 |
|      ALL |  187 |   55.2 | 2.7% | 0.407 | 0.0 |      183 | 60.0% |  18.8% | 6.9× | 1.2% |   0.0874 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   80 |   12.9 | 11.2% | 0.599 | 0.1 |       78 | 11.1% |  20.0% | 1.7× | 11.0% |   0.0641 |
|       OK |   41 |   37.1 | 2.4% | 0.535 | 0.0 |       40 | 0.0% |      - |    - | 2.5% |   0.0000 |
| DEGRADED |   66 |  117.8 | 0.0% | 0.498 | 0.0 |       65 |    - |   0.0% |    - | 0.0% |   0.0154 |
|      ALL |  187 |   55.2 | 5.3% | 0.549 | 0.1 |      183 | 10.0% |  16.7% | 3.0× | 5.1% |   0.0328 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   13.9 | 17.6% | 0.529 | 0.2 |       15 | 66.7% |  28.6% | 1.4× | 12.5% |   0.4667 |
|       OK |    8 |   37.6 | 0.0% | 0.438 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
| DEGRADED |    6 |   70.8 | 0.0% | 0.401 | 0.0 |        5 |    - |   0.0% |    - | 0.0% |   0.2000 |
|      ALL |   31 |   31.0 | 9.7% | 0.480 | 0.1 |       27 | 66.7% |  22.2% | 2.0× | 5.6% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   13.9 | 0.0% | 0.495 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|       OK |    8 |   37.6 | 0.0% | 0.401 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   70.8 | 0.0% | 0.366 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   31.0 | 0.0% | 0.446 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   13.9 | 0.0% | 0.570 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   37.6 | 0.0% | 0.562 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   70.8 | 0.0% | 0.552 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   31.0 | 0.0% | 0.565 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available