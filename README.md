# Ansible
## ![Ansible Logo]

# Estudio del Módulo get_url en Ansible

## 1. Nombre del módulo: get_url

### Descripción
El módulo `get_url` de Ansible se utiliza para descargar archivos desde una URL y guardarlos en un destino específico en el nodo remoto. Es útil cuando se necesita obtener archivos desde servidores web, repositorios o cualquier fuente accesible mediante HTTP o HTTPS.

Este módulo permite definir el destino del archivo, validar su integridad mediante `checksum`, manejar autenticación en URLs protegidas y configurar permisos sobre el archivo descargado.

---

## 2. Ejemplos de funcionamiento

### Ejemplo 1: Descargar un archivo público
Este playbook descarga un archivo desde una URL pública y lo guarda en el directorio `/tmp`.

```yaml
- name: Descargar un archivo público
  hosts: servidores
  tasks:
    - name: Descargar un archivo desde una URL pública
      ansible.builtin.get_url:
        url: https://example.com/archivo.tar.gz
        dest: /tmp/archivo.tar.gz
```

### Ejemplo 2: Descargar un archivo con autenticación
Este playbook descarga un archivo desde una URL que requiere autenticación básica.

```yaml
- name: Descargar un archivo con autenticación
  hosts: servidores
  tasks:
    - name: Obtener un archivo con usuario y contraseña
      ansible.builtin.get_url:
        url: https://secure.example.com/privado.zip
        dest: /opt/privado.zip
        username: usuario
        password: contraseña
```

### Ejemplo 3: Descargar un archivo y verificar su checksum
Este playbook asegura que el archivo descargado coincide con un hash específico.

```yaml
- name: Descargar un archivo con verificación de integridad
  hosts: servidores
  tasks:
    - name: Descargar y validar un archivo con checksum
      ansible.builtin.get_url:
        url: https://example.com/software.deb
        dest: /usr/local/src/software.deb
        checksum: sha256:3a7bd3a6b7d4f3b56e5f4e634f1837c5d4d8e3b6e5a2f4c6f5b6e7f6d9a4b3c2
```

---

## 3. Referencias
- [Documentación oficial del módulo get_url](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/get_url_module.html)
- [Guía de Ansible](https://docs.ansible.com/ansible/latest/user_guide/index.html)

---

## Capturas
(Aquí debes agregar capturas del playbook ejecutándose y del resultado obtenido en el nodo remoto)

