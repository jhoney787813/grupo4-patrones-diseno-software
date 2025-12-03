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

