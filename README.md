# Prueba Kevin Alejandro Manzano Torres - QA Automatizador

# Sección 1 – Conocimientos Teóricos
### 1.1 Explica brevemente la diferencia entre pruebas funcionales y no funcionales.

**Respuesta**: Las pruebas funcionales buscan validar un comportamiento a nivel de usuario (interacción, accesibilidad, etc.) mientras que
las pruebas no funcionales validan comportamientos a nivel de infraestructura, código, etc.

### 1.2 Menciona al menos dos ventajas de usar automatización de pruebas en comparación con pruebas manuales.

**Respuesta**: La automatización asegura la ejecución de las pruebas 24/7 garantizando calidad el 99% del tiempo, y otra ventaja es
la escalabilidad y confiabilidad en pruebas recurrentes y repetitivas.

### 1.3 ¿Cuál es la diferencia entre una prueba de carga y una prueba de estrés?

**Respuesta**: Las pruebas de carga validan como se comporta la aplicación con X cantidad de sesiones, transacciones, etc. para identificar y medir tiempos
de respuesta. Por el otro lado las pruebas de estrés buscan llevar la aplicación al limite de uso entonces no tiene una cantidad de data definida
ya que depende de varios factores, esta prueba busca identificar los topes de uso de la aplicación.

### 1.4 ¿Qué es el ciclo de vida del bug (Bug Life Cycle)?

**Respuesta**: Es el proceso de reporte de un bug y sus distintos estados a lo largo del tiempo, el primer estado es el reporte del mismo, la asignación
y reparación por parte de un miembro del equipo de desarrollo, la re-ejecución de las pruebas y el cierre de la incidencia si las pruebas
fueron exitosas, si se encuentra un nuevo defecto o el anterior no se solucionó se inicia de nuevo el proceso. 

### 1.5 En metodologías ágiles, ¿qué rol tiene un QA en un equipo Scrum?

**Respuesta**: QA tiene el rol de garantizar calidad desde la definición de los criterios de aceptación hasta el desarrollo de la funcionalidad garantizando
que se cumplen los criterios antes definidos.

# Sección 2 – Ejercicios Prácticos Conceptuales
### 2.1 SQL – Validación de datos
Dada la tabla Pedidos:
| PedidoID | ClienteID | Fecha | Total |
|----------|-----------|-------------|-------|
| 1 | 100 | 2025-08-01 | 250 |
| 2 | 101 | 2025-08-02 | 400 |
| 3 | 100 | 2025-08-03 | 150 |
Escribe una consulta SQL para obtener el total de compras por ClienteID.

**Respuesta**: `SELECT * FROM Pedidos WHERE ClienteId = 100`

### 2.2 API Testing

Tienes un endpoint `GET /users/{id}` que devuelve:

```json
{
    "id": 1,
    "name": "Juan",
    "email": "juan@test.com"
}
```

Escribe 2 validaciones que harías en Postman o similar.

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

```javascript
pm.test("Your test name", function () {
    var data = pm.response.json();
    pm.expect(data.id).to.eql(1);
    pm.expect(data.name).to.eql("Juan");
    pm.expect(data.email).to.eql("juan@test.com");
});
```

### 2.3 Selenium/Cypress

Queremos automatizar el login de una página con campos `#username`, `#password` y botón `#loginBtn`.
Escribe un snippet de prueba (en pseudo-código o en Cypress/Selenium simplificado).

**Cypress**

```javascript
describe("Login", () => {
    it("Success Login", () => {
        cy.visit("https://example.com");
        cy.get("#username").type("John Doe");
        cy.get("#password").type("SecretPassword123*");
        cy.get("#loginBtn").click();
    })
});
```
