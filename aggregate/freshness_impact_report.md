# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-04 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (6.4%) is 2.5× the overall rate (2.6%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (14.9%) is 2.2× the overall rate (6.8%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   47 |   12.2 | 17.0% | 0.482 | 0.3 |       43 | 100.0% |  20.0% | 2.1× | 0.0% |   0.4651 |
|       OK |   25 |   37.4 | 4.0% | 0.389 | 0.0 |       25 | 100.0% |  33.3% | 8.3× | 0.0% |   0.1200 |
| DEGRADED |   45 |  120.4 | 2.2% | 0.405 | 0.0 |       45 | 0.0% |   0.0% |    - | 2.9% |   0.2444 |
|      ALL |  117 |   59.2 | 8.6% | 0.433 | 0.1 |      113 | 83.3% |  14.7% | 2.8× | 1.3% |   0.3009 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   47 |   12.2 | 6.4% | 0.478 | 0.1 |       43 |    - |   0.0% |    - | 0.0% |   0.1628 |
|       OK |   25 |   37.4 | 0.0% | 0.323 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   45 |  120.4 | 0.0% | 0.351 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |  117 |   59.2 | 2.6% | 0.396 | 0.0 |      113 |    - |   0.0% |    - | 0.0% |   0.0885 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   47 |   12.2 | 14.9% | 0.624 | 0.1 |       43 | 0.0% |   0.0% |    - | 7.7% |   0.0930 |
|       OK |   25 |   37.4 | 4.0% | 0.541 | 0.0 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |
| DEGRADED |   45 |  120.4 | 0.0% | 0.500 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0222 |
|      ALL |  117 |   59.2 | 6.8% | 0.559 | 0.1 |      113 | 0.0% |   0.0% |    - | 3.7% |   0.0442 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   10.5 | 26.7% | 0.582 | 0.5 |       11 |    - |   0.0% |    - | 0.0% |   0.3636 |
|       OK |    5 |   40.4 | 0.0% | 0.371 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.8 | 9.1% | 0.522 | 0.1 |       11 | 0.0% |   0.0% |    - | 11.1% |   0.1818 |
|      ALL |   31 |   49.5 | 16.1% | 0.527 | 0.3 |       27 | 0.0% |   0.0% |    - | 4.8% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   10.5 | 20.0% | 0.598 | 0.2 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |    5 |   40.4 | 0.0% | 0.283 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.8 | 0.0% | 0.474 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   49.5 | 9.7% | 0.503 | 0.1 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   10.5 | 33.3% | 0.706 | 0.3 |       11 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |    5 |   40.4 | 0.0% | 0.577 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.8 | 0.0% | 0.547 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   49.5 | 16.1% | 0.629 | 0.2 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available