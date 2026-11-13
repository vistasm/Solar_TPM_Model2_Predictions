# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-13 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (72.2%) is 22.2% HIGHER than DEGRADED (50.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (5.9%) is 2.9× the overall rate (2.0%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.6%) is 2.6× the overall rate (4.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   85 |   12.8 | 21.2% | 0.515 | 0.3 |       84 | 72.2% |  35.1% | 1.6× | 10.6% |   0.4405 |
|       OK |   45 |   36.8 | 11.1% | 0.441 | 0.1 |       43 | 50.0% |  33.3% | 3.6× | 5.4% |   0.1395 |
| DEGRADED |  119 |  120.0 | 5.9% | 0.388 | 0.1 |      118 | 50.0% |  13.0% | 2.6× | 3.2% |   0.1949 |
|      ALL |  249 |   68.4 | 12.0% | 0.441 | 0.1 |      245 | 64.3% |  27.3% | 2.4× | 5.6% |   0.2694 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   85 |   12.8 | 5.9% | 0.505 | 0.1 |       84 | 60.0% |  23.1% | 3.9× | 2.8% |   0.1548 |
|       OK |   45 |   36.8 | 0.0% | 0.386 | 0.0 |       43 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  119 |  120.0 | 0.0% | 0.344 | 0.0 |      118 |    - |   0.0% |    - | 0.0% |   0.0424 |
|      ALL |  249 |   68.4 | 2.0% | 0.407 | 0.0 |      245 | 60.0% |  16.7% | 8.2× | 0.9% |   0.0735 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   85 |   12.8 | 10.6% | 0.597 | 0.1 |       84 | 11.1% |  20.0% | 1.9× | 10.1% |   0.0595 |
|       OK |   45 |   36.8 | 2.2% | 0.539 | 0.0 |       43 | 0.0% |      - |    - | 2.3% |   0.0000 |
| DEGRADED |  119 |  120.0 | 0.0% | 0.518 | 0.0 |      118 |    - |   0.0% |    - | 0.0% |   0.0085 |
|      ALL |  249 |   68.4 | 4.0% | 0.549 | 0.0 |      245 | 10.0% |  16.7% | 4.1× | 3.8% |   0.0245 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   10.4 | 75.0% | 0.800 | 0.8 |        3 | 33.3% | 100.0% | 1.0× | 100.0% |   0.3333 |
|       OK |    3 |   34.2 | 66.7% | 0.746 | 0.7 |        1 | 100.0% | 100.0% | 1.0× |   - |   1.0000 |
| DEGRADED |   24 |  112.6 | 4.2% | 0.363 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.1304 |
|      ALL |   31 |   91.8 | 19.4% | 0.456 | 0.2 |       27 | 50.0% |  40.0% | 2.7× | 9.1% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   10.4 | 0.0% | 0.860 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   34.2 | 0.0% | 0.788 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   24 |  112.6 | 0.0% | 0.368 | 0.0 |       23 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   91.8 | 0.0% | 0.472 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   10.4 | 0.0% | 0.598 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   34.2 | 0.0% | 0.596 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   24 |  112.6 | 0.0% | 0.540 | 0.0 |       23 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   91.8 | 0.0% | 0.553 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available