# PilarBus

PilarBus es una aplicación móvil y web que permite a los ciudadanos de Pilar consultar el recorrido de los colectivos en tiempo real. Su objetivo es evitar la incertidumbre de la espera en la parada: además de mostrar las unidades en un mapa, la plataforma notificará los desvíos, se integrará con SUBE y contará con un sistema de reclamos para los usuarios.

El proyecto se desarrolla para el Segundo Parcial de Fundamentos del Desarrollo de Software y Metodologías Ágiles (UNPilar, Comisión 03).

## Metodología de trabajo

El equipo trabaja con Scrum, en sprints de dos semanas. Dado que las funcionalidades se ajustan según los comentarios semanales de los usuarios beta, el backlog se revisa y se reordena en cada sprint. El seguimiento de las tareas se realiza en un tablero de Trello con tres columnas (To Do, In Progress y Done). La columna In Progress tiene un límite de 3 tareas simultáneas, de modo que se termine el trabajo en curso antes de iniciar uno nuevo. Cada tarea cuenta con su estimación en Story Points.

## Flujo de cambios

La rama `main` debe mantenerse siempre estable, por lo que no se realizan cambios directamente sobre ella. Cada tarea se desarrolla en una rama propia (por ejemplo, `feature/mapa-colectivos`) y, al finalizar, se abre un Pull Request hacia `main`. Para poder integrarlo, otro miembro del equipo debe revisarlo y deben aprobarse los chequeos automáticos. Este procedimiento mejora la calidad del código, permite que todo el equipo conozca cómo está construido el sistema y deja registro de cada modificación y su motivo.

## Integración y entrega continua (CI/CD)

La validación automática se realiza con GitHub Actions, mediante el archivo `.github/workflows/ci.yml`. Cada vez que se abre un Pull Request, el sistema compila el proyecto (build) y ejecuta las pruebas (test). Si alguna de estas etapas falla, el Pull Request no puede integrarse, lo que permite detectar errores en pocos minutos sin depender de pruebas manuales.

Una vez que el Pull Request se integra a `main` y todas las validaciones resultan exitosas, el mismo pipeline ejecuta el despliegue (deploy) en la nube. Este se realiza de forma gradual (rolling update), actualizando una instancia por vez, de modo que la aplicación continúe disponible para los pasajeros durante la actualización.

## Equipo

- Isabel León (Product Owner)
- Martina Gaitan (Scrum Master)
- Mia Bustos (Developer)
