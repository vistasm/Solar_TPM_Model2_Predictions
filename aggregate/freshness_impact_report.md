# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-26 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (76.9%) is 76.9% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (7.0%) is 2.4× the overall rate (2.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (12.7%) is 2.2× the overall rate (5.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   71 |   12.8 | 19.7% | 0.520 | 0.3 |       69 | 76.9% |  32.3% | 1.7× | 7.9% |   0.4493 |
|       OK |   36 |   37.4 | 8.3% | 0.425 | 0.1 |       35 | 33.3% |  20.0% | 2.3× | 6.7% |   0.1429 |
| DEGRADED |   63 |  120.1 | 1.6% | 0.395 | 0.0 |       62 | 0.0% |   0.0% |    - | 2.1% |   0.2258 |
|      ALL |  170 |   57.8 | 10.6% | 0.453 | 0.1 |      166 | 64.7% |  22.0% | 2.1× | 5.2% |   0.3012 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   71 |   12.8 | 7.0% | 0.511 | 0.1 |       69 | 60.0% |  25.0% | 3.5× | 3.5% |   0.1739 |
|       OK |   36 |   37.4 | 0.0% | 0.364 | 0.0 |       35 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   63 |  120.1 | 0.0% | 0.342 | 0.0 |       62 |    - |   0.0% |    - | 0.0% |   0.0484 |
|      ALL |  170 |   57.8 | 2.9% | 0.417 | 0.0 |      166 | 60.0% |  20.0% | 6.6× | 1.3% |   0.0904 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   71 |   12.8 | 12.7% | 0.605 | 0.1 |       69 | 11.1% |  20.0% | 1.5× | 12.5% |   0.0725 |
|       OK |   36 |   37.4 | 2.8% | 0.533 | 0.0 |       35 | 0.0% |      - |    - | 2.9% |   0.0000 |
| DEGRADED |   63 |  120.1 | 0.0% | 0.495 | 0.0 |       62 |    - |   0.0% |    - | 0.0% |   0.0161 |
|      ALL |  170 |   57.8 | 5.9% | 0.549 | 0.1 |      166 | 10.0% |  16.7% | 2.8× | 5.6% |   0.0361 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.0 | 18.2% | 0.583 | 0.3 |        9 | 0.0% |   0.0% |    - | 14.3% |   0.2222 |
|       OK |    7 |   37.4 | 28.6% | 0.592 | 0.3 |        6 | 0.0% |   0.0% |    - | 40.0% |   0.1667 |
| DEGRADED |   13 |  129.7 | 0.0% | 0.392 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   31 |   67.8 | 12.9% | 0.505 | 0.2 |       27 | 0.0% |   0.0% |    - | 13.0% |   0.1481 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.0 | 0.0% | 0.568 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    7 |   37.4 | 0.0% | 0.551 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  129.7 | 0.0% | 0.370 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   67.8 | 0.0% | 0.481 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.0 | 0.0% | 0.569 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   37.4 | 0.0% | 0.524 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  129.7 | 0.0% | 0.530 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   67.8 | 0.0% | 0.543 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available