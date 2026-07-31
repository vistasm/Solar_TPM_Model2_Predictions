# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-31 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (83.3%) is 83.3% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (8.1%) is 2.3× the overall rate (3.5%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (14.5%) is 2.1× the overall rate (6.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.6 | 19.4% | 0.505 | 0.3 |       61 | 83.3% |  34.5% | 1.8× | 6.2% |   0.4754 |
|       OK |   31 |   36.8 | 3.2% | 0.384 | 0.0 |       29 | 100.0% |  25.0% | 7.2× | 0.0% |   0.1379 |
| DEGRADED |   51 |  116.4 | 2.0% | 0.398 | 0.0 |       50 | 0.0% |   0.0% |    - | 2.7% |   0.2600 |
|      ALL |  144 |   54.6 | 9.7% | 0.441 | 0.1 |      140 | 78.6% |  23.9% | 2.4× | 3.2% |   0.3286 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.6 | 8.1% | 0.499 | 0.1 |       61 | 60.0% |  27.3% | 3.3× | 4.0% |   0.1803 |
|       OK |   31 |   36.8 | 0.0% | 0.319 | 0.0 |       29 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   51 |  116.4 | 0.0% | 0.338 | 0.0 |       50 |    - |   0.0% |    - | 0.0% |   0.0600 |
|      ALL |  144 |   54.6 | 3.5% | 0.403 | 0.0 |      140 | 60.0% |  21.4% | 6.0× | 1.6% |   0.1000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.6 | 14.5% | 0.608 | 0.1 |       61 | 11.1% |  20.0% | 1.4× | 14.3% |   0.0820 |
|       OK |   31 |   36.8 | 3.2% | 0.526 | 0.0 |       29 | 0.0% |      - |    - | 3.5% |   0.0000 |
| DEGRADED |   51 |  116.4 | 0.0% | 0.486 | 0.0 |       50 |    - |   0.0% |    - | 0.0% |   0.0200 |
|      ALL |  144 |   54.6 | 6.9% | 0.547 | 0.1 |      140 | 10.0% |  16.7% | 2.3× | 6.7% |   0.0429 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   12.0 | 42.1% | 0.658 | 0.7 |       18 | 75.0% |  66.7% | 1.5× | 22.2% |   0.5000 |
|       OK |    6 |   34.6 | 0.0% | 0.362 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
| DEGRADED |    6 |   87.0 | 0.0% | 0.346 | 0.0 |        5 |    - |   0.0% |    - | 0.0% |   0.4000 |
|      ALL |   31 |   30.9 | 25.8% | 0.540 | 0.5 |       27 | 75.0% |  50.0% | 1.7× | 13.3% |   0.4444 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   12.0 | 26.3% | 0.646 | 0.3 |       18 | 60.0% |  75.0% | 2.7× | 14.3% |   0.2222 |
|       OK |    6 |   34.6 | 0.0% | 0.306 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   87.0 | 0.0% | 0.242 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   30.9 | 16.1% | 0.502 | 0.2 |       27 | 60.0% |  75.0% | 4.0× | 8.7% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   12.0 | 31.6% | 0.650 | 0.3 |       18 | 16.7% | 100.0% | 3.0× | 29.4% |   0.0556 |
|       OK |    6 |   34.6 | 0.0% | 0.465 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   87.0 | 0.0% | 0.382 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   30.9 | 19.4% | 0.562 | 0.2 |       27 | 16.7% | 100.0% | 4.5× | 19.2% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available