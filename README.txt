https://nextjs.org/docs/app/getting-started/installation

npx create-next-app@latest

Si a todo, exceptuando a personalizar el alias @ para los import complicados de en rutas relativas:
import Header from '@/components/Header';
Es lo mismo que
import Header from 'src/components/Header';

Eslint es 

Turbopack  es una alternativa más rápida a webpack, para empaquetar, optimizar y gestionar dependencias.
esLINT sirve para solucionar errores en el código (uso de variables no definidas, import o variables no usadas, espaciado incorrecto, 
dependencias en useEffect, problemas de accesibilidad (alt en imágenes, ), incosistencia en proyectos colaborativos)

Librerías instaladas:
react
react-dom (ReactDOM.createPortal, ReactDOM.createRoot)
next

Ahora tenemos que entendero el fichero package.json:
stándar SemVer (Semantic Versioning): MAJOR.MINOR.PATCH
 "version": "0.1.0", => etapa de desarrollo
MAJOR: cambios que pueden romper la funcionalidad existente: 1.0.0 a 2.0.0
 Ejemplo: cambios en los parámetros de una función
MINOR: nuevas funcionalidades que no rompen funcionalidad existente: 1.0.0 a 1.1.0
PATCH: solución de errores: 1.0.0 a 1.0.1

Fase inicial de desarrollo => 0.1.0
Agrego cambios incomaptibles => 1.0.0
Agrego nuevas funcionalidades compatibles => 1.1.0
correcciones de errores => 1.1.1

entonces, si yo le quiero pasar mi proyecto a otro desarrollador, no hace falta que le pase la carpeta node_modules, 
le paso los ficheros package.json y package-lock.json y que el haga un npm install para volver a recrear node modules

Resumiendo, en el repositorio hay que incluir los siguientes ficheros:
package.json
package-lock.json
Ignorar node_modules
.gitignore: node_modules/

Estilos:
https://nextjs.org/docs/pages/building-your-application/optimizing/fonts
https://fonts.google.com/variablefonts

// layout.js
import { Montserrat } from 'next/font/google';
import './globals.css';

const montserrat = Montserrat({
  subsets: ['latin'],
  variable: '--font-montserrat',
});

export default function RootLayout({ children }) {
  return (
    <html lang="en">
      <body>
        {children}
      </body>
    </html>
  );
}

body {
  font-family: var(--font-montserrat), sans-serif;
}

