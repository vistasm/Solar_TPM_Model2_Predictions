# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-19 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (90.0%) is 90.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (8.9%) is 2.4× the overall rate (3.8%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (16.1%) is 2.1× the overall rate (7.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   56 |   12.4 | 17.9% | 0.496 | 0.3 |       56 | 90.0% |  33.3% | 1.9× | 3.5% |   0.4821 |
|       OK |   28 |   37.3 | 3.6% | 0.385 | 0.0 |       27 | 100.0% |  25.0% | 6.8× | 0.0% |   0.1481 |
| DEGRADED |   48 |  118.4 | 2.1% | 0.391 | 0.0 |       45 | 0.0% |   0.0% |    - | 2.9% |   0.2444 |
|      ALL |  132 |   56.2 | 9.1% | 0.434 | 0.1 |      128 | 83.3% |  23.8% | 2.5× | 2.3% |   0.3281 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   56 |   12.4 | 8.9% | 0.484 | 0.1 |       56 | 60.0% |  27.3% | 3.0× | 4.4% |   0.1964 |
|       OK |   28 |   37.3 | 0.0% | 0.321 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   48 |  118.4 | 0.0% | 0.335 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |  132 |   56.2 | 3.8% | 0.395 | 0.0 |      128 | 60.0% |  21.4% | 5.5× | 1.8% |   0.1094 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   56 |   12.4 | 16.1% | 0.622 | 0.2 |       56 | 11.1% |  20.0% | 1.2× | 15.7% |   0.0893 |
|       OK |   28 |   37.3 | 3.6% | 0.536 | 0.0 |       27 | 0.0% |      - |    - | 3.7% |   0.0000 |
| DEGRADED |   48 |  118.4 | 0.0% | 0.487 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0222 |
|      ALL |  132 |   56.2 | 7.6% | 0.555 | 0.1 |      128 | 10.0% |  16.7% | 2.1× | 7.4% |   0.0469 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.4 | 35.3% | 0.635 | 0.7 |       17 | 83.3% |  50.0% | 1.4× | 14.3% |   0.5882 |
|       OK |    4 |   36.3 | 0.0% | 0.441 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |   10 |  111.3 | 10.0% | 0.472 | 0.1 |        7 | 0.0% |   0.0% |    - | 20.0% |   0.2857 |
|      ALL |   31 |   46.3 | 22.6% | 0.557 | 0.4 |       27 | 71.4% |  38.5% | 1.5× | 14.3% |   0.4815 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.4 | 29.4% | 0.590 | 0.3 |       17 | 60.0% |  50.0% | 1.7× | 18.2% |   0.3529 |
|       OK |    4 |   36.3 | 0.0% | 0.319 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  111.3 | 0.0% | 0.390 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.3 | 16.1% | 0.490 | 0.2 |       27 | 60.0% |  50.0% | 2.7× | 9.5% |   0.2222 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.4 | 35.3% | 0.681 | 0.3 |       17 | 16.7% |  50.0% | 1.4× | 33.3% |   0.1176 |
|       OK |    4 |   36.3 | 0.0% | 0.532 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  111.3 | 0.0% | 0.527 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.3 | 19.4% | 0.612 | 0.2 |       27 | 16.7% |  50.0% | 2.2× | 20.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available