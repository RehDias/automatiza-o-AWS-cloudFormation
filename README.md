#  Implementando uma Infraestrutura Automatizada com AWS CloudFormation

Projeto desenvolvido durante o curso **Computação em Nuvem com AWS** da **DIO (Digital Innovation One)** em parceria com o **Santander Code Girls - 2025**.

---

##  Sobre o Projeto

Este projeto teve como objetivo compreender e aplicar o conceito de **Infrastructure as Code (IaC)** utilizando o **AWS CloudFormation** para **automatizar a criação de infraestrutura na nuvem**.

A proposta foi criar uma Stack que provisiona recursos de forma **declarativa e reprodutível**, sem a necessidade de configuração manual, e entender as diferenças entre o **CloudFormation** e o **Terraform**, duas das principais ferramentas de IaC do mercado.

---

##  O que é o AWS CloudFormation

O **AWS CloudFormation** é um serviço que permite **definir, provisionar e gerenciar recursos da AWS por meio de templates** escritos em **YAML ou JSON**.

Esses templates descrevem toda a infraestrutura desejada (como instâncias EC2, buckets S3, bancos de dados, funções Lambda, entre outros), e o CloudFormation executa automaticamente a criação e configuração desses recursos de forma segura e ordenada.

Em outras palavras: você **descreve a infraestrutura como código** e a AWS faz o resto.

---

##  Por que usar Infrastructure as Code (IaC)

-  **Automação:** cria e atualiza recursos de forma consistente.  
-  **Reutilização:** os templates podem ser versionados e replicados em outros ambientes.  
-  **Padronização:** reduz erros e garante ambientes idênticos em produção e testes.  
-  **Agilidade:** provisiona rapidamente infraestrutura completa com poucos comandos.

---

##  Passo a Passo: Criando uma Stack no AWS CloudFormation

A seguir, um passo a passo simples para criar sua primeira infraestrutura automatizada com o CloudFormation.

### 1️ Acessar o serviço
- No console da AWS, busque por **CloudFormation** e clique no serviço.

### 2️ Criar uma nova Stack
- Clique em **Create stack** → **With new resources (standard)**.

### 3️ Definir o template
- Escolha a opção **Upload a template file** e envie seu arquivo **.yaml** ou **.json**.  
  Exemplo simples em YAML:


  ```json
  {
    "AWSTemplateFormatVersion": "2010-09-09",
    "Description": "Criação automatizada de um bucket S3",
    "Resources": {
      "MeuBucketS3": {
        "Type": "AWS::S3::Bucket",
        "Properties": {
          "BucketName": "meu-bucket-cloudformation-exemplo"
        }
      }
    }
  }

### 4️ Configurar detalhes da Stack

* Dê um nome à Stack (ex: `InfraAutomatizadaStack`).
* Adicione parâmetros, tags ou permissões, se necessário.

### 5️ Revisar e criar

* Verifique as configurações e clique em **Create stack**.
* O CloudFormation criará automaticamente os recursos definidos no template.

### 6️ Monitorar a criação

* Acompanhe o progresso da criação em **Events**.
* Quando o status mostrar **CREATE_COMPLETE**, sua infraestrutura estará pronta.

### 7️ Atualizar ou deletar

* Para atualizar a infraestrutura, envie um novo template.
* Para remover, selecione a Stack e clique em **Delete** — todos os recursos serão excluídos automaticamente.

---

##  Diferença entre AWS CloudFormation e Terraform

| Característica                | **AWS CloudFormation**           | **Terraform**                                        |
| ----------------------------- | -------------------------------- | ---------------------------------------------------- |
| **Provedor**                  | Exclusivo da AWS                 | Multicloud (AWS, Azure, GCP, etc.)                   |
| **Linguagem**                 | YAML ou JSON                     | HCL (HashiCorp Configuration Language)               |
| **Gerenciamento de Estado**   | Automático e interno da AWS      | Requer arquivo de estado (`terraform.tfstate`)       |
| **Execução**                  | Realizada dentro da AWS          | Realizada localmente ou via Terraform Cloud          |
| **Velocidade de atualização** | Depende da AWS                   | Mais flexível para alterações                        |
| **Facilidade de uso**         | Simples para quem usa apenas AWS | Mais poderoso e abrangente para múltiplos provedores |

 **Em resumo:**

* Use **CloudFormation** se você trabalha **somente com AWS** e quer simplicidade e integração nativa.
* Use **Terraform** se você precisa de **flexibilidade, controle detalhado e integração com múltiplas nuvens**.

---

##  Insights Aprendidos

Durante o desenvolvimento deste projeto, foi possível compreender que:

* A **automação de infraestrutura** reduz erros humanos e aumenta a eficiência;
* O uso de **IaC** torna o ambiente previsível e fácil de replicar;
* O **CloudFormation** é ideal para automatizar recursos da AWS de forma nativa;
* Entender a diferença entre CloudFormation e Terraform é essencial para escolher a ferramenta ideal conforme o contexto do projeto.

---

##  Conclusão

O uso do **AWS CloudFormation** permite implementar infraestruturas seguras, escaláveis e automatizadas com poucos comandos.
Essa prática reforça a importância do **Infrastructure as Code (IaC)** no desenvolvimento moderno, promovendo **agilidade, controle e padronização** na criação de ambientes em nuvem.
