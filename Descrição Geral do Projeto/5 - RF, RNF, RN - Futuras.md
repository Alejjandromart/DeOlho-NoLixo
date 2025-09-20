## 🚧 Requisitos para Próximas Versões

<br>

> **Atenção:**  
> Os requisitos listados a seguir correspondem a **funcionalidades previstas, em análise ou prototipação**, planejadas para versões futuras do aplicativo DeOlho NoLixo – Citizen Waste Monitoring App.  
> Eles **não fazem parte da versão atual** do sistema, sendo apresentados aqui exclusivamente para fins de documentação de evolução do projeto e registro acadêmico.


Os requisitos abaixo seguem a formatação oficial do projeto para RF (Requisito Funcional), RNF (Requisito Não Funcional) e RN (Regra de Negócio), e visam nortear o planejamento futuro, a documentação e análises de impacto decorrentes da evolução do **DeOlho NoLixo**.

<br>

---

<br>

### Futuros Requisitos Funcionais (RF)

| **Id** | **Descrição**                                                                                                                                                     | **Prioridade** | **Pré-condição**                               | **Pós-condição**                                  | **Testável**                               |
| ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------- | ---------------------------------------------- | ------------------------------------------------- | ------------------------------------------ |
| RF-H17 | O usuário poderá anexar vídeos curtos (até 30s) junto às fotos na denúncia.                                                                                       | Média          | Função de denúncia ativa e permissão de câmera | Vídeo anexado à denúncia                          | Sim, testar upload e visualização de vídeo |
| RF-H18 | O app deve permitir acompanhamento do horário do caminhão de coleta seletiva, caso haja integração municipal.                                                     | Média          | Localização habilitada e integração ativa      | Usuário visualiza horários e próximos itinerários | Sim, teste com integração real             |
| RF-H19 | O app deve oferecer painel de estatísticas pessoais, informando histórico de denúncias feitas, resolvidas e o impacto ambiental gerado pelo usuário.              | Baixa          | Usuário autenticado                            | Painel de estatísticas atualizado no perfil       | Sim, conferir dados no perfil              |
| RF-H20 | O usuário poderá cadastrar e sugerir pontos públicos de coleta voluntária (ex: eletrônicos, recicláveis), incluindo endereço, foto e validação pela comunidade.   | Média          | Usuário autenticado                            | Sugestão de ponto novo entra em moderação         | Sim, cadastro e validação em fluxo real    |
| RF-H21 | O app deve permitir salvamento automático de rascunhos de denúncias em edição, garantindo que nenhuma informação seja perdida por queda de conexão ou aplicativo. | Baixa          | Usuário em processo de preenchimento           | Dados do rascunho salvos no dispositivo           | Sim, simular interrupção e recuperação     |

<br>

---
<br>

### Futuros Requisitos Não Funcionais (RNF)

|**Id**|**Descrição**|**Categoria**|**Prioridade**|**Testável / Verificável**|
|---|---|---|---|---|
|RNF-H17|Vídeos anexados devem ser automaticamente comprimidos para upload eficiente em redes lentas (3G/4G).|Desempenho/Usabilidade|Alta|Sim, medir tempo de upload|
|RNF-H18|Consultas de horários de coleta devem funcionar mesmo com conexão instável, utilizando cache de dados locais.|Desempenho/Confiabilidade|Alta|Sim, testar offline/falha de Internet|
|RNF-H19|Estatísticas pessoais devem ser protegidas por autenticação forte e transmitidas apenas via canal seguro (HTTPS).|Segurança|Alta|Sim, análise de tráfego de rede|
|RNF-H20|Points de coleta sugeridos devem permitir anexar fotos em alta resolução, mas com limite de 8MB por arquivo.|Usabilidade/Compatib.|Média|Sim, tentar uploads acima do permitido|
|RNF-H21|Salvamento automático de rascunho deve ocorrer a cada 30 segundos de edição e antes de qualquer transição de tela.|Usabilidade/Desempenho|Alta|Sim, monitoramento no fluxo de uso|

<br>

---
<br>

### Futuras Regras de Negócio (RN)

| **Id** | **Descrição**                                                                                                                     | **Prioridade** |
| ------ | --------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| RN-H17 | Cada denúncia pode ter, além das fotos, um único vídeo de até 30 segundos em formato .mp4 ou .mov.                                | Alta           |
| RN-H18 | Horários exibidos de coleta são sincronizados oficialmente por convênio municipal e devem ser atualizados diariamente.            | Alta           |
| RN-H19 | Estatísticas no painel pessoal só contabilizam denúncias efetivamente públicas e confirmadas por moderação.                       | Média          |
| RN-H20 | Pontos de coleta sugeridos ficam visíveis só após aprovação por votação de, no mínimo, 3 usuários distintos ou moderação interna. | Média          |
| RN-H21 | Rascunhos de denúncias ficam armazenados localmente por até 15 dias; após esse prazo, são removidos automaticamente.              | Baixa          |
