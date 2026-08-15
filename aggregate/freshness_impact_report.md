# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-15 UTC
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
🟡 **X+**: FRESH alert rate (14.1%) is 2.2× the overall rate (6.3%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   64 |   12.8 | 18.8% | 0.500 | 0.3 |       63 | 83.3% |  34.5% | 1.8× | 5.9% |   0.4603 |
|       OK |   33 |   36.9 | 9.1% | 0.409 | 0.1 |       32 | 50.0% |  25.0% | 4.0× | 3.6% |   0.1250 |
| DEGRADED |   62 |  121.0 | 1.6% | 0.390 | 0.0 |       60 | 0.0% |   0.0% |    - | 2.2% |   0.2333 |
|      ALL |  159 |   60.0 | 10.1% | 0.438 | 0.1 |      155 | 73.3% |  23.4% | 2.4× | 3.7% |   0.3032 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   64 |   12.8 | 7.8% | 0.494 | 0.1 |       63 | 60.0% |  27.3% | 3.4× | 3.9% |   0.1746 |
|       OK |   33 |   36.9 | 0.0% | 0.342 | 0.0 |       32 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   62 |  121.0 | 0.0% | 0.337 | 0.0 |       60 |    - |   0.0% |    - | 0.0% |   0.0500 |
|      ALL |  159 |   60.0 | 3.1% | 0.401 | 0.0 |      155 | 60.0% |  21.4% | 6.6× | 1.4% |   0.0903 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   64 |   12.8 | 14.1% | 0.606 | 0.1 |       63 | 11.1% |  20.0% | 1.4× | 13.8% |   0.0794 |
|       OK |   33 |   36.9 | 3.0% | 0.529 | 0.0 |       32 | 0.0% |      - |    - | 3.1% |   0.0000 |
| DEGRADED |   62 |  121.0 | 0.0% | 0.494 | 0.0 |       60 |    - |   0.0% |    - | 0.0% |   0.0167 |
|      ALL |  159 |   60.0 | 6.3% | 0.546 | 0.1 |      155 | 10.0% |  16.7% | 2.6× | 6.0% |   0.0387 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   15.4 | 25.0% | 0.525 | 0.2 |        7 | 50.0% |  50.0% | 1.8× | 20.0% |   0.2857 |
|       OK |    6 |   35.8 | 33.3% | 0.475 | 0.3 |        5 | 0.0% |      - |    - | 20.0% |   0.0000 |
| DEGRADED |   17 |  122.6 | 0.0% | 0.351 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.2000 |
|      ALL |   31 |   78.1 | 12.9% | 0.420 | 0.1 |       27 | 33.3% |  20.0% | 1.8× | 9.1% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   15.4 | 0.0% | 0.570 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   35.8 | 0.0% | 0.395 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  122.6 | 0.0% | 0.298 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   78.1 | 0.0% | 0.387 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   15.4 | 0.0% | 0.494 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   35.8 | 0.0% | 0.475 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  122.6 | 0.0% | 0.478 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   78.1 | 0.0% | 0.481 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available