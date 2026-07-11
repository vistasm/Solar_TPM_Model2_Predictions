# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-11 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (90.0%) is 90.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (9.4%) is 2.3× the overall rate (4.0%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (17.0%) is 2.1× the overall rate (8.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   53 |   12.3 | 18.9% | 0.500 | 0.3 |       49 | 90.0% |  36.0% | 1.8× | 4.2% |   0.5102 |
|       OK |   26 |   36.9 | 3.9% | 0.398 | 0.0 |       26 | 100.0% |  25.0% | 6.5× | 0.0% |   0.1538 |
| DEGRADED |   45 |  120.4 | 2.2% | 0.405 | 0.0 |       45 | 0.0% |   0.0% |    - | 2.9% |   0.2444 |
|      ALL |  124 |   56.7 | 9.7% | 0.444 | 0.1 |      120 | 83.3% |  25.0% | 2.5× | 2.5% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   53 |   12.3 | 9.4% | 0.489 | 0.1 |       49 | 60.0% |  27.3% | 2.7× | 5.3% |   0.2245 |
|       OK |   26 |   36.9 | 0.0% | 0.334 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   45 |  120.4 | 0.0% | 0.351 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |  124 |   56.7 | 4.0% | 0.406 | 0.0 |      120 | 60.0% |  21.4% | 5.1× | 1.9% |   0.1167 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   53 |   12.3 | 17.0% | 0.629 | 0.2 |       49 | 11.1% |  20.0% | 1.1× | 18.2% |   0.1020 |
|       OK |   26 |   36.9 | 3.9% | 0.545 | 0.0 |       26 | 0.0% |      - |    - | 3.9% |   0.0000 |
| DEGRADED |   45 |  120.4 | 0.0% | 0.500 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0222 |
|      ALL |  124 |   56.7 | 8.1% | 0.565 | 0.1 |      120 | 10.0% |  16.7% | 2.0× | 7.9% |   0.0500 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.4 | 35.3% | 0.619 | 0.7 |       13 | 83.3% |  62.5% | 1.4× | 20.0% |   0.6154 |
|       OK |    4 |   36.1 | 0.0% | 0.406 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
| DEGRADED |   10 |  111.1 | 10.0% | 0.506 | 0.1 |       10 | 0.0% |   0.0% |    - | 12.5% |   0.2000 |
|      ALL |   31 |   46.2 | 22.6% | 0.555 | 0.4 |       27 | 71.4% |  45.5% | 1.8× | 12.5% |   0.4074 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.4 | 29.4% | 0.599 | 0.3 |       13 | 60.0% |  50.0% | 1.3× | 28.6% |   0.4615 |
|       OK |    4 |   36.1 | 0.0% | 0.331 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  111.1 | 0.0% | 0.456 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.2 | 16.1% | 0.518 | 0.2 |       27 | 60.0% |  50.0% | 2.7× | 9.5% |   0.2222 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.4 | 35.3% | 0.689 | 0.3 |       13 | 16.7% |  50.0% | 1.1× | 45.5% |   0.1538 |
|       OK |    4 |   36.1 | 0.0% | 0.541 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  111.1 | 0.0% | 0.546 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.2 | 19.4% | 0.624 | 0.2 |       27 | 16.7% |  50.0% | 2.2× | 20.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available