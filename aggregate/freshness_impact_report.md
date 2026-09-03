# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-03 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (78.6%) is 78.6% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (6.8%) is 2.4× the overall rate (2.8%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (12.2%) is 2.2× the overall rate (5.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   74 |   12.6 | 18.9% | 0.520 | 0.3 |       72 | 78.6% |  33.3% | 1.7× | 7.7% |   0.4583 |
|       OK |   39 |   36.7 | 7.7% | 0.424 | 0.1 |       37 | 33.3% |  20.0% | 2.5× | 6.2% |   0.1351 |
| DEGRADED |   65 |  118.5 | 1.5% | 0.393 | 0.0 |       65 | 0.0% |   0.0% |    - | 2.0% |   0.2308 |
|      ALL |  178 |   56.6 | 10.1% | 0.453 | 0.1 |      174 | 66.7% |  22.6% | 2.2× | 5.0% |   0.3046 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   74 |   12.6 | 6.8% | 0.511 | 0.1 |       72 | 60.0% |  23.1% | 3.3× | 3.4% |   0.1806 |
|       OK |   39 |   36.7 | 0.0% | 0.365 | 0.0 |       37 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   65 |  118.5 | 0.0% | 0.338 | 0.0 |       65 |    - |   0.0% |    - | 0.0% |   0.0462 |
|      ALL |  178 |   56.6 | 2.8% | 0.416 | 0.0 |      174 | 60.0% |  18.8% | 6.5× | 1.3% |   0.0920 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   74 |   12.6 | 12.2% | 0.603 | 0.1 |       72 | 11.1% |  20.0% | 1.6× | 11.9% |   0.0694 |
|       OK |   39 |   36.7 | 2.6% | 0.536 | 0.0 |       37 | 0.0% |      - |    - | 2.7% |   0.0000 |
| DEGRADED |   65 |  118.5 | 0.0% | 0.498 | 0.0 |       65 |    - |   0.0% |    - | 0.0% |   0.0154 |
|      ALL |  178 |   56.6 | 5.6% | 0.550 | 0.1 |      174 | 10.0% |  16.7% | 2.9× | 5.4% |   0.0345 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.8 | 16.7% | 0.598 | 0.2 |       10 | 50.0% |  25.0% | 1.2× | 16.7% |   0.4000 |
|       OK |    7 |   36.3 | 14.3% | 0.554 | 0.1 |        5 | 0.0% |   0.0% |    - | 25.0% |   0.2000 |
| DEGRADED |   12 |  135.1 | 0.0% | 0.352 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   31 |   65.5 | 9.7% | 0.493 | 0.1 |       27 | 33.3% |  16.7% | 1.5× | 9.5% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.8 | 0.0% | 0.574 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.2000 |
|       OK |    7 |   36.3 | 0.0% | 0.528 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  135.1 | 0.0% | 0.301 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   65.5 | 0.0% | 0.458 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.8 | 0.0% | 0.577 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   36.3 | 0.0% | 0.574 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |  135.1 | 0.0% | 0.537 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   65.5 | 0.0% | 0.561 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available