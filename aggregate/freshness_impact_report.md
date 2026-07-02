# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-02 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.2%) is 2.6× the overall rate (0.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (11.1%) is 2.1× the overall rate (5.2%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   45 |   12.5 | 13.3% | 0.460 | 0.2 |       42 | 100.0% |  21.1% | 2.2× | 0.0% |   0.4524 |
|       OK |   25 |   37.4 | 4.0% | 0.389 | 0.0 |       25 | 100.0% |  33.3% | 8.3× | 0.0% |   0.1200 |
| DEGRADED |   45 |  120.4 | 2.2% | 0.405 | 0.0 |       44 | 0.0% |   0.0% |    - | 2.9% |   0.2273 |
|      ALL |  115 |   60.1 | 7.0% | 0.423 | 0.1 |      111 | 83.3% |  15.6% | 2.9× | 1.3% |   0.2883 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   45 |   12.5 | 2.2% | 0.455 | 0.0 |       42 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |   25 |   37.4 | 0.0% | 0.323 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   45 |  120.4 | 0.0% | 0.351 | 0.0 |       44 |    - |   0.0% |    - | 0.0% |   0.0682 |
|      ALL |  115 |   60.1 | 0.9% | 0.385 | 0.0 |      111 |    - |   0.0% |    - | 0.0% |   0.0811 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   45 |   12.5 | 11.1% | 0.608 | 0.1 |       42 | 0.0% |   0.0% |    - | 7.7% |   0.0714 |
|       OK |   25 |   37.4 | 4.0% | 0.541 | 0.0 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |
| DEGRADED |   45 |  120.4 | 0.0% | 0.500 | 0.0 |       44 |    - |   0.0% |    - | 0.0% |   0.0227 |
|      ALL |  115 |   60.1 | 5.2% | 0.551 | 0.1 |      111 | 0.0% |   0.0% |    - | 3.7% |   0.0360 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   10.8 | 14.3% | 0.514 | 0.2 |       11 |    - |   0.0% |    - | 0.0% |   0.3636 |
|       OK |    5 |   40.4 | 0.0% | 0.371 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  105.8 | 8.3% | 0.502 | 0.1 |       11 | 0.0% |   0.0% |    - | 11.1% |   0.1818 |
|      ALL |   31 |   52.4 | 9.7% | 0.486 | 0.1 |       27 | 0.0% |   0.0% |    - | 4.8% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   10.8 | 7.1% | 0.523 | 0.1 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |    5 |   40.4 | 0.0% | 0.283 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  105.8 | 0.0% | 0.456 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   31 |   52.4 | 3.2% | 0.458 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   10.8 | 21.4% | 0.648 | 0.2 |       11 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |    5 |   40.4 | 0.0% | 0.577 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  105.8 | 0.0% | 0.547 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   52.4 | 9.7% | 0.597 | 0.1 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available