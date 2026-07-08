# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-08 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M+**: FRESH alert rate (20.0%) is 2.0× the overall rate (9.9%) — score distribution shift detected
🟡 **M5+**: FRESH alert rate (10.0%) is 2.4× the overall rate (4.1%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (18.0%) is 2.2× the overall rate (8.3%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   50 |   12.1 | 20.0% | 0.503 | 0.3 |       47 | 100.0% |  33.3% | 2.0× | 0.0% |   0.5106 |
|       OK |   26 |   36.9 | 3.9% | 0.398 | 0.0 |       25 | 100.0% |  33.3% | 8.3× | 0.0% |   0.1200 |
| DEGRADED |   45 |  120.4 | 2.2% | 0.405 | 0.0 |       45 | 0.0% |   0.0% |    - | 2.9% |   0.2444 |
|      ALL |  121 |   57.7 | 9.9% | 0.444 | 0.2 |      117 | 90.0% |  23.7% | 2.8× | 1.3% |   0.3248 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   50 |   12.1 | 10.0% | 0.495 | 0.1 |       47 | 66.7% |  20.0% | 3.1× | 2.7% |   0.2128 |
|       OK |   26 |   36.9 | 0.0% | 0.334 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   45 |  120.4 | 0.0% | 0.351 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |  121 |   57.7 | 4.1% | 0.407 | 0.0 |      117 | 66.7% |  15.4% | 6.0× | 1.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   50 |   12.1 | 18.0% | 0.638 | 0.2 |       47 | 14.3% |  20.0% | 1.3× | 14.3% |   0.1064 |
|       OK |   26 |   36.9 | 3.9% | 0.545 | 0.0 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |
| DEGRADED |   45 |  120.4 | 0.0% | 0.500 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0222 |
|      ALL |  121 |   57.7 | 8.3% | 0.567 | 0.1 |      117 | 12.5% |  16.7% | 2.4× | 6.3% |   0.0513 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |    9.2 | 40.0% | 0.652 | 0.8 |       12 | 100.0% |  57.1% | 1.7× | 0.0% |   0.5833 |
|       OK |    5 |   36.8 | 0.0% | 0.401 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.8 | 9.1% | 0.522 | 0.1 |       11 | 0.0% |   0.0% |    - | 11.1% |   0.1818 |
|      ALL |   31 |   48.3 | 22.6% | 0.565 | 0.4 |       27 | 80.0% |  44.4% | 2.4× | 5.6% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |    9.2 | 33.3% | 0.653 | 0.3 |       12 | 66.7% |  40.0% | 1.6× | 14.3% |   0.4167 |
|       OK |    5 |   36.8 | 0.0% | 0.338 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.8 | 0.0% | 0.474 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   48.3 | 16.1% | 0.539 | 0.2 |       27 | 66.7% |  40.0% | 3.6× | 4.5% |   0.1852 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |    9.2 | 40.0% | 0.732 | 0.4 |       12 | 25.0% |  50.0% | 1.5× | 30.0% |   0.1667 |
|       OK |    5 |   36.8 | 0.0% | 0.556 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.8 | 0.0% | 0.547 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   48.3 | 19.4% | 0.638 | 0.2 |       27 | 25.0% |  50.0% | 3.4× | 12.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available