
# Sistema de Gestión de Guardias de Profesores 📚

![image](https://github.com/user-attachments/assets/0211957c-3e64-42c1-914a-1ff291ac0916)


## Descripción 📝

Este proyecto tiene como objetivo el desarrollo de una **aplicación web** que registre y gestione las **guardias de los profesores** en caso de ausencias. A través de esta aplicación, los administradores o usuarios autorizados pueden anotar las guardias, asignar profesores sustitutos, indicar los grupos y aulas afectados, y registrar si hay alumnos problemáticos.

**Futuro**: El sistema se expandirá con el reemplazo de la base de datos actual por una **API RESTful con Laravel** y la **integración con el sistema Delphos** para obtener datos más actualizados de los profesores.

---

## Funcionalidades 🔧

- **Gestión de Guardias**: Registrar ausencias y asignar profesores sustitutos.
- **Formulario Interactivo**: Visualización de las guardias en un formulario que puede ser llenado y enviado en tiempo real.
- **Petición AJAX**: Enviar los datos al servidor con jQuery para guardarlos en un archivo JSON local.
- **Validación de Campos**: Asegura que todos los campos obligatorios se completen antes de enviarlo.
- **Interactividad con Vue.js**: Creación de una interfaz dinámica y actualizada de manera automática.

---

## Tecnologías Usadas 💻

- **Vue.js**: Framework JavaScript para crear interfaces reactivas y dinámicas.
- **Tailwind**: Para crear elementos modernos y nos sea facil modificarlos a lo largo de las modificaciones que tenga el proyecto , sin depender tanto de una hoja de estilos.
- **JSON Server**: Simulación de una base de datos local para el almacenamiento de datos.
- **Laravel (Futuro)**: API RESTful para mejorar la gestión y escalabilidad del sistema.
- **Delphos (Futuro)**: Integración con el sistema educativo para obtener datos reales de los profesores.

---

## Estructura de Datos 📂

### **Base de datos (db.json)**

Profesores:

Contiene los datos de los profesores, como nombre, id, etc. Estos datos se cargarán dinámicamente en el formulario para facilitar la selección de profesores al registrar una guardia.

#### Ejemplo:
```json
[
    {
      "id": "1",
      "nombre": "Ana Martínez",
      "asignaturas": [
        "Matemáticas",
        "Física"
      ],
      "grupo": "1º A"
    }
]
```
Aqui registramos los profesores y almacenamos las asignaturas que imparte y que aulas.


Guardias:
Almacena las guardias registradas, con información sobre la hora, profesor asignado, grupo y aula afectados, entre otros detalles importantes.

Ejemplo:
```json
[
    {
      "id": "39b3",
      "fecha_guardia": "2025-03-18",
      "hora": "10:20 - 11:15",
      "profesor_id": "3",
      "grupo": "1",
      "aula": "c",
      "solucion": "xc",
      "alumnos_problematicos": false,
      "registro_firmado": true,
      "dia": "Martes",
      "fecha_creacion": "17/03/2025, 13:35:29",
      "fecha_guardia_formateada": "18/03/2025",
      "sustituto_id": "2"p
    }
]
```

fecha creacion: momento en el que se creo la guardia
fecha_guardia: el dia en el que hay que cubrir la guardia
fecha_guardia_formateada : fecha_guardia formateada al formato español

profesor_id : el profesor que va a faltar
sustituto_id : el profesor que va a cubrir la guardia

registro_firmado : un booleano para marcar el estado de las guardias , false no esta firmada , true si


Futuras implementaciones :

Se puede apreciar que lo que es la "base de datos" esta bastante verde,
si tubieramos el back con laravel podriamos implementar una estructura de tablas
mas sofisticada , lo cual haria nuesto sistema de creacion de guardias mas robusto 
a la hora de introducir datos , por ejemplo autorrellenando campos con informacion que es obvia
, en lugar de como es acutalmnente , que son campos en los que el usuario introduce el texto a mano
y puede generar errores e inconcluencias.

## CONCLUSIONES ✔

Hemos enfocado el punto fuerte del proyecto en crear una interfaz ligera y que agrada a primera vista al usuario
, que muestra bastante informacion a un solo golpe de vista y da una sensacion moderna , que por lo general 
en aplicaciones de este estilo , se suele cuidar menos este aspecto , lo cual puede llegar a hacer perder interes 
en el usuario y que prefiera usar el sistema antiguo (hoja de papel). 

Nuestra interfaz es facil de usar tanto en pc como en movil , centrando el foco en las guardias a cubrir del dia actual , o en defecto si es fin de semana
del lunes. Aun asi , en el mismo vistazo podemos comprobar el estado de las demas guardias sin ampliar los demas dias o con un solo click ampliamos otro dia. 

Por ultimo añadimos un selector de semanas sencillo , que se selecciona automaticamente dependiendo de la hora actual del navegador 



Al haber utilizado vue y tailwind , seria muy facil modificar lo que mostramos en la pagina , tanto como estilo , como funcionalidad, 
este es el motivo por que el que hemos puesto bastante esfuerzo en el diseño en lugar de añadir mas funcionalidad, dada la estructura de nuestro programa 
y los frameworks que utilizamos , podriamos añadirla mas tarde sin problema , mostrando en esta version del producto todo el potencial que puede llegar a tener 
y asi destacar sobre los demas proyectos.

Se podria implementar facilmente:

**-Login y acceso por usuarios** (administradores , moderadores , usuario, invitado)
**-Filtrado de las guardias por profesores** , dia , hora etc... Ya que es facil mostrarlos con VUE modificando nuestros componentes
**-Editar el estilo ,a partir de la funcionalidad que añadimos a la pagina** , seria mas facil gracias a la fusion de tailwind + vue
-Actualmente la pagina esta pensada para ofrecer una vista para PC/tablet y otra para smartphones , pero con tailwind podemos **añadir responsividad muy facilmente**

En resumen creemos que tenemos una estructura bastante robusta y lo mas importante escalable , en funcion de lo que queramos implementar en un futuro, en caso de que fuera necesario y 
en su defecto tenemos una aplicacion que aunque simple , no deja de ser funcional y lo mas importante , agradable al usuario.





