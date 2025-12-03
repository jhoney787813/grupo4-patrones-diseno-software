El objetivo de este repositorio es consolidar los temas que cada integrante del equipo debe preparar para la entrega de Temas avanzados en diseño de software


Entrega
Actividad Sumativa
Patrones de diseño de software


Módulo: Temas avanzados en
diseño de software
Unidad 4


# Plan de Trabajo Desacoplado para 5 Integrantes

## Contexto y Problema General (Base para Todos)

**Empresa:** PoliMarket  
**Sistema:** Conformado por módulos separados (Bodega, Ventas, RRHH, Proveedores, Entregas), pero con alta interdependencia y acoplamiento directo entre ellos.

---

## Problema de Diseño Identificado

### 1. Acoplamiento Fuerte
Los módulos dependen directamente entre sí.  
Cualquier cambio en un módulo afecta a varios otros, generando inestabilidad y alto costo de mantenimiento.

### 2. Lógica Compleja
- Creación de objetos con validaciones dispersas.  
- Notificaciones manuales entre módulos.  
- Acceso directo a subsistemas internos.  

Esto provoca código difícil de extender o probar.

### 3. Poca Flexibilidad
Agregar nuevos comportamientos o módulos requiere modificar código existente, lo cual viola el principio *Open/Closed*.

### 4. Código Duplicado
La lógica de acceso, validación y comunicación entre módulos está repetida en varios puntos del sistema.

---

## Objetivo de la Unidad 4

Aplicar **5 patrones de diseño GoF** para resolver estos problemas, logrando:

- Mayor mantenibilidad  
- Menor acoplamiento  
- Flexibilidad para extender el sistema  
- Código más limpio y organizado  

Los estudiantes deberán seleccionar y aplicar patrones que respondan a los puntos críticos anteriores.



# Plan de Integración Final

## Puntos de Sincronización Mínimos

- **Día 3:** Todos los integrantes comparten avances (código base completado).
- **Día 5:** El Integrante 4 presenta los diagramas preliminares.
- **Día 7:** El Integrante 5 envía el documento final integrado para la revisión final del equipo.

---

## Reglas Clave para Reducir Dependencias

1. **Cada integrante debe usar los fragmentos de código base proporcionados** en este documento para garantizar coherencia técnica.
2. Los **namespace deben ser consistentes**, siguiendo la convención:  
   `PoliMarket.[Modulo]`
3. Para **interfaces compartidas**, se deben respetar exactamente los ejemplos y firmas entregadas.
4. Si un integrante necesita **referenciar una clase creada por otro**, debe hacerlo exclusivamente a través de su **interfaz pública**, **no la implementación interna**.
5. Evitar acoplamientos directos entre módulos; los patrones aplicados (Facade, Proxy, Observer, Strategy, Factory) deben funcionar como capa de desacoplamiento.

---

## Nota Final

Este plan de integración garantiza que cada integrante pueda trabajar **de forma independiente**, con un **marco claro**, responsabilidades definidas y código inicial estructurado.  
¡Éxitos en el proceso de desarrollo y ensamblaje final del proyecto!

