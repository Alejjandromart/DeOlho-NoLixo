## Requisitos Funcionais (RF) - DeOlho NoLixo

Os **Requisitos Funcionais (RF)** listados abaixo definem as funcionalidades essenciais do aplicativo **DeOlho NoLixo**, uma plataforma mobile para monitoramento comunitário e denúncia de pontos de descarte irregulares de resíduos. Esses requisitos foram elaborados para garantir que o sistema atenda às necessidades dos usuários, promovendo transparência, engajamento cidadão e eficiência no combate ao descarte irregular.

A tabela organiza os requisitos com colunas que especificam o **Id**, a **Descrição** e a **Prioridade** de cada funcionalidade, além de informações complementares como **Pré-condição**, **Pós-condição** e **Testável**, para facilitar o desenvolvimento e a validação. Cada requisito funcional deve ser representado como uma elipse no diagrama de caso de uso, conectando-se aos atores relevantes (ex.: "Usuário"), conforme as melhores práticas de modelagem de sistemas.

<br>

---

<br>

| **Id**   | **Descrição**                                                                                     | **Prioridade** | **Pré-condição**                              | **Pós-condição**                                      | **Testável**                                                                 |
|----------|---------------------------------------------------------------------------------------------------|----------------|-----------------------------------------------|-------------------------------------------------------|------------------------------------------------------------------------------|
| RF-H1    | O sistema deve permitir que o usuário faça login utilizando e-mail e senha.                      | Alta           | Usuário deve ter uma conta registrada.        | Usuário autenticado e redirecionado para a tela inicial. | Sim, verificar se login com credenciais corretas concede acesso.            |
| RF-H2    | O sistema deve permitir que o usuário crie uma conta informando nome, e-mail e senha.            | Alta           | Usuário não deve ter conta existente.         | Conta criada e usuário notificado do sucesso.         | Sim, testar criação de conta com dados válidos e inválidos.                 |
| RF-H3    | O sistema deve permitir que o usuário recupere a senha por meio de um link enviado ao e-mail cadastrado. | Média        | Usuário deve ter e-mail registrado.           | Link de recuperação enviado ao e-mail informado.      | Sim, confirmar envio de e-mail e funcionalidade do link de recuperação.     |
| RF-H4    | O sistema deve permitir que o usuário anexe fotos à denúncia, capturando-as pela câmera ou selecionadas da galeria. | Alta      | Usuário deve estar logado e criando denúncia. | Fotos anexadas visíveis no formulário de denúncia.    | Sim, testar upload de fotos por câmera e galeria em diferentes dispositivos. |
| RF-H6    | O sistema deve exibir na tela inicial um botão “Denunciar”, destacado para iniciar rapidamente a criação de uma denúncia. | Alta     | Usuário deve estar logado.                    | Botão visível e funcional, levando ao formulário.     | Sim, verificar visibilidade e navegação ao clicar no botão.                |
| RF-H7    | O sistema deve disponibilizar um formulário para que o usuário detalhe a denúncia, incluindo tipo, descrição, local e evidências. | Alta   | Usuário deve ter iniciado uma denúncia.       | Formulário preenchido e dados salvos para envio.      | Sim, testar preenchimento e validação dos campos do formulário.             |
| RF-H8    | O sistema deve permitir que o usuário compartilhe sua localização em tempo real, mediante consentimento, ao registrar a denúncia. | Alta   | Usuário deve consentir com compartilhamento.  | Localização anexada à denúncia com precisão.          | Sim, testar precisão da localização e opção de consentimento.               |
| RF-H14   | O sistema deve permitir que o usuário compartilhe o post da denúncia no feed de denúncias.       | Média          | Denúncia deve estar registrada.               | Denúncia visível no feed de outros usuários.          | Sim, verificar se a denúncia aparece no feed após compartilhamento.         |
| RF-H16   | O sistema deve exibir um feed de denúncias (ou local escolhido pelo usuário), com possibilidade de aplicar filtros e atualizar em tempo real. | Alta | Usuário deve estar logado.                    | Feed exibido com filtros funcionais e atualizações.   | Sim, testar carregamento, filtros e atualizações em tempo real.            |

