# Code Guardian

**Code Guardian** es una skill para Claude Code enfocada en revisar la salud técnica de un repositorio antes de modificarlo.

Su objetivo es ayudar a trabajar con más control, seguridad y trazabilidad, especialmente en proyectos donde no se quiere que el agente modifique demasiados archivos sin explicar qué va a tocar y por qué.

## Propósito

Code Guardian revisa un repositorio y genera un diagnóstico claro sobre:

- estructura del proyecto;
- archivos importantes faltantes;
- riesgos de seguridad;
- posibles secretos expuestos;
- dependencias sospechosas o innecesarias;
- documentación faltante;
- consistencia con ADRs;
- cambios pendientes en Git;
- riesgos antes de ejecutar tareas;
- alcance recomendado para próximos cambios.

## Principio principal

> Code Guardian no modifica archivos por defecto.

Primero analiza, luego reporta, y solo sugiere cambios pequeños y controlados.

## Instalación local

Para guardar la skill como colección personal:

```powershell
mkdir "D:\Aplicaciones\Skills"
cd "D:\Aplicaciones\Skills"
```

Copiá esta carpeta completa:

```text
code-guardian
```

Para usarla dentro de un proyecto con Claude Code, copiá únicamente esta carpeta:

```text
code-guardian\skills\code-guardian
```

hacia:

```text
TU_PROYECTO\.claude\skills\code-guardian
```

Ejemplo para Nebulosa:

```powershell
mkdir "D:\Aplicaciones\Nebulosa\.claude\skills"
xcopy "D:\Aplicaciones\Skills\code-guardian\skills\code-guardian" "D:\Aplicaciones\Nebulosa\.claude\skills\code-guardian" /E /I
```

## Estructura

```text
code-guardian/
  README.md
  LICENSE
  CHANGELOG.md
  skills/
    code-guardian/
      SKILL.md
  docs/
    usage.md
    checklist.md
    publishing-notes.md
  examples/
    basic-report.md
    security-report.md
    pre-change-report.md
```

## Cuándo usarla

Usá Code Guardian cuando querás:

- revisar un repo antes de pedir cambios;
- detectar riesgos antes de instalar dependencias;
- revisar si un proyecto tiene buena estructura inicial;
- validar que Claude Code no se salga del alcance;
- pedir una revisión de seguridad básica;
- preparar un diagnóstico antes de un commit;
- revisar si un proyecto está listo para publicarse.

## Ejemplos de uso en Claude Code

```text
Use the code-guardian skill to inspect this repository.
Do not modify files.
Return a repository health report grouped by severity.
```

```text
Use code-guardian before this change.
Tell me which files you would inspect, what risks exist, and whether this task should be split.
Do not edit files.
```

```text
Use code-guardian to review security risks before installing any dependency.
Do not install anything.
```

## Filosofía

Code Guardian prioriza:

1. seguridad;
2. claridad;
3. cambios pequeños;
4. evidencia;
5. trazabilidad;
6. mantenibilidad.

## Estado

Versión inicial experimental para uso personal y para el proyecto Nebulosa.
