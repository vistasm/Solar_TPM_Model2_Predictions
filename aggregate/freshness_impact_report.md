# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-12 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

✅ No anomalies detected. Insufficient data or metrics within normal range.

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.7 | 0.0% | 0.342 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.5333 |
|       OK |   11 |   35.8 | 9.1% | 0.405 | 0.1 |        9 |    - |   0.0% |    - | 0.0% |   0.2222 |
| DEGRADED |    7 |   78.1 | 0.0% | 0.300 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   34 |   34.1 | 2.9% | 0.353 | 0.0 |       30 |    - |   0.0% |    - | 0.0% |   0.3667 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.7 | 0.0% | 0.375 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|       OK |   11 |   35.8 | 0.0% | 0.387 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    7 |   78.1 | 0.0% | 0.287 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   34 |   34.1 | 0.0% | 0.361 | 0.0 |       30 |    - |   0.0% |    - | 0.0% |   0.0667 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.7 | 0.0% | 0.531 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|       OK |   11 |   35.8 | 9.1% | 0.522 | 0.1 |        9 | 0.0% |      - |    - | 11.1% |   0.0000 |
| DEGRADED |    7 |   78.1 | 0.0% | 0.446 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   34 |   34.1 | 2.9% | 0.510 | 0.0 |       30 | 0.0% |   0.0% |    - | 3.5% |   0.0333 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.4 | 0.0% | 0.338 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.5714 |
|       OK |    9 |   35.2 | 11.1% | 0.406 | 0.1 |        7 |    - |   0.0% |    - | 0.0% |   0.2857 |
| DEGRADED |    7 |   78.1 | 0.0% | 0.300 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   31 |   34.4 | 3.2% | 0.349 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.4074 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.4 | 0.0% | 0.375 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    9 |   35.2 | 0.0% | 0.381 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    7 |   78.1 | 0.0% | 0.287 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   34.4 | 0.0% | 0.357 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   13.4 | 0.0% | 0.539 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|       OK |    9 |   35.2 | 11.1% | 0.530 | 0.1 |        7 | 0.0% |      - |    - | 14.3% |   0.0000 |
| DEGRADED |    7 |   78.1 | 0.0% | 0.446 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   34.4 | 3.2% | 0.515 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available