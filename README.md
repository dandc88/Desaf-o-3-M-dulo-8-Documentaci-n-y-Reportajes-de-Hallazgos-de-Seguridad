# 🔒 Desafío 3 – Módulo 8: Documentación y Reportajes de Hallazgos de Seguridad

Este repositorio contiene el informe técnico elaborado como parte del curso **Seguridad en Redes de Datos – Módulo 8**, enfocado en la **documentación de hallazgos de seguridad y propuestas de mitigación**.

---

## 📖 Descripción del Caso

La empresa ficticia **TechSecure** solicitó evaluar la seguridad de su infraestructura de red, con especial atención en un **servidor Linux clave**.  
Se realizó una prueba de ataque **Man-in-the-Middle (MitM) mediante ARP Spoofing** con el objetivo de identificar vulnerabilidades y documentar las posibles contramedidas.

---

## 🛠️ Procedimiento del Ataque

- **Herramienta utilizada:** Ettercap en Kali Linux.  
- **Pasos principales:**
  1. Activación del reenvío de paquetes (IP Forwarding).
  2. Escaneo de la red interna (**labnet**) para identificar máquinas activas.
  3. Selección de objetivos: cliente Windows (192.168.1.107) y servidor Ubuntu (192.168.1.108).
  4. Ejecución del ataque de **ARP Spoofing**, logrando interceptar el tráfico entre ambos.

---

## 🧾 Evidencias

- **Servidor Ubuntu:** La tabla ARP (`ip neigh`) muestra la suplantación de la MAC del cliente.  
- **Cliente Windows:** La salida de `arp -a` refleja la suplantación de la MAC del servidor.  
- Ambas pruebas demuestran que el atacante (Kali) se ubicó exitosamente en medio de la comunicación.

---

## 🛡️ Contramedidas Recomendadas

1. **Firewall restrictivo:** Configurar `ufw` o `iptables` para permitir solo tráfico autorizado.  
2. **ARP estático:** Registrar manualmente entradas ARP en dispositivos críticos.  
3. **Port Security en switches:** Asociar MACs específicas a puertos para evitar suplantaciones.  
4. **Cifrado extremo a extremo:** Implementar **HTTPS/SSL/TLS** para proteger datos sensibles.

---

## ✅ Conclusiones

- La red de TechSecure es vulnerable a **ARP Spoofing**, demostrando la importancia de complementar la seguridad perimetral con controles a nivel de host.  
- Las contramedidas propuestas reducen significativamente el riesgo de ataques similares.  
- Se comprobó la necesidad de integrar **firewalls, segmentación, seguridad en switches y cifrado de tráfico** como parte de la estrategia de defensa.

---

## 📂 Contenido del Repositorio

- 📄 `Informe_Seguridad_TechSecure.pdf` → Informe completo con pruebas y conclusiones.  
- 🖼️ Capturas de pantalla → Evidencias de la ejecución del ataque y resultados en cliente/servidor.  

---

## 👨‍💻 Autor

**Daniel Dávila**  
Curso: *Seguridad en Redes de Datos – G3*  
Fecha: *28-08-2025*  
