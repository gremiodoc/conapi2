# Cálculo de Vacaciones Docentes 2025

Una calculadora web para determinar el monto de las vacaciones de los docentes en Venezuela, basada en un salario quincenal (sin descuentos), 88 días de trabajo, un bono de $40 del MPPE, y un bono de $50 de la Plataforma Patria, convertidos a Bolívares usando la tasa oficial del BCV obtenida dinámicamente a través de la API de [PyDolarVenezuela](https://pydolarve.org/apidocs).

## Características

- **Cálculo de Vacaciones**: Calcula el pago de vacaciones para 88 días basado en el salario quincenal ingresado.
- **Bonos**: Incluye un bono de $40 (MPPE) y $50 (Plataforma Patria), convertidos a Bolívares usando la tasa BCV.
- **Tasa BCV Dinámica**: Obtiene la tasa oficial del BCV en tiempo real desde la API de PyDolarVenezuela, con opción para ajuste manual.
- **Interfaz Amigable**: Diseño responsivo usando [Tailwind CSS](https://tailwindcss.com/), con el logo de GremioDocente y botones para calcular y reiniciar.
- **Reinicio Parcioal**: El botón de reinicio limpia el salario y los resultados, pero mantiene la tasa BCV para evitar llamadas innecesarias a la API.

## Requisitos

- Navegador web moderno (Chrome, Firefox, Safari, etc.).
- Conexión a internet para cargar la API de PyDolarVenezuela y Tailwind CSS (via CDN).
- (Opcional) Servidor local para pruebas (por ejemplo, Live Server en VS Code).

## Instalación

1. Clona el repositorio:
   ```bash
   git clone https://github.com/usuario/repositorio.git
   ```
2. Navega al directorio del proyecto:
   ```bash
   cd repositorio
   ```
3. Abre el archivo `index.html` en un navegador web. Puedes usar un servidor local para una mejor experiencia:
   ```bash
   npx live-server
   ```

**Nota**: No se requieren dependencias adicionales, ya que Tailwind CSS se carga vía CDN y la lógica está escrita en JavaScript puro.

## Uso

1. Abre `index.html` en un navegador.
2. La calculadora cargará automáticamente la tasa BCV desde la API de PyDolarVenezuela.
3. Ingresa tu salario quincenal (sin descuentos) en el campo correspondiente.
4. (Opcional) Ajusta la tasa BCV manualmente si es necesario.
5. Haz clic en **Calcular** para ver:
   - Monto por 88 días de vacaciones.
   - Bono MPPE ($40 a tasa BCV).
   - Bono Plataforma Patria ($50 a tasa BCV).
   - Monto total en Bolívares.
6. Usa el botón **Reiniciar** para limpiar el salario y los resultados (la tasa BCV se mantiene).

## Estructura del Proyecto

- `index.html`: Archivo principal que contiene la interfaz y la lógica de la calculadora.
- (Placeholder) Logo de GremioDocente: Actualmente usa una imagen de `via.placeholder.com`. Reemplaza la URL en `index.html` con el logo oficial.

## API Utilizada

- **PyDolarVenezuela API**: [https://pydolarve.org/apidocs](https://pydolarve.org/apidocs)
  - Endpoint: `https://pydolarve.org/api/v2/tipo-cambio?currency=usd&monitor=bcv`
  - Proporciona la tasa oficial del BCV para USD.
  - Límite: 500 solicitudes gratuitas por día. Contacta al proveedor para límites mayores.

## Notas Importantes

- **Logo**: Reemplaza la URL del logo (`https://via.placeholder.com/150x50?text=GremioDocente+Logo`) con la URL del logo oficial de GremioDocente.
- **Tasa de Respaldo**: Si la API falla, la calculadora usa una tasa de respaldo de 109 Bs/USD.
- **CORS**: La API se llama desde el cliente. Si hay problemas de CORS, considera usar un servidor proxy o contactar al proveedor de la API.
- **Pruebas**: Verifica los cálculos con diferentes salarios y tasas BCV. Compara la tasa obtenida con fuentes oficiales del BCV.

## Contribuciones

¡Las contribuciones son bienvenidas! Por favor, sigue estos pasos:

1. Haz un fork del repositorio.
2. Crea una rama para tu cambio:
   ```bash
   git checkout -b mi-cambio
   ```
3. Realiza los cambios y haz commit:
   ```bash
   git commit -m "Descripción del cambio"
   ```
4. Envía un pull request.

## Licencia

Este proyecto está bajo la [Licencia MIT](LICENSE). Consulta el archivo `LICENSE` para más detalles.

## Contacto

Para preguntas o sugerencias, contacta al mantenedor del proyecto en [correo@ejemplo.com](mailto:correo@ejemplo.com) o abre un issue en GitHub.