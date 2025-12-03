# INTEGRANTE 2: Especialista en Patrones de Comportamiento (1)

## Entregables Específicos
- Documentación de **2 patrones de comportamiento**: Observer y Strategy.  
- Código C# de implementación para ambos patrones.  
- Ejemplos de uso aplicados al contexto **PoliMarket**.

---

# Trabajo Independiente - Instrucciones

---

## 1. Patrón OBSERVER – Notificaciones de ventas

### Problema Específico
Cuando se realiza una venta, múltiples sistemas deben ser notificados automáticamente:

- Bodega  
- Entregas  
- Contabilidad  

Actualmente, esta notificación es manual y acoplada.  
El objetivo es **implementar el patrón Observer** para automatizar y desacoplar estos eventos.

---

## Código Base Inicial (C#)

```csharp
// ====== CÓDIGO BASE PARA INTEGRANTE 2 - OBSERVER ======
// Tu trabajo es IMPLEMENTAR el patrón Observer completo

// Interfaz para observadores (COMPLETAR)
public interface IObservadorVenta
{
    void Actualizar(Venta venta);
}

// Clase de datos para ventas (YA EXISTE)
public class Venta
{
    public string VendedorId { get; set; }
    public string ProductoId { get; set; }
    public int Cantidad { get; set; }
    public DateTime Fecha { get; set; }
}

// Sujeto observable (COMPLETAR)
public class SistemaVentasObservable
{
    private List<IObservadorVenta> observadores = new List<IObservadorVenta>();
    
    // Métodos para agregar/remover observadores (IMPLEMENTAR)
    
    public void RealizarVenta(string vendedorId, string productoId, int cantidad)
    {
        // 1. Crear objeto Venta
        // 2. Notificar a todos los observadores
        // 3. (Opcional) Guardar la venta en BD
    }
    
    private void NotificarObservadores(Venta venta)
    {
        // IMPLEMENTAR
    }
}

// Observadores concretos (CREAR al menos 2)
// 1. ObservadorBodega: Actualiza stock
// 2. ObservadorEntregas: Genera orden de entrega
// Ejemplo:
public class ObservadorBodega : IObservadorVenta
{
    public void Actualizar(Venta venta)
    {
        Console.WriteLine($"Bodega: Actualizando stock tras venta de {venta.ProductoId}");
    }
}
```

# Diagrama de Clases - Fragmento para Tu Trabajo:

```text
[Integrante 2 - Fragmento de Diagrama]
+------------------------+        +----------------------+
| IObservadorVenta       |        | IMetodoEntrega       |
+------------------------+        +----------------------+
| +Actualizar(Venta)     |        | +CalcularCosto()     |
+------------------------+        | +CalcularTiempo()    |
         ^                         | +RealizarEntrega()   |
         |                         +----------------------+
         |                                  ^
+----------------------+                    |
| SistemaVentas        |        +----------------------+
| Observable           |        | ServicioEntregas     |
+----------------------+        +----------------------+
| -observadores        |        | -metodoEntrega       |
+----------------------+        +----------------------+
| +AgregarObservador() |        | +SetMetodoEntrega()  |
| +RealizarVenta()     |        | +ProcesarEntrega()   |
| +NotificarObservadores() +----------------------+
+----------------------+

TUS CLASES A CREAR:
+---------------------+     +---------------------+
| ObservadorBodega    |     | EntregaExpress      |
+---------------------+     +---------------------+
| +Actualizar()       |     | +CalcularCosto()    |
+---------------------+     | +RealizarEntrega()  |
                            +---------------------+
+---------------------+     +---------------------+
| ObservadorEntregas  |     | EntregaEstandar     |
+---------------------+     +---------------------+
| +Actualizar()       |     | +CalcularCosto()    |
+---------------------+     | +RealizarEntrega()  |
                            +---------------------+
```

Fecha de entrega al grupo: [Tu fecha] - Entregar código C# completo + documentación de los 2 patrones.


