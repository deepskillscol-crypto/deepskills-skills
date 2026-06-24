# Plataformas de Ad Tech — Guía de trabajo

## Las tres plataformas del rol

Este rol opera principalmente a través de plataformas de ad-tech, no directamente en Amazon Ads Console. Conocer las diferencias es clave.

---

## 🟦 Xnurta

**Especialidad:** Automatización de Amazon Ads con IA — fuerte en optimización de bids y keyword management.

### Flujos clave en Xnurta
- **Bid optimization:** Usa las reglas automáticas de Xnurta para ajustar bids según ACoS objetivo. Configura una regla base por campaña.
- **Keyword harvesting:** Xnurta puede automatizar la migración de search terms ganadores desde Auto → Exact. Activa esta función en cuentas con suficiente volumen (>50 pedidos/mes).
- **Budget rules:** Configura alertas de pacing directamente en Xnurta para recibir notificaciones si una campaña consume >X% del budget antes del día 20.

### Buenas prácticas
- Siempre revisa los cambios automáticos de Xnurta en el change log antes de hacer ajustes manuales (evitar conflictos)
- No actives bid automation en campañas Defensive — manejálas manualmente
- Usa el dashboard de "Account Health" como primera pantalla cada lunes

---

## 🟨 Pacvue

**Especialidad:** Plataforma enterprise con foco en reporting, dayparting y gestión multi-cuenta.

### Flujos clave en Pacvue
- **Dayparting:** Pacvue permite configurar ajustes de bid por hora del día. Útil para concentrar spend en horas de alta conversión (típicamente 9am-2pm en el timezone del mercado).
- **Bulk operations:** Para cuentas con muchas campañas, usa la función de bulk edits para cambios masivos de bids o budgets.
- **Custom dashboards:** Aunque el rol no requiere reportes custom para clientes, sí puedes crear vistas internas de performance por cuenta.

### Buenas prácticas
- Usa Pacvue para el pacing check semanal — tiene la vista de "Budget Utilization" más clara que la consola nativa
- El módulo de "Competitive Intelligence" en Pacvue es útil para detectar cuando un competidor aumenta su share
- Para el business update mensual, exporta el summary de Pacvue y úsalo como base

---

## 🟩 Skai (antes Kenshoo)

**Especialidad:** Plataforma omnicanal — si el cliente tiene presencia en Amazon + Walmart + otros marketplaces, Skai los unifica.

### Flujos clave en Skai
- **Cross-channel reporting:** Si el cliente vende en Amazon + otro canal, Skai permite comparar performance en una sola vista
- **Budget allocation:** Skai tiene herramientas de portfolio bidding — permite redistribuir budget entre campañas según el objetivo global (no campaña por campaña)
- **Automated actions:** Similar a Xnurta, pero con lógica más configurable — útil para cuentas más complejas

### Buenas prácticas
- En cuentas solo-Amazon, Skai puede ser "overkill" — prioriza Pacvue o Xnurta para esas
- Aprovecha Skai cuando el cliente tenga múltiples marketplaces activos
- El reporting de Skai es el más robusto de los tres — úsalo para el quarterly review

---

## Comparativa rápida

| Función | Xnurta | Pacvue | Skai |
|---|---|---|---|
| Bid automation con IA | ⭐⭐⭐ | ⭐⭐ | ⭐⭐ |
| Pacing & budget tracking | ⭐⭐ | ⭐⭐⭐ | ⭐⭐ |
| Reporting / dashboards | ⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ |
| Multi-canal (Amazon + otros) | ❌ | ⭐⭐ | ⭐⭐⭐ |
| Bulk operations | ⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ |
| Curva de aprendizaje | Baja | Media | Alta |

---

## Tips para ser eficiente desde el día 1

1. **Pide acceso de lectura primero** — antes de tocar cualquier cosa, entiende la estructura de campañas existente
2. **Documenta el estado inicial** — captura screenshot o export del performance baseline antes de hacer cambios
3. **Un cambio a la vez** — en la primera semana, cambia solo una variable por campaña para poder atribuir resultados
4. **Usa el change log** — todas las plataformas tienen historial de cambios. Revísalo antes de preguntar "¿por qué cambió el performance?"
