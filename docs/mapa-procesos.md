# Mapa de Procesos y Modelo de Ciclo de Vida — PetTracker

> Generado con el workflow paralelo: se ejecuta el flujo inicial de
> definición (6.4.2 → 6.4.3 → 6.4.4); luego la rama de Firmware (3
> procesos) y la rama de Plataforma y App (3 procesos) se ejecutan de
> forma simultánea; al final, Integración, Validación y Transición
> unen ambas ramas y cierran el flujo. La definición formal del modelo
> de ciclo de vida se documenta en la wiki, página `04c-Modelo-Ciclo-Vida`.

## Proceso: Definición de necesidades y requisitos de los interesados (6.4.2)

- **Entradas:** Modelo verbal (RFP); extensión del modelo verbal (Paso 1)
- **Actividades:** Preparar la definición; identificar actores y definir sus necesidades; desarrollar el concepto de operación; transformar las necesidades en requisitos de los interesados; analizarlos
- **Salidas:** Actores (02b); necesidades de negocio (02c); necesidades de los interesados (02d)
- **Recursos:** BABOK v3; equipo; wiki

## Proceso: Definición de requisitos del sistema/software (6.4.3)

- **Entradas:** Necesidades de negocio y de los interesados (02c, 02d)
- **Actividades:** Preparar la definición; definir los requisitos funcionales (historias de usuario con criterios de aceptación), no funcionales (con métrica y umbral) y de interfaz; analizarlos; gestionarlos con trazabilidad
- **Salidas:** Módulos, RF y RNF como issues; requisitos de interfaz (02e); vista "Registro de Requisitos"
- **Recursos:** BABOK v3; formularios de issues; GitHub Project

## Proceso: Definición de la arquitectura (6.4.4)

- **Entradas:** Requisitos del sistema/software; requisitos de interfaz (02e); especificaciones del collar adquirido; resultados del análisis del sistema (6.4.6)
- **Actividades:** Preparar la definición de la arquitectura; definir puntos de vista relevantes (dispositivo, comunicación, datos, seguridad); desarrollar y evaluar arquitecturas candidatas; relacionar la arquitectura con el diseño
- **Salidas:** Arquitectura del sistema (componentes, interfaces y protocolo entre collar y plataforma); decisiones de seguridad y privacidad
- **Recursos:** Arquitecto de software del equipo; herramienta libre de diagramas

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

## Rama Plataforma y App Móvil

### Proceso: Definición del diseño, rama plataforma y app (6.4.5)

- **Entradas:** Arquitectura del sistema; RF y RNF de los módulos MOD-01 a MOD-06; requisitos de interfaz (02e)
- **Actividades:** Diseñar los servicios de la plataforma, base de datos, motor de alertas y las pantallas/navegación de la app móvil
- **Salidas:** Diseño de la plataforma y de la app
- **Recursos:** Equipo de desarrollo de plataforma y app; React Native; herramienta de prototipos de interfaz

### Proceso: Implementación, rama plataforma y app (6.4.7)

- **Entradas:** Diseño de la plataforma y de la app
- **Actividades:** Preparar la implementación; construir el backend y la app móvil; gestionar versiones y defectos
- **Salidas:** Plataforma y app construidas y versionadas
- **Recursos:** React Native; framework del backend; servicios externos de mapas, notificaciones y correo; Git

### Proceso: Verificación, rama plataforma y app (6.4.9)

- **Entradas:** Plataforma y app construidas; RF y RNF de la plataforma y la app
- **Actividades:** Verificar criterios de aceptación de los RF, tiempo de carga de 3 s, respuesta de 2 s y compatibilidad en matriz de teléfonos
- **Salidas:** Plataforma y app verificadas; reporte de verificación; defectos registrados
- **Recursos:** Entorno de pruebas; matriz de teléfonos (RNF-15); herramientas de pruebas automatizadas

## Proceso: Integración (6.4.8)

- **Entradas:** Firmware verificado; plataforma y app verificadas; collares aceptados (6.1.1)
- **Actividades:** Preparar la integración; integrar paso a paso el firmware en el collar, el collar con la plataforma por red móvil y la plataforma con la app
- **Salidas:** Sistema completo integrado; reporte de integración
- **Recursos:** Collares del proveedor; plataforma en entorno de pruebas; teléfonos de prueba

## Proceso: Validación (6.4.11)

- **Entradas:** Sistema integrado; necesidades de los interesados (02d); RNF de usabilidad y precisión
- **Actividades:** Preparar escenarios de uso real; validar con usuarios y mascotas (pruebas de campo en ciudad, prueba SUS con usuarios de varias edades, aceptación del cliente)
- **Salidas:** Reporte de validación; aceptación del cliente
- **Recursos:** Usuarios de prueba; mascotas con collar; cuestionario SUS; representante del cliente

## Proceso: Transición (6.4.10)

- **Entradas:** Sistema validado; aceptación del cliente
- **Actividades:** Preparar la transición; desplegar la plataforma, publicar la app en Google Play y App Store, cargar el firmware en los collares y entregar documentación al cliente
- **Salidas:** Sistema en producción; app publicada; acta de entrega
- **Recursos:** Cuentas de desarrollador en las tiendas; infraestructura de producción; manuales de uso

