# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-18 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (72.2%) is 15.1% HIGHER than DEGRADED (57.1%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (5.7%) is 2.9× the overall rate (2.0%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.2%) is 2.6× the overall rate (3.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   88 |   12.7 | 20.4% | 0.517 | 0.3 |       85 | 72.2% |  35.1% | 1.7× | 10.4% |   0.4353 |
|       OK |   46 |   36.7 | 10.9% | 0.438 | 0.1 |       45 | 40.0% |  33.3% | 3.0× | 7.7% |   0.1333 |
| DEGRADED |  120 |  119.5 | 5.8% | 0.387 | 0.1 |      120 | 57.1% |  16.7% | 2.9× | 3.1% |   0.2000 |
|      ALL |  254 |   67.5 | 11.8% | 0.441 | 0.1 |      250 | 63.3% |  28.4% | 2.4× | 6.0% |   0.2680 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   88 |   12.7 | 5.7% | 0.501 | 0.1 |       85 | 60.0% |  23.1% | 3.9× | 2.8% |   0.1529 |
|       OK |   46 |   36.7 | 0.0% | 0.386 | 0.0 |       45 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  120 |  119.5 | 0.0% | 0.343 | 0.0 |      120 |    - |   0.0% |    - | 0.0% |   0.0417 |
|      ALL |  254 |   67.5 | 2.0% | 0.406 | 0.0 |      250 | 60.0% |  16.7% | 8.3× | 0.9% |   0.0720 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   88 |   12.7 | 10.2% | 0.596 | 0.1 |       85 | 11.1% |  20.0% | 1.9× | 10.0% |   0.0588 |
|       OK |   46 |   36.7 | 2.2% | 0.539 | 0.0 |       45 | 0.0% |      - |    - | 2.2% |   0.0000 |
| DEGRADED |  120 |  119.5 | 0.0% | 0.517 | 0.0 |      120 |    - |   0.0% |    - | 0.0% |   0.0083 |
|      ALL |  254 |   67.5 | 3.9% | 0.548 | 0.0 |      250 | 10.0% |  16.7% | 4.2× | 3.7% |   0.0240 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   10.2 | 42.9% | 0.698 | 0.4 |        4 | 33.3% | 100.0% | 1.3× | 66.7% |   0.2500 |
|       OK |    4 |   33.7 | 50.0% | 0.640 | 0.5 |        3 | 50.0% | 100.0% | 1.5× | 50.0% |   0.3333 |
| DEGRADED |   20 |  113.8 | 5.0% | 0.321 | 0.1 |       20 | 100.0% |  33.3% | 6.7× | 0.0% |   0.1500 |
|      ALL |   31 |   80.1 | 19.4% | 0.447 | 0.2 |       27 | 50.0% |  60.0% | 2.7× | 13.6% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   10.2 | 0.0% | 0.663 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    4 |   33.7 | 0.0% | 0.682 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   20 |  113.8 | 0.0% | 0.296 | 0.0 |       20 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   80.1 | 0.0% | 0.429 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   10.2 | 0.0% | 0.577 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    4 |   33.7 | 0.0% | 0.581 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   20 |  113.8 | 0.0% | 0.522 | 0.0 |       20 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   80.1 | 0.0% | 0.542 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available