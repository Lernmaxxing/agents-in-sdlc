---
title: "Lección 12 - Publica el sitio con GitHub Pages"
description: "Usa la aplicación GitHub Copilot para configurar un flujo de trabajo de Pages, revisar su solicitud de cambios y comprobar el Space Quiz publicado."
authors:
  - jamesmontemagno
lastUpdated: 2026-10-12
---

Publica Space Quiz en GitHub Pages para que todo el mundo pueda acceder a él. Copilot puede preparar el flujo de trabajo y guiarte durante la implementación, pero tú eres responsable de revisar los cambios y confirmar que el sitio está disponible.

En esta lección:

- pedirás a Copilot que configure una implementación en GitHub Pages.
- revisarás el flujo de trabajo y la solicitud de cambios antes de combinarla.
- seguirás la implementación y comprobarás el sitio publicado.

## Escenario

Space Quiz ya está en un repositorio de GitHub, pero hace falta una forma sencilla de probarlo. Publicar el sitio de un solo archivo con GitHub Pages permite acceder a él mediante una URL pública sin añadir un servidor ni una dependencia del entorno de ejecución.

## Pide a Copilot que prepare la implementación

> [!WARNING]
> Crear una solicitud de cambios puede confirmar y enviar código. Revisa la configuración de aprobación y el repositorio de destino antes de enviar este prompt. Si está seleccionado **Approve all**, no esperes otro aviso de confirmación.

En la sesión de la aplicación Copilot para `space-quiz`, envía este prompt:

```plaintext
Prepara una implementación de GitHub Pages para este repositorio. Crea un flujo de trabajo de GitHub Actions que compile el sitio web si es necesario y lo implemente en GitHub Pages cuando los cambios lleguen a la rama predeterminada. Añade un README que describa la aplicación y cómo ejecutarla localmente si aún no existe. Crea una solicitud de cambios con estos cambios e indica su enlace y cualquier configuración o permiso de Pages necesario. No combines la solicitud, no habilites la combinación automática, no cambies la configuración de Pages ni implementes el sitio. Detente y espera a que revise los cambios.
```

## Revisa el flujo de trabajo y la solicitud de cambios

1. Confirma que el README solo se ha añadido si el repositorio aún no tenía uno.
2. Revisa los cambios de la solicitud, incluidos los pasos de compilación e implementación del flujo de trabajo, sus activadores y sus permisos.
3. Confirma que el flujo de trabajo implementa desde la rama predeterminada, no desde una solicitud de cambios que aún no se ha combinado.
4. Pide las correcciones necesarias y revisa el diff actualizado. Espera a que se superen las comprobaciones obligatorias de la solicitud antes de autorizar su combinación.

## Autoriza la combinación y la implementación

> [!WARNING]
> El siguiente prompt autoriza al agente a combinar la solicitud de cambios revisada, modificar la configuración de Pages del repositorio y publicar el sitio. Envíalo solo después de revisar los cambios y confirmar el repositorio y la solicitud. Según la configuración de aprobación, estas acciones podrían realizarse sin otro aviso de confirmación.

Sustituye `<PR_NUMBER>` por el número de la solicitud de cambios que has revisado y envía este prompt por separado:

```plaintext
He revisado la solicitud de cambios <PR_NUMBER> de este repositorio y autorizo su combinación e implementación. Habilita GitHub Pages con GitHub Actions, combina esa solicitud solo cuando se superen las comprobaciones obligatorias y supervisa la implementación hasta que termine correctamente. Indica la URL final del sitio web publicado. Si no tienes permiso para habilitar Pages o combinar la solicitud, dime exactamente qué debo aprobar o hacer; no informes de que se ha completado hasta que el sitio esté publicado.
```

![Diagrama de tres fases: una solicitud de cambios de space-quiz combinada; una ejecución correcta de GitHub Actions, Deploy website, con los pasos Build website, Upload artifact y Deploy to Pages; y Space Quiz publicado en yourname.github.io/space-quiz/.](../../../_images/first-steps-app-pages-deploy.svg)

## Comprueba la implementación

1. Sigue la ejecución de implementación de GitHub Actions hasta que termine correctamente.
2. Abre la URL indicada y confirma que se carga Space Quiz.

Si el agente no puede habilitar Pages o combinar la solicitud de cambios, sigue las instrucciones concretas que te proporcione. No des la tarea por terminada hasta que la implementación se complete y el sitio publicado se cargue.

## Resumen y siguientes pasos

Space Quiz ya está disponible como sitio web y has comprobado la implementación en lugar de confiar únicamente en el informe del agente. Continúa con la [lección 13: Repaso y próximos pasos][next-lesson].

[next-lesson]: ../13-review/
