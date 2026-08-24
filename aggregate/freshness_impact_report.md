# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-24 UTC
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
🟡 **X+**: FRESH alert rate (13.0%) is 2.2× the overall rate (5.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   69 |   12.8 | 18.8% | 0.512 | 0.3 |       67 | 83.3% |  33.3% | 1.9× | 5.4% |   0.4478 |
|       OK |   36 |   37.4 | 8.3% | 0.425 | 0.1 |       35 | 33.3% |  20.0% | 2.3× | 6.7% |   0.1429 |
| DEGRADED |   63 |  120.1 | 1.6% | 0.395 | 0.0 |       62 | 0.0% |   0.0% |    - | 2.1% |   0.2258 |
|      ALL |  168 |   58.3 | 10.1% | 0.449 | 0.1 |      164 | 68.8% |  22.4% | 2.3× | 4.3% |   0.2988 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   69 |   12.8 | 7.2% | 0.502 | 0.1 |       67 | 60.0% |  25.0% | 3.4× | 3.6% |   0.1791 |
|       OK |   36 |   37.4 | 0.0% | 0.364 | 0.0 |       35 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   63 |  120.1 | 0.0% | 0.342 | 0.0 |       62 |    - |   0.0% |    - | 0.0% |   0.0484 |
|      ALL |  168 |   58.3 | 3.0% | 0.412 | 0.0 |      164 | 60.0% |  20.0% | 6.6× | 1.3% |   0.0915 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   69 |   12.8 | 13.0% | 0.604 | 0.1 |       67 | 11.1% |  20.0% | 1.5× | 12.9% |   0.0746 |
|       OK |   36 |   37.4 | 2.8% | 0.533 | 0.0 |       35 | 0.0% |      - |    - | 2.9% |   0.0000 |
| DEGRADED |   63 |  120.1 | 0.0% | 0.495 | 0.0 |       62 |    - |   0.0% |    - | 0.0% |   0.0161 |
|      ALL |  168 |   58.3 | 5.9% | 0.548 | 0.1 |      164 | 10.0% |  16.7% | 2.7× | 5.7% |   0.0366 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.8 | 11.1% | 0.533 | 0.2 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    8 |   37.6 | 25.0% | 0.564 | 0.2 |        7 | 0.0% |   0.0% |    - | 33.3% |   0.1429 |
| DEGRADED |   14 |  124.9 | 0.0% | 0.398 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|      ALL |   31 |   70.4 | 9.7% | 0.480 | 0.1 |       27 | 0.0% |   0.0% |    - | 8.7% |   0.1481 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.8 | 0.0% | 0.513 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    8 |   37.6 | 0.0% | 0.514 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  124.9 | 0.0% | 0.370 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   70.4 | 0.0% | 0.449 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.8 | 0.0% | 0.552 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   37.6 | 0.0% | 0.524 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  124.9 | 0.0% | 0.533 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   70.4 | 0.0% | 0.536 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available