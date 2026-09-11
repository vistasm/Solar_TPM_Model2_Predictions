# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-11 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (80.0%) is 80.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (6.2%) is 2.3× the overall rate (2.7%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (11.2%) is 2.1× the overall rate (5.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   80 |   12.9 | 18.8% | 0.506 | 0.3 |       78 | 80.0% |  33.3% | 1.7× | 7.1% |   0.4615 |
|       OK |   41 |   37.1 | 7.3% | 0.414 | 0.1 |       39 | 33.3% |  20.0% | 2.6× | 5.9% |   0.1282 |
| DEGRADED |   65 |  118.5 | 1.5% | 0.393 | 0.0 |       65 | 0.0% |   0.0% |    - | 2.0% |   0.2308 |
|      ALL |  186 |   55.1 | 10.2% | 0.446 | 0.1 |      182 | 68.4% |  23.2% | 2.2× | 4.8% |   0.3077 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   80 |   12.9 | 6.2% | 0.493 | 0.1 |       78 | 60.0% |  23.1% | 3.6× | 3.1% |   0.1667 |
|       OK |   41 |   37.1 | 0.0% | 0.354 | 0.0 |       39 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   65 |  118.5 | 0.0% | 0.338 | 0.0 |       65 |    - |   0.0% |    - | 0.0% |   0.0462 |
|      ALL |  186 |   55.1 | 2.7% | 0.408 | 0.0 |      182 | 60.0% |  18.8% | 6.8× | 1.2% |   0.0879 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   80 |   12.9 | 11.2% | 0.599 | 0.1 |       78 | 11.1% |  20.0% | 1.7× | 11.0% |   0.0641 |
|       OK |   41 |   37.1 | 2.4% | 0.535 | 0.0 |       39 | 0.0% |      - |    - | 2.6% |   0.0000 |
| DEGRADED |   65 |  118.5 | 0.0% | 0.498 | 0.0 |       65 |    - |   0.0% |    - | 0.0% |   0.0154 |
|      ALL |  186 |   55.1 | 5.4% | 0.550 | 0.1 |      182 | 10.0% |  16.7% | 3.0× | 5.1% |   0.0330 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   13.9 | 17.6% | 0.529 | 0.2 |       15 | 66.7% |  28.6% | 1.4× | 12.5% |   0.4667 |
|       OK |    9 |   37.9 | 11.1% | 0.479 | 0.1 |        7 | 0.0% |   0.0% |    - | 16.7% |   0.1429 |
| DEGRADED |    5 |   71.3 | 0.0% | 0.438 | 0.0 |        5 |    - |   0.0% |    - | 0.0% |   0.2000 |
|      ALL |   31 |   30.1 | 12.9% | 0.500 | 0.2 |       27 | 50.0% |  22.2% | 1.5× | 11.1% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   13.9 | 0.0% | 0.495 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|       OK |    9 |   37.9 | 0.0% | 0.441 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    5 |   71.3 | 0.0% | 0.397 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   30.1 | 0.0% | 0.463 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   13.9 | 0.0% | 0.570 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    9 |   37.9 | 0.0% | 0.565 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    5 |   71.3 | 0.0% | 0.556 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   30.1 | 0.0% | 0.567 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available