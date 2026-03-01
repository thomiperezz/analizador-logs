# 🔍 Analizador de Logs de Autenticación (Bash)

Script en Bash para analizar logs de autenticación de Linux (`/var/log/auth.log`) y detectar intentos de fuerza bruta por SSH, generando un reporte con IPs sospechosas y número de intentos fallidos.

## 🎯 Objetivo

Automatizar la detección de posibles ataques de fuerza bruta en servidores Linux, facilitando la identificación temprana de amenazas y reduciendo el tiempo de análisis manual.

## 🛠️ Tecnologías utilizadas

- Bash scripting
- Linux (Ubuntu/Debian, CentOS/RHEL)
- Herramientas estándar: `grep`, `awk`, `sort`, `uniq`

## 📋 Requisitos previos

- Sistema Linux con logs de autenticación (generalmente en `/var/log/auth.log` o `/var/log/secure`)
- Permisos de lectura sobre los archivos de log
- Bash 4.0 o superior

## ⚙️ Instalación

1. Clona este repositorio:
   ```bash
   git clone https://github.com/thomiperezz/analizador-logs.git
   cd analizador-logs
Dale permisos de ejecución al script:

bash
chmod +x analizador.sh
🚀 Uso
Ejecuta el script pasando como argumento la ruta al archivo de log:

bash
./analizador.sh /var/log/auth.log
Opcionalmente, puedes especificar un umbral de intentos fallidos (por defecto 10):

bash
./analizador.sh /var/log/auth.log 5
📄 Ejemplo de salida
text
=== REPORTE DE INTENTOS DE FUERZA BRUTA ===
Fecha del análisis: 2026-03-01 15:30
Archivo analizado: /var/log/auth.log
Umbral de alerta: 10 intentos fallidos

IPs sospechosas (con más de 10 intentos fallidos):
192.168.1.100: 23 intentos
10.0.0.50: 15 intentos

Total de intentos fallidos (todas las IPs): 157
🔮 Próximas mejoras
Enviar alertas por correo electrónico

Generar reporte en formato HTML

Integración con herramientas de SIEM (ej. Wazuh)

Análisis de logs comprimidos rotados

👤 Autor
Creado por Thomi como parte de mi formación en administración de sistemas y ciberseguridad.
Contacto: perezthomas17@hotmail.com | https://www.linkedin.com/in/thperez17/

📝 Notas
Este script es educativo y está diseñado para entornos controlados. Ajusta los umbrales según las necesidades de tu servidor.
