# Спринт 2
## Часть 2
### Развертывание приложения 
1. Заходим на мастер-сервер "k8s-master"
```console
ssh ubuntu@<ip_addr>
```
2. Клонируем репазиторий 
```console
git clone https://github.com/vggalkin/Helm-charts.git
cd Helm-charts/chart
```
3. Правим тэг образа на v1.1.1 в app-chart/values.yaml

```yaml
image:
  repository: gvstudioddnsnet/django-pg-docker:v1.1.1
  pullPolicy: Always
```
4. Применяем
```console
helm upgrade --install --namespace default --values db-chart/values.yaml mydb db-chart
helm upgrade --install --namespace default --values app-chart/values.yaml myapp app-chart
```
5. Проверяем, что поды развернуты
```console
kubectl get pods
```
6. Проверяем, что приложение доступно по адресу ВМ k8s-worker

![django_site](https://user-images.githubusercontent.com/3630798/197576558-c5cf9b50-e31e-4284-8d0e-456ca3f5f12d.png)

