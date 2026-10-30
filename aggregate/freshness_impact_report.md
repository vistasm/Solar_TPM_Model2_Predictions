# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-10-30 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (80.0%) is 30.0% HIGHER than DEGRADED (50.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (6.2%) is 2.7× the overall rate (2.3%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (11.1%) is 2.4× the overall rate (4.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 18.5% | 0.501 | 0.3 |       81 | 80.0% |  33.3% | 1.8× | 6.7% |   0.4444 |
|       OK |   42 |   37.0 | 7.1% | 0.419 | 0.1 |       42 | 33.3% |  20.0% | 2.8× | 5.4% |   0.1190 |
| DEGRADED |   95 |  121.9 | 6.3% | 0.395 | 0.1 |       95 | 50.0% |  15.0% | 2.4× | 4.0% |   0.2105 |
|      ALL |  218 |   65.0 | 11.0% | 0.439 | 0.1 |      218 | 66.7% |  26.2% | 2.4× | 5.1% |   0.2798 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 6.2% | 0.487 | 0.1 |       81 | 60.0% |  23.1% | 3.7× | 2.9% |   0.1605 |
|       OK |   42 |   37.0 | 0.0% | 0.358 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   95 |  121.9 | 0.0% | 0.338 | 0.0 |       95 |    - |   0.0% |    - | 0.0% |   0.0526 |
|      ALL |  218 |   65.0 | 2.3% | 0.397 | 0.0 |      218 | 60.0% |  16.7% | 7.3× | 1.0% |   0.0826 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 11.1% | 0.597 | 0.1 |       81 | 11.1% |  20.0% | 1.8× | 10.5% |   0.0617 |
|       OK |   42 |   37.0 | 2.4% | 0.535 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |   95 |  121.9 | 0.0% | 0.512 | 0.0 |       95 |    - |   0.0% |    - | 0.0% |   0.0105 |
|      ALL |  218 |   65.0 | 4.6% | 0.548 | 0.1 |      218 | 10.0% |  16.7% | 3.6× | 4.2% |   0.0275 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   14 |  107.4 | 35.7% | 0.544 | 0.4 |       14 | 60.0% |  60.0% | 1.7× | 22.2% |   0.3571 |
|      ALL |   14 |  107.4 | 35.7% | 0.544 | 0.4 |       14 | 60.0% |  60.0% | 1.7× | 22.2% |   0.3571 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   14 |  107.4 | 0.0% | 0.496 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|      ALL |   14 |  107.4 | 0.0% | 0.496 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   14 |  107.4 | 0.0% | 0.576 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   14 |  107.4 | 0.0% | 0.576 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available