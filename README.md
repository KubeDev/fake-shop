# Fake Shop

## Sistema de Gerenciamento de Produtos e Vendas

É sistema de gerenciamento de produtos e vendas utilizando **Docker** e **Kubernetes**. O ambiente conta com balanceamento de carga, serviços e deploy automatizado, além de gerenciamento de versões e rollback. A **DigitalOcean** foi utilizada como provedor de nuvem para a hospedagem e gerenciamento do cluster Kubernetes. 

---

## Descrição
### Aplicação

![Interface da aplicação](image-1.png)
![Fluxo da aplicação](image.png)

### Cluster Kubernetes na DigitalOcean

![Configuração do cluster](image-3.png)

### IP, Nodes e Pods criados no Kubernetes

![Detalhes dos nodes e pods](image-2.png)

---

## Variáveis de Ambiente

Para configurar o ambiente corretamente, defina as seguintes variáveis:

| Variável        | Descrição |
|----------------|-----------|
| `DB_HOST`      | Host do banco de dados PostgreSQL. |
| `DB_USER`      | Nome do usuário do banco de dados PostgreSQL. |
| `DB_PASSWORD`  | Senha do usuário do banco de dados PostgreSQL. |
| `DB_NAME`      | Nome do banco de dados PostgreSQL. |
| `DB_PORT`      | Porta de conexão com o banco de dados PostgreSQL. |

---

## Tecnologias Utilizadas
- **Docker** para containerização dos serviços.
- **Kubernetes** para orquestração dos contêineres.
- **PostgreSQL** como banco de dados.
- **DigitalOcean** como provedor de infraestrutura.
- **Load Balancer** para distribuir o tráfego entre os pods.

# Instruções de Deploy  

## 1. Instalar Dependências  
Antes de começar, certifique-se de ter instalado os seguintes componentes:  
- `kubectl`  
- `k3d` (opcional, caso queira rodar um cluster local)  
- `Docker`  

## 2. Criar um Cluster Kubernetes  
Você pode criar um cluster de duas formas:  
1. **Localmente**, utilizando `k3d`, `k3s`, `minikube` ou outra ferramenta.  
2. **Na nuvem**, através de serviços como AWS EKS, Google GKE ou Azure AKS.

Se optar por um cluster local com k3d: 
```sh
k3d cluster create --servers 3 --agents 3 -p "5000:30000@loadbalancer"
```
Se optar por um cluster na nuvem, será necessário atualizar o arquivo de configuração do `kubectl`:  
```sh
cd ~/.kube/
code config  # Abre o arquivo no VS Code (substitua 'code' pelo editor de sua preferência)
```


Este projeto oferece uma solução escalável e confiável para gerenciamento de produtos e vendas, facilitando a implantação e o gerenciamento contínuo da aplicação.

