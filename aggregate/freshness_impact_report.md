# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-21 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (13.8%) is 2.0× the overall rate (6.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   29 |   12.8 | 13.8% | 0.447 | 0.2 |       28 | 100.0% |  26.7% | 1.9× | 0.0% |   0.5357 |
|       OK |   18 |   35.7 | 5.6% | 0.377 | 0.1 |       16 | 100.0% |  33.3% | 5.3× | 0.0% |   0.1875 |
| DEGRADED |   26 |  132.0 | 0.0% | 0.351 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.2000 |
|      ALL |   73 |   60.9 | 6.9% | 0.396 | 0.1 |       69 | 100.0% |  21.7% | 3.0× | 0.0% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   29 |   12.8 | 0.0% | 0.440 | 0.0 |       28 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |   18 |   35.7 | 0.0% | 0.324 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   26 |  132.0 | 0.0% | 0.305 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0800 |
|      ALL |   73 |   60.9 | 0.0% | 0.363 | 0.0 |       69 |    - |   0.0% |    - | 0.0% |   0.0870 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   29 |   12.8 | 6.9% | 0.593 | 0.1 |       28 | 0.0% |   0.0% |    - | 7.7% |   0.0714 |
|       OK |   18 |   35.7 | 5.6% | 0.527 | 0.1 |       16 | 0.0% |      - |    - | 6.2% |   0.0000 |
| DEGRADED |   26 |  132.0 | 0.0% | 0.457 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0400 |
|      ALL |   73 |   60.9 | 4.1% | 0.528 | 0.0 |       69 | 0.0% |   0.0% |    - | 4.5% |   0.0435 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.6 | 30.8% | 0.578 | 0.4 |       12 | 100.0% |  57.1% | 1.7× | 0.0% |   0.5833 |
|       OK |    7 |   35.6 | 0.0% | 0.333 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  133.7 | 0.0% | 0.386 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.4000 |
|      ALL |   31 |   60.3 | 12.9% | 0.454 | 0.2 |       27 | 100.0% |  36.4% | 2.5× | 0.0% |   0.4074 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.6 | 0.0% | 0.519 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    7 |   35.6 | 0.0% | 0.225 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  133.7 | 0.0% | 0.307 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.2000 |
|      ALL |   31 |   60.3 | 0.0% | 0.377 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.6 | 15.4% | 0.669 | 0.1 |       12 | 0.0% |   0.0% |    - | 18.2% |   0.0833 |
|       OK |    7 |   35.6 | 0.0% | 0.536 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  133.7 | 0.0% | 0.510 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|      ALL |   31 |   60.3 | 6.5% | 0.583 | 0.1 |       27 | 0.0% |   0.0% |    - | 8.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available