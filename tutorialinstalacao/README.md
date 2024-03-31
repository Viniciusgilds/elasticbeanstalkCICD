## Criando primeiro fluxo de CI/CD

https://github.com/Viniciusgilds/elasticbeanstalkCICD/blob/main/tutorialinstalacao/Projeto%20beanstalk.png

# 1 Baixe o repositorio do GitHub 
``
git clone Viniciusgilds/elasticbeanstalkCICD
``
# 2 Criando aplicação no Beanstalk

- Ambiente de servidor web
- Escolha um nome para a aplicação
- Escolha um nome para o ambiente (bia-youtube)
- No dominio pode ser o mesmo nome do ambiente
- Plataforma Docker
- Instância única
 
Passo 2 
- Criar e usar um novo perfil de serviço
- Crie uma função no IAM com o nome da politica de `AWSElasticBeanstalkWebTier` e escolha essa função 

Passo 3 
- Escolha VPC padrão 
- Adicione as AZ para ela e ative o IP público

Passo 4 

- Crie ou adicione o SG, com as permissões HTTP porta 80 permitindo todo trafego
- Escolha a instância T3-Medium

# 3 Configurando CodePipeline

Passo 1
- Nome:bia-pipeline-youtube
- Modo de execução: substituida

Passo 2 

- Conecte-se no seu Github com os arquivos já salvos lá 
- Escolha seu repositorio
- Campo trigger escolha nenhum filtro
- Na proxima aba de compilação pule está etapa
- Adicionar etapa de implantação coloque ElasticBeanstalk e escolha o nome do aplicativo que colocou no ElasticBeanstalk