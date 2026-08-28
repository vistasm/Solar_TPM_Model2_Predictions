# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-28 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (76.9%) is 76.9% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (6.9%) is 2.4× the overall rate (2.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (12.5%) is 2.2× the overall rate (5.8%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   72 |   12.7 | 19.4% | 0.523 | 0.3 |       69 | 76.9% |  32.3% | 1.7× | 7.9% |   0.4493 |
|       OK |   37 |   37.2 | 8.1% | 0.432 | 0.1 |       36 | 33.3% |  20.0% | 2.4× | 6.5% |   0.1389 |
| DEGRADED |   63 |  120.1 | 1.6% | 0.395 | 0.0 |       63 | 0.0% |   0.0% |    - | 2.1% |   0.2381 |
|      ALL |  172 |   57.3 | 10.5% | 0.457 | 0.1 |      168 | 64.7% |  21.6% | 2.1× | 5.1% |   0.3036 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   72 |   12.7 | 6.9% | 0.514 | 0.1 |       69 | 60.0% |  25.0% | 3.5× | 3.5% |   0.1739 |
|       OK |   37 |   37.2 | 0.0% | 0.375 | 0.0 |       36 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   63 |  120.1 | 0.0% | 0.342 | 0.0 |       63 |    - |   0.0% |    - | 0.0% |   0.0476 |
|      ALL |  172 |   57.3 | 2.9% | 0.421 | 0.0 |      168 | 60.0% |  20.0% | 6.7× | 1.3% |   0.0893 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   72 |   12.7 | 12.5% | 0.606 | 0.1 |       69 | 11.1% |  20.0% | 1.5× | 12.5% |   0.0725 |
|       OK |   37 |   37.2 | 2.7% | 0.536 | 0.0 |       36 | 0.0% |      - |    - | 2.8% |   0.0000 |
| DEGRADED |   63 |  120.1 | 0.0% | 0.495 | 0.0 |       63 |    - |   0.0% |    - | 0.0% |   0.0159 |
|      ALL |  172 |   57.3 | 5.8% | 0.550 | 0.1 |      168 | 10.0% |  16.7% | 2.8× | 5.6% |   0.0357 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.4 | 18.2% | 0.620 | 0.3 |        8 | 0.0% |   0.0% |    - | 16.7% |   0.2500 |
|       OK |    7 |   38.2 | 28.6% | 0.634 | 0.3 |        6 | 0.0% |   0.0% |    - | 40.0% |   0.1667 |
| DEGRADED |   13 |  129.7 | 0.0% | 0.392 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|      ALL |   31 |   67.8 | 12.9% | 0.528 | 0.2 |       27 | 0.0% |   0.0% |    - | 13.6% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.4 | 0.0% | 0.603 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    7 |   38.2 | 0.0% | 0.629 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  129.7 | 0.0% | 0.370 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   67.8 | 0.0% | 0.511 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.4 | 0.0% | 0.584 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   38.2 | 0.0% | 0.559 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |  129.7 | 0.0% | 0.530 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   67.8 | 0.0% | 0.556 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available