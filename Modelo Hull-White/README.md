# 📘 Modelo de Hull & White: Simulación de rendimientos de CETES

Este archivo contiene una guía teórico-práctica sobre el **modelo de Hull & White** aplicado a la valoración de tasas de interés y derivados financieros.  Incluye fundamentos matemáticos, simulaciones en Python y una implementación con datos reales de **CETES (BANXICO)**.

El modelo de Hull & White es un modelo de tasas de interés de un factor ampliamente utilizado en finanzas para valorar bonos, derivados de renta fija y otros instrumentos de tasas de interés. Fue desarrollado por John Hull y Alan White en 1990 y se caracteriza por incorporar la media a la que tienden las tasas de interés, lo que le permite capturar la estructura temporal de tasas de forma más flexible.

## Características principales
- **Modelo de un factor**: Considera que la dinámica de la tasa de interés a corto plazo está gobernada por un solo factor estocástico.
- **Media a la que tiende la tasa**: La tasa de interés sigue una tendencia hacia un nivel de equilibrio que puede variar con el tiempo.
- **Volatilidad estocástica**: Permite modelar la volatilidad de la tasa de interés, facilitando la calibración con los precios de los bonos y opciones sobre tasas de interés.
- **Ecuación del modelo**: La dinámica de la tasa de interés \(r(t)\) se describe mediante la siguiente ecuación diferencial estocástica:


<p align="center">
  <img src="https://latex.codecogs.com/svg.latex?dr(t)%20=%20[\theta(t)%20-%20a%20r(t)]%20dt%20+%20\sigma%20dW(t)" alt="EDE Hull-White">
</p>


donde:
- $$a$$ es la velocidad de reversión a la media,
- $$\theta(t)$$ es una función que asegura el ajuste a la curva de tasas inicial,
- $$\sigma\$$ es la volatilidad de la tasa,
- $$W(t)$$ es un movimiento Browniano estándar.

## Aplicaciones
- Valoración de bonos y derivados de renta fija.
- Modelado de la evolución de la curva de tasas de interés.
- Gestión de riesgos de tasas de interés en portafolios de inversión.

El modelo de Hull & White es muy popular por su flexibilidad y capacidad de calibrarse a los datos del mercado, lo que lo convierte en una herramienta útil para analistas financieros y traders de renta fija, en este caso será usado para modelar las tasas de rendimientos de los Certificados de la Tesorería (CETES) con datos obtenidos de BANXICO. En el presente trabajo se abordan:

1. **Fundamentos teóricos**
   - Movimiento Browniano y procesos estocásticos.
   - Definición del modelo Hull-White y sus propiedades.

2. **Matemática del modelo**
   - Existencia y unicidad de la solución.
   - Distribución estacionaria, momentos y probabilidades de transición.

3. **Simulación en Python**
   - Método de Euler-Maruyama.
   - Análisis de sensibilidad a parámetros.
   - Caso con $\theta(t)$ variable en el tiempo.

4. **Inferencia estadística**
   - Estimación de parámetros por máxima verosimilitud.
   - Casos con $\theta$ constante y $\theta(t)$ dependiente del tiempo.

5. **Aplicación con datos reales**
   - Valuación de CETES como bonos cupón cero.
   - Construcción de la curva cupón cero.
   - Ajuste del modelo Hull-White con datos de BANXICO.

---

Los integrantes del proyecto desarrollado son estudiantes de la licenciatura en **Matemáticas Aplicadas** de la **Facultad de Ciencias** 

- Niño Pedraza Eduardo
- Reyes Ramírez Raquel
- Salas Cortés Emiliano
