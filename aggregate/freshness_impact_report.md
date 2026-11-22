# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-22 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (72.2%) is 15.1% HIGHER than DEGRADED (57.1%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (5.6%) is 2.9× the overall rate (1.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.1%) is 2.6× the overall rate (3.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   89 |   12.7 | 20.2% | 0.517 | 0.3 |       88 | 72.2% |  34.2% | 1.7× | 10.0% |   0.4318 |
|       OK |   48 |   36.6 | 10.4% | 0.433 | 0.1 |       46 | 40.0% |  33.3% | 3.1× | 7.5% |   0.1304 |
| DEGRADED |  121 |  119.0 | 5.8% | 0.385 | 0.1 |      120 | 57.1% |  16.7% | 2.9× | 3.1% |   0.2000 |
|      ALL |  258 |   67.0 | 11.6% | 0.439 | 0.1 |      254 | 63.3% |  27.9% | 2.4× | 5.9% |   0.2677 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   89 |   12.7 | 5.6% | 0.503 | 0.1 |       88 | 60.0% |  23.1% | 4.1× | 2.7% |   0.1477 |
|       OK |   48 |   36.6 | 0.0% | 0.381 | 0.0 |       46 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  121 |  119.0 | 0.0% | 0.341 | 0.0 |      120 |    - |   0.0% |    - | 0.0% |   0.0417 |
|      ALL |  258 |   67.0 | 1.9% | 0.404 | 0.0 |      254 | 60.0% |  16.7% | 8.5× | 0.9% |   0.0709 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   89 |   12.7 | 10.1% | 0.595 | 0.1 |       88 | 11.1% |  20.0% | 2.0× | 9.6% |   0.0568 |
|       OK |   48 |   36.6 | 2.1% | 0.539 | 0.0 |       46 | 0.0% |      - |    - | 2.2% |   0.0000 |
| DEGRADED |  121 |  119.0 | 0.0% | 0.517 | 0.0 |      120 |    - |   0.0% |    - | 0.0% |   0.0083 |
|      ALL |  258 |   67.0 | 3.9% | 0.548 | 0.0 |      254 | 10.0% |  16.7% | 4.2× | 3.6% |   0.0236 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.9 | 37.5% | 0.678 | 0.4 |        7 | 33.3% |  50.0% | 1.2× | 40.0% |   0.2857 |
|       OK |    6 |   33.4 | 33.3% | 0.532 | 0.3 |        4 | 50.0% | 100.0% | 2.0× | 33.3% |   0.2500 |
| DEGRADED |   17 |  114.9 | 5.9% | 0.300 | 0.1 |       16 | 100.0% |  50.0% | 8.0× | 0.0% |   0.1250 |
|      ALL |   31 |   72.3 | 19.4% | 0.442 | 0.2 |       27 | 50.0% |  60.0% | 2.7× | 13.6% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.9 | 0.0% | 0.664 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   33.4 | 0.0% | 0.541 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  114.9 | 0.0% | 0.241 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   72.3 | 0.0% | 0.408 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.9 | 0.0% | 0.571 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   33.4 | 0.0% | 0.563 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  114.9 | 0.0% | 0.511 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   72.3 | 0.0% | 0.537 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available