# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-14 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (90.0%) is 90.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (9.1%) is 2.3× the overall rate (3.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (16.4%) is 2.1× the overall rate (7.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   55 |   12.3 | 18.2% | 0.502 | 0.3 |       52 | 90.0% |  34.6% | 1.8× | 3.9% |   0.5000 |
|       OK |   27 |   37.2 | 3.7% | 0.394 | 0.0 |       26 | 100.0% |  25.0% | 6.5× | 0.0% |   0.1538 |
| DEGRADED |   45 |  120.4 | 2.2% | 0.405 | 0.0 |       45 | 0.0% |   0.0% |    - | 2.9% |   0.2444 |
|      ALL |  127 |   55.9 | 9.4% | 0.445 | 0.1 |      123 | 83.3% |  24.4% | 2.5× | 2.4% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   55 |   12.3 | 9.1% | 0.490 | 0.1 |       52 | 60.0% |  27.3% | 2.8× | 4.9% |   0.2115 |
|       OK |   27 |   37.2 | 0.0% | 0.331 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   45 |  120.4 | 0.0% | 0.351 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |  127 |   55.9 | 3.9% | 0.407 | 0.0 |      123 | 60.0% |  21.4% | 5.3× | 1.8% |   0.1138 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   55 |   12.3 | 16.4% | 0.625 | 0.2 |       52 | 11.1% |  20.0% | 1.2× | 17.0% |   0.0962 |
|       OK |   27 |   37.2 | 3.7% | 0.541 | 0.0 |       26 | 0.0% |      - |    - | 3.9% |   0.0000 |
| DEGRADED |   45 |  120.4 | 0.0% | 0.500 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0222 |
|      ALL |  127 |   55.9 | 7.9% | 0.563 | 0.1 |      123 | 10.0% |  16.7% | 2.0× | 7.7% |   0.0488 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.4 | 35.3% | 0.632 | 0.7 |       14 | 83.3% |  55.6% | 1.3× | 20.0% |   0.6429 |
|       OK |    4 |   36.2 | 0.0% | 0.442 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |   10 |  111.1 | 10.0% | 0.506 | 0.1 |       10 | 0.0% |   0.0% |    - | 12.5% |   0.2000 |
|      ALL |   31 |   46.2 | 22.6% | 0.567 | 0.4 |       27 | 71.4% |  41.7% | 1.6× | 13.3% |   0.4444 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.4 | 29.4% | 0.595 | 0.3 |       14 | 60.0% |  50.0% | 1.4× | 25.0% |   0.4286 |
|       OK |    4 |   36.2 | 0.0% | 0.339 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  111.1 | 0.0% | 0.456 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.2 | 16.1% | 0.517 | 0.2 |       27 | 60.0% |  50.0% | 2.7× | 9.5% |   0.2222 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   10.4 | 35.3% | 0.675 | 0.3 |       14 | 16.7% |  50.0% | 1.2× | 41.7% |   0.1429 |
|       OK |    4 |   36.2 | 0.0% | 0.522 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |  111.1 | 0.0% | 0.546 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.2 | 19.4% | 0.614 | 0.2 |       27 | 16.7% |  50.0% | 2.2× | 20.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available