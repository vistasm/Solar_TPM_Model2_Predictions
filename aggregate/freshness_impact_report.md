# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-12 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (10.5%) is 2.0× the overall rate (5.3%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   38 |   13.2 | 10.5% | 0.443 | 0.1 |       35 | 100.0% |  23.5% | 2.1× | 0.0% |   0.4857 |
|       OK |   22 |   37.0 | 4.5% | 0.396 | 0.1 |       22 | 100.0% |  33.3% | 7.3× | 0.0% |   0.1364 |
| DEGRADED |   35 |  123.0 | 0.0% | 0.377 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.2647 |
|      ALL |   95 |   59.2 | 5.3% | 0.408 | 0.1 |       91 | 100.0% |  17.2% | 3.1× | 0.0% |   0.3187 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   38 |   13.2 | 0.0% | 0.443 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |   22 |   37.0 | 0.0% | 0.335 | 0.0 |       22 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   35 |  123.0 | 0.0% | 0.321 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0882 |
|      ALL |   95 |   59.2 | 0.0% | 0.373 | 0.0 |       91 |    - |   0.0% |    - | 0.0% |   0.0879 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   38 |   13.2 | 7.9% | 0.603 | 0.1 |       35 | 0.0% |   0.0% |    - | 9.4% |   0.0857 |
|       OK |   22 |   37.0 | 4.5% | 0.546 | 0.1 |       22 | 0.0% |      - |    - | 4.5% |   0.0000 |
| DEGRADED |   35 |  123.0 | 0.0% | 0.487 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0294 |
|      ALL |   95 |   59.2 | 4.2% | 0.547 | 0.0 |       91 | 0.0% |   0.0% |    - | 4.6% |   0.0440 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   14.2 | 0.0% | 0.400 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.3333 |
|       OK |    7 |   39.3 | 0.0% | 0.368 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.5 | 0.0% | 0.440 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.3636 |
|      ALL |   31 |   49.0 | 0.0% | 0.408 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   14.2 | 0.0% | 0.397 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    7 |   39.3 | 0.0% | 0.273 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.5 | 0.0% | 0.335 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   31 |   49.0 | 0.0% | 0.345 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   14.2 | 8.3% | 0.609 | 0.1 |        9 | 0.0% |   0.0% |    - | 12.5% |   0.1111 |
|       OK |    7 |   39.3 | 0.0% | 0.586 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.5 | 0.0% | 0.570 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   49.0 | 3.2% | 0.589 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available