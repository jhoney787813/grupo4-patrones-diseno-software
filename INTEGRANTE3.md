
# INTEGRANTE 3: Especialista en Patrones Creacionales

## Entregables Específicos
- Documentación de **1 patrón creacional**: Factory Method.  
- Código C# de implementación.  
- Diagrama de secuencia para la creación de objetos.

---

# Trabajo Independiente - Instrucciones

---

## Patrón FACTORY METHOD – Creación de Vendedores

### Problema Específico
La creación de objetos **Vendedor** es compleja, ya que:

- Requiere validación previa por **RRHH**.  
- Existen diferentes tipos de vendedores: **Junior**, **Senior**, **Temporal**.  
- Se desea centralizar la creación para evitar duplicar lógica.

### Tu Tarea
Implementar el **patrón Factory Method** para manejar la creación de vendedores de forma flexible, limpia y escalable.

---

## Código Base Inicial (C#)

```csharp
// ====== CÓDIGO BASE PARA INTEGRANTE 3 - FACTORY METHOD ======
// Tu trabajo es IMPLEMENTAR el patrón Factory Method completo

// Producto abstracto (DEFINIR)
public abstract class Vendedor
{
    public string Id { get; set; }
    public string Nombre { get; set; }
    public abstract string Tipo { get; }
    
    public abstract void RealizarVenta(string productoId, int cantidad);
    public abstract decimal CalcularComision(decimal montoVenta);
}

// Productos concretos (CREAR al menos 3)
// 1. VendedorJunior
// 2. VendedorSenior
// 3. VendedorTemporal


// Creador abstracto (DEFINIR)
public abstract class VendedorFactory
{
    // Factory Method
    public abstract Vendedor CrearVendedor(string id, string nombre);
    
    // Método de validación común
    protected bool ValidarConRRHH(string id)
    {
        // Simular validación
        SistemaRRHH rrhh = new SistemaRRHH();
        return rrhh.EstaAutorizado(id);
    }
}

// Creadores concretos (CREAR al menos 2)
// 1. FactoryVendedorLocal
// 2. FactoryVendedorExterno


// Clase de uso (COMPLETAR)
public class SistemaGestionVendedores
{
    public Vendedor RegistrarNuevoVendedor(string id, string nombre, string tipo)
    {
        VendedorFactory factory;
        
        // Seleccionar factory basado en tipo
        if (tipo == "Local")
            factory = new FactoryVendedorLocal();
        else if (tipo == "Externo")
            factory = new FactoryVendedorExterno();
        else
            throw new ArgumentException("Tipo no válido");
        
        // Usar factory para crear vendedor
        return factory.CrearVendedor(id, nombre);
    }
}
```

# Diagrama de Clases - Fragmento para Tu Trabajo:

```text
[Integrante 3 - Fragmento de Diagrama]
+---------------------+
| Vendedor (Abstract) |
+---------------------+
| +Id                 |
| +Nombre             |
| +Tipo               |
+---------------------+
| +RealizarVenta()    |
| +CalcularComision() |
+---------------------+
         ^
         |
+---------------------+       +---------------------+
| VendedorFactory     |       | VendedorJunior      |
| (Abstract)          |       +---------------------+
+---------------------+       | +Tipo = "Junior"    |
| +CrearVendedor()    |       | +CalcularComision() |
| +ValidarConRRHH()   |       +---------------------+
+---------------------+       
         ^                    +---------------------+
         |                    | VendedorSenior      |
+---------------------+       +---------------------+
| FactoryVendedorLocal|       | +Tipo = "Senior"    |
+---------------------+       | +CalcularComision() |
| +CrearVendedor()    |       +---------------------+
+---------------------+       
                             +---------------------+
                             | VendedorTemporal    |
+---------------------+       +---------------------+
| FactoryVendedorExterno|     | +Tipo = "Temporal"  |
+---------------------+       | +CalcularComision() |
| +CrearVendedor()    |       +---------------------+
+---------------------+
```
Fecha de entrega al grupo: [Tu fecha] - Entregar código C# completo + documentación del patrón.
