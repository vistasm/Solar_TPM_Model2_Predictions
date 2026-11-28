# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-28 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (72.2%) is 15.1% HIGHER than DEGRADED (57.1%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (5.5%) is 2.9× the overall rate (1.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (9.9%) is 2.6× the overall rate (3.8%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   91 |   12.8 | 19.8% | 0.511 | 0.3 |       89 | 72.2% |  34.2% | 1.7× | 9.8% |   0.4270 |
|       OK |   48 |   36.6 | 10.4% | 0.433 | 0.1 |       48 | 40.0% |  28.6% | 2.7× | 7.3% |   0.1458 |
| DEGRADED |  125 |  119.2 | 5.6% | 0.377 | 0.1 |      123 | 57.1% |  16.7% | 2.9× | 3.0% |   0.1951 |
|      ALL |  264 |   67.5 | 11.4% | 0.433 | 0.1 |      260 | 63.3% |  27.5% | 2.4× | 5.8% |   0.2654 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   91 |   12.8 | 5.5% | 0.497 | 0.1 |       89 | 60.0% |  23.1% | 4.1× | 2.6% |   0.1461 |
|       OK |   48 |   36.6 | 0.0% | 0.381 | 0.0 |       48 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  125 |  119.2 | 0.0% | 0.333 | 0.0 |      123 |    - |   0.0% |    - | 0.0% |   0.0406 |
|      ALL |  264 |   67.5 | 1.9% | 0.398 | 0.0 |      260 | 60.0% |  16.7% | 8.7× | 0.8% |   0.0692 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   91 |   12.8 | 9.9% | 0.593 | 0.1 |       89 | 11.1% |  20.0% | 2.0× | 9.5% |   0.0562 |
|       OK |   48 |   36.6 | 2.1% | 0.539 | 0.0 |       48 | 0.0% |      - |    - | 2.1% |   0.0000 |
| DEGRADED |  125 |  119.2 | 0.0% | 0.517 | 0.0 |      123 |    - |   0.0% |    - | 0.0% |   0.0081 |
|      ALL |  264 |   67.5 | 3.8% | 0.547 | 0.0 |      260 | 10.0% |  16.7% | 4.3× | 3.5% |   0.0231 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.8 | 30.0% | 0.596 | 0.3 |        8 | 33.3% |  50.0% | 1.3× | 33.3% |   0.2500 |
|       OK |    6 |   33.4 | 33.3% | 0.532 | 0.3 |        6 | 50.0% |  50.0% | 1.5× | 25.0% |   0.3333 |
| DEGRADED |   15 |  124.6 | 6.7% | 0.238 | 0.1 |       13 | 100.0% |  50.0% | 6.5× | 0.0% |   0.1538 |
|      ALL |   31 |   70.6 | 19.4% | 0.410 | 0.2 |       27 | 50.0% |  50.0% | 2.2× | 14.3% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.8 | 0.0% | 0.575 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   33.4 | 0.0% | 0.541 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  124.6 | 0.0% | 0.184 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   70.6 | 0.0% | 0.379 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.8 | 0.0% | 0.556 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   33.4 | 0.0% | 0.563 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  124.6 | 0.0% | 0.508 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   70.6 | 0.0% | 0.534 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available