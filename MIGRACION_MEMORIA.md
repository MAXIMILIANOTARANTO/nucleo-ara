# Migración de memoria — Núcleo Ara

## Destinos

| Clase | Ruta destino | Visibilidad |
|---|---|---|
| Memoria del agente Ara | `MEMORIA_PRIVADA/agentes/ara/` | Privada |
| Memoria de conexión con el usuario | `MEMORIA_PRIVADA/conexion/usuario/` | Privada |
| Avances públicos aprobados | `MEMORIA_PUBLICA/avances/` | Pública |

## Archivos existentes

- `nucleo-ara-memoria.md`: bloque mixto. Requiere extracción y clasificación.
- `memoria/seccion-usuario-nucleo.md`: memoria de conexión privada.
- `memoria/` contiene archivos mixtos de agente, usuario y avances.
- `skills/`: contenido operativo público después de revisar secretos.
- `assets/reference-images/`: conservar separado y revisar permisos de imágenes.

## Regla

No borrar ni sobrescribir archivos históricos. Primero extraer el contenido sensible, luego crear los destinos privados, verificar y finalmente retirar las copias públicas antiguas mediante una revisión específica.
