# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-28 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (83.3%) is 83.3% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (8.2%) is 2.3× the overall rate (3.5%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (14.8%) is 2.1× the overall rate (7.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   61 |   12.6 | 19.7% | 0.505 | 0.3 |       60 | 83.3% |  34.5% | 1.7× | 6.5% |   0.4833 |
|       OK |   30 |   37.0 | 3.3% | 0.385 | 0.0 |       28 | 100.0% |  25.0% | 7.0× | 0.0% |   0.1429 |
| DEGRADED |   50 |  117.7 | 2.0% | 0.396 | 0.0 |       49 | 0.0% |   0.0% |    - | 2.7% |   0.2449 |
|      ALL |  141 |   55.0 | 9.9% | 0.441 | 0.1 |      137 | 78.6% |  24.4% | 2.4× | 3.3% |   0.3285 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   61 |   12.6 | 8.2% | 0.497 | 0.1 |       60 | 60.0% |  27.3% | 3.3× | 4.1% |   0.1833 |
|       OK |   30 |   37.0 | 0.0% | 0.316 | 0.0 |       28 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   50 |  117.7 | 0.0% | 0.335 | 0.0 |       49 |    - |   0.0% |    - | 0.0% |   0.0612 |
|      ALL |  141 |   55.0 | 3.5% | 0.401 | 0.0 |      137 | 60.0% |  21.4% | 5.9× | 1.6% |   0.1022 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   61 |   12.6 | 14.8% | 0.610 | 0.1 |       60 | 11.1% |  20.0% | 1.3× | 14.5% |   0.0833 |
|       OK |   30 |   37.0 | 3.3% | 0.530 | 0.0 |       28 | 0.0% |      - |    - | 3.6% |   0.0000 |
| DEGRADED |   50 |  117.7 | 0.0% | 0.486 | 0.0 |       49 |    - |   0.0% |    - | 0.0% |   0.0204 |
|      ALL |  141 |   55.0 | 7.1% | 0.549 | 0.1 |      137 | 10.0% |  16.7% | 2.3× | 6.9% |   0.0438 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   11.5 | 42.1% | 0.666 | 0.7 |       18 | 75.0% |  60.0% | 1.4× | 25.0% |   0.5556 |
|       OK |    5 |   35.3 | 0.0% | 0.365 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |    7 |  114.2 | 0.0% | 0.391 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.3333 |
|      ALL |   31 |   38.6 | 25.8% | 0.555 | 0.5 |       27 | 75.0% |  46.2% | 1.6× | 14.3% |   0.4815 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   11.5 | 26.3% | 0.655 | 0.3 |       18 | 60.0% |  60.0% | 2.2× | 15.4% |   0.2778 |
|       OK |    5 |   35.3 | 0.0% | 0.283 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    7 |  114.2 | 0.0% | 0.299 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   38.6 | 16.1% | 0.515 | 0.2 |       27 | 60.0% |  60.0% | 3.2× | 9.1% |   0.1852 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   11.5 | 31.6% | 0.660 | 0.3 |       18 | 16.7% |  50.0% | 1.5× | 31.2% |   0.1111 |
|       OK |    5 |   35.3 | 0.0% | 0.478 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    7 |  114.2 | 0.0% | 0.459 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   38.6 | 19.4% | 0.585 | 0.2 |       27 | 16.7% |  50.0% | 2.2× | 20.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available