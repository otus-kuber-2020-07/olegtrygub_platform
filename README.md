# Выполнено ДЗ № 1

 - [x] Основное ДЗ
 - [x] Задание со *

## В процессе сделано:
 - установил kubectl, minikube
 - создал dockerfile описывающий контейнер с nginx как требовалось в ДЗ, запушил в dockerhub
 - запушил frontend image в dockerhub

## Почему все pod в namespace kube-system восстановились после удаления:
- Все pods кроме coredns это statis pods, которые контролируются kubelet. coredns же работает как обычный deployment: \

```
$ kubectl get deployments -n kube-system
```

## Выясните причину, по которой pod frontend находится в статусе Error
 - Команда 
 ```
$ kubectl logs frontend
```
показывает, что сервис требует различные переменные окружения, например: 
```
❯ kubectl logs frontend
{"message":"Tracing enabled.","severity":"info","timestamp":"2020-11-11T21:18:41.242188684Z"}
{"message":"Profiling enabled.","severity":"info","timestamp":"2020-11-11T21:18:41.242673925Z"}
panic: environment variable "CURRENCY_SERVICE_ADDR" not set

goroutine 1 [running]:
main.mustMapEnv(0xc000394018, 0xb18330, 0x15)
        /src/main.go:259 +0x10b
main.main()
        /src/main.go:118 +0x53a
```
 Я скопировал их из примера, приведенного по ссылку.

## PR checklist:
 - [x] Выставлен label с темой домашнего задания
