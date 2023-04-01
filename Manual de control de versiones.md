# Manual de control de versiones

En este manual se define los distintos métodos, reglas, conceptos y recomendaciones que
se aplicarán para un óptimo control de versiones para el desarrollo del proyecto de
laboratorios UCA.

## Conceptos

1. **Fork**: Fork o Bifurcación, es una copia de un código o un repositorio en concreto, de
tal manera que cualquier modificación al Fork no afecta al repositorio original (Upstream).
2. **Upstream**: Hace referencia al repositorio padre, el que tiene el flujo principal. En
este caso, nos referimos al Repositorio principal.
3. **Pull Request**: También llamado **Merge Request**, es una solicitud de un desarrollador
para que sus cambios sean aplicados al proyecto deseado.

## Reglas

1. Sólo los gerentes de proyecto tendrán permiso para editar el repositorio principal.
2. Cada gerente de proyecto tendrá un **Fork** del repositorio.
3. Cada equipo trabajará sobre el **Fork** que el gerente posee.
4. Los cambios al repositorio principal se aplicarán únicamente a través de **Pull Requests**
de parte del **Fork** de cada gerente de proyecto.
5. Los cambios en los **Fork** se aplicarán a consideración de cada gerente. Se
recomiendan algunos métodos que se explicarán más adelante.
6. Se podrá realizar un cambio al repositorio principal sin necesidad de un **Pull Request**
siempre y cuando sea necesario y aprobado por todos los gerentes de proyecto.

## Recomendaciones

1. El contenido del mensaje de cada commit debe estar en ¿Inglés? <!-- TODO: Definir el idioma de cada commit -->
2. Los commits deben ser lo más descriptivo posibles. Ejemplos:
    - 🟢 `Added the CRUD methods for Usuario in UsuarioNegocio`
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

## Metodologías

Como se mencionó en las reglas, cada gerente realizará un **Fork** del repositorio principal y
su equipo trabajará únicamente sobre ese **Fork**. Luego, cuando el gerente y todo su equipo
haya verificado que los cambios son satisfactorios, se realizará un **Pull Request** al proyecto
principal que será aceptado por los demás gerentes de proyecto.

El método de **Pull Requests** será obligatorio de parte del **Fork** del gerente hacia el Upstream.
En cambio, la metodología de control de versiones del equipo quedará a discreción y
preferencia de cada equipo. Para ello, se recomiendan los siguientes métodos.

### Ramas individuales

El método que seguramente ya conocen, cada integrante del equipo tiene acceso para editar
el proyecto y posee una rama individual (puede ser el nombre del integrante).
Cuando el Gerente y/o Administrador de la configuración considere que los cambios de un
integrante son satisfactorios, se hará un `merge` a la rama `master` del **Fork**.

#### Creación de rama individual

```bash
git clone https://github.com/FORK_PROYECTO_LABORATORIOS.git # Se clona el repositorio Fork de su gerente
cd FORK_PROYECTO_LABORATORIOS # Entramos al repositorio
git checkout -b NOMBRE_INTEGRANTE # Creamos y entramos a una rama con el nombre del integrante
```

#### Merge de las ramas individuales

```bash
git switch master # Se cambia a la rama master
git merge NOMBRE_INTEGRANTE # Se aplican los cambios de NOMBRE_INTEGRANTE a la rama master
```

### Forks anidados

Se aplica la misma metodología que en el Proyecto principal. Cada integrante del equipo
hará un **Fork** del repositorio que cada Gerente posee y realizarán sus cambios directamente
en su propio repositorio. Una vez que el integrante considere que sus cambios están listos,
se realiza un **Pull Request** hacia el proyecto del Gerente y éste último lo aceptará.

### Ramas y Pull Requests

Es una combinación más sencilla de las Ramas individuales y los Forks anidados. Consiste en
que cada integrante posee una rama individual en la que podrá colaborar, pero el Gerente
y/o Administrador de la configuración no podrá hacer `merge` inmediato de sus cambios, para
ello el integrante deberá crear su **Pull Request** hacia el mismo proyecto del Gerente y
este último lo tendrá que aceptar. En síntesis, se aplican los **Pull Requests** sin necesidad
de que cada integrante realice un **Fork**.
