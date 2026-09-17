# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-17 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (80.0%) is 80.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (6.2%) is 2.4× the overall rate (2.6%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (11.2%) is 2.1× the overall rate (5.2%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   80 |   12.9 | 18.8% | 0.506 | 0.3 |       80 | 80.0% |  33.3% | 1.8× | 6.8% |   0.4500 |
|       OK |   41 |   37.1 | 7.3% | 0.414 | 0.1 |       41 | 33.3% |  20.0% | 2.7× | 5.6% |   0.1220 |
| DEGRADED |   70 |  119.8 | 1.4% | 0.380 | 0.0 |       66 | 0.0% |   0.0% |    - | 2.0% |   0.2273 |
|      ALL |  191 |   57.3 | 10.0% | 0.440 | 0.1 |      187 | 68.4% |  23.2% | 2.3× | 4.6% |   0.2995 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   80 |   12.9 | 6.2% | 0.493 | 0.1 |       80 | 60.0% |  23.1% | 3.7× | 3.0% |   0.1625 |
|       OK |   41 |   37.1 | 0.0% | 0.354 | 0.0 |       41 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   70 |  119.8 | 0.0% | 0.324 | 0.0 |       66 |    - |   0.0% |    - | 0.0% |   0.0455 |
|      ALL |  191 |   57.3 | 2.6% | 0.401 | 0.0 |      187 | 60.0% |  18.8% | 7.0× | 1.2% |   0.0856 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   80 |   12.9 | 11.2% | 0.599 | 0.1 |       80 | 11.1% |  20.0% | 1.8× | 10.7% |   0.0625 |
|       OK |   41 |   37.1 | 2.4% | 0.535 | 0.0 |       41 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |   70 |  119.8 | 0.0% | 0.499 | 0.0 |       66 |    - |   0.0% |    - | 0.0% |   0.0152 |
|      ALL |  191 |   57.3 | 5.2% | 0.548 | 0.1 |      187 | 10.0% |  16.7% | 3.1× | 5.0% |   0.0321 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.6 | 20.0% | 0.533 | 0.3 |       15 | 66.7% |  28.6% | 1.4× | 12.5% |   0.4667 |
|       OK |    7 |   36.4 | 0.0% | 0.443 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
| DEGRADED |    8 |  110.3 | 0.0% | 0.296 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
|      ALL |   30 |   44.7 | 10.0% | 0.449 | 0.1 |       26 | 66.7% |  22.2% | 1.9× | 5.9% |   0.3462 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.6 | 0.0% | 0.489 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|       OK |    7 |   36.4 | 0.0% | 0.387 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |  110.3 | 0.0% | 0.230 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   44.7 | 0.0% | 0.396 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0769 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.6 | 0.0% | 0.574 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   36.4 | 0.0% | 0.564 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |  110.3 | 0.0% | 0.535 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   44.7 | 0.0% | 0.561 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available