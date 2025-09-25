# Opción 3: Netlify Functions + Base de datos

## Crear función serverless:
```javascript
// netlify/functions/contact.js
exports.handler = async (event, context) => {
    if (event.httpMethod !== 'POST') {
        return { statusCode: 405, body: 'Method Not Allowed' };
    }
    
    const { name, email, subject, message } = JSON.parse(event.body);
    
    // Aquí puedes:
    // 1. Guardar en Airtable, Google Sheets, o base de datos
    // 2. Enviar email con Nodemailer
    // 3. Enviar a Discord webhook
    
    return {
        statusCode: 200,
        body: JSON.stringify({ success: true })
    };
};
```

**Ventajas**:
✅ Control total
✅ Puedes guardar en base de datos
✅ Gratis en Netlify
✅ Envío de emails personalizados