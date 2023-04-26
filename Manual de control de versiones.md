# Manual de control de versiones

En este manual se define los distintos métodos, reglas, conceptos y recomendaciones que
se aplicarán para un óptimo control de versiones para el desarrollo del proyecto de
laboratorios UCA.

## Conceptos

1. **Upstream**: Hace referencia al repositorio padre, el que tiene el flujo principal. En
este caso, nos referimos al Repositorio principal.
2. **Pull Request**: También llamado **Merge Request**, es una solicitud de un desarrollador
para que sus cambios sean aplicados al proyecto deseado.
2. **Board**: O **[tablero](https://github.com/orgs/ProyectoLabUCA/projects/1)** es la herramienta que utilizaremos para llevar hacer seguimiento a las tareas o items.

## Reglas

1. Sólo los gerentes de proyecto tendrán permiso para editar el repositorio principal.
2. Sólo los gerentes de proyecto podrán crear y asignar items en el board.
3. Los cambios al repositorio principal se aplicarán únicamente a través de **Pull Requests** a partir de la rama `dev` del repositorio principal. Para los proyectos del manual y del template, se harán Pull Requests a partir de la rama `master`
4. La nomenclatura de las ramas es `{dev}/{#item}-{descripción}`. Por ejemplo: `ameza/1-actualizar-control-de-versiones`.
5. En cada pull request, agregar como reviewer a cualquiera de las siguientes personas:
    - Jezer Mejía
    - Armando Meza
6. Enlazar cada pull request con su respectivo item.
7. El desarrollador es dueño y responsable por sus items de trabajo, por lo tanto, debe moverlos por cada columna en el board.

## Recomendaciones

1. El contenido del mensaje de cada commit debe estar en español.
2. Los commits deben ser lo más descriptivo posibles. Ejemplos:
    - 🟢 `Métodos CRUD de Usuario añadidos a UsuarioNegocio`
    - 🟢 `Fixed some styling issues in wfGestionarUsuarios`
    - 🔴 `Commit`
    - 🔴 `Usuario`
3. Intentar hacer commits pequeños. O sea, una vez has implementado una funcionalidad,
crea un commit. Tampoco exageres y hagas un commit por cada línea de código escrita.
Ni lo contrario, no hagas un commit de 10,000 líneas de código en el que creas un
sistema operativo completo.
4. Se recomienda el uso de la terminal. Sin embargo, si te resulta difícil siempre puedes
usar herramientas gráficas como `GIT GUI`, `GitHub Desktop` o las herramientas del IDE
(siempre y cuando sepas usarlas).
5. Avisar a través del grupo de whatsapp cuando se haga un pull request para pedir revisión. Etiquetar al reviewer para más visibilidad.
## Flujo de trabajo

- Toda tarea empieza con un item asignado en el board. Los gerentes son responsables de asignar
tareas a los desarrolladores de sus respectivos equipos.
- A partir de esta tarea en la columna de **Backlog**, la moveremos a **In progress** y crearemos una rama a partir de la rama `dev`.
- `git checkout dev`, para cambiar a la rama `dev`
- `git pull`, para bajar los últimos cambios del upstream. `git pull -u origin dev`, si el comando anterior falla.
- `git checkout -b nombre-de-nuestra-rama`, para crear la rama a partir de la cual haremos el pull request a `dev`. Asegurarse de seguir correctamente la nomenclatura para las ramas..
- Realizar los cambios y commits necesarios para cumplir la tarea. Prestar atención a los [estándares de desarrollo](./Estandares%20de%20desarrollo%20y%20bases%20de%20datos.md). Fallar en su implementación resultará en pull requests rechazados.
- `git push -u origin nombre-de-nuestra-rama`, para subir nuestros cambios.
- Dirigirnos a github, crear el pull request. 
    - Rama base: `dev`, compare: `nombre-de-nuestra-rama`
    - Poner como descripción `Closes #item`, para enlazar el item con el pull request.
    - Añadir al respectivo reviewer.
    - Creamos el pull request.
    - Avisar por el grupo de whatsapp al reviewer.
- En el board, mover el item a review y esperar feedback. Si fue aprobado, mover el item a **Done**, 
sino, devolverlo a **In progress** y repetir el proceso.

