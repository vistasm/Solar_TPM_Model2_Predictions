# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-12 UTC
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
🟡 **X+**: FRESH alert rate (14.3%) is 2.2× the overall rate (6.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   63 |   12.6 | 19.1% | 0.500 | 0.3 |       62 | 83.3% |  34.5% | 1.8× | 6.1% |   0.4677 |
|       OK |   33 |   36.9 | 9.1% | 0.409 | 0.1 |       32 | 50.0% |  25.0% | 4.0× | 3.6% |   0.1250 |
| DEGRADED |   60 |  122.5 | 1.7% | 0.389 | 0.0 |       58 | 0.0% |   0.0% |    - | 2.3% |   0.2414 |
|      ALL |  156 |   60.0 | 10.3% | 0.438 | 0.1 |      152 | 73.3% |  23.4% | 2.4× | 3.8% |   0.3092 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   63 |   12.6 | 7.9% | 0.493 | 0.1 |       62 | 60.0% |  27.3% | 3.4× | 3.9% |   0.1774 |
|       OK |   33 |   36.9 | 0.0% | 0.342 | 0.0 |       32 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   60 |  122.5 | 0.0% | 0.333 | 0.0 |       58 |    - |   0.0% |    - | 0.0% |   0.0517 |
|      ALL |  156 |   60.0 | 3.2% | 0.400 | 0.0 |      152 | 60.0% |  21.4% | 6.5× | 1.5% |   0.0921 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   63 |   12.6 | 14.3% | 0.607 | 0.1 |       62 | 11.1% |  20.0% | 1.4× | 14.0% |   0.0806 |
|       OK |   33 |   36.9 | 3.0% | 0.529 | 0.0 |       32 | 0.0% |      - |    - | 3.1% |   0.0000 |
| DEGRADED |   60 |  122.5 | 0.0% | 0.493 | 0.0 |       58 |    - |   0.0% |    - | 0.0% |   0.0172 |
|      ALL |  156 |   60.0 | 6.4% | 0.546 | 0.1 |      152 | 10.0% |  16.7% | 2.5× | 6.2% |   0.0395 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   15.4 | 22.2% | 0.488 | 0.2 |        8 | 50.0% |  50.0% | 2.0× | 16.7% |   0.2500 |
|       OK |    7 |   37.2 | 28.6% | 0.450 | 0.3 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
| DEGRADED |   15 |  128.8 | 0.0% | 0.340 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.2308 |
|      ALL |   31 |   75.2 | 12.9% | 0.408 | 0.1 |       27 | 33.3% |  20.0% | 1.8× | 9.1% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   15.4 | 0.0% | 0.503 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   37.2 | 0.0% | 0.371 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  128.8 | 0.0% | 0.280 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   75.2 | 0.0% | 0.365 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   15.4 | 0.0% | 0.487 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   37.2 | 0.0% | 0.469 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  128.8 | 0.0% | 0.471 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   75.2 | 0.0% | 0.475 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available