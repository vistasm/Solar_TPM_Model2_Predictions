# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-25 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (83.3%) is 83.3% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (7.1%) is 2.4× the overall rate (3.0%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (12.9%) is 2.2× the overall rate (5.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   70 |   12.7 | 18.6% | 0.515 | 0.3 |       68 | 83.3% |  32.3% | 1.8× | 5.4% |   0.4559 |
|       OK |   36 |   37.4 | 8.3% | 0.425 | 0.1 |       35 | 33.3% |  20.0% | 2.3× | 6.7% |   0.1429 |
| DEGRADED |   63 |  120.1 | 1.6% | 0.395 | 0.0 |       62 | 0.0% |   0.0% |    - | 2.1% |   0.2258 |
|      ALL |  169 |   58.0 | 10.1% | 0.451 | 0.1 |      165 | 68.8% |  22.0% | 2.3× | 4.3% |   0.3030 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   70 |   12.7 | 7.1% | 0.506 | 0.1 |       68 | 60.0% |  25.0% | 3.4× | 3.6% |   0.1765 |
|       OK |   36 |   37.4 | 0.0% | 0.364 | 0.0 |       35 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   63 |  120.1 | 0.0% | 0.342 | 0.0 |       62 |    - |   0.0% |    - | 0.0% |   0.0484 |
|      ALL |  169 |   58.0 | 3.0% | 0.414 | 0.0 |      165 | 60.0% |  20.0% | 6.6× | 1.3% |   0.0909 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   70 |   12.7 | 12.9% | 0.604 | 0.1 |       68 | 11.1% |  20.0% | 1.5× | 12.7% |   0.0735 |
|       OK |   36 |   37.4 | 2.8% | 0.533 | 0.0 |       35 | 0.0% |      - |    - | 2.9% |   0.0000 |
| DEGRADED |   63 |  120.1 | 0.0% | 0.495 | 0.0 |       62 |    - |   0.0% |    - | 0.0% |   0.0161 |
|      ALL |  169 |   58.0 | 5.9% | 0.548 | 0.1 |      165 | 10.0% |  16.7% | 2.8× | 5.7% |   0.0364 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   13.7 | 10.0% | 0.552 | 0.2 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|       OK |    7 |   37.4 | 28.6% | 0.592 | 0.3 |        6 | 0.0% |   0.0% |    - | 40.0% |   0.1667 |
| DEGRADED |   14 |  124.9 | 0.0% | 0.398 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|      ALL |   31 |   69.3 | 9.7% | 0.491 | 0.1 |       27 | 0.0% |   0.0% |    - | 9.1% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   13.7 | 0.0% | 0.538 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    7 |   37.4 | 0.0% | 0.551 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  124.9 | 0.0% | 0.370 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   69.3 | 0.0% | 0.465 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   13.7 | 0.0% | 0.558 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   37.4 | 0.0% | 0.524 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  124.9 | 0.0% | 0.533 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   69.3 | 0.0% | 0.539 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available