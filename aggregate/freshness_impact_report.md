# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-28 UTC
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
|    FRESH |   21 |   12.9 | 19.1% | 0.454 | 0.2 |       17 |    - |   0.0% |    - | 0.0% |   0.5294 |
|       OK |   11 |   35.8 | 9.1% | 0.405 | 0.1 |       11 | 100.0% |  33.3% | 3.7× | 0.0% |   0.2727 |
| DEGRADED |   18 |  160.5 | 0.0% | 0.338 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   50 |   71.0 | 10.0% | 0.402 | 0.1 |       46 | 100.0% |   6.7% | 3.1× | 0.0% |   0.3261 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   21 |   12.9 | 0.0% | 0.471 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.1765 |
|       OK |   11 |   35.8 | 0.0% | 0.387 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  160.5 | 0.0% | 0.325 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   50 |   71.0 | 0.0% | 0.400 | 0.0 |       46 |    - |   0.0% |    - | 0.0% |   0.0870 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   21 |   12.9 | 9.5% | 0.601 | 0.1 |       17 |    - |   0.0% |    - | 0.0% |   0.1176 |
|       OK |   11 |   35.8 | 9.1% | 0.522 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
| DEGRADED |   18 |  160.5 | 0.0% | 0.416 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   50 |   71.0 | 6.0% | 0.517 | 0.1 |       46 | 0.0% |   0.0% |    - | 2.3% |   0.0652 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   10.8 | 30.8% | 0.524 | 0.4 |        9 |    - |   0.0% |    - | 0.0% |   0.5556 |
|       OK |    4 |   33.1 | 25.0% | 0.553 | 0.2 |        4 | 100.0% | 100.0% | 4.0× | 0.0% |   0.2500 |
| DEGRADED |   14 |  181.7 | 0.0% | 0.342 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|      ALL |   31 |   90.8 | 16.1% | 0.446 | 0.2 |       27 | 100.0% |  12.5% | 3.4× | 0.0% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   10.8 | 0.0% | 0.513 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.3333 |
|       OK |    4 |   33.1 | 0.0% | 0.398 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  181.7 | 0.0% | 0.321 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   90.8 | 0.0% | 0.412 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   10.8 | 15.4% | 0.686 | 0.1 |        9 |    - |   0.0% |    - | 0.0% |   0.2222 |
|       OK |    4 |   33.1 | 25.0% | 0.562 | 0.2 |        4 | 0.0% |      - |    - | 25.0% |   0.0000 |
| DEGRADED |   14 |  181.7 | 0.0% | 0.404 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   90.8 | 9.7% | 0.543 | 0.1 |       27 | 0.0% |   0.0% |    - | 4.2% |   0.1111 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available