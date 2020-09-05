# Desfio Dock- Cloud Security

> Status do desafio: Concluido

## Descrição do Seviço

Foi criado uma Stack com uma Instancia Ec2(dockEC2Instance), um Bucket S3(FileRepository), Uma IAM ROLE(RootRole)
com as Policies para dar acesso à gravação e consulta ao Bucket S3.

## Funcionalidades

- O script listaIpsTor é executado a cada hora de acordo com a cron abaixo:
  
  **0 * * * *  /home/listaIpsTor.sh**
  
- Liberando a execução do script abaixo contido no arquivo:

  **now=$(date +"%m-%d-%Y-%H-%M-%S")
    curl https://www.dan.me.uk/tornodes --output /temp/Lista_ips_$now.txt
    aws s3 cp /temp/Lista_ips_$now.txt s3://FileRepository**


 ## Arquivos:
 - listaIpsTor.sh
 - cloudformation.yaml
