# Estructura de Campañas — Amazon Ads Manager

## Tipos de campaña en el modelo Support Lite

### 1. 🛡️ Defensive Campaign Structure
**Objetivo:** Proteger tu propio ASIN de competidores

| Componente | Detalle |
|---|---|
| Tipo | Sponsored Products — Exact Match |
| Keywords | Brand name + variaciones exactas del ASIN |
| Bid | Agresivo (top of search) |
| Budget | 15-20% del presupuesto total |
| Naming | `[ASIN]_DEF_SP_Exact_Brand` |

**Cuándo activar:** Siempre. Es la primera campaña a construir para cualquier cuenta.

---

### 2. 📈 Incremental Campaign Coverage
**Objetivo:** Capturar demanda incremental — nuevos compradores que no buscan tu marca

| Componente | Detalle |
|---|---|
| Tipo | Sponsored Products — Broad + Phrase / Sponsored Brands |
| Keywords | Categoría + competidores + términos de descubrimiento |
| Bid | Moderado, con ajuste por placement |
| Budget | 50-60% del presupuesto total |
| Naming | `[ASIN]_INC_SP_Broad_[Categoría]` |

**Estructura interna:**
```
Campaign: [ASIN]_INC_SP_Broad_Categoria
  └── Ad Group: Competitor_Terms
  └── Ad Group: Category_Generic
  └── Ad Group: Use_Case_Terms
```

---

### 3. 🔬 Performance / RSC Campaigns (Keyword Harvesting)
**Objetivo:** Identificar nuevos términos ganadores para automatizar y escalar

| Componente | Detalle |
|---|---|
| Tipo | Sponsored Products — Auto / Broad con harvesting |
| Lógica | Auto campaign alimenta search terms → migrar winners a Exact |
| Budget | 20-25% del presupuesto |
| Naming | `[ASIN]_RSC_AUTO_Harvest` |
| Revisión | Semanal — search term report |

**Flujo de harvesting:**
```
Auto Campaign (descubrimiento)
    ↓ search terms con ventas + ACoS aceptable
Exact Campaign (escala)
    ↓ negative exact en Auto
Optimización continua
```

---

## 📐 Naming Convention estándar

```
[CLIENTE]_[ASIN/Producto]_[Tipo]_[Match]_[Segmento]_[Fecha]

Ejemplos:
NEAR_B09XYZ_DEF_SP_Exact_Brand_2606
NEAR_B09XYZ_INC_SP_Broad_Category_2606
NEAR_B09XYZ_RSC_AUTO_Harvest_2606
```

---

## 🎯 Bid Strategy por tipo

| Tipo campaña | Bid strategy recomendada | Placement adjustment |
|---|---|---|
| Defensive | Fixed bids | Top of Search: +50-100% |
| Incremental | Dynamic bids - down only | Top of Search: +20-40% |
| RSC/Auto | Dynamic bids - down only | Sin adjustment inicial |
| Sponsored Brands | Fixed / Budget rules | Top of Search prioritario |

---

## ✅ Checklist lanzamiento nuevo ASIN

- [ ] Defensive campaign activa con brand terms
- [ ] Al menos 1 campaña Incremental con 15-20 keywords relevantes
- [ ] Auto campaign para harvesting
- [ ] Negative keywords cross-campaign configurados
- [ ] Daily budget suficiente para no limitar en hora pico (10am-3pm)
- [ ] Bid inicial basado en CPC promedio de categoría
- [ ] Tracking de conversión verificado
