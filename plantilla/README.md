# Formularios en Netlify

El manejo de formularios serverless de Netlify permite gestionar formularios sin llamadas adicionales a la API o JavaScript adicional. Una vez habilitada, la función de detección de formularios incorporada permite que nuestro sistema de compilación analice automáticamente el HTML en el momento del despliegue, por lo que no es necesario realizar una llamada a la API ni JavaScript adicional incluido en el sitio.

Esta es una opción práctica para incorporar formularios de contacto por ejemplo, en páginas sencillas o portafolios de proyectos.

## Set up Netlify

Para habilitar la detección de formularios en el sitio:

- En la interfaz de usuario de Netlify, ve a Configuración del sitio > Formularios.

- Selecciona Habilitar detección de formularios.

- A partir del próximo despliegue del sitio, Netlify escaneará automáticamente los despliegues en busca de formularios que requieran el manejo de envíos.


![Forms Configuration](/assets/images/form-detection.jpg)


## HTML forms

Agrega el atributo `data-netlify="true"` de Netlify al formulario HTML.


```
<form name="contact" method="POST" data-netlify="true" >
    <label for="name">Nombre:</label>
    <input type="text" id="name" name="name" required>

    <label for="email">Correo Electrónico:</label>
    <input type="email" id="email" name="email" required>

    <button type="submit">Enviar</button>
</form>
```

NOTA: De acuerdo a la documentación de Netlify, es posible agregar el atributo  `netlify` en lugar de `data-netlify="true"` sin embargo presentó errores al enviar la información del formulario


## Form Notifications

Puedes enviar notificaciones para envíos de formularios verificados en Configuración del sitio > Formularios > Notificaciones de formularios. Estas notificaciones pueden enviarse por correo electrónico, webhooks o Slack. En las opciones de configuración, puedes optar por recibir notificaciones para un formulario específico en particular o para todos los envíos verificados de cualquier formulario de tu sitio.


[Documentación en inglés](https://docs.netlify.com/forms/setup/)