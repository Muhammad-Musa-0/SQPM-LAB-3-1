Lab 3-1 Commands

cd ~
git clone https://github.com/Muhammad-Musa-0/SQPM-LAB-3-1/

cd SQPM-LAB-3-1/sqpm_lab3-1/BinaryCalculatorWebapp
mvn package

docker build -t northamerica-northeast2-docker.pkg.dev/lab3-1-453018/sofe3980u/binarycalculator .

docker push northamerica-northeast2-docker.pkg.dev/lab3-1-453018/sofe3980u/binarycalculator

kubectl create deployment binarycalculator-deployment --image northamerica-northeast2-docker.pkg.dev/lab3-1-453018/sofe3980u/binarycalculator --port=8080 

kubectl expose deployment binarycalculator-deployment --type=LoadBalancer --name=binarycalculator-service 

kubectl get service
