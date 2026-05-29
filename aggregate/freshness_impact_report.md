# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-29 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (13.3%) is 2.2× the overall rate (6.2%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   13.0 | 13.3% | 0.442 | 0.2 |       30 | 100.0% |  26.7% | 2.0× | 0.0% |   0.5000 |
|       OK |   19 |   36.1 | 5.3% | 0.385 | 0.1 |       19 | 100.0% |  33.3% | 6.3× | 0.0% |   0.1579 |
| DEGRADED |   32 |  127.4 | 0.0% | 0.372 | 0.0 |       28 |    - |   0.0% |    - | 0.0% |   0.2143 |
|      ALL |   81 |   63.6 | 6.2% | 0.401 | 0.1 |       77 | 100.0% |  20.8% | 3.2× | 0.0% |   0.3117 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   13.0 | 0.0% | 0.430 | 0.0 |       30 |    - |   0.0% |    - | 0.0% |   0.1333 |
|       OK |   19 |   36.1 | 0.0% | 0.331 | 0.0 |       19 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   32 |  127.4 | 0.0% | 0.315 | 0.0 |       28 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   81 |   63.6 | 0.0% | 0.361 | 0.0 |       77 |    - |   0.0% |    - | 0.0% |   0.0779 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   13.0 | 6.7% | 0.590 | 0.1 |       30 | 0.0% |   0.0% |    - | 7.1% |   0.0667 |
|       OK |   19 |   36.1 | 5.3% | 0.530 | 0.1 |       19 | 0.0% |      - |    - | 5.3% |   0.0000 |
| DEGRADED |   32 |  127.4 | 0.0% | 0.480 | 0.0 |       28 |    - |   0.0% |    - | 0.0% |   0.0357 |
|      ALL |   81 |   63.6 | 3.7% | 0.532 | 0.0 |       77 | 0.0% |   0.0% |    - | 4.0% |   0.0390 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.2 | 0.0% | 0.414 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.2222 |
|       OK |    8 |   36.6 | 0.0% | 0.357 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   84.8 | 0.0% | 0.416 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.3000 |
|      ALL |   31 |   51.6 | 0.0% | 0.400 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.2 | 0.0% | 0.334 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   36.6 | 0.0% | 0.254 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   84.8 | 0.0% | 0.301 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|      ALL |   31 |   51.6 | 0.0% | 0.299 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.2 | 0.0% | 0.566 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   36.6 | 0.0% | 0.540 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   84.8 | 0.0% | 0.563 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   51.6 | 0.0% | 0.558 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available