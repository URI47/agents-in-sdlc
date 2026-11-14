---
title: "Lección 12 - Publicar el sitio con GitHub Pages"
description: "Usa la aplicación GitHub Copilot para configurar un flujo de trabajo de Pages, revisar su pull request y verificar que Space Quiz está disponible."
authors:
  - jamesmontemagno
lastUpdated: 2026-10-12
---

Publica Space Quiz en GitHub Pages para que todo el mundo pueda acceder al sitio. Copilot puede preparar el flujo de trabajo y guiarte durante la publicación, pero eres responsable de revisar los cambios y confirmar que el sitio está disponible.

En esta lección:

- Pedirás a Copilot que configure la publicación en GitHub Pages.
- Revisarás el flujo de trabajo y el pull request antes de combinarlo.
- Seguirás la publicación y verificarás el sitio publicado.

## Escenario

Space Quiz ya está en un repositorio de GitHub, pero aún hace falta una forma sencilla de probarlo. Publicar el sitio de un solo archivo con GitHub Pages permite acceder a él mediante una URL pública sin añadir un servidor ni una dependencia del entorno de ejecución.

## Pide a Copilot que prepare la publicación

> [!WARNING]
> Crear un pull request puede confirmar y enviar código. Revisa la configuración de aprobación y el repositorio de destino antes de enviar este prompt. Si está seleccionada la opción **Approve all**, no esperes otro mensaje de confirmación.

En la sesión de la aplicación Copilot para `space-quiz`, envía este prompt:

```plaintext
Prepara la publicación de GitHub Pages para este repositorio. Crea un flujo de trabajo de GitHub Actions que compile el sitio web si es necesario y lo publique en GitHub Pages cuando los cambios lleguen a la rama predeterminada. Añade un README que describa la aplicación y cómo ejecutarla localmente si aún no existe. Crea un pull request con estos cambios e indica su enlace y cualquier configuración o permiso de Pages necesario. No combines el pull request, no habilites la combinación automática, no cambies la configuración de Pages ni publiques el sitio. Detente y espera a que revise los cambios.
```

## Revisa el flujo de trabajo y el pull request

1. Confirma que el README solo se añade si el repositorio aún no tiene uno.
2. Revisa los cambios del pull request, incluidos los pasos de compilación y publicación del flujo de trabajo, sus desencadenadores y sus permisos.
3. Confirma que el flujo de trabajo publica desde la rama predeterminada, no desde un pull request sin combinar.
4. Solicita las correcciones necesarias y revisa el diff actualizado. Antes de autorizar la combinación, espera a que pasen las comprobaciones obligatorias del pull request.

## Autoriza la combinación y la publicación

> [!WARNING]
> El siguiente prompt autoriza al agente a combinar el pull request revisado, cambiar la configuración de Pages del repositorio y publicar el sitio. Envíalo solo después de revisar los cambios y confirmar el repositorio y el pull request. La configuración de aprobación puede permitir estas acciones sin otro mensaje de confirmación.

Sustituye `<PR_NUMBER>` por el número del pull request que has revisado y envía este prompt por separado:

```plaintext
He revisado el pull request <PR_NUMBER> de este repositorio y autorizo su combinación y la publicación. Habilita GitHub Pages mediante GitHub Actions, combina únicamente ese pull request después de que pasen las comprobaciones obligatorias y supervisa la publicación hasta que finalice correctamente. Indica la URL final del sitio web publicado. Si no tienes permiso para habilitar Pages o combinar el pull request, dime exactamente qué debo aprobar o hacer; no indiques que se ha publicado correctamente hasta que el sitio esté disponible.
```

![Diagrama en tres etapas: un pull request de space-quiz combinado; una ejecución correcta de Deploy website en GitHub Actions, con los pasos Build website, Upload artifact y Deploy to Pages; y Space Quiz publicado en yourname.github.io/space-quiz/.](../../../_images/first-steps-app-pages-deploy.svg)

## Verifica la publicación

1. Sigue la ejecución de publicación de GitHub Actions hasta que termine correctamente.
2. Abre la URL indicada y confirma que Space Quiz se carga.

Si el agente no puede habilitar Pages o combinar el pull request, sigue las instrucciones específicas que te proporcione. No des la tarea por terminada hasta que la publicación finalice correctamente y el sitio esté disponible.

## Resumen y siguientes pasos

Space Quiz ya está disponible como sitio web y has verificado la publicación en lugar de confiar únicamente en el informe del agente. Continúa con la [lección 13: Revisión y siguientes pasos][next-lesson].

[next-lesson]: ../13-review/
