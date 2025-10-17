# Guía para contribuir

¡Gracias por tu interés en contribuir a este proyecto! Este documento describe las buenas prácticas y convenciones que seguimos para mantener un flujo de trabajo limpio, una base de código coherente y una colaboración efectiva.

---

## Tipo de proyecto

Este es un proyecto frontend basado en **React**, estructurado según los principios de **Atomic Design**, y utiliza **React Router** para la navegación.

---

## Flujo de trabajo con Git

Seguimos un modelo de trabajo basado en **GitFlow simplificado**, adaptado para un equipo pequeño.

### Ramas
- `main`: Contiene todo el codigo estable y funcional del proyecto, ademas de un workflow, contributing.md y readme.md.
- `workflow`: Contiene el workflow para este proyecto que genera un workflow que instala dependencias basicas, ejecuta los test,
revisa el codigo con Eslint, analiza dependencias son synk, ejecuta analizis con sonarcloud y contruye una img en docker
(Esta rama deberería estar eliminada pero por temas de evaluación esta activa).
- `Readme`: Explica qué hace el workflow y cómo levantar los contenedores (Esta rama deberería estar eliminada pero por temas de evaluación esta activa).
- `Contributing`: Contiene buenas practicas, metodo de trabajo, estructuras para el codigo, estructura para el orden del proyecto
(Esta rama deberería estar eliminada pero por temas de evaluación esta activa).

### Cómo trabajar con ramas

1. **Crea una nueva rama desde `main`** para cada funcionalidad, corrección o cambio.
2. El nombre de la rama debe describir brevemente el propósito del cambio:

| Tipo      | Prefijo sugerido         | Ejemplo                             |
|-----------|--------------------------|-------------------------------------|
| Funcionalidad nueva | `descripcionFuncionalidad/`              | `workflow`               |
| Ajuste urgente      | `hotfix/`               | `hotfix/AjusteUrgente`             |

### Proceso de integración

1. Una vez que la funcionalidad esté **terminada y probada localmente**, realiza un **pull a `main`** desde tu rama.
2. Verifica que no existan conflictos ni errores.
3. **Elimina la rama** tanto local como remotamente para mantener el repositorio limpio.


### Composición del proyecto

- Este proyecto sigue la arquitectura de Atomic Design, con las siguientes capas:
```
src/
  └── componentes/
        ├── atomos/       # Elementos indivisibles (Botón, Imagen, Texto)
        ├── moleculas/    # Composición de átomos (Card)
        ├── organismos/   # Secciones completas (ListaCard)
        ├── plantillas/   # Estructura general de página (Layout)
        └── paginas/      # Vistas del router (Descripcion, Home.)
```

### Pruebas

- Actualmente, las pruebas se hacen manualmente en entorno local (npm start).

### Formato y estilo

1. Asegúrate de mantener una indentación consistente (2 o 4 espacios según configuración).
2. Usa comillas dobles para strings, como "texto" (según convención actual).
3. Ordena props y atributos JSX con lógica y consistencia.
4. Agrega saltos de línea donde mejoren la legibilidad.
