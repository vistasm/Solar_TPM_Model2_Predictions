# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-28 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (13.3%) is 2.1× the overall rate (6.2%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   13.0 | 13.3% | 0.442 | 0.2 |       30 | 100.0% |  26.7% | 2.0× | 0.0% |   0.5000 |
|       OK |   19 |   36.1 | 5.3% | 0.385 | 0.1 |       19 | 100.0% |  33.3% | 6.3× | 0.0% |   0.1579 |
| DEGRADED |   31 |  126.2 | 0.0% | 0.376 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.2222 |
|      ALL |   80 |   62.3 | 6.2% | 0.403 | 0.1 |       76 | 100.0% |  20.8% | 3.2× | 0.0% |   0.3158 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   13.0 | 0.0% | 0.430 | 0.0 |       30 |    - |   0.0% |    - | 0.0% |   0.1333 |
|       OK |   19 |   36.1 | 0.0% | 0.331 | 0.0 |       19 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   31 |  126.2 | 0.0% | 0.318 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |
|      ALL |   80 |   62.3 | 0.0% | 0.363 | 0.0 |       76 |    - |   0.0% |    - | 0.0% |   0.0789 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   13.0 | 6.7% | 0.590 | 0.1 |       30 | 0.0% |   0.0% |    - | 7.1% |   0.0667 |
|       OK |   19 |   36.1 | 5.3% | 0.530 | 0.1 |       19 | 0.0% |      - |    - | 5.3% |   0.0000 |
| DEGRADED |   31 |  126.2 | 0.0% | 0.477 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |
|      ALL |   80 |   62.3 | 3.8% | 0.532 | 0.0 |       76 | 0.0% |   0.0% |    - | 4.1% |   0.0395 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.2 | 10.0% | 0.454 | 0.1 |       10 | 100.0% |  33.3% | 3.3× | 0.0% |   0.3000 |
|       OK |    8 |   36.6 | 0.0% | 0.357 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   78.8 | 0.0% | 0.429 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.3333 |
|      ALL |   31 |   47.0 | 3.2% | 0.419 | 0.0 |       27 | 100.0% |  16.7% | 4.5× | 0.0% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.2 | 0.0% | 0.372 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   36.6 | 0.0% | 0.254 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   78.8 | 0.0% | 0.309 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|      ALL |   31 |   47.0 | 0.0% | 0.315 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.2 | 0.0% | 0.588 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   36.6 | 0.0% | 0.540 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   78.8 | 0.0% | 0.561 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   47.0 | 0.0% | 0.564 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available