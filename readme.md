
Este arquivo `docker-compose.yml` configura uma infraestrutura **100% open source** que integra serviços como WordPress, MariaDB, Redis, Prometheus, Grafana e Zabbix. A solução é modular, permitindo expansões e personalizações de forma eficiente.

#### **Serviços Configurados**

1. **WordPress**
    
    - CMS (Sistema de Gerenciamento de Conteúdo) para criação e gestão de sites.
    - Conecta-se ao MariaDB como banco de dados e ao Redis para caching.
2. **MariaDB**
    
    - Banco de dados relacional utilizado pelo WordPress.
    - Configurado com credenciais seguras e persistência.
3. **Redis**
    
    - Utilizado como sistema de cache para otimizar o desempenho do WordPress.
4. **MySQL (mysql-zabbix)**
    
    - Banco de dados exclusivo para o Zabbix Server.
    - Já configurado para suportar os dados do Zabbix.
5. **Prometheus**
    
    - Ferramenta de monitoramento para coletar métricas dos serviços.
    - Pronta para integração com novos serviços.
6. **Grafana**
    
    - Interface gráfica para análise e visualização de métricas.
    - Integração básica com Prometheus configurada.
7. **Zabbix Server e Web**
    
    - Plataforma de monitoramento completa para coleta de dados e alertas.
    - Configurado com MySQL e interface web acessível.

---

### Passos para Utilizar

#### **Pré-requisitos**

- **Docker** e **Docker Compose** instalados no sistema.

#### **Como Iniciar os Serviços**

1. Suba os serviços com o comando:
```
    
    `docker-compose up -d`
    
   ``` 
2. Acessos aos serviços:
    
    - **WordPress:** [http://localhost:8081](http://localhost:8081)
    - **Zabbix Web:** [http://localhost:8085](http://localhost:8085)
    - **Grafana:** http://localhost:3000  
        Usuário: `admin`  
        Senha: `admin`
    - **Prometheus:** http://localhost:9090
3. **Volumes persistentes:**  
    Os dados de todos os serviços são armazenados em volumes, garantindo que não sejam perdidos em reinicializações.
    

---

### Próximos Passos

1. **Integração de Métricas**
    
    - Configurar o Prometheus para coletar métricas do Zabbix e do WordPress.
    - Criar dashboards personalizados no Grafana.
2. **Segurança**
    
    - Adicionar suporte a **HTTPS** nos serviços, utilizando certificados SSL.
    - Revisar e fortalecer credenciais de serviços (WordPress, Zabbix e Grafana).
3. **Alertas Automatizados**
    
    - Configurar alertas no Prometheus para enviar notificações via **e-mail**, **Slack** ou **Microsoft Teams**.
    - Criar templates de alertas no Zabbix.
4. **Otimização de Recursos**
    
    - Ajustar alocação de CPU e memória para melhorar o desempenho e reduzir consumo.
5. **Centralização de Logs**
    
    - Adicionar uma solução como **ELK Stack** (Elasticsearch, Logstash e Kibana) para gerenciar logs de todos os serviços.
6. **Expansão para Produção**
    
    - Migrar para uma solução de orquestração como **Kubernetes**.
    - Configurar backups automáticos para bancos de dados.
7. **Automação com CI/CD**
    
    - Integrar com ferramentas como **Jenkins** para automatizar deploys e atualizações de serviços.

---

### Conclusão

Esta infraestrutura foi projetada para ser **modular**, **escalável** e **open source**, facilitando seu uso em ambientes de desenvolvimento e produção. Pode ser facilmente utilizada como base para construir projetos mais robustos, mantendo simplicidade e flexibilidade.

Caso tenha dúvidas ou sugestões, utilize este projeto como ponto de partida para sua própria solução ou contribua com melhorias!