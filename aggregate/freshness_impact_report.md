# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-15 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (72.2%) is 15.1% HIGHER than DEGRADED (57.1%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (5.8%) is 2.9× the overall rate (2.0%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.5%) is 2.6× the overall rate (4.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   86 |   12.7 | 20.9% | 0.516 | 0.3 |       84 | 72.2% |  35.1% | 1.6× | 10.6% |   0.4405 |
|       OK |   45 |   36.8 | 11.1% | 0.441 | 0.1 |       44 | 40.0% |  33.3% | 2.9× | 7.9% |   0.1364 |
| DEGRADED |  120 |  119.5 | 5.8% | 0.387 | 0.1 |      119 | 57.1% |  16.7% | 2.8× | 3.2% |   0.2017 |
|      ALL |  251 |   68.1 | 11.9% | 0.441 | 0.1 |      247 | 63.3% |  28.4% | 2.3× | 6.1% |   0.2713 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   86 |   12.7 | 5.8% | 0.505 | 0.1 |       84 | 60.0% |  23.1% | 3.9× | 2.8% |   0.1548 |
|       OK |   45 |   36.8 | 0.0% | 0.386 | 0.0 |       44 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  120 |  119.5 | 0.0% | 0.343 | 0.0 |      119 |    - |   0.0% |    - | 0.0% |   0.0420 |
|      ALL |  251 |   68.1 | 2.0% | 0.406 | 0.0 |      247 | 60.0% |  16.7% | 8.2× | 0.9% |   0.0729 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   86 |   12.7 | 10.5% | 0.597 | 0.1 |       84 | 11.1% |  20.0% | 1.9× | 10.1% |   0.0595 |
|       OK |   45 |   36.8 | 2.2% | 0.539 | 0.0 |       44 | 0.0% |      - |    - | 2.3% |   0.0000 |
| DEGRADED |  120 |  119.5 | 0.0% | 0.517 | 0.0 |      119 |    - |   0.0% |    - | 0.0% |   0.0084 |
|      ALL |  251 |   68.1 | 4.0% | 0.549 | 0.0 |      247 | 10.0% |  16.7% | 4.1× | 3.7% |   0.0243 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |   10.0 | 60.0% | 0.759 | 0.6 |        3 | 33.3% | 100.0% | 1.0× | 100.0% |   0.3333 |
|       OK |    3 |   34.2 | 66.7% | 0.746 | 0.7 |        2 | 50.0% | 100.0% | 1.0× | 100.0% |   0.5000 |
| DEGRADED |   23 |  111.5 | 4.3% | 0.346 | 0.0 |       22 | 100.0% |  25.0% | 5.5× | 0.0% |   0.1818 |
|      ALL |   31 |   87.7 | 19.4% | 0.451 | 0.2 |       27 | 50.0% |  50.0% | 2.2× | 14.3% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |   10.0 | 0.0% | 0.797 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   34.2 | 0.0% | 0.788 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   23 |  111.5 | 0.0% | 0.347 | 0.0 |       22 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   87.7 | 0.0% | 0.463 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |   10.0 | 0.0% | 0.599 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   34.2 | 0.0% | 0.596 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   23 |  111.5 | 0.0% | 0.534 | 0.0 |       22 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   87.7 | 0.0% | 0.550 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available