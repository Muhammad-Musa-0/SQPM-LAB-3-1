#Lab 3-1 Commands#

#Video 1:#

cd ~
git clone https://github.com/Muhammad-Musa-0/SQPM-LAB-3-1/

cd SQPM-LAB-3-1/sqpm_lab3-1/BinaryCalculatorWebapp

mvn package

docker build -t northamerica-northeast2-docker.pkg.dev/lab3-1-453018/sofe3980u/binarycalculator .

docker push northamerica-northeast2-docker.pkg.dev/lab3-1-453018/sofe3980u/binarycalculator

kubectl create deployment binarycalculator-deployment --image northamerica-northeast2-docker.pkg.dev/lab3-1-453018/sofe3980u/binarycalculator --port=8080 

kubectl expose deployment binarycalculator-deployment --type=LoadBalancer --name=binarycalculator-service 

kubectl get service


#Video 2:#

#METHOD 1:#

kubectl create deployment mysql-deployment --image mysql/mysql-server --port=3306 

kubectl expose deployment mysql-deployment --type=LoadBalancer --name=mysql-service 

kubectl get service

mysql -uuser -psofe3980u -h<IP-Address>

kubectl delete deployment mysql-deployment 

kubectl delete service mysql-service 

#METHOD 2:#

git clone https://github.com/Muhammad-Musa-0/SQPM-LAB-3-1/

cd SQPM-LAB-3-1/MySQL

kubectl create -f mysql-service.yaml

kubectl get service

mysql -uuser -psofe3980u -h<IP-Address>

cd SOFE3980U-Lab3-Part1/MySQL

kubectl delete -f mysql-service.yaml
kubectl delete -f mysql-deployment.yaml
