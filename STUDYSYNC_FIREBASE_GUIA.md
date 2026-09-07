# StudySync — Firebase + GitHub

## 1. Firebase
1. Crea un proyecto en Firebase Console.
2. Registra una aplicación Web.
3. Copia el `firebaseConfig` que Firebase te entrega y reemplaza los valores `REEMPLAZAR_...` en `index.html`.
4. En Authentication > Sign-in method, activa Email/Password.
5. En Firestore Database, crea la base de datos.
6. Publica las reglas de `firestore.rules`.

## 2. Estructura de datos
Cada usuario queda separado por su UID:
users/{uid}
  tasks/{taskId}
  notes/{noteId}
  pet/main

La app solo consulta/escribe la ruta del usuario autenticado.

## 3. GitHub
Sube `index.html`, `firebase.json` y `firestore.rules` al repositorio.
Puedes probar primero abriendo `index.html` localmente, pero Firebase Authentication/Firestore funcionan mejor al servir la web por HTTP/HTTPS.

## 4. Firebase Hosting (recomendado)
Instala Firebase CLI y, desde la carpeta del proyecto:
firebase login
firebase init hosting
firebase deploy --only hosting

Si usas la configuración incluida, revisa que el directorio público sea el directorio donde está `index.html`.

## 5. GitHub Pages
También puedes publicar `index.html` con GitHub Pages. Si lo haces, añade el dominio de tu GitHub Pages en Firebase Authentication > Settings > Authorized domains.

## 6. Importante
El `firebaseConfig` de una app web no es una contraseña. La protección real de los datos viene de Authentication + Firestore Security Rules. No publiques claves privadas de cuentas de servicio ni archivos de credenciales.
