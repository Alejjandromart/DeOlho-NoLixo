## Visão Geral do Diagrama de Casos de Uso

O sistema **DeOlho NoLixo** foi modelado para apoiar o monitoramento cidadão de descarte irregular de lixo, com funcionalidades que abrangem desde a **denúncia**, **processamento por inteligência artificial**, atualização de status, **comunicação externa com órgãos responsáveis** e interação em **feed social** com comentários e curtidas. 

O conjunto dos **diagramas mostra como usuários, o sistema e entidades externas (órgãos) interagem para registrar, processar, consultar e encaminhar denúncias**, promovendo um fluxo transparente e orientado à ação para o combate ao descarte irregular de resíduos.

---

### 1. **Diagrama de Visão Geral**

<img width="13104" height="5826" alt="Visão Geral" src="https://github.com/user-attachments/assets/412de091-2140-40c0-9ecc-a9873d875cae" />

- **Atores Principais:** Usuário (cidadão), Sistema, Sistema de IA, Órgão Responsável.
- **Principais Casos de Uso:**
    - **Criação e envio de denúncia:** Inclui anexar foto, localização, categoria e descrição.
    - **Processamento por IA:** Análise de texto e imagem, classificação do tipo de resíduo e impacto ambiental, validação e geração de tags automáticas.
    - **Atualização de status:** O sistema pode alterar o status de uma denúncia (por ex.: recebida, em análise, solucionada).
    - **Comunicação externa:** Gerar e enviar e-mails a órgãos responsáveis.
    - **Gestão de perfil/autenticação:** Login, cadastro, edição de perfil, visualização de histórico.
    - **Acessos a detalhes da denúncia:** Visualizar detalhes, histórico, status, fotos, mapa, comentários, relatórios de problemas.
<br>

---

### 2. **Criação de Denúncia**

<img width="4405" height="2205" alt="Criação de Denúncia" src="https://github.com/user-attachments/assets/8eae84c1-686b-4fc6-b4cf-4d7bd7ecc813" />

- **Atores:** Usuário
- **Casos de Uso Chave:**
    - Criar denúncia: centraliza as ações para iniciar um novo registro.
    - Salvar rascunho: permite guardar uma denúncia incompleta.
    - Enviar denúncia: finaliza e envia a denúncia registrada.
    - **Subprocessos obrigatórios/possíveis:** Capturar/selecionar foto, adicionar localização, escolher categoria, adicionar descrição.
- **Relações:** O usuário executa todos os casos; os subprocessos são inclusos na criação da denúncia, tornando modular e flexível o cadastro.
<br>

---

### 3. **Detalhe da Denúncia**

<img width="4105" height="2055" alt="Detalhe da Denúncia" src="https://github.com/user-attachments/assets/08f9a8a1-9201-40f7-9d36-978e614d1cd7" />

- **Atores:** Usuário.
- **Casos de Uso Principais:**
    - Visualizar status e detalhes da denúncia; inclui visualizar fotos e localização no mapa.
    - Adicionar comentário/mensagem.
    - Reportar problemas (sobre denúncias mal preenchidas, spam, etc.).
- **Organização:** Os casos ligados à visualização detalhada incluem outros mais específicos, como visualização de fotos e de localização, promovendo clareza na jornada do usuário por diferentes níveis de informação.
<br>

---

### 4. **Atualização de Status**

<img width="1820" height="1455" alt="Atualização de Status" src="https://github.com/user-attachments/assets/ee977e51-2a41-4f59-ac38-28de7dd7989c" />

- **Atores:** Sistema.
- **Caso de Uso:** Atualizar o status de uma denúncia ao longo do processo (por ex.: aguardando, em análise, resolvido). O sistema pode disparar essas atualizações automaticamente (por regras) ou mediante ações de operadores.
<br>

---

### 5. **Feed de Denúncia**

<img width="4105" height="2555" alt="Feed de Denúncia" src="https://github.com/user-attachments/assets/399fc5b7-649d-43e7-a42d-c74b4a9585ff" />

- **Atores:** Usuário.
- **Casos de Uso:**
    - Visualizar feed de denúncias, filtrar denúncias conforme critérios (categoria, status, etc.).
    - Curtir, comentar, buscar e compartilhar denúncias.
- **Relações:** O feed apoia a interação social e transparência. O usuário pode filtrar o feed, e cada denúncia pode receber comentários, curtidas e ser compartilhada.
<br>

---

### 6. **Comunicação Externa**

<img width="2595" height="2960" alt="Comunicação Externa" src="https://github.com/user-attachments/assets/918312f8-98fa-4bb5-9e93-aec61ac5d97d" />

- **Atores:** Usuário, Órgão Responsável.
- **Fluxo:** O usuário ou sistema seleciona o órgão competente, gera o corpo do e-mail padronizado e envia a mensagem para o órgão responsável tomar providências — tudo encapsulado como “Comunicação Externa”.
- **Notas:** Esse processo pode ser iniciado automaticamente pelo app ou pelo próprio usuário.
<br>

---

### 7. **Processamento de IA**

<img width="3655" height="3005" alt="Processamento de IA" src="https://github.com/user-attachments/assets/e2618eb2-6826-4e7b-ac75-7bfc0d7a8bd5" />

- **Ator:** Sistema de IA.
- **Processos:**
    - Análise de texto: extração de informações e geração de tags automáticas, classificação do tipo de resíduo.
    - Processamento de imagem: classificação de impacto ambiental.
    - Classificações são validadas em fluxo recursivo.

- **Resultado:** O subsistema de IA aprimora o registro das denúncias, sugere categorias e avalia gravidade, acelerando resposta e triagem pelos órgãos competentes.
<br>
