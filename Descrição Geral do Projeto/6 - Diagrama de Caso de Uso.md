## Visão Geral do Diagrama de Casos de Uso

O sistema **DeOlho NoLixo** foi modelado para apoiar o monitoramento cidadão de descarte irregular de lixo, com funcionalidades que abrangem desde a **denúncia**, **processamento por inteligência artificial**, atualização de status, **comunicação externa com órgãos responsáveis** e interação em **feed social** com comentários e curtidas. 

O conjunto dos **diagramas mostra como usuários, o sistema e entidades externas (órgãos) interagem para registrar, processar, consultar e encaminhar denúncias**, promovendo um fluxo transparente e orientado à ação para o combate ao descarte irregular de resíduos.

---

### 1. **Diagrama de Visão Geral**

<img width="16384" height="8297" alt="Visão Geral" src="https://github.com/user-attachments/assets/b5c795f3-b153-4572-849f-6173c6dab2ee" />

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

<img width="4405" height="2205" alt="Criação de Denúncia" src="https://github.com/user-attachments/assets/76103e3b-300f-43d1-8325-cb1a3f642c2f" />

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

<img width="4105" height="2055" alt="Detalhe da Denúncia" src="https://github.com/user-attachments/assets/b7d884ed-401f-4ac5-b24c-2d54c393b0c6" />

- **Atores:** Usuário.
- **Casos de Uso Principais:**
    - Visualizar status e detalhes da denúncia; inclui visualizar fotos e localização no mapa.
    - Adicionar comentário/mensagem.
    - Reportar problemas (sobre denúncias mal preenchidas, spam, etc.).
- **Organização:** Os casos ligados à visualização detalhada incluem outros mais específicos, como visualização de fotos e de localização, promovendo clareza na jornada do usuário por diferentes níveis de informação.
<br>

---

### 4. **Atualização de Status**

<img width="1545" height="1155" alt="Atualização de Status" src="https://github.com/user-attachments/assets/c2e0ecc3-d354-47a8-af2d-4132b6111c7a" />

- **Atores:** Sistema.
- **Caso de Uso:** Atualizar o status de uma denúncia ao longo do processo (por ex.: aguardando, em análise, resolvido). O sistema pode disparar essas atualizações automaticamente (por regras) ou mediante ações de operadores.
<br>

---

### 5. **Feed de Denúncia**

<img width="4130" height="2555" alt="Feed de Denúncia" src="https://github.com/user-attachments/assets/fbb66dcf-14d5-4776-8eeb-25568dd6d6f8" />

- **Atores:** Usuário.
- **Casos de Uso:**
    - Visualizar feed de denúncias, filtrar denúncias conforme critérios (categoria, status, etc.).
    - Curtir, comentar, buscar e compartilhar denúncias.
- **Relações:** O feed apoia a interação social e transparência. O usuário pode filtrar o feed, e cada denúncia pode receber comentários, curtidas e ser compartilhada.
<br>

---

### 6. **Comunicação Externa**

<img width="2615" height="2960" alt="Comunicação Externa" src="https://github.com/user-attachments/assets/97e79158-6e11-4597-8984-ce00dd2fac17" />

- **Atores:** Usuário, Órgão Responsável.
- **Fluxo:** O usuário ou sistema seleciona o órgão competente, gera o corpo do e-mail padronizado e envia a mensagem para o órgão responsável tomar providências — tudo encapsulado como “Comunicação Externa”.
- **Notas:** Esse processo pode ser iniciado automaticamente pelo app ou pelo próprio usuário.
<br>

---

### 7. **Processamento de IA**

<img width="3120" height="3005" alt="Processamento de IA" src="https://github.com/user-attachments/assets/7d096532-0ced-41ca-a741-f398e06def1a" />

- **Ator:** Sistema de IA.
- **Processos:**
    - Análise de texto: extração de informações, classificação do tipo de resíduo.
    - Processamento de imagem: classificação de impacto ambiental.
    - Classificações são validadas em fluxo recursivo.

- **Resultado:** O subsistema de IA aprimora o registro das denúncias, sugere categorias e avalia gravidade, acelerando resposta e triagem pelos órgãos competentes.
<br>


