# 🔄 Entity Service Communication 

##### Um ecossistema de dois aplicativos Android (Service e Client) desenvolvido em Kotlin para demonstrar a Comunicação entre Processos (IPC) utilizando a interface AIDL (Android Interface Definition Language).
##### O objetivo principal é permitir que um aplicativo cliente solicite serviços de um aplicativo provedor, executando lógica de negócio (incremento de contador) de forma remota e segura.

##### Este projeto foi criado para fins acadêmicos no contexto da disciplina D2DA2 - Des. Android 2, com foco em:

- Implementação de Bound Services (Serviços Vinculados)
- Definição de contratos de interface via AIDL
- Comunicação entre diferentes processos (Inter-Process Communication - IPC)
- Uso do padrão Stub para conversão de interfaces remotas
- Gerenciamento de ciclo de vida de conexão com ServiceConnection
- Execução de chamadas remotas em Threads secundárias para evitar ANR (App Not Responding)
- Uso de ViewBinding para manipulação da interface do usuário


## 🚀 Funcionalidades

##### ✔️ Comunicação Transparente: O cliente interage com o serviço remoto como se fosse um objeto local.
##### ✔️ Incremento Remoto: O serviço recebe um valor inteiro, realiza o processamento e retorna o resultado incrementado.
##### ✔️ Gerenciamento de Threads: Chamadas ao serviço remoto são encapsuladas em Threads, garantindo a fluidez da UI.
##### ✔️ Sincronização de UI: Uso de runOnUiThread para atualizar a tela do cliente após o retorno do serviço remoto.
##### ✔️ Verificação de Disponibilidade: O cliente detecta e notifica caso o serviço provedor não esteja instalado ou disponível.
##### ✔️ Desvinculação Automática: Gerenciamento eficiente de memória desfazendo o bind do serviço no onDestroy.


## 🛠 Tecnologias Utilizadas
- Kotlin — Linguagem principal
- AIDL — Definição da interface de comunicação entre processos
- Android Services — Componente fundamental para execução em segundo plano
- ViewBinding — Acesso seguro aos elementos de UI
- ServiceConnection — Monitoramento do estado da conexão cliente-servidor
- Threads/Handlers — Gerenciamento de concorrência para chamadas remotas
- Material Design — Interface moderna com Toolbars e botões interativos


## 📸 Estrutura do Projeto

#### 01 - EntityServiceCommunication (Service)

##### O "Servidor" que contém a lógica do IncrementBoundService e expõe a interface .aidl.

#### 02 - EntityServiceCommunicationClient (Client)

##### O "Cliente" que possui a interface visual e se conecta ao serviço remoto para solicitar o incremento.

##### (Dica: Para o funcionamento correto, o aplicativo do Serviço deve estar instalado no dispositivo para que o Cliente consiga localizá-lo)


## ▶️ Como Executar o Projeto

##### 1. Clone os repositórios (Serviço e Cliente):
###### git clone https://github.com/MADS1974/EntityServiceCommunication.git
###### git clone https://github.com/MADS1974/EntityServiceCommunicationClient.git
##### 2. Abra ambos os projetos no Android Studio.
##### 3. Instale primeiro o aplicativo EntityServiceCommunication no emulador ou dispositivo físico.
##### 4. Instale e execute o aplicativo EntityServiceCommunicationClient.
##### 5. No aplicativo Cliente, utilize o botão de incremento para testar a comunicação remota.


#### 📚 Créditos

##### Projeto acadêmico desenvolvido para a disciplina Desenvolvimento para Android 2 – D2DA2, ministrada pelo professor Pedro Northon Nobile (IFSP).

#### 🙋‍♂️ Autor
#### Márcio Adriano

##### 🔗 Conecte-se comigo:
##### LinkedIn - Márcio Adriano

##### Nota Técnica: Este projeto demonstra como o Android utiliza o Binder para realizar a marshalling/unmarshalling de dados entre espaços de memória de aplicativos distintos.
