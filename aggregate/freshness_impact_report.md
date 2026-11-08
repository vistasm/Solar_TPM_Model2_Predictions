# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-08 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (80.0%) is 30.0% HIGHER than DEGRADED (50.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (6.0%) is 2.9× the overall rate (2.1%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.8%) is 2.6× the overall rate (4.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   83 |   12.8 | 20.5% | 0.510 | 0.3 |       81 | 80.0% |  33.3% | 1.8× | 6.7% |   0.4444 |
|       OK |   43 |   37.0 | 9.3% | 0.428 | 0.1 |       42 | 33.3% |  20.0% | 2.8× | 5.4% |   0.1190 |
| DEGRADED |  118 |  120.5 | 5.1% | 0.385 | 0.1 |      117 | 50.0% |  13.6% | 2.7× | 3.2% |   0.1880 |
|      ALL |  244 |   69.2 | 11.1% | 0.435 | 0.1 |      240 | 66.7% |  25.4% | 2.5× | 4.5% |   0.2625 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   83 |   12.8 | 6.0% | 0.498 | 0.1 |       81 | 60.0% |  23.1% | 3.7× | 2.9% |   0.1605 |
|       OK |   43 |   37.0 | 0.0% | 0.370 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  118 |  120.5 | 0.0% | 0.340 | 0.0 |      117 |    - |   0.0% |    - | 0.0% |   0.0427 |
|      ALL |  244 |   69.2 | 2.1% | 0.399 | 0.0 |      240 | 60.0% |  16.7% | 8.0× | 0.9% |   0.0750 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   83 |   12.8 | 10.8% | 0.597 | 0.1 |       81 | 11.1% |  20.0% | 1.8× | 10.5% |   0.0617 |
|       OK |   43 |   37.0 | 2.3% | 0.536 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |  118 |  120.5 | 0.0% | 0.517 | 0.0 |      117 |    - |   0.0% |    - | 0.0% |   0.0085 |
|      ALL |  244 |   69.2 | 4.1% | 0.548 | 0.0 |      240 | 10.0% |  16.7% | 4.0× | 3.9% |   0.0250 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    2 |   11.0 | 100.0% | 0.868 | 1.0 |        0 |    - |      - |    - |   - |        - |
|       OK |    1 |   35.1 | 100.0% | 0.812 | 1.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   28 |  111.6 | 14.3% | 0.435 | 0.1 |       27 | 50.0% |  50.0% | 3.4× | 8.7% |   0.1481 |
|      ALL |   31 |  102.6 | 22.6% | 0.475 | 0.2 |       27 | 50.0% |  50.0% | 3.4× | 8.7% |   0.1481 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    2 |   11.0 | 0.0% | 0.917 | 0.0 |        0 |    - |      - |    - |   - |        - |
|       OK |    1 |   35.1 | 0.0% | 0.895 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   28 |  111.6 | 0.0% | 0.434 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |
|      ALL |   31 |  102.6 | 0.0% | 0.480 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    2 |   11.0 | 0.0% | 0.603 | 0.0 |        0 |    - |      - |    - |   - |        - |
|       OK |    1 |   35.1 | 0.0% | 0.587 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   28 |  111.6 | 0.0% | 0.559 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |  102.6 | 0.0% | 0.563 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available