# Спринт 2
## Часть 2
### Развертывание приложения 
1. Заходим на мастер-сервер "k8s-master"
```console
ssh ubuntu@<ip_addr>
```
2. Клонируем репазиторий 
```console
git clone git@github.com:vggalkin/Helm-charts.git
cd Helm-charts/chart
```
3. Правим тэг образа на v1.1.1 в app-chart/values.yaml

```yaml
image:
  repository: gvstudioddnsnet/django-pg-docker:v.1.1.1
  pullPolicy: IfNotPresent
```


 Git Hub
git@github.com:vggalkin/django-pg-docker.git

Docker Hub
gvstudioddnsnet/django-pg-docker
