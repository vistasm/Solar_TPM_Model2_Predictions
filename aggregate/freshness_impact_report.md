# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-17 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (83.3%) is 83.3% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (7.7%) is 2.5× the overall rate (3.1%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (13.9%) is 2.2× the overall rate (6.2%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   65 |   12.7 | 18.5% | 0.500 | 0.3 |       63 | 83.3% |  34.5% | 1.8× | 5.9% |   0.4603 |
|       OK |   34 |   37.2 | 8.8% | 0.408 | 0.1 |       33 | 33.3% |  25.0% | 2.8× | 6.9% |   0.1212 |
| DEGRADED |   62 |  121.0 | 1.6% | 0.390 | 0.0 |       61 | 0.0% |   0.0% |    - | 2.1% |   0.2295 |
|      ALL |  161 |   59.6 | 9.9% | 0.439 | 0.1 |      157 | 68.8% |  23.4% | 2.3× | 4.5% |   0.2994 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   65 |   12.7 | 7.7% | 0.494 | 0.1 |       63 | 60.0% |  27.3% | 3.4× | 3.9% |   0.1746 |
|       OK |   34 |   37.2 | 0.0% | 0.347 | 0.0 |       33 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   62 |  121.0 | 0.0% | 0.337 | 0.0 |       61 |    - |   0.0% |    - | 0.0% |   0.0492 |
|      ALL |  161 |   59.6 | 3.1% | 0.402 | 0.0 |      157 | 60.0% |  21.4% | 6.7× | 1.4% |   0.0892 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   65 |   12.7 | 13.9% | 0.605 | 0.1 |       63 | 11.1% |  20.0% | 1.4× | 13.8% |   0.0794 |
|       OK |   34 |   37.2 | 2.9% | 0.530 | 0.0 |       33 | 0.0% |      - |    - | 3.0% |   0.0000 |
| DEGRADED |   62 |  121.0 | 0.0% | 0.494 | 0.0 |       61 |    - |   0.0% |    - | 0.0% |   0.0164 |
|      ALL |  161 |   59.6 | 6.2% | 0.546 | 0.1 |      157 | 10.0% |  16.7% | 2.6× | 6.0% |   0.0382 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.8 | 22.2% | 0.523 | 0.2 |        7 | 50.0% |  50.0% | 1.8× | 20.0% |   0.2857 |
|       OK |    6 |   36.7 | 33.3% | 0.519 | 0.3 |        5 | 0.0% |      - |    - | 40.0% |   0.0000 |
| DEGRADED |   16 |  126.2 | 0.0% | 0.364 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.2000 |
|      ALL |   31 |   76.5 | 12.9% | 0.440 | 0.1 |       27 | 25.0% |  20.0% | 1.4× | 13.6% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.8 | 0.0% | 0.557 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.7 | 0.0% | 0.469 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  126.2 | 0.0% | 0.313 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   76.5 | 0.0% | 0.414 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.8 | 0.0% | 0.500 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.7 | 0.0% | 0.501 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  126.2 | 0.0% | 0.489 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   76.5 | 0.0% | 0.494 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available