# Traktera

Traccar ad hoc — fork del back-end de [Traccar](https://www.traccar.org) con personalización propia.

## Estructura

- `traccar/` — back-end Java (servidor Traccar). Ver su [README](traccar/README.md).
- `traccar/traccar-web/` — front-end (React + Vite) incluido como directorio normal del repo.

## Requisitos

- **Java 21** (obligatorio, `sourceCompatibility = 21`)
- Gradle wrapper incluido (`./gradlew`), no hace falta instalar Gradle
- Para el front-end: Node.js 18+ y npm

## Configuración local (no se commitea)

`traccar/gradle.properties` está en `.gitignore` para que cada desarrollador ponga ahí sus rutas y flags locales, por ejemplo:

```properties
org.gradle.java.home=K:/descargas_generales/jdk_21/jdk-21.0.12.1
```

Alternativa recomendada: definir `JAVA_HOME` en el sistema y no usar `org.gradle.java.home`.

## Compilar y ejecutar (back-end)

```shell
cd traccar
./gradlew build          # Linux/macOS
gradlew.bat build        # Windows
```

Para desarrollo rápido, Traccar usa `debug.xml` como configuración por defecto en el IDE; ajusta ahí tu base de datos.

### Docker (alternativa rápida con MySQL)

```shell
cd traccar
docker compose -f docker/compose/traccar-mysql.yaml up -d
```

Traccar queda disponible en `http://localhost:8082`.

## Front-end

```shell
cd traccar/traccar-web
npm install
npm start
```

## Notas del fork

- `traccar-web` ya NO es un git submodule: es parte del repositorio.
- No commitear rutas locales (`org.gradle.java.home` va en `gradle.properties` ignorado por git).
