# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-30 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (78.6%) is 78.6% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (6.9%) is 2.4× the overall rate (2.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (12.5%) is 2.2× the overall rate (5.8%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   72 |   12.7 | 19.4% | 0.523 | 0.3 |       71 | 78.6% |  33.3% | 1.7× | 7.9% |   0.4648 |
|       OK |   37 |   37.2 | 8.1% | 0.432 | 0.1 |       36 | 33.3% |  20.0% | 2.4× | 6.5% |   0.1389 |
| DEGRADED |   65 |  118.5 | 1.5% | 0.393 | 0.0 |       63 | 0.0% |   0.0% |    - | 2.1% |   0.2381 |
|      ALL |  174 |   57.5 | 10.3% | 0.455 | 0.1 |      170 | 66.7% |  22.6% | 2.1× | 5.1% |   0.3118 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   72 |   12.7 | 6.9% | 0.514 | 0.1 |       71 | 60.0% |  23.1% | 3.3× | 3.5% |   0.1831 |
|       OK |   37 |   37.2 | 0.0% | 0.375 | 0.0 |       36 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   65 |  118.5 | 0.0% | 0.338 | 0.0 |       63 |    - |   0.0% |    - | 0.0% |   0.0476 |
|      ALL |  174 |   57.5 | 2.9% | 0.419 | 0.0 |      170 | 60.0% |  18.8% | 6.4× | 1.3% |   0.0941 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   72 |   12.7 | 12.5% | 0.606 | 0.1 |       71 | 11.1% |  20.0% | 1.6× | 12.1% |   0.0704 |
|       OK |   37 |   37.2 | 2.7% | 0.536 | 0.0 |       36 | 0.0% |      - |    - | 2.8% |   0.0000 |
| DEGRADED |   65 |  118.5 | 0.0% | 0.498 | 0.0 |       63 |    - |   0.0% |    - | 0.0% |   0.0159 |
|      ALL |  174 |   57.5 | 5.8% | 0.550 | 0.1 |      170 | 10.0% |  16.7% | 2.8× | 5.5% |   0.0353 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.4 | 18.2% | 0.620 | 0.3 |       10 | 50.0% |  25.0% | 1.2× | 16.7% |   0.4000 |
|       OK |    6 |   39.4 | 33.3% | 0.682 | 0.3 |        5 | 0.0% |   0.0% |    - | 50.0% |   0.2000 |
| DEGRADED |   14 |  126.2 | 0.0% | 0.373 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   31 |   69.4 | 12.9% | 0.520 | 0.2 |       27 | 25.0% |  16.7% | 1.1× | 14.3% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.4 | 0.0% | 0.603 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.2000 |
|       OK |    6 |   39.4 | 0.0% | 0.663 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  126.2 | 0.0% | 0.338 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   69.4 | 0.0% | 0.495 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.4 | 0.0% | 0.584 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   39.4 | 0.0% | 0.586 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  126.2 | 0.0% | 0.540 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   69.4 | 0.0% | 0.565 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available