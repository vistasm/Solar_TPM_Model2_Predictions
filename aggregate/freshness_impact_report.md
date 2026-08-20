# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-20 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (83.3%) is 83.3% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (7.5%) is 2.4× the overall rate (3.0%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (13.4%) is 2.2× the overall rate (6.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   67 |   12.7 | 17.9% | 0.503 | 0.3 |       64 | 83.3% |  34.5% | 1.8× | 5.7% |   0.4531 |
|       OK |   35 |   37.2 | 8.6% | 0.417 | 0.1 |       34 | 33.3% |  25.0% | 2.8× | 6.7% |   0.1176 |
| DEGRADED |   62 |  121.0 | 1.6% | 0.390 | 0.0 |       62 | 0.0% |   0.0% |    - | 2.1% |   0.2258 |
|      ALL |  164 |   58.9 | 9.8% | 0.442 | 0.1 |      160 | 68.8% |  23.4% | 2.3× | 4.4% |   0.2938 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   67 |   12.7 | 7.5% | 0.499 | 0.1 |       64 | 60.0% |  27.3% | 3.5× | 3.8% |   0.1719 |
|       OK |   35 |   37.2 | 0.0% | 0.356 | 0.0 |       34 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   62 |  121.0 | 0.0% | 0.337 | 0.0 |       62 |    - |   0.0% |    - | 0.0% |   0.0484 |
|      ALL |  164 |   58.9 | 3.0% | 0.407 | 0.0 |      160 | 60.0% |  21.4% | 6.9× | 1.4% |   0.0875 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   67 |   12.7 | 13.4% | 0.604 | 0.1 |       64 | 11.1% |  20.0% | 1.4× | 13.6% |   0.0781 |
|       OK |   35 |   37.2 | 2.9% | 0.531 | 0.0 |       34 | 0.0% |      - |    - | 2.9% |   0.0000 |
| DEGRADED |   62 |  121.0 | 0.0% | 0.494 | 0.0 |       62 |    - |   0.0% |    - | 0.0% |   0.0161 |
|      ALL |  164 |   58.9 | 6.1% | 0.547 | 0.1 |      160 | 10.0% |  16.7% | 2.7× | 5.8% |   0.0375 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.3 | 18.2% | 0.539 | 0.2 |        8 | 50.0% |  50.0% | 2.0× | 16.7% |   0.2500 |
|       OK |    7 |   36.7 | 28.6% | 0.545 | 0.3 |        6 | 0.0% |      - |    - | 33.3% |   0.0000 |
| DEGRADED |   13 |  129.3 | 0.0% | 0.376 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|      ALL |   31 |   67.5 | 12.9% | 0.472 | 0.1 |       27 | 25.0% |  25.0% | 1.7× | 13.0% |   0.1481 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.3 | 0.0% | 0.580 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   36.7 | 0.0% | 0.496 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  129.3 | 0.0% | 0.346 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   67.5 | 0.0% | 0.463 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.3 | 0.0% | 0.513 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   36.7 | 0.0% | 0.513 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  129.3 | 0.0% | 0.529 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   67.5 | 0.0% | 0.520 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available