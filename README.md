# Testeo-login-Giraldes-Pezzo

Login con Google con Firebase:

Acá en el README se va a explicar como implementar el login con Google usando Firebase

Paso 1: Creando el proyecto en Firebase

. Ingresá a firebase.google.com e iniciá sesión con tu cuenta de Google
. . Hacé clic en "Agregar proyecto"
. . . Poné un nombre, desactivá Google Analytics si no lo necesitás, y creá el proyecto
. . . . Una vez adentro, hacé clic en el ícono </> (Web) para registrar tu app
. . . . . Poné un nombre para la app y hacé clic en "Registrar app"
. . . . . . Firebase te va a mostrar un bloque de código con tu firebaseConfig. Copialo, lo vas a necesitar después



Paso 2 — Activar el login con Google

Dentro del proyecto de Firebase:

En el menú, entrá a Authentication
Hacé clic en "Comenzar" si es la primera vez
Andá a la pestaña "Sign-in method"
Buscá Google en la lista y hací clic
Activalo con el toggle, elegí un correo de soporte y guardá


Paso 3 — Agregar tu dominio

Esto es necesario para que Firebase acepte solicitudes desde tu página.

En Authentication, andá a la pestaña "Settings"
Buscá la sección "Authorized domains"
Si vas a subir la página a un hosting, agregá tu dominio ahí (por ejemplo miapp.netlify.app)
Si solo vas a probar en tu computadora, localhost ya está habilitado por defecto, no hace falta tocarlo


Paso 4 — Pegar la configuración en el código

Abrí el archivo index.html y buscá esta parte:

jsconst firebaseConfig = {
    apiKey: "...",
    authDomain: "...",
    projectId: "...",
};

Reemplazala con el bloque que copiaste en el Paso 1. Cada proyecto de Firebase tiene su propia configuración, así que no uses la de otro.


Paso 5 — Abrir la página

No hace falta ningún servidor especial. Podés:


Abrir el index.html directamente en el navegador (doble clic) para probar
Subir el archivo a cualquier hosting estático: Netlify, Vercel, GitHub Pages, etc.


Si lo abrís como archivo local (file://...), el popup de Google puede bloquearse en algunos navegadores. Lo más cómodo para probar es usar la extensión Live Server de VS Code.


inicio sesión:

- El usuario hace clic en el botón
- Se abre un popup con la pantalla de Google
- El usuario elige su cuenta
- Google le avisa a Firebase que el usuario es válido
- Firebase guarda la sesión en el navegador
- La página muestra automáticamente el nombre, correo y foto


La siguiente vez, al ingresar basicamente Firebase recuerda la sesión y lo muestra directo sin necesidad de clickear de nuevo
