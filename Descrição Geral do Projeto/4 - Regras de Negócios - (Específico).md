## Regras de Negócio (RN) – DeOlho NoLixo

As **Regras de Negócio (RN)** definem os critérios, lógicas e restrições que governam o funcionamento do aplicativo **DeOlho NoLixo**. Elas são a base para a criação dos Requisitos Funcionais e garantem que o sistema opere de maneira consistente, segura e alinhada aos objetivos do projeto.

Esta documentação serve como um guia para a equipe de desenvolvimento, detalhando as condições que devem ser atendidas em cada funcionalidade. Toda regra de negócio deve ser validada e implementada para assegurar a integridade dos dados e a qualidade da experiência do usuário.

<br>

---
<br>

### Tabela de Regras de Negócio

|**Id**|**Descrição**|**Prioridade**|
|---|---|---|
|**H1: Acesso à Conta**|
|RN-H1-01|**Formato do E-mail:** O e-mail deve seguir um formato válido (ex: `usuario@dominio.com`) e ter no máximo 254 caracteres.|Alta|
|RN-H1-02|**Complexidade da Senha:** A senha deve conter no mínimo 8 caracteres, incluindo pelo menos 1 letra maiúscula, 1 minúscula, 1 número e 1 caractere especial (`!@#$%^&*`).|Alta|
|RN-H1-03|**Bloqueio por Tentativas de Login:** Após 3 tentativas de login falhas consecutivas, o sistema deve bloquear o acesso da conta por 5 minutos.|Alta|
|**H2: Cadastro de Usuário**|
|RN-H2-01|**Conclusão do Cadastro:** O cadastro só será concluído se todos os campos obrigatórios forem preenchidos corretamente e a confirmação de senha corresponder à senha digitada.|Alta|
|RN-H2-02|**Validação de Nome/Sobrenome:** O preenchimento é obrigatório, deve conter apenas letras, espaços e apóstrofos, com tamanho entre 3 e 50 caracteres.|Alta|
|RN-H2-03|**Unicidade do E-mail:** O e-mail deve ser único na base de dados. O sistema precisa verificar sua existência em tempo real durante o cadastro.|Alta|
|RN-H2-04|**Validação de Nome de Usuário (UserName):** O preenchimento é obrigatório, deve conter apenas letras, underlines e números, com tamanho entre 3 e 20 caracteres.|Alta|
|RN-H2-05|**Mensagens de Erro Específicas:** O sistema deve exibir mensagens de erro claras e próximas ao campo correspondente (ex: "E-mail já cadastrado", "A senha deve conter um número").|Alta|
|RN-H2-06|**Verificação de E-mail Pós-Cadastro:** Após o cadastro, o sistema deve enviar um e-mail de verificação contendo um link único com validade de 24 horas.|Média|
|RN-H2-07|**Redirecionamento Pós-Cadastro:** Após o sucesso no cadastro, o usuário deve ser redirecionado para uma tela de tutorial com vídeo explicativo, que pode ser pulado.|Média|
|**H3: Recuperação de Senha**|
|RN-H3-01|**Expiração do Link de Recuperação:** O link de redefinição de senha enviado por e-mail deve expirar em 30 minutos para garantir a segurança.|Alta|
|RN-H3-02|**Mensagem Genérica de Recuperação:** Para proteger a privacidade, o sistema deve exibir uma mensagem genérica de confirmação, independentemente de o e-mail existir na base de dados.|Alta|
|RN-H3-03|**Limite de Solicitações de Recuperação:** O sistema deve limitar o número de solicitações de redefinição de senha a no máximo 3 por hora para um mesmo e-mail.|Média|
|**H4, H6, H7: Registro de Denúncias**|
|RN-H4-01|**Consentimento de Câmera:** O uso da câmera exige consentimento explícito do usuário, conforme as diretrizes de privacidade da plataforma (Android/iOS).|Alta|
|RN-H4-02|**Consentimento de Localização:** O sistema deve solicitar permissão para acessar a localização do usuário no momento do registro da denúncia, em conformidade com a LGPD.|Alta|
|RN-H4-03|**Remoção de Metadados EXIF:** Antes do upload, o sistema deve remover todos os metadados EXIF da imagem, exceto a geolocalização (GPS), que será tratada como um dado separado.|Alta|
|RN-H4-04|**Confirmação de Uso de Dados:** Próximo ao botão "Enviar Denúncia", um texto deve informar ao usuário que fotos e localização serão usadas exclusivamente para processar a denúncia.|Alta|
|RN-H6-01|**Acesso Autenticado para Denunciar:** O envio de denúncias só é permitido a usuários autenticados no sistema.|Alta|
|RN-H6-02|**Obrigatoriedade de Campos:** Para validar uma denúncia, o usuário deve preencher obrigatoriamente uma descrição, anexar pelo menos uma imagem e fornecer a localização (automática ou manual).|Alta|
|RN-H7-01|**Categorias de Descarte:** O sistema deve oferecer uma lista pré-definida de categorias de descarte (ex: lixo doméstico, entulho, eletrônico) para classificação da denúncia.|Alta|
|RN-H7-02|**Limite de Anexos:** O formulário deve aceitar no máximo 5 fotos por denúncia, nos formatos JPEG ou PNG, rejeitando arquivos que não atendam a esses padrões.|Média|
|**H8, H14, H16: Gestão e Visualização de Denúncias**|
|RN-H8-01|**Modos de Localização:** O sistema deve permitir dois modos de uso da localização: **única** (padrão, no momento do registro) e **contínua** (opcional, para monitoramento).|Média|
|RN-H14-01|**Anonimização no Compartilhamento Público:** Dados pessoais do denunciante (nome, e-mail, etc.) não podem ser exibidos em denúncias públicas. Apenas informações do problema (descrição, fotos, localização aproximada) devem ser visíveis.|Alta|
|RN-H16-01|**Feed Baseado em Localização:** O feed de denúncias é exibido com base na localização do usuário, desde que ele permita o acesso ao GPS.|Alta|
|RN-H16-02|**Informações do Card de Denúncia:** Cada item do feed deve exibir o tipo de descarte, a distância aproximada, a data/hora do registro, o status atual e uma miniatura da imagem principal.|Alta|
|RN-H16-03|**Acompanhamento de Status:** Após o registro, o sistema deve disponibilizar ao usuário o acompanhamento do status da denúncia (Novo, Confirmado, Em Acompanhamento, Resolvido).|Alta|

<br>  

### Observações Gerais

- **Prioridade Alta:** Indica regras críticas para a segurança, funcionalidade principal ou conformidade legal do aplicativo.
- **Prioridade Média:** Refere-se a regras importantes para a experiência do usuário e a robustez do sistema, mas que não são impeditivas para o funcionamento básico.

- **Relação com Requisitos Funcionais:** Lembre-se que toda Regra de Negócio deve gerar um ou mais Requisitos Funcionais. Por exemplo, a `RN-H1-02` (Complexidade da Senha) se traduz no requisito funcional de validar a senha durante o cadastro e a troca.
