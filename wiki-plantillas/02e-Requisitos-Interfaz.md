# Paso 2.5 — Requisitos de Interfaz

_Interacciones con otros sistemas o servicios mencionados o inferidos
(APIs, pasarelas de pago, servicios de notificación, etc.)._

| Sistema/Servicio externo | Tipo de interacción | Justificación/Origen |
|---|---|---|
| Servicio de posicionamiento GPS/GNSS | El collar recibe señales satelitales mediante su módulo GPS para obtener coordenadas. | Explícito en el modelo verbal y en la extensión del Paso 1, que describen el módulo GPS y los reportes de ubicación. |
| Red móvil del operador | El collar transmite su ubicación y sincroniza los recorridos almacenados cuando hay cobertura; la aplicación recibe los reportes de la plataforma. | Explícito en la extensión del Paso 1, que contempla la pérdida temporal de señal celular y la sincronización al restablecerse la red. |
| Servicio de mapas | La aplicación consulta recursos cartográficos para mostrar la ubicación actual, la última ubicación conocida y los recorridos históricos. | Inferido del modelo verbal, que requiere visualizar ubicaciones y rutas en un mapa; no se especifica proveedor. |
| Servicio de notificaciones móviles | La plataforma solicita el envío de alertas de salida del área segura y de batería baja a la aplicación del dueño. | Las alertas están descritas en el modelo verbal y en la extensión del Paso 1; el uso de un servicio externo de notificaciones se infiere y no se especifica proveedor. |

No se identifica en los insumos una pasarela de pago ni una integración externa con veterinarias u otros sistemas. El backend de PetTracker y la aplicación propia se consideran componentes internos del sistema, no servicios externos.
