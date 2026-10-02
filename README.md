# Hola PostCSS

Proyecto de partida para la sesión de **PostCSS**. Es un Vite con TypeScript ya montado, con una página maquetada y **sin PostCSS configurado**: eso lo vamos añadiendo paso a paso.

<br />

## Arrancar

Necesitas [Node.js y npm](https://nodejs.org/en/) (20.19.0 || >=22.12.0), que es lo que pide Vite 8.

> ⚠ Comprueba tu versión con `node -v` y `npm -v`. Versiones anteriores dan error al arrancar.

```bash
npm install
npm run dev
```

Abre **la dirección que muestra el terminal** y deja el proceso encendido mientras trabajas: Vite recarga al guardar.

<br />

## Las piezas

| Fichero | Para qué sirve |
| --- | --- |
| `index.html` | La página que vamos a estilar, con clases BEM. |
| `src/main.ts` | La entrada: solo importa el CSS. Hoy no programamos en TypeScript. |
| `src/css/main.css` | Los estilos: variables, reset y la maquetación. |
| `package.json` | Dependencias y comandos (`dev`, `build`, `preview`). |
| `tsconfig.json` | Configuración de TypeScript. |

Dos cosas de cómo funciona Vite:

- **El CSS entra desde TypeScript.** En `main.ts` hay un `import './css/main.css'`; no hay un `<link>` en el HTML.
- **La carpeta `dist/` no se toca.** La genera el build y no se sube al repositorio.

<br />

## Comandos

| Comando | Qué hace |
| --- | --- |
| `npm run dev` | Servidor de desarrollo con recarga al guardar |
| `npm run build` | Genera `dist/` para producción, minificado |
| `npm run preview` | Sirve `dist/` para probar la build antes de subirla |

Durante la sesión miraremos mucho el CSS que sale del build. Para leerlo sin minificar:

```bash
npm run build -- --minify false
```

El resultado está en `dist/assets/index-xxxx.css`.

<br />

## Antes de empezar

No hace falta instalar nada global: ni PostCSS, ni la CLI de Vite. Todo entra como dependencia del proyecto.

Recomendada la extensión de VS Code **PostCSS Language Support**, para que el editor no marque en rojo sintaxis como `@custom-media` o `@define-mixin`. Es solo cosmético: compila igual.
