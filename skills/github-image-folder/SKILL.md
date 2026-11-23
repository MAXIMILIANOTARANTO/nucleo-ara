---
name: github-image-folder
description: Gestiona una carpeta de imágenes de referencia alojada en el repositorio GitHub del usuario (nucleo-ara/assets/reference-images/). Actúa como carpeta local en la nube. Permite listar, añadir y obtener URLs públicas raw de imágenes para usarlas en flujos de browser upload, EzMaker, Valentina y 3D. Triggers — github image folder, carpeta de imágenes github, reference images repo, subir imagen a github folder, listar referencias valentina.
---

# GitHub Image Folder — Carpeta Local en la Nube

## Propósito

Mantener una carpeta estructurada de imágenes de referencia dentro del repositorio MAXIMILIANOTARANTO/nucleo-ara que el agente puede tratar como una carpeta local. 

Ruta canónica: assets/reference-images/

## Estructura recomendada

```
assets/reference-images/
├── valentina/
│   ├── character-sheet-black-crochet.jpg
│   ├── sunset-window-white-crop.jpg
│   ├── bed-ivory-crochet.jpg
│   └── ...
├── general/
└── README.md
```

## Operaciones

### Listar imágenes
Usar github___get_file_contents o github___search_code sobre assets/reference-images/.

### Añadir una nueva imagen
1. Tener el archivo local en /home/workdir/artifacts/ o attachments.
2. Convertir a base64 si es necesario o usar el conector de push (cuando soporte binarios) / gh CLI / release asset.
3. Documentar en el README de la carpeta.

### Obtener URL pública raw
Formato:
```
https://raw.githubusercontent.com/MAXIMILIANOTARANTO/nucleo-ara/main/assets/reference-images/valentina/NOMBRE.jpg
```

## Integración

- browser-file-upload-bridge: Usa las URLs o rutas de esta carpeta como fuente.
- ezmaker-image-to-image: Toma la imagen de referencia desde aquí.
- valentina-valiente: Las imágenes oficiales de Valentina viven en esta carpeta.

## Principios

- Todo queda versionado y soberano en el repo del usuario.
- Preferir nombres descriptivos y estables.
- Mantener un README.md actualizado con el inventario.
