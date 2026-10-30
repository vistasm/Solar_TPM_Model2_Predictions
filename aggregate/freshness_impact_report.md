# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-10-30 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (80.0%) is 80.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M+**: FRESH alert rate (18.5%) is 2.0× the overall rate (9.2%) — score distribution shift detected
🟡 **M5+**: FRESH alert rate (6.2%) is 2.5× the overall rate (2.4%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (11.1%) is 2.3× the overall rate (4.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 18.5% | 0.501 | 0.3 |       81 | 80.0% |  33.3% | 1.8× | 6.7% |   0.4444 |
|       OK |   42 |   37.0 | 7.1% | 0.419 | 0.1 |       42 | 33.3% |  20.0% | 2.8× | 5.4% |   0.1190 |
| DEGRADED |   83 |  125.6 | 1.2% | 0.365 | 0.0 |       83 | 0.0% |   0.0% |    - | 1.5% |   0.1807 |
|      ALL |  206 |   63.2 | 9.2% | 0.429 | 0.1 |      206 | 68.4% |  23.2% | 2.5× | 4.0% |   0.2718 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 6.2% | 0.487 | 0.1 |       81 | 60.0% |  23.1% | 3.7× | 2.9% |   0.1605 |
|       OK |   42 |   37.0 | 0.0% | 0.358 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   83 |  125.6 | 0.0% | 0.306 | 0.0 |       83 |    - |   0.0% |    - | 0.0% |   0.0361 |
|      ALL |  206 |   63.2 | 2.4% | 0.388 | 0.0 |      206 | 60.0% |  18.8% | 7.7× | 1.1% |   0.0777 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 11.1% | 0.597 | 0.1 |       81 | 11.1% |  20.0% | 1.8× | 10.5% |   0.0617 |
|       OK |   42 |   37.0 | 2.4% | 0.535 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |   83 |  125.6 | 0.0% | 0.501 | 0.0 |       83 |    - |   0.0% |    - | 0.0% |   0.0120 |
|      ALL |  206 |   63.2 | 4.9% | 0.546 | 0.1 |      206 | 10.0% |  16.7% | 3.4× | 4.5% |   0.0291 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |    2 |  173.9 | 0.0% | 0.183 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    2 |  173.9 | 0.0% | 0.183 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |    2 |  173.9 | 0.0% | 0.101 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    2 |  173.9 | 0.0% | 0.101 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |    2 |  173.9 | 0.0% | 0.489 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    2 |  173.9 | 0.0% | 0.489 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available