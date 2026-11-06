# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-06 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (80.0%) is 30.0% HIGHER than DEGRADED (50.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (6.1%) is 2.9× the overall rate (2.1%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (11.0%) is 2.7× the overall rate (4.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   82 |   12.9 | 19.5% | 0.506 | 0.3 |       81 | 80.0% |  33.3% | 1.8× | 6.7% |   0.4444 |
|       OK |   42 |   37.0 | 7.1% | 0.419 | 0.1 |       42 | 33.3% |  20.0% | 2.8× | 5.4% |   0.1190 |
| DEGRADED |  118 |  120.5 | 5.1% | 0.385 | 0.1 |      115 | 50.0% |  13.6% | 2.6× | 3.2% |   0.1913 |
|      ALL |  242 |   69.6 | 10.3% | 0.432 | 0.1 |      238 | 66.7% |  25.4% | 2.5× | 4.6% |   0.2647 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   82 |   12.9 | 6.1% | 0.493 | 0.1 |       81 | 60.0% |  23.1% | 3.7× | 2.9% |   0.1605 |
|       OK |   42 |   37.0 | 0.0% | 0.358 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  118 |  120.5 | 0.0% | 0.340 | 0.0 |      115 |    - |   0.0% |    - | 0.0% |   0.0435 |
|      ALL |  242 |   69.6 | 2.1% | 0.395 | 0.0 |      238 | 60.0% |  16.7% | 7.9× | 0.9% |   0.0756 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   82 |   12.9 | 11.0% | 0.598 | 0.1 |       81 | 11.1% |  20.0% | 1.8× | 10.5% |   0.0617 |
|       OK |   42 |   37.0 | 2.4% | 0.535 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |  118 |  120.5 | 0.0% | 0.517 | 0.0 |      115 |    - |   0.0% |    - | 0.0% |   0.0087 |
|      ALL |  242 |   69.6 | 4.1% | 0.547 | 0.0 |      238 | 10.0% |  16.7% | 4.0× | 3.9% |   0.0252 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    1 |   11.1 | 100.0% | 0.893 | 1.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   30 |  110.6 | 16.7% | 0.460 | 0.2 |       27 | 60.0% |  60.0% | 3.2× | 9.1% |   0.1852 |
|      ALL |   31 |  107.4 | 19.4% | 0.474 | 0.2 |       27 | 60.0% |  60.0% | 3.2× | 9.1% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    1 |   11.1 | 0.0% | 0.956 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   30 |  110.6 | 0.0% | 0.463 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |
|      ALL |   31 |  107.4 | 0.0% | 0.478 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    1 |   11.1 | 0.0% | 0.629 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   30 |  110.6 | 0.0% | 0.563 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |  107.4 | 0.0% | 0.565 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available