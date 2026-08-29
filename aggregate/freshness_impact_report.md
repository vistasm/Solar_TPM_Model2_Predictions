# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-29 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (76.9%) is 76.9% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (6.9%) is 2.4× the overall rate (2.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (12.5%) is 2.2× the overall rate (5.8%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   72 |   12.7 | 19.4% | 0.523 | 0.3 |       70 | 76.9% |  31.2% | 1.7× | 7.9% |   0.4571 |
|       OK |   37 |   37.2 | 8.1% | 0.432 | 0.1 |       36 | 33.3% |  20.0% | 2.4× | 6.5% |   0.1389 |
| DEGRADED |   64 |  119.1 | 1.6% | 0.394 | 0.0 |       63 | 0.0% |   0.0% |    - | 2.1% |   0.2381 |
|      ALL |  173 |   57.3 | 10.4% | 0.456 | 0.1 |      169 | 64.7% |  21.1% | 2.1× | 5.1% |   0.3077 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   72 |   12.7 | 6.9% | 0.514 | 0.1 |       70 | 60.0% |  23.1% | 3.2× | 3.5% |   0.1857 |
|       OK |   37 |   37.2 | 0.0% | 0.375 | 0.0 |       36 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   64 |  119.1 | 0.0% | 0.341 | 0.0 |       63 |    - |   0.0% |    - | 0.0% |   0.0476 |
|      ALL |  173 |   57.3 | 2.9% | 0.420 | 0.0 |      169 | 60.0% |  18.8% | 6.3× | 1.3% |   0.0947 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   72 |   12.7 | 12.5% | 0.606 | 0.1 |       70 | 11.1% |  20.0% | 1.6× | 12.3% |   0.0714 |
|       OK |   37 |   37.2 | 2.7% | 0.536 | 0.0 |       36 | 0.0% |      - |    - | 2.8% |   0.0000 |
| DEGRADED |   64 |  119.1 | 0.0% | 0.497 | 0.0 |       63 |    - |   0.0% |    - | 0.0% |   0.0159 |
|      ALL |  173 |   57.3 | 5.8% | 0.550 | 0.1 |      169 | 10.0% |  16.7% | 2.8× | 5.5% |   0.0355 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.4 | 18.2% | 0.620 | 0.3 |        9 | 0.0% |   0.0% |    - | 16.7% |   0.3333 |
|       OK |    6 |   39.4 | 33.3% | 0.682 | 0.3 |        5 | 0.0% |   0.0% |    - | 50.0% |   0.2000 |
| DEGRADED |   14 |  124.4 | 0.0% | 0.390 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|      ALL |   31 |   68.6 | 12.9% | 0.528 | 0.2 |       27 | 0.0% |   0.0% |    - | 14.3% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.4 | 0.0% | 0.603 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.2222 |
|       OK |    6 |   39.4 | 0.0% | 0.663 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  124.4 | 0.0% | 0.363 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   68.6 | 0.0% | 0.507 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.4 | 0.0% | 0.584 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   39.4 | 0.0% | 0.586 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  124.4 | 0.0% | 0.533 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   68.6 | 0.0% | 0.561 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available