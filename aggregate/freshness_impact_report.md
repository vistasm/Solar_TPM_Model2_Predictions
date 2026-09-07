# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-07 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (78.6%) is 78.6% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (6.4%) is 2.3× the overall rate (2.8%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (11.5%) is 2.1× the overall rate (5.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   78 |   12.7 | 19.2% | 0.515 | 0.3 |       74 | 78.6% |  32.4% | 1.7× | 7.5% |   0.4595 |
|       OK |   39 |   36.7 | 7.7% | 0.424 | 0.1 |       39 | 33.3% |  20.0% | 2.6× | 5.9% |   0.1282 |
| DEGRADED |   65 |  118.5 | 1.5% | 0.393 | 0.0 |       65 | 0.0% |   0.0% |    - | 2.0% |   0.2308 |
|      ALL |  182 |   55.7 | 10.4% | 0.452 | 0.1 |      178 | 66.7% |  22.2% | 2.2× | 4.8% |   0.3034 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   78 |   12.7 | 6.4% | 0.502 | 0.1 |       74 | 60.0% |  23.1% | 3.4× | 3.3% |   0.1757 |
|       OK |   39 |   36.7 | 0.0% | 0.365 | 0.0 |       39 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   65 |  118.5 | 0.0% | 0.338 | 0.0 |       65 |    - |   0.0% |    - | 0.0% |   0.0462 |
|      ALL |  182 |   55.7 | 2.8% | 0.414 | 0.0 |      178 | 60.0% |  18.8% | 6.7× | 1.2% |   0.0899 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   78 |   12.7 | 11.5% | 0.601 | 0.1 |       74 | 11.1% |  20.0% | 1.6× | 11.6% |   0.0676 |
|       OK |   39 |   36.7 | 2.6% | 0.536 | 0.0 |       39 | 0.0% |      - |    - | 2.6% |   0.0000 |
| DEGRADED |   65 |  118.5 | 0.0% | 0.498 | 0.0 |       65 |    - |   0.0% |    - | 0.0% |   0.0154 |
|      ALL |  182 |   55.7 | 5.5% | 0.550 | 0.1 |      178 | 10.0% |  16.7% | 3.0× | 5.2% |   0.0337 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.4 | 18.8% | 0.553 | 0.2 |       12 | 50.0% |  20.0% | 1.2× | 14.3% |   0.4167 |
|       OK |    7 |   36.3 | 14.3% | 0.554 | 0.1 |        7 | 0.0% |   0.0% |    - | 16.7% |   0.1429 |
| DEGRADED |    8 |  130.3 | 0.0% | 0.339 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|      ALL |   31 |   48.8 | 12.9% | 0.498 | 0.2 |       27 | 33.3% |  14.3% | 1.3× | 10.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.4 | 0.0% | 0.515 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    7 |   36.3 | 0.0% | 0.528 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |  130.3 | 0.0% | 0.281 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   48.8 | 0.0% | 0.458 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.4 | 0.0% | 0.571 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   36.3 | 0.0% | 0.574 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |  130.3 | 0.0% | 0.530 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   48.8 | 0.0% | 0.561 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available