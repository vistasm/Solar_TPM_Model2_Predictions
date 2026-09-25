# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-25 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (80.0%) is 80.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (6.2%) is 2.5× the overall rate (2.5%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (11.1%) is 2.2× the overall rate (5.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 18.5% | 0.501 | 0.3 |       81 | 80.0% |  33.3% | 1.8× | 6.7% |   0.4444 |
|       OK |   42 |   37.0 | 7.1% | 0.419 | 0.1 |       42 | 33.3% |  20.0% | 2.8× | 5.4% |   0.1190 |
| DEGRADED |   76 |  121.2 | 1.3% | 0.377 | 0.0 |       72 | 0.0% |   0.0% |    - | 1.8% |   0.2083 |
|      ALL |  199 |   59.4 | 9.6% | 0.436 | 0.1 |      195 | 68.4% |  23.2% | 2.4× | 4.3% |   0.2872 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 6.2% | 0.487 | 0.1 |       81 | 60.0% |  23.1% | 3.7× | 2.9% |   0.1605 |
|       OK |   42 |   37.0 | 0.0% | 0.358 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   76 |  121.2 | 0.0% | 0.320 | 0.0 |       72 |    - |   0.0% |    - | 0.0% |   0.0417 |
|      ALL |  199 |   59.4 | 2.5% | 0.396 | 0.0 |      195 | 60.0% |  18.8% | 7.3× | 1.1% |   0.0821 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 11.1% | 0.597 | 0.1 |       81 | 11.1% |  20.0% | 1.8× | 10.5% |   0.0617 |
|       OK |   42 |   37.0 | 2.4% | 0.535 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |   76 |  121.2 | 0.0% | 0.500 | 0.0 |       72 |    - |   0.0% |    - | 0.0% |   0.0139 |
|      ALL |  199 |   59.4 | 5.0% | 0.547 | 0.1 |      195 | 10.0% |  16.7% | 3.2× | 4.8% |   0.0308 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.0 | 18.2% | 0.414 | 0.2 |       11 | 100.0% |  50.0% | 2.8× | 0.0% |   0.3636 |
|       OK |    6 |   34.9 | 0.0% | 0.383 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  126.6 | 0.0% | 0.292 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   66.9 | 6.7% | 0.355 | 0.1 |       26 | 100.0% |  50.0% | 6.5× | 0.0% |   0.1538 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.0 | 0.0% | 0.369 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   34.9 | 0.0% | 0.321 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  126.6 | 0.0% | 0.213 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   66.9 | 0.0% | 0.292 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.0 | 0.0% | 0.554 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   34.9 | 0.0% | 0.548 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  126.6 | 0.0% | 0.525 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   66.9 | 0.0% | 0.540 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available