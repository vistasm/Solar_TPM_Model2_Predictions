# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-26 UTC
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
🟡 **X+**: FRESH alert rate (10.1%) is 2.6× the overall rate (3.8%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   89 |   12.7 | 20.2% | 0.517 | 0.3 |       89 | 72.2% |  34.2% | 1.7× | 9.8% |   0.4270 |
|       OK |   48 |   36.6 | 10.4% | 0.433 | 0.1 |       48 | 40.0% |  28.6% | 2.7× | 7.3% |   0.1458 |
| DEGRADED |  125 |  119.2 | 5.6% | 0.377 | 0.1 |      121 | 57.1% |  16.7% | 2.9× | 3.1% |   0.1983 |
|      ALL |  262 |   67.9 | 11.5% | 0.435 | 0.1 |      258 | 63.3% |  27.5% | 2.4× | 5.8% |   0.2674 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   89 |   12.7 | 5.6% | 0.503 | 0.1 |       89 | 60.0% |  23.1% | 4.1× | 2.6% |   0.1461 |
|       OK |   48 |   36.6 | 0.0% | 0.381 | 0.0 |       48 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  125 |  119.2 | 0.0% | 0.333 | 0.0 |      121 |    - |   0.0% |    - | 0.0% |   0.0413 |
|      ALL |  262 |   67.9 | 1.9% | 0.399 | 0.0 |      258 | 60.0% |  16.7% | 8.6× | 0.8% |   0.0698 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   89 |   12.7 | 10.1% | 0.595 | 0.1 |       89 | 11.1% |  20.0% | 2.0× | 9.5% |   0.0562 |
|       OK |   48 |   36.6 | 2.1% | 0.539 | 0.0 |       48 | 0.0% |      - |    - | 2.1% |   0.0000 |
| DEGRADED |  125 |  119.2 | 0.0% | 0.517 | 0.0 |      121 |    - |   0.0% |    - | 0.0% |   0.0083 |
|      ALL |  262 |   67.9 | 3.8% | 0.547 | 0.0 |      258 | 10.0% |  16.7% | 4.3× | 3.6% |   0.0233 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.9 | 37.5% | 0.678 | 0.4 |        8 | 33.3% |  50.0% | 1.3× | 33.3% |   0.2500 |
|       OK |    6 |   33.4 | 33.3% | 0.532 | 0.3 |        6 | 50.0% |  50.0% | 1.5× | 25.0% |   0.3333 |
| DEGRADED |   17 |  121.3 | 5.9% | 0.261 | 0.1 |       13 | 100.0% |  50.0% | 6.5× | 0.0% |   0.1538 |
|      ALL |   31 |   75.8 | 19.4% | 0.421 | 0.2 |       27 | 50.0% |  50.0% | 2.2× | 14.3% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.9 | 0.0% | 0.664 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   33.4 | 0.0% | 0.541 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  121.3 | 0.0% | 0.202 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   75.8 | 0.0% | 0.387 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   10.9 | 0.0% | 0.571 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   33.4 | 0.0% | 0.563 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  121.3 | 0.0% | 0.509 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   75.8 | 0.0% | 0.536 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available