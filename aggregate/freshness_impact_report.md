# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-14 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (15.4%) is 2.0× the overall rate (7.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   26 |   12.7 | 15.4% | 0.464 | 0.2 |       25 | 100.0% |  28.6% | 1.8× | 0.0% |   0.5600 |
|       OK |   15 |   36.0 | 6.7% | 0.409 | 0.1 |       14 | 100.0% |  33.3% | 4.7× | 0.0% |   0.2143 |
| DEGRADED |   25 |  135.3 | 0.0% | 0.355 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.2174 |
|      ALL |   66 |   64.4 | 7.6% | 0.410 | 0.1 |       62 | 100.0% |  22.7% | 2.8× | 0.0% |   0.3548 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   26 |   12.7 | 0.0% | 0.465 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.1600 |
|       OK |   15 |   36.0 | 0.0% | 0.364 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   25 |  135.3 | 0.0% | 0.312 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.0870 |
|      ALL |   66 |   64.4 | 0.0% | 0.384 | 0.0 |       62 |    - |   0.0% |    - | 0.0% |   0.0968 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   26 |   12.7 | 7.7% | 0.600 | 0.1 |       25 | 0.0% |   0.0% |    - | 8.7% |   0.0800 |
|       OK |   15 |   36.0 | 6.7% | 0.527 | 0.1 |       14 | 0.0% |      - |    - | 7.1% |   0.0000 |
| DEGRADED |   25 |  135.3 | 0.0% | 0.455 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.0435 |
|      ALL |   66 |   64.4 | 4.5% | 0.528 | 0.1 |       62 | 0.0% |   0.0% |    - | 5.1% |   0.0484 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.2 | 40.0% | 0.658 | 0.5 |        9 | 100.0% |  66.7% | 1.5× | 0.0% |   0.6667 |
|       OK |    4 |   36.5 | 0.0% | 0.421 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  161.4 | 0.0% | 0.383 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.2667 |
|      ALL |   31 |   96.8 | 12.9% | 0.476 | 0.2 |       27 | 100.0% |  40.0% | 2.7× | 0.0% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.2 | 0.0% | 0.609 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.2222 |
|       OK |    4 |   36.5 | 0.0% | 0.300 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  161.4 | 0.0% | 0.330 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|      ALL |   31 |   96.8 | 0.0% | 0.416 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.2 | 20.0% | 0.711 | 0.2 |        9 | 0.0% |   0.0% |    - | 25.0% |   0.1111 |
|       OK |    4 |   36.5 | 0.0% | 0.542 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  161.4 | 0.0% | 0.467 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   31 |   96.8 | 6.5% | 0.555 | 0.1 |       27 | 0.0% |   0.0% |    - | 8.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available