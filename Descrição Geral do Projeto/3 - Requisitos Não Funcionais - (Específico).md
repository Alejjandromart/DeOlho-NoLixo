## Requisitos Não Funcionais (RNF)

Abaixo estão listados os principais **Requisitos Não Funcionais (RNF)** do projeto **DeOlho NoLixo**. Estes requisitos descrevem restrições de usabilidade, desempenho, segurança e compatibilidade, garantindo a robustez, acessibilidade e qualidade da aplicação.

As colunas **Id**, **Descrição**, **Categoria** e **Prioridade** são obrigatórias. As colunas **Testável** e **Verificável** são opcionais, mas facilitam a validação dos critérios durante o desenvolvimento.

<br>

---

<br>

|**Id**|**Descrição**|**Categoria**|**Prioridade**|**Testável / Verificável**|
|---|---|---|---|---|
|RNF-H4-1|O preview da foto deve ser exibido em tela cheia, com opção de confirmar ou refazer a captura.|Usabilidade|Alta|Sim, inspecionando o comportamento da tela de captura.|
|RNF-H4-2|As fotos devem ser capturadas em formato JPG ou PNG e redimensionadas para reduzir o tamanho do arquivo.|Compatibilidade/Desempenho|Alta|Sim, verificando formato e tamanho do arquivo resultante.|
|RNF-H6-1|O sistema deve bloquear múltiplos cliques repetidos no botão em menos de 2 segundos para evitar spam.|Desempenho/Segurança|Alta|Sim, tentando cliques rápidos sucessivos.|
|RNF-H7-1|O processamento para validar todos os campos deve ocorrer em até 500ms.|Desempenho|Média|Sim, por meio de cronômetro/logs.|
|RNF-H7-2|Deve permitir upload de fotos tanto da câmera quanto da galeria do dispositivo.|Usabilidade|Alta|Sim, testando ambos caminhos (câmera/galeria).|
|RNF-H7-3|O botão de envio deve estar sempre visível ao final do formulário, sem necessidade de rolagem excessiva.|Usabilidade/Acessibilidade|Alta|Sim, verificando posição/visibilidade em telas diversas.|
|RNF-H8-1|O usuário deve ser notificado de forma clara e contínua quando o compartilhamento de localização estiver ativo.|UX/Avisos|Alta|Sim, testando mensagens de status da localização.|
|RNF-H8-2|Em caso de falha de rede, o sistema deve tentar reconectar automaticamente a cada 10 segundos.|Resiliência/Desempenho|Média|Sim, simulando queda e restauração de conexão.|
|RNF-H8-3|O usuário deve poder cancelar o compartilhamento a qualquer momento sem necessidade de reiniciar o aplicativo.|Usabilidade/Privacidade|Alta|Sim, realizando cancelamento durante a denúncia.|
|RNF-H14-1|O compartilhamento deve expor apenas informações públicas da denúncia, preservando dados pessoais e sensíveis.|Privacidade/Segurança|Alta|Sim, inspecionando payloads e logs do compartilhamento.|
|RNF-H14-2|O compartilhamento deve funcionar para pelo menos os principais aplicativos: WhatsApp, Instagram e e-mail.|Compatibilidade|Alta|Sim, testando compartilhamento real em diferentes apps.|
|RNF-H14-3|O link compartilhado deve permanecer válido por no mínimo 12 meses.|Sustentabilidade/TI|Média|Sim, verificando data de expiração do link.|
|RNF-H16-1|Dados pessoais dos denunciantes não devem ser exibidos no feed, garantindo anonimato.|Privacidade|Alta|Sim, analisando o que é exibido/publicado no feed.|
|RNF-H16-2|O sistema deve otimizar a frequência de atualização do feed, evitando requisições desnecessárias quando o usuário está parado.|Desempenho/Eficiência|Média|Sim, monitorando requests com o usuário inativo.|

---

### Observações:

- **Categorias**: Correspondem ao tipo de restrição, como usabilidade, desempenho, segurança, compatibilidade, privacidade, etc.
- **Prioridade**: Indica o impacto do requisito no funcionamento e experiência do usuário (“Alta” = tratamento prioritário; “Média” = importante, mas não crítica para o MVP).
- **Testável / Verificável**: Indica se há critérios práticos para validação do requisito durante testes e revisões de código.

<br>


> Estes RNFs devem ser adotados e monitorados em todas as etapas do desenvolvimento para garantir a qualidade e segurança do sistema.
