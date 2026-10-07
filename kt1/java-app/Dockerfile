# Образ с JDK 21
FROM eclipse-temurin:21-jdk

WORKDIR /app

# Скачиваем JDBC-драйвер PostgreSQL
RUN apt-get update \
    && apt-get install -y --no-install-recommends curl ca-certificates \
    && curl -L -o postgresql.jar https://jdbc.postgresql.org/download/postgresql-42.7.3.jar \
    && apt-get purge -y curl \
    && apt-get autoremove -y \
    && rm -rf /var/lib/apt/lists/*

# Копируем исходник и компилируем
COPY App.java .
RUN javac -cp postgresql.jar App.java

# Запускаем
CMD ["java", "-cp", ".:postgresql.jar", "App"]