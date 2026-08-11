# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-11 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (83.3%) is 83.3% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (7.9%) is 2.5× the overall rate (3.2%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (14.3%) is 2.2× the overall rate (6.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   63 |   12.6 | 19.1% | 0.500 | 0.3 |       62 | 83.3% |  34.5% | 1.8× | 6.1% |   0.4677 |
|       OK |   32 |   36.8 | 6.2% | 0.396 | 0.1 |       32 | 50.0% |  25.0% | 4.0× | 3.6% |   0.1250 |
| DEGRADED |   60 |  122.5 | 1.7% | 0.389 | 0.0 |       57 | 0.0% |   0.0% |    - | 2.3% |   0.2456 |
|      ALL |  155 |   60.1 | 9.7% | 0.436 | 0.1 |      151 | 73.3% |  23.4% | 2.4× | 3.9% |   0.3113 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   63 |   12.6 | 7.9% | 0.493 | 0.1 |       62 | 60.0% |  27.3% | 3.4× | 3.9% |   0.1774 |
|       OK |   32 |   36.8 | 0.0% | 0.329 | 0.0 |       32 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   60 |  122.5 | 0.0% | 0.333 | 0.0 |       57 |    - |   0.0% |    - | 0.0% |   0.0526 |
|      ALL |  155 |   60.1 | 3.2% | 0.397 | 0.0 |      151 | 60.0% |  21.4% | 6.5× | 1.5% |   0.0927 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   63 |   12.6 | 14.3% | 0.607 | 0.1 |       62 | 11.1% |  20.0% | 1.4× | 14.0% |   0.0806 |
|       OK |   32 |   36.8 | 3.1% | 0.527 | 0.0 |       32 | 0.0% |      - |    - | 3.1% |   0.0000 |
| DEGRADED |   60 |  122.5 | 0.0% | 0.493 | 0.0 |       57 |    - |   0.0% |    - | 0.0% |   0.0175 |
|      ALL |  155 |   60.1 | 6.5% | 0.546 | 0.1 |      151 | 10.0% |  16.7% | 2.5× | 6.2% |   0.0397 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.4 | 20.0% | 0.499 | 0.2 |        9 | 50.0% |  33.3% | 1.5× | 16.7% |   0.3333 |
|       OK |    6 |   36.6 | 16.7% | 0.390 | 0.2 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
| DEGRADED |   15 |  128.8 | 0.0% | 0.340 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.2500 |
|      ALL |   31 |   74.0 | 9.7% | 0.401 | 0.1 |       27 | 33.3% |  16.7% | 1.5× | 9.5% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.4 | 0.0% | 0.512 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.6 | 0.0% | 0.306 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  128.8 | 0.0% | 0.280 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   74.0 | 0.0% | 0.360 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.4 | 0.0% | 0.486 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.6 | 0.0% | 0.449 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  128.8 | 0.0% | 0.471 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   74.0 | 0.0% | 0.472 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available