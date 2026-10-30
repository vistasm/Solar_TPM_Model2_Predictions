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

🟢 **M+**: FRESH precision (80.0%) is 30.0% HIGHER than DEGRADED (50.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (6.2%) is 2.8× the overall rate (2.2%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (11.1%) is 2.5× the overall rate (4.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 18.5% | 0.501 | 0.3 |       81 | 80.0% |  33.3% | 1.8× | 6.7% |   0.4444 |
|       OK |   42 |   37.0 | 7.1% | 0.419 | 0.1 |       42 | 33.3% |  20.0% | 2.8× | 5.4% |   0.1190 |
| DEGRADED |  105 |  119.5 | 5.7% | 0.398 | 0.1 |      105 | 50.0% |  13.6% | 2.4× | 3.6% |   0.2095 |
|      ALL |  228 |   66.4 | 10.5% | 0.438 | 0.1 |      228 | 66.7% |  25.4% | 2.4× | 4.9% |   0.2763 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 6.2% | 0.487 | 0.1 |       81 | 60.0% |  23.1% | 3.7× | 2.9% |   0.1605 |
|       OK |   42 |   37.0 | 0.0% | 0.358 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  105 |  119.5 | 0.0% | 0.356 | 0.0 |      105 |    - |   0.0% |    - | 0.0% |   0.0476 |
|      ALL |  228 |   66.4 | 2.2% | 0.403 | 0.0 |      228 | 60.0% |  16.7% | 7.6× | 0.9% |   0.0789 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   81 |   12.9 | 11.1% | 0.597 | 0.1 |       81 | 11.1% |  20.0% | 1.8× | 10.5% |   0.0617 |
|       OK |   42 |   37.0 | 2.4% | 0.535 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |  105 |  119.5 | 0.0% | 0.518 | 0.0 |      105 |    - |   0.0% |    - | 0.0% |   0.0095 |
|      ALL |  228 |   66.4 | 4.4% | 0.549 | 0.0 |      228 | 10.0% |  16.7% | 3.8× | 4.0% |   0.0263 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   24 |  102.9 | 20.8% | 0.493 | 0.2 |       24 | 60.0% |  42.9% | 2.1× | 11.8% |   0.2917 |
|      ALL |   24 |  102.9 | 20.8% | 0.493 | 0.2 |       24 | 60.0% |  42.9% | 2.1× | 11.8% |   0.2917 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   24 |  102.9 | 0.0% | 0.507 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   24 |  102.9 | 0.0% | 0.507 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   24 |  102.9 | 0.0% | 0.577 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   24 |  102.9 | 0.0% | 0.577 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available