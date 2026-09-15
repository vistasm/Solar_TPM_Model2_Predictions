# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-15 UTC
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
🟡 **X+**: FRESH alert rate (11.2%) is 2.1× the overall rate (5.3%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   80 |   12.9 | 18.8% | 0.506 | 0.3 |       80 | 80.0% |  33.3% | 1.8× | 6.8% |   0.4500 |
|       OK |   41 |   37.1 | 7.3% | 0.414 | 0.1 |       41 | 33.3% |  20.0% | 2.7× | 5.6% |   0.1220 |
| DEGRADED |   68 |  118.1 | 1.5% | 0.385 | 0.0 |       65 | 0.0% |   0.0% |    - | 2.0% |   0.2308 |
|      ALL |  189 |   56.0 | 10.1% | 0.443 | 0.1 |      186 | 68.4% |  23.2% | 2.3× | 4.6% |   0.3011 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   80 |   12.9 | 6.2% | 0.493 | 0.1 |       80 | 60.0% |  23.1% | 3.7× | 3.0% |   0.1625 |
|       OK |   41 |   37.1 | 0.0% | 0.354 | 0.0 |       41 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   68 |  118.1 | 0.0% | 0.331 | 0.0 |       65 |    - |   0.0% |    - | 0.0% |   0.0462 |
|      ALL |  189 |   56.0 | 2.6% | 0.404 | 0.0 |      186 | 60.0% |  18.8% | 7.0× | 1.2% |   0.0860 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   80 |   12.9 | 11.2% | 0.599 | 0.1 |       80 | 11.1% |  20.0% | 1.8× | 10.7% |   0.0625 |
|       OK |   41 |   37.1 | 2.4% | 0.535 | 0.0 |       41 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |   68 |  118.1 | 0.0% | 0.499 | 0.0 |       65 |    - |   0.0% |    - | 0.0% |   0.0154 |
|      ALL |  189 |   56.0 | 5.3% | 0.549 | 0.1 |      186 | 10.0% |  16.7% | 3.1× | 5.0% |   0.0323 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.4 | 18.8% | 0.531 | 0.2 |       16 | 66.7% |  28.6% | 1.5× | 11.1% |   0.4375 |
|       OK |    8 |   37.6 | 0.0% | 0.438 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
| DEGRADED |    6 |   88.2 | 0.0% | 0.330 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
|      ALL |   30 |   34.8 | 10.0% | 0.466 | 0.1 |       27 | 66.7% |  22.2% | 2.0× | 5.6% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.4 | 0.0% | 0.487 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    8 |   37.6 | 0.0% | 0.401 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   88.2 | 0.0% | 0.269 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   34.8 | 0.0% | 0.421 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.4 | 0.0% | 0.572 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   37.6 | 0.0% | 0.562 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   88.2 | 0.0% | 0.548 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   34.8 | 0.0% | 0.565 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available