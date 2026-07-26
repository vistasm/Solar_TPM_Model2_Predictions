# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-26 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (90.9%) is 90.9% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (8.3%) is 2.3× the overall rate (3.6%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (15.0%) is 2.1× the overall rate (7.2%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   12.5 | 20.0% | 0.508 | 0.3 |       58 | 90.9% |  34.5% | 1.8× | 3.5% |   0.5000 |
|       OK |   29 |   37.4 | 3.5% | 0.384 | 0.0 |       28 | 100.0% |  25.0% | 7.0× | 0.0% |   0.1429 |
| DEGRADED |   50 |  117.7 | 2.0% | 0.396 | 0.0 |       49 | 0.0% |   0.0% |    - | 2.7% |   0.2449 |
|      ALL |  139 |   55.5 | 10.1% | 0.442 | 0.1 |      135 | 84.6% |  24.4% | 2.5× | 2.2% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   12.5 | 8.3% | 0.500 | 0.1 |       58 | 60.0% |  27.3% | 3.2× | 4.3% |   0.1897 |
|       OK |   29 |   37.4 | 0.0% | 0.318 | 0.0 |       28 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   50 |  117.7 | 0.0% | 0.335 | 0.0 |       49 |    - |   0.0% |    - | 0.0% |   0.0612 |
|      ALL |  139 |   55.5 | 3.6% | 0.403 | 0.0 |      135 | 60.0% |  21.4% | 5.8× | 1.7% |   0.1037 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   12.5 | 15.0% | 0.612 | 0.1 |       58 | 11.1% |  20.0% | 1.3× | 15.1% |   0.0862 |
|       OK |   29 |   37.4 | 3.5% | 0.535 | 0.0 |       28 | 0.0% |      - |    - | 3.6% |   0.0000 |
| DEGRADED |   50 |  117.7 | 0.0% | 0.486 | 0.0 |       49 |    - |   0.0% |    - | 0.0% |   0.0204 |
|      ALL |  139 |   55.5 | 7.2% | 0.551 | 0.1 |      135 | 10.0% |  16.7% | 2.2× | 7.0% |   0.0444 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   11.4 | 44.4% | 0.685 | 0.8 |       16 | 85.7% |  60.0% | 1.4× | 16.7% |   0.6250 |
|       OK |    4 |   37.4 | 0.0% | 0.353 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |    9 |  115.1 | 11.1% | 0.479 | 0.1 |        8 | 0.0% |   0.0% |    - | 16.7% |   0.2500 |
|      ALL |   31 |   44.9 | 29.0% | 0.583 | 0.5 |       27 | 75.0% |  46.2% | 1.6× | 14.3% |   0.4815 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   11.4 | 27.8% | 0.673 | 0.3 |       16 | 60.0% |  60.0% | 1.9× | 18.2% |   0.3125 |
|       OK |    4 |   37.4 | 0.0% | 0.293 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |  115.1 | 0.0% | 0.388 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   44.9 | 16.1% | 0.541 | 0.2 |       27 | 60.0% |  60.0% | 3.2× | 9.1% |   0.1852 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   11.4 | 33.3% | 0.670 | 0.3 |       16 | 16.7% |  50.0% | 1.3× | 35.7% |   0.1250 |
|       OK |    4 |   37.4 | 0.0% | 0.500 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |  115.1 | 0.0% | 0.534 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   44.9 | 19.4% | 0.609 | 0.2 |       27 | 16.7% |  50.0% | 2.2× | 20.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available