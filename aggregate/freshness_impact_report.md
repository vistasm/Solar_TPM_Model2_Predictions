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
🟡 **M5+**: FRESH alert rate (6.2%) is 2.8× the overall rate (2.2%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (11.1%) is 2.5× the overall rate (4.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 18.5% | 0.501 | 0.3 |       81 | 80.0% |  33.3% | 1.8× | 6.7% |   0.4444 |
|       OK |   42 |   37.0 | 7.1% | 0.419 | 0.1 |       42 | 33.3% |  20.0% | 2.8× | 5.4% |   0.1190 |
| DEGRADED |  103 |  119.9 | 5.8% | 0.400 | 0.1 |      103 | 50.0% |  13.6% | 2.3× | 3.7% |   0.2136 |
|      ALL |  226 |   66.1 | 10.6% | 0.440 | 0.1 |      226 | 66.7% |  25.4% | 2.4× | 4.9% |   0.2788 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 6.2% | 0.487 | 0.1 |       81 | 60.0% |  23.1% | 3.7× | 2.9% |   0.1605 |
|       OK |   42 |   37.0 | 0.0% | 0.358 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  103 |  119.9 | 0.0% | 0.358 | 0.0 |      103 |    - |   0.0% |    - | 0.0% |   0.0485 |
|      ALL |  226 |   66.1 | 2.2% | 0.404 | 0.0 |      226 | 60.0% |  16.7% | 7.5× | 1.0% |   0.0796 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 11.1% | 0.597 | 0.1 |       81 | 11.1% |  20.0% | 1.8× | 10.5% |   0.0617 |
|       OK |   42 |   37.0 | 2.4% | 0.535 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |  103 |  119.9 | 0.0% | 0.518 | 0.0 |      103 |    - |   0.0% |    - | 0.0% |   0.0097 |
|      ALL |  226 |   66.1 | 4.4% | 0.550 | 0.0 |      226 | 10.0% |  16.7% | 3.8× | 4.1% |   0.0265 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   22 |  103.4 | 22.7% | 0.515 | 0.2 |       22 | 60.0% |  42.9% | 1.9× | 13.3% |   0.3182 |
|      ALL |   22 |  103.4 | 22.7% | 0.515 | 0.2 |       22 | 60.0% |  42.9% | 1.9× | 13.3% |   0.3182 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   22 |  103.4 | 0.0% | 0.531 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   22 |  103.4 | 0.0% | 0.531 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0909 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   22 |  103.4 | 0.0% | 0.582 | 0.0 |       22 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   22 |  103.4 | 0.0% | 0.582 | 0.0 |       22 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available