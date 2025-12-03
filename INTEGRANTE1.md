
# INTEGRANTE 1: Arquitecto de Patrones Estructurales

## Entregables Específicos
- Documentación de **2 patrones estructurales** (Facade y Proxy) en tabla.
- Código C# de implementación para ambos patrones.
- Contribución a conclusiones sobre beneficios estructurales.

---

# Trabajo Independiente - Instrucciones

---

## 1. Patrón **FACADE** – Simplificación del módulo de Bodega

### Problema Específico
El módulo de **Ventas** necesita interactuar con múltiples subsistemas internos de **Bodega** (Inventario, Proveedores, Alertas) de forma compleja y acoplada.

### Tu Tarea
Crear una **fachada** que unifique y simplifique este acceso.

---

## Código Base Inicial (C#)

### Subsistemas existentes (No modificar)

```csharp
// ====== CÓDIGO BASE PARA INTEGRANTE 1 - FACADE ======
// Tu trabajo es COMPLETAR estas clases según el patrón Facade

// Subsistemas complejos de Bodega (YA EXISTEN - NO MODIFICAR)
namespace PoliMarket.Bodega.Subsistemas
{
    public class SistemaInventario
    {
        public bool VerificarDisponibilidad(string productoId, int cantidad)
        {
            // Lógica compleja de verificación
            Console.WriteLine($"Verificando disponibilidad de {cantidad} unidades de {productoId}");
            return cantidad <= 100; // Simulación
        }
        
        public void ActualizarStock(string productoId, int cantidad)
        {
            Console.WriteLine($"Actualizando stock de {productoId}: {cantidad} unidades");
        }
    }

    public class SistemaProveedores
    {
        public void SolicitarProducto(string productoId, int cantidad)
        {
            Console.WriteLine($"Solicitando a proveedores: {cantidad} de {productoId}");
        }
    }

    public class SistemaAlertas
    {
        public void EnviarAlertaBajoStock(string productoId)
        {
            Console.WriteLine($"ALERTA: Stock bajo para {productoId}");
        }
    }
}

```

# ESPACIO PARA TU TRABAJO

Debes crear:

```csharp
// 1. Crea la clase FachadaBodega aquí
// 2. Implementa métodos simplificados como:
//    - VerificarYActualizarStock(string productoId, int cantidad)
//    - SolicitarReposicion(string productoId, int cantidad)
```

##  2. Patrón PROXY – Control de acceso al módulo de Ventas
### Problema Específico

Los vendedores deben estar autorizados por RRHH antes de usar el sistema de Ventas.

###  Tu Tarea:

Crear un Proxy que valide permisos antes de delegar al sistema real de ventas.


```csharp
// 1. Crea la clase ProxySistemaVentas que implemente ISistemaVentas
// 2. Agrega lógica de validación con RRHH antes de delegar al SistemaVentasReal
// 3. Usa esta clase simulación para RRHH:
public class SistemaRRHH
{
    public bool EstaAutorizado(string vendedorId)
    {
        return vendedorId.StartsWith("V"); // Solo vendedores con ID que empiezan con V
    }
}


```

## Diagrama de Clases - Fragmento para Tu Trabajo:

```text
[Integrante 1 - Fragmento de Diagrama]
Clases EXISTENTES:
+----------------+       +-----------------------+
| SistemaVentas  |       | SubsistemaInventario  |
| Real           |       +-----------------------+
+----------------+       | +VerificarDisponibilidad()
| +RealizarVenta()|       | +ActualizarStock()    |
| +ObtenerClientes|       +-----------------------+
+----------------+

TUS CLASES A AGREGAR:
+---------------------+
|   FachadaBodega     |
+---------------------+
| +VerificarYActualizarStock()
| +SolicitarReposicion()
+---------------------+

+---------------------+
| ProxySistemaVentas  |
+---------------------+
| -sistemaReal        |
| -sistemaRRHH        |
+---------------------+
| +RealizarVenta()    |
| +ObtenerClientes()  |
+---------------------+
```

Fecha de entrega al grupo: [Tu fecha] - Entregar  aproximaciòn de código C#  + documentación de los 2 patrones.
