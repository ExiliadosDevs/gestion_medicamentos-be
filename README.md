# gestion_medicamentos-be

## Tecnologías utilizadas

- **Java 23**
- **Spring Boot 3**
- **Spring Data JPA**
- **Spring Security** (si aplica)
- **Hibernate**
- **MySQL** (Alojado en Railway)
- **Maven**
- **Git y GitHub**

---

##  Cómo configurar y ejecutar el backend

###  1. Clonar el repositorio
Ejecuta el siguiente comando en la terminal:
```bash
git clone https://github.com/ExiliadosDevs/gestion_medicamentos-be.git
```

###  2. Acceder al directorio del proyecto
```bash
cd gestion_medicamentos-be
```

###  3. Configurar la base de datos en Railway
El backend usa una base de datos en **Railway**. Para conectarse, se deben configurar las variables de entorno.

#### **Opción 1: Usar variables de entorno en el sistema**
Configura las siguientes variables en tu sistema operativo:
```bash
export MySQL_MYSQL_URL="jdbc:mysql://TU_HOST/TU_BASE_DE_DATOS"
export MySQL_USER="TU_USUARIO"
export MySQL_PASSWORD="TU_CONTRASEÑA"
```
*(En Windows, usa `set` en lugar de `export`)*

#### **Opción 2: Usar un archivo `.env`**
Si prefieres manejar las credenciales en un archivo, crea un archivo **`.env`** en la raíz del proyecto con el siguiente contenido:
```
MySQL_MYSQL_URL=jdbc:mysql://TU_HOST/TU_BASE_DE_DATOS
MySQL_USER=TU_USUARIO
MySQL_PASSWORD=TU_CONTRASEÑA
```
Luego, asegúrate de que `application.properties` las use así:
```properties
spring.datasource.url=${MySQL_MYSQL_URL}
spring.datasource.username=${MySQL_USER}
spring.datasource.password=${MySQL_PASSWORD}
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
spring.jpa.database-platform=org.hibernate.dialect.MySQL8Dialect
spring.jpa.hibernate.ddl-auto=update
```

### 📌 4. Instalar dependencias
Ejecuta el siguiente comando para descargar las dependencias necesarias:
```bash
mvn clean install
```

### 📌 5. Ejecutar el backend
Para iniciar el backend con **Maven**, usa:
```bash
mvn spring-boot:run
```

## Para mi lo recomendable seria usar la opcion 1 para la base de datos, para poder usarla en tiempo real, pero pues hay estan las dos opciones

