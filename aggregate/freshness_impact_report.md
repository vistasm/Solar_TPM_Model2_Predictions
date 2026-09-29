# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-29 UTC
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
🟡 **X+**: FRESH alert rate (11.1%) is 2.3× the overall rate (4.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 18.5% | 0.501 | 0.3 |       81 | 80.0% |  33.3% | 1.8× | 6.7% |   0.4444 |
|       OK |   42 |   37.0 | 7.1% | 0.419 | 0.1 |       42 | 33.3% |  20.0% | 2.8× | 5.4% |   0.1190 |
| DEGRADED |   80 |  124.7 | 1.2% | 0.371 | 0.0 |       76 | 0.0% |   0.0% |    - | 1.6% |   0.1974 |
|      ALL |  203 |   62.0 | 9.4% | 0.433 | 0.1 |      199 | 68.4% |  23.2% | 2.4× | 4.2% |   0.2814 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 6.2% | 0.487 | 0.1 |       81 | 60.0% |  23.1% | 3.7× | 2.9% |   0.1605 |
|       OK |   42 |   37.0 | 0.0% | 0.358 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   80 |  124.7 | 0.0% | 0.313 | 0.0 |       76 |    - |   0.0% |    - | 0.0% |   0.0395 |
|      ALL |  203 |   62.0 | 2.5% | 0.392 | 0.0 |      199 | 60.0% |  18.8% | 7.5× | 1.1% |   0.0804 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 11.1% | 0.597 | 0.1 |       81 | 11.1% |  20.0% | 1.8× | 10.5% |   0.0617 |
|       OK |   42 |   37.0 | 2.4% | 0.535 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |   80 |  124.7 | 0.0% | 0.501 | 0.0 |       76 |    - |   0.0% |    - | 0.0% |   0.0132 |
|      ALL |  203 |   62.0 | 4.9% | 0.546 | 0.1 |      199 | 10.0% |  16.7% | 3.3× | 4.7% |   0.0302 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.3 | 11.1% | 0.326 | 0.1 |        9 | 100.0% |  33.3% | 3.0× | 0.0% |   0.3333 |
|       OK |    5 |   35.5 | 0.0% | 0.317 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  147.2 | 0.0% | 0.279 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   88.7 | 3.3% | 0.299 | 0.0 |       26 | 100.0% |  33.3% | 8.7× | 0.0% |   0.1154 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.3 | 0.0% | 0.276 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    5 |   35.5 | 0.0% | 0.228 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  147.2 | 0.0% | 0.201 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   88.7 | 0.0% | 0.228 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.3 | 0.0% | 0.531 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    5 |   35.5 | 0.0% | 0.531 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  147.2 | 0.0% | 0.516 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   88.7 | 0.0% | 0.523 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available