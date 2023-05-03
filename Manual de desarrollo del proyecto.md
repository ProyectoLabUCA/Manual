# Manual de desarrollo del proyecto

En este manual se define el cómo se estructura el proyecto de Laboratorios
de Informática y cómo se debe de desarrollar para llevar a cabo la
finalización de este proyecto.

Además de este manual, recordar aplicar las reglas que el departamento de
Informática nos otorgó para el desarrollo del proyecto.

## Conceptos

## Estructura del proyecto

El proyecto se estructura según el modelo de N-capas, teniendo así:

- Datos:
  En donde se realizan las solicitudes a la Base de Datos con el
  EntityFramework y el modelo de Entidades.
- Entidades:
  Donde se definen todas las entidades del sistema, así como el modelo
  de entidades de la base de datos generado por el EntityFramework.
- Negocio:
  En donde se realizan todas las validaciones, comprobaciones y reglas
  de negocio del sistema.
- LabInformática (Presentación):
  Es el apartado de la presentación, en donde se trabajará el diseño y
  las interacciones con la capa de Negocio.

### Consideraciones

1. La capa de Entidades en teoría no se debería de tocar más que por los gerentes y encargados de la base de datos. Se supone que actualmente ya está lista, y si llegaran a hacerse cambios, serían muy mínimos.
2. La capa de datos sólo debería de encargarse de hacer las solicitudes SQL a través de la capa de Entidades, nada más, nada menos.
2. La capa de Negocio y de Presentación es en donde se trabajará la mayor parte del tiempo.

## Cómo desarrollar

### Diseño

A la hora de desarrollar el diseño, considerando que ya casi todo está hecho en el repositorio del [Template](https://github.com/ProyectoLabUCA/LaboratoriosInformaticaTemplate), a la hora de pasarlo al repositorio de [LabInformatica](https://github.com/ProyectoLabUCA/LabInformatica) es mayormente copiar y pegar.

Ahora, se definirán algunas rutas/carpetas importantes de la capa de Presentación:

- `Styles/`: Aquí es donde colocarán los archivos CSS que vean convenientes, siempre y cuando tengan el mismo nombre del webForm (`wfDashboard.css`, por ejemplo).
- `Scripts/`: Aquí no toquen nada.
- `Content/`: Aquí tampoco toquen nada.
- `Scripts/InfoLabs/`: Aquí es donde agregarán los archivos JavaScript que vean convenientes y sean necesarios, siempre y cuando tengan el mismo nombre del webForm (`wfDashboard.js`, por ejemplo).
- `TecnicoVistas/`: Aquí definirán sus archivos aspx para cada página de parte de la vista del Técnico.
- `EstudianteVistas/`: Aquí definirán sus archivos aspx para cada página de parte de la vista del Estudiante.

Posterior a esto, para importar un archivo JavaScript en su aspx, pueden usar el siguiente ejemplo:

```aspx
<script src="<%=ResolveClientUrl("~/Scripts/InfoLabs/wfSolicitudes.js")%>" type="text/javascript"></script>
```

> A través del aspx con la función `ResolveClientUrl` obtenemos la ruta absoluta del archivo JavaScript en cuestión, de tal manera que siempre se obtendrá el archivo correcto.

Para importar un archivo CSS en su aspx, al igual que con JavaScript, pueden usar el siguiente ejemplo:

```aspx
<link rel="stylesheet" href="<%=ResolveClientUrl("~/Styles/wfSolicitudes.css")%>">
```

> De igual manera, gracias a la función `ResolveClientUrl` obtenemos la ruta absoluta del archivo CSS en cuestión.
