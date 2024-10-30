# aws_emr_ec2_airflow_etl


sudo apt update

sudo apt install docker.io -y

sudo systemctl start docker

sudo usermod -aG docker $ubuntu  # To avoid permission issues

sudo chown ubuntu:docker /var/run/docker.sock

sudo chmod 660 /var/run/docker.sock

curl -LfO 'https://airflow.apache.org/docs/apache-airflow/2.10.2/docker-compose.yaml'


mkdir -p ./dags ./logs ./plugins ./config
echo -e "AIRFLOW_UID=$(id -u)" > .env

docker build -t custom-airflow .
docker run -d -p 8080:8080 custom-airflow

docker build .
docker compose up airflow-init


<img width="942" alt="image" src="https://github.com/user-attachments/assets/d6467e15-5256-4a13-9208-ad759423165c">
