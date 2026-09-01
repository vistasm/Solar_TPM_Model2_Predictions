# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-01 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (78.6%) is 78.6% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (6.9%) is 2.4× the overall rate (2.8%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (12.5%) is 2.2× the overall rate (5.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   72 |   12.7 | 19.4% | 0.523 | 0.3 |       72 | 78.6% |  33.3% | 1.7× | 7.7% |   0.4583 |
|       OK |   39 |   36.7 | 7.7% | 0.424 | 0.1 |       37 | 33.3% |  20.0% | 2.5× | 6.2% |   0.1351 |
| DEGRADED |   65 |  118.5 | 1.5% | 0.393 | 0.0 |       63 | 0.0% |   0.0% |    - | 2.1% |   0.2381 |
|      ALL |  176 |   57.1 | 10.2% | 0.453 | 0.1 |      172 | 66.7% |  22.6% | 2.2× | 5.0% |   0.3081 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   72 |   12.7 | 6.9% | 0.514 | 0.1 |       72 | 60.0% |  23.1% | 3.3× | 3.4% |   0.1806 |
|       OK |   39 |   36.7 | 0.0% | 0.365 | 0.0 |       37 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   65 |  118.5 | 0.0% | 0.338 | 0.0 |       63 |    - |   0.0% |    - | 0.0% |   0.0476 |
|      ALL |  176 |   57.1 | 2.8% | 0.416 | 0.0 |      172 | 60.0% |  18.8% | 6.5× | 1.3% |   0.0930 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   72 |   12.7 | 12.5% | 0.606 | 0.1 |       72 | 11.1% |  20.0% | 1.6× | 11.9% |   0.0694 |
|       OK |   39 |   36.7 | 2.6% | 0.536 | 0.0 |       37 | 0.0% |      - |    - | 2.7% |   0.0000 |
| DEGRADED |   65 |  118.5 | 0.0% | 0.498 | 0.0 |       63 |    - |   0.0% |    - | 0.0% |   0.0159 |
|      ALL |  176 |   57.1 | 5.7% | 0.550 | 0.1 |      172 | 10.0% |  16.7% | 2.9× | 5.4% |   0.0349 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   13.5 | 20.0% | 0.635 | 0.3 |       10 | 50.0% |  25.0% | 1.2× | 16.7% |   0.4000 |
|       OK |    7 |   36.3 | 14.3% | 0.554 | 0.1 |        5 | 0.0% |   0.0% |    - | 25.0% |   0.2000 |
| DEGRADED |   14 |  126.2 | 0.0% | 0.373 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   31 |   69.5 | 9.7% | 0.498 | 0.1 |       27 | 33.3% |  16.7% | 1.5× | 9.5% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   13.5 | 0.0% | 0.607 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.2000 |
|       OK |    7 |   36.3 | 0.0% | 0.528 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  126.2 | 0.0% | 0.338 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   69.5 | 0.0% | 0.468 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   13.5 | 0.0% | 0.588 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   36.3 | 0.0% | 0.574 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  126.2 | 0.0% | 0.540 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   69.5 | 0.0% | 0.563 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available