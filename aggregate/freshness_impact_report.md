# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-01 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (12.9%) is 2.2× the overall rate (5.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   31 |   13.3 | 12.9% | 0.436 | 0.2 |       30 | 100.0% |  26.7% | 2.0× | 0.0% |   0.5000 |
|       OK |   20 |   36.6 | 5.0% | 0.394 | 0.1 |       19 | 100.0% |  33.3% | 6.3× | 0.0% |   0.1579 |
| DEGRADED |   33 |  125.6 | 0.0% | 0.370 | 0.0 |       31 |    - |   0.0% |    - | 0.0% |   0.1935 |
|      ALL |   84 |   63.0 | 5.9% | 0.400 | 0.1 |       80 | 100.0% |  20.8% | 3.3× | 0.0% |   0.3000 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   31 |   13.3 | 0.0% | 0.424 | 0.0 |       30 |    - |   0.0% |    - | 0.0% |   0.1333 |
|       OK |   20 |   36.6 | 0.0% | 0.332 | 0.0 |       19 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   33 |  125.6 | 0.0% | 0.313 | 0.0 |       31 |    - |   0.0% |    - | 0.0% |   0.0645 |
|      ALL |   84 |   63.0 | 0.0% | 0.358 | 0.0 |       80 |    - |   0.0% |    - | 0.0% |   0.0750 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   31 |   13.3 | 6.5% | 0.590 | 0.1 |       30 | 0.0% |   0.0% |    - | 7.1% |   0.0667 |
|       OK |   20 |   36.6 | 5.0% | 0.532 | 0.1 |       19 | 0.0% |      - |    - | 5.3% |   0.0000 |
| DEGRADED |   33 |  125.6 | 0.0% | 0.483 | 0.0 |       31 |    - |   0.0% |    - | 0.0% |   0.0323 |
|      ALL |   84 |   63.0 | 3.6% | 0.534 | 0.0 |       80 | 0.0% |   0.0% |    - | 3.9% |   0.0375 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.0 | 0.0% | 0.361 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|       OK |    8 |   37.4 | 0.0% | 0.365 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   85.3 | 0.0% | 0.401 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.2500 |
|      ALL |   31 |   52.3 | 0.0% | 0.380 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.0 | 0.0% | 0.281 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   37.4 | 0.0% | 0.255 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   85.3 | 0.0% | 0.299 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   31 |   52.3 | 0.0% | 0.282 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.0 | 0.0% | 0.543 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   37.4 | 0.0% | 0.546 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   85.3 | 0.0% | 0.564 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   52.3 | 0.0% | 0.554 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available