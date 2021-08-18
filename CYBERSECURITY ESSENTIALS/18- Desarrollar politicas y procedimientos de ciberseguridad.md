## Escenario:

ACME Healthcare es una empresa de atención médica que administra más de 25 instalaciones médicas que incluyen atención 
al paciente, diagnóstico, atención ambulatoria y atención de emergencia. La organización ha experimentado varias 
filtraciones de datos en los últimos cinco años. Estas filtraciones de datos le han costado financieramente a la 
organización y han dañado su reputación.
El equipo de liderazgo ejecutivo contrató recientemente a un nuevo director de seguridad de la información (CISO). El
nuevo CISO ha contratado a uno de los mejores equipos de penetración de ciberseguridad para realizar una auditoría de 
seguridad completa en toda la organización. Este contratista independiente realizó la auditoría y encontró las 
siguientes vulnerabilidades:

1) Se identificaron varias cuentas para empleados que ya no son empleados de ACME.
2) Varias cuentas de usuario permitieron privilegios no autorizados y escalados. Estas cuentas accedieron a sistemas e 
información sin autorización formal.
3) Varios dispositivos y sistemas permitieron el acceso remoto no seguro.
4) El cuarenta por ciento de todas las contraseñas de organizaciones auditadas se descifraron en 6 horas.
5) No se estandarizó la caducidad de la contraseña.
6) Se encontraron archivos confidenciales sin cifrar en los dispositivos de los usuarios.
7) Varios puntos de acceso inalámbricos usaban WEP para el cifrado y la autenticación.
8) La evidencia indica que se envió correo electrónico confidencial hacia y desde los hogares y dispositivos móviles de
los empleados sin encriptación.
9) Los registros de detección de intrusos se revisaban y analizaban con poca frecuencia.
10) Los dispositivos con datos confidenciales de la empresa fueron utilizados por empleados para uso privado.
11) Los dispositivos de los empleados se dejaron desatendidos y los empleados no cerraron la sesión de la red y los 
sistemas de datos de la empresa.
12) Se realizaron actualizaciones y configuraciones de dispositivos inconsistentes.
13) Se establecieron varias reglas de firewall para permitir todo el tráfico a menos que se niegue específicamente.
14) Los servidores de la empresa no se actualizaron con los últimos parches.
15) El servidor web de la intranet permitía a los usuarios cambiar su información personal, incluida la información de 
contacto.

## Parte 1: Revisión del Escenario

Lea el escenario dado arriba. Mire el video de la Política de seguridad de la información. Tome notas que le ayuden a 
diferenciar los distintos niveles y tipos de pólizas.

## Parte 2: Revisar y priorizar los hallazgos de la auditoría

a) Investigue los tipos de vulnerabilidades enumeradas para determinar cuál de ellas representa la mayor amenaza. Vaya 
a Principales vulnerabilidades de seguridad informática para obtener más información.
b) Según su investigación, enumere los cinco principales hallazgos de auditoría de seguridad que ACME debe abordar, 
comenzando con la mayor vulnerabilidad.
c) Registre sus clasificaciones en una tabla de clasificación de vulnerabilidades, como la que se muestra a 
continuación. Enumera las vulnerabilidades, la política recomendada para mitigar esta vulnerabilidad y su 
justificación para la clasificación que determinó.

Tabla de clasificación de vulnerabilidades

    1) Vulnerabilidad:
    Se identificaron varias cuentas para empleados que ya no están empleados por ACME.

    Política recomendada:
    Cuando un empleado deja la empresa:
    • Revisar todos los permisos de acceso
    • Recuperar datos del empleado si corresponde
    • Terminar el acceso y restablecer todas las contraseñas

    Justificación:
    El exempleado puede obtener acceso no autorizado a información y equipos de propiedad y confidenciales.
    Cualquier persona con las credenciales del ex empleado puede obtener acceso no autorizado al sistema interno.
    
    ---------------------------------------------------------------------

    2) Vulnerabilidad:
    Varias cuentas de usuario permitieron privilegios no autorizados y escalados y accedieron a sistemas e información 
    sin autorización formal.
    
    Política recomendada:
    • Asignar el privilegio mínimo para realizar la tarea
    • Registrar cuando se usan privilegios elevados
    
    Justificación:
    El privilegio mínimo le permite al usuario realizar todas las tareas necesarias sin el riesgo de causar cambios 
    sistémicos sin querer.

    ---------------------------------------------------------------------

    3) Vulnerabilidad:
    Varios dispositivos y sistemas permitieron el acceso remoto no seguro.
    
    Política recomendada:
    • Deshabilite el acceso remoto no seguro, como Telnet
    • Requerir acceso remoto seguro, como SSH y VPN
    
    Justificación:
    El acceso remoto no seguro transmite los datos en texto sin formato. La transmisión de texto sin formato puede exponer 
    información confidencial, como las credenciales de los usuarios, para que los actores maliciosos realicen 
    reconocimientos y ataques.

    ---------------------------------------------------------------------

    4) Vulnerabilidad:
    El cuarenta por ciento de todas las contraseñas de organizaciones auditadas se descifraron en 6 horas.
    
    Política recomendada:
    Nueva política de contraseñas:
    • Implementar 2FA o MFA
    • Contraseñas de usuario
    • Cambie las contraseñas solo después de evidencia de compromiso
    • Sin reutilización de contraseñas antiguas
    • Sin reutilización de contraseñas en diferentes aplicaciones
    • Habilitar copiar/pegar contraseñas
    • Educar a los usuarios sobre ciberseguridad básica
    
    Justificación:
    Cuando se descifran las contraseñas, el atacante puede obtener acceso no autorizado y cambiar las contraseñas para 
    bloquear a los usuarios autorizados.

    ---------------------------------------------------------------------

    5) Vulnerabilidad:
    Varios puntos de acceso inalámbricos usaban WEP para el cifrado y la autenticación.
    
    Política recomendada:
    Actualice los puntos de acceso inalámbricos al cifrado y la autenticación más seguros disponibles
    
    Justificación:
    WEP es propenso a ataques de intermediarios y la clave se descifra fácilmente y es difícil de distribuir a los usuarios.

    ---------------------------------------------------------------------

    6) Vulnerabilidad:
    Los servidores de la empresa no se actualizaron con los últimos parches.
    
    Política recomendada:
    Establezca un plan para actualizar/probar los últimos parches a intervalos regulares.
    
    Justificación:
    La actualización regular puede proteger los datos, corregir la vulnerabilidad de seguridad y mejorar la estabilidad 
    del sistema operativo y las aplicaciones.



