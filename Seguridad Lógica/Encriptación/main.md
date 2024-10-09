# Encriptación: Cifrado Simétrico y Asimétrico

## Cifrado Simétrico

### ¿Cómo funciona?
- **Clave única**: El cifrado simétrico utiliza una única clave tanto para cifrar como para descifrar la información. 
- La misma clave convierte los datos legibles (texto claro) en texto cifrado, y luego convierte el texto cifrado de nuevo en texto claro.
  
### Proceso:
1. El remitente usa una **clave secreta** para cifrar el mensaje.
2. El mensaje cifrado se envía al destinatario.
3. El destinatario utiliza **la misma clave** para descifrar el mensaje y obtener el texto original.

### Ejemplo:
- Si Alice quiere enviar un mensaje a Bob, ambos deben compartir previamente una clave secreta. Alice cifra el mensaje con esa clave, lo envía a Bob, y Bob lo descifra con la misma clave.
  
### Ventajas:
- **Rápido y eficiente**: Adecuado para encriptar grandes volúmenes de datos.
  
### Desventajas:
- **Distribución de claves**: La clave debe ser compartida de forma segura entre las partes antes de que pueda usarse, lo que genera vulnerabilidades si la clave se compromete.

### Ejemplos de Algoritmos:
- **AES** (Advanced Encryption Standard)
- **DES** (Data Encryption Standard)
- **RC4** (Rivest Cipher 4)


## Cifrado Asimétrico

### ¿Cómo funciona?
- **Par de claves**: El cifrado asimétrico utiliza dos claves relacionadas matemáticamente: una **clave pública** y una **clave privada**.
  - **Clave pública**: Se utiliza para cifrar los datos.
  - **Clave privada**: Se utiliza para descifrar los datos.
  
### Proceso:
1. El remitente obtiene la **clave pública** del destinatario.
2. Usa la clave pública para cifrar el mensaje.
3. El destinatario, con su **clave privada**, descifra el mensaje.

### Ejemplo:
- Si Alice quiere enviar un mensaje a Bob, Alice utiliza la **clave pública** de Bob para cifrar el mensaje. Cuando Bob recibe el mensaje, usa su **clave privada** para descifrarlo.

### Ventajas:
- **No es necesario intercambiar la clave privada**: Solo la clave pública se comparte, por lo que el proceso es más seguro.
  
### Desventajas:
- **Más lento**: El cifrado asimétrico es más lento y consume más recursos que el cifrado simétrico.

### Ejemplos de Algoritmos:
- **RSA** (Rivest-Shamir-Adleman)
- **ECC** (Elliptic Curve Cryptography)
- **DSA** (Digital Signature Algorithm)


## Cifrado Híbrido (Simétrico con Clave Pública)

### ¿Cómo funciona?
- **Mezcla lo mejor de ambos**: Se usa el cifrado asimétrico para intercambiar de forma segura una clave simétrica y luego se utiliza esa clave simétrica para el resto de la comunicación.
  
### Proceso:
1. El remitente genera una **clave simétrica** para cifrar los datos.
2. Usa el **cifrado asimétrico** (clave pública del destinatario) para cifrar esa clave simétrica.
3. Envía la clave simétrica cifrada junto con los datos cifrados.
4. El destinatario usa su **clave privada** para descifrar la clave simétrica.
5. Con la clave simétrica, descifra los datos.

### Ejemplo:
- En **HTTPS**, un servidor y un navegador usan un cifrado asimétrico para intercambiar una clave de sesión simétrica, que luego se usa para cifrar el resto de la comunicación.

### Ventajas:
- **Rápido y seguro**: Combina la seguridad del cifrado asimétrico para el intercambio de claves con la rapidez del cifrado simétrico para el intercambio de datos.

## Cifrado con Clave Envolvente (Wrapped-Key Encryption)

### ¿Cómo funciona?
- El concepto de **wrapped-key** consiste en utilizar una clave para cifrar otra clave. Este enfoque suele aplicarse en sistemas donde se manejan múltiples claves para diferentes propósitos.
  
### Proceso:
1. Se genera una **clave de datos** (clave simétrica) que se utilizará para cifrar la información sensible.
2. Esta clave de datos se cifra utilizando una **clave de envoltura** (puede ser simétrica o asimétrica).
3. El resultado es una clave de datos cifrada (wrapped key) que se almacena o transfiere de forma segura.
4. Para descifrar la información, primero se descifra la clave de datos usando la clave de envoltura, y luego se utiliza la clave de datos para descifrar los datos originales.

### Ejemplo:
- En sistemas de almacenamiento en la nube, los datos se cifran con una **clave simétrica**, y esa clave simétrica es cifrada con una **clave pública** del destinatario o sistema seguro.
  
### Beneficios:
- **Seguridad adicional**: Protege la clave de datos al envolverla en otra capa de cifrado.
- **Gestión de claves**: Permite una mejor administración de claves en entornos donde múltiples claves simétricas se usan para cifrar diferentes partes de los datos.

### Ejemplos de Uso:
- **Hardware Security Modules (HSM)**: Utilizan el cifrado de claves envolventes para proteger las claves de datos en hardware dedicado.
- **Gestión de Claves en Infraestructuras de Clave Pública (PKI)**: Utilizan claves envolventes para asegurar claves de sesión simétricas en sistemas de comunicación seguros.

### Ventajas:
- **Mayor seguridad**: La clave simétrica está protegida mediante un cifrado adicional.
- **Escalabilidad**: Facilita la distribución y protección de claves simétricas en sistemas de gran escala.

### Desventajas:
- **Complejidad**: Requiere más pasos en el proceso de cifrado y descifrado, lo que puede agregar complejidad.

## Certificados Digitales

### ¿Qué son los certificados digitales?
- Un **certificado digital** es un documento electrónico que vincula una **clave pública** con la identidad de una persona o entidad.
- Este certificado es emitido y firmado por una **Autoridad de Certificación (CA)**, que garantiza que la clave pública pertenece realmente a esa persona o entidad.
  
### ¿Cómo funcionan?
1. **Creación del certificado**:
   - Una entidad (como una empresa o individuo) genera un par de claves: una **clave pública** y una **clave privada**.
   - La clave pública se incluye en una solicitud de certificado (CSR) que se envía a una **Autoridad de Certificación (CA)**.
   - La CA verifica la identidad de la entidad y emite un **certificado digital** que incluye la clave pública de esa entidad.
   
2. **Uso del certificado**:
   - Cuando alguien envía un mensaje cifrado con la **clave pública** de esa entidad, solo el propietario de la **clave privada** puede descifrarlo, garantizando que el mensaje solo puede ser leído por el destinatario correcto.
   - Además, el emisor puede firmar digitalmente el mensaje con su **clave privada**. Los receptores pueden verificar la autenticidad del mensaje usando la **clave pública** del certificado digital para comprobar la firma.

3. **Verificación de la identidad**:
   - Si alguien recibe un mensaje firmado digitalmente, puede verificar la autenticidad de la firma usando la clave pública del certificado del remitente.
   - La verificación confirma que el mensaje fue enviado por la persona o entidad propietaria del certificado y que no ha sido alterado en el camino.

### Componentes de un certificado digital:
- **Clave pública**: La clave utilizada para verificar firmas y cifrar mensajes.
- **Identidad del propietario**: Información sobre la persona o entidad dueña de la clave pública (nombre, dirección, etc.).
- **Firma de la Autoridad de Certificación (CA)**: Confirma que el certificado es legítimo y ha sido emitido por una CA confiable.
- **Fecha de expiración**: Los certificados tienen un tiempo de validez limitado, después del cual deben ser renovados.

### Ejemplo de uso:
- **HTTPS**: Cuando visitas un sitio web seguro (https://), tu navegador recibe el certificado digital del sitio. Este certificado contiene la clave pública del servidor. Luego, tu navegador utiliza esta clave pública para establecer una conexión cifrada con el servidor y verificar que estás conectando al servidor legítimo y no a un impostor.

### ¿Qué garantiza un certificado digital?
- **Autenticidad**: Garantiza que la información que se recibe proviene de la persona o entidad indicada.
- **Integridad**: Asegura que el mensaje o datos no han sido alterados durante el tránsito.
- **No repudio**: El remitente no puede negar haber enviado el mensaje, ya que está firmado digitalmente con su clave privada.

### Ejemplos de Certificados:
- **Certificado SSL/TLS**: Utilizados en sitios web para asegurar las conexiones (HTTPS).
- **Certificado de Firma Digital**: Usado para firmar documentos y asegurar su autenticidad.
- **Certificados de Email (S/MIME)**: Usados para cifrar correos electrónicos y asegurar su procedencia.

### Ventajas:
- **Confianza**: Permiten a las partes confiar en la identidad del remitente y en la seguridad de la comunicación.
- **Seguridad**: Protegen contra ataques de suplantación de identidad (phishing) y aseguran que los mensajes no sean modificados en tránsito.

### Desventajas:
- **Coste**: Obtener certificados de confianza de una CA puede ser costoso.
- **Gestión de Certificados**: Las organizaciones deben gestionar múltiples certificados y asegurarse de renovarlos antes de su expiración.


