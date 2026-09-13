# Kubernetes Hello-World Java Application

Учебный проект по развертыванию Java-приложения в локальном кластере Kubernetes (Minikube).

## Структура проекта
* `Main.java` — HTTP-сервер на чистом Java (`com.sun.net.httpserver`), работающий на порту 32777 и отдающий ответ в кодировке UTF-8.
* `Dockerfile` — двухэтапная (multi-stage) сборка на базе `eclipse-temurin:21`.
* `deployment.yaml` — манифест Kubernetes Deployment с 2 репликами приложения.
* `service.yaml` — манифест Kubernetes Service (тип NodePort) для доступа к подам.

## Инструкция по запуску

1. **Сборка и публикация Docker-образа:**
   ```bash
   docker build -t aseto0/hello-app:v3 .
   docker push aseto0/hello-app:v3
