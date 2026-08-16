# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-16 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (83.3%) is 83.3% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (7.8%) is 2.5× the overall rate (3.1%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (14.1%) is 2.2× the overall rate (6.2%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   64 |   12.8 | 18.8% | 0.500 | 0.3 |       63 | 83.3% |  34.5% | 1.8× | 5.9% |   0.4603 |
|       OK |   34 |   37.2 | 8.8% | 0.408 | 0.1 |       33 | 33.3% |  25.0% | 2.8× | 6.9% |   0.1212 |
| DEGRADED |   62 |  121.0 | 1.6% | 0.390 | 0.0 |       60 | 0.0% |   0.0% |    - | 2.2% |   0.2333 |
|      ALL |  160 |   59.9 | 10.0% | 0.438 | 0.1 |      156 | 68.8% |  23.4% | 2.3× | 4.6% |   0.3013 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   64 |   12.8 | 7.8% | 0.494 | 0.1 |       63 | 60.0% |  27.3% | 3.4× | 3.9% |   0.1746 |
|       OK |   34 |   37.2 | 0.0% | 0.347 | 0.0 |       33 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   62 |  121.0 | 0.0% | 0.337 | 0.0 |       60 |    - |   0.0% |    - | 0.0% |   0.0500 |
|      ALL |  160 |   59.9 | 3.1% | 0.402 | 0.0 |      156 | 60.0% |  21.4% | 6.7× | 1.4% |   0.0897 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   64 |   12.8 | 14.1% | 0.606 | 0.1 |       63 | 11.1% |  20.0% | 1.4× | 13.8% |   0.0794 |
|       OK |   34 |   37.2 | 2.9% | 0.530 | 0.0 |       33 | 0.0% |      - |    - | 3.0% |   0.0000 |
| DEGRADED |   62 |  121.0 | 0.0% | 0.494 | 0.0 |       60 |    - |   0.0% |    - | 0.0% |   0.0167 |
|      ALL |  160 |   59.9 | 6.2% | 0.546 | 0.1 |      156 | 10.0% |  16.7% | 2.6× | 6.0% |   0.0385 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   15.4 | 25.0% | 0.525 | 0.2 |        7 | 50.0% |  50.0% | 1.8× | 20.0% |   0.2857 |
|       OK |    6 |   36.7 | 33.3% | 0.519 | 0.3 |        5 | 0.0% |      - |    - | 40.0% |   0.0000 |
| DEGRADED |   17 |  122.6 | 0.0% | 0.351 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.2000 |
|      ALL |   31 |   78.3 | 12.9% | 0.428 | 0.1 |       27 | 25.0% |  20.0% | 1.4× | 13.6% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   15.4 | 0.0% | 0.570 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.7 | 0.0% | 0.469 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  122.6 | 0.0% | 0.298 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   78.3 | 0.0% | 0.402 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   15.4 | 0.0% | 0.494 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.7 | 0.0% | 0.501 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  122.6 | 0.0% | 0.478 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   78.3 | 0.0% | 0.486 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available