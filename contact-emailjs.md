# Opción 2: EmailJS

## Pasos:
1. Crear cuenta en [emailjs.com](https://www.emailjs.com/)
2. Configurar un servicio de email (Gmail, Outlook, etc.)
3. Crear una plantilla de email
4. Instalar EmailJS: `npm install emailjs-com`
5. Reemplazar el script del formulario

## Código del script:
```javascript
import emailjs from 'emailjs-com';

form?.addEventListener('submit', async (e) => {
    e.preventDefault();
    
    const formData = new FormData(form);
    const templateParams = {
        from_name: formData.get('name'),
        from_email: formData.get('email'),
        subject: formData.get('subject'),
        message: formData.get('message')
    };
    
    try {
        await emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', templateParams, 'YOUR_PUBLIC_KEY');
        // Mostrar éxito
    } catch (error) {
        // Mostrar error
    }
});
```

**Ventajas**: 
✅ 200 emails gratis/mes
✅ Más personalización
✅ Plantillas de email custom