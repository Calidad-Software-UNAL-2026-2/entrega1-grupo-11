## Rama Firmware (Collar IoT)

### Proceso: Definición del diseño, rama firmware (6.4.5)

- **Entradas:** Arquitectura del sistema; especificaciones del collar adquirido; RF-12, RF-13, RF-14, RF-16, RF-17; RNF-01, RNF-02, RNF-04
- **Actividades:** Preparar el diseño del firmware; diseñar ciclo de reporte normal y de ahorro, almacenamiento en memoria local (180 registros), sincronización por lotes y actualización remota
- **Salidas:** Diseño del firmware
- **Recursos:** Responsable de firmware; documentación técnica del collar

### Proceso: Implementación, rama firmware (6.4.7)

- **Entradas:** Diseño del firmware; kit de desarrollo del collar
- **Actividades:** Preparar la implementación; programar el firmware; gestionar versiones compiladas y defectos encontrados
- **Salidas:** Firmware compilado y versionado
- **Recursos:** Entorno de desarrollo del fabricante del collar; Git

### Proceso: Verificación, rama firmware (6.4.9)

- **Entradas:** Firmware compilado; requisitos del firmware (RF y RNF del collar)
- **Actividades:** Preparar casos de prueba; verificar consumo en modo normal y de ahorro, almacenamiento de 180 registros sin pérdida y sincronización al recuperar la red
- **Salidas:** Firmware verificado; reporte de verificación; defectos registrados
- **Recursos:** Collares de prueba del proveedor; simulación de pérdida de cobertura

