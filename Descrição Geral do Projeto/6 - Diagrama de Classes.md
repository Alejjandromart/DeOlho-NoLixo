# 🚀 Diagrama de Classes – DeOlho NoLixo

</br>
</br>

```mermaid
---
config:
  layout: elk
---
classDiagram
class NotificacaoService {
  <<interface>>
  +enviarNotificacao(): boolean
  +gerarConteudo(): string
}
class Usuario {
  +userName: string
  +dataCadastro: date
  +nome: string
  +email: string
  +senha: string
  +foto: base64
  +LoginGoogle(): boolean
  +recuperarSenha(): void
  +Logout(): void
  +editarPerfil(): void
  +visualizarHistorico(): List~Denuncia~
}
class Denuncia {
  +id: int
  +descricao: string
  +localizacao: string
  +categoria: string
  +foto: base64
  +status: StatusDenuncia
  +dataEnvio: date
  +curtidas: int
  +registrar(): void
  +compartilhar(): void
  +curtir(): void
}
class StatusDenuncia {
  <<enumeration>>
  EmAnalise
  Enviada
  Resolvida
}
class Feed {
  +visualizarFeed(): List~Denuncia~
  +filtrarDenuncias(filtro: string): List~Denuncia~
}
class ClassificacaoIA {
  +processarImagem(imagem: string): ResultadoClassificacao
  +classificarImpactoAmbiental(denuncia: Denuncia): string
  +classificarTipoResiduo(denuncia: Denuncia): string
  +analisarTexto(texto: string): string
  +gerarResumo(denuncia: Denuncia): string
  +validarClassificacao(resultado: ResultadoClassificacao): boolean
}
class OrgaoResponsavel {
  +sigla: string
  +dataCadastro: date
  +email: string
  +tipoOrgao: string
}
class IntegracaoExterna {
  +enviarEmailOrgao(denuncia: Denuncia, orgao: OrgaoResponsavel): boolean
  +gerarCorpoEmail(denuncia: Denuncia, resumo: string): string
  +notificarOrgaoResponsavel(denuncia: Denuncia): void
  +selecionarOrgaoCompetente(categoria: string): OrgaoResponsavel
}
NotificacaoService <|.. IntegracaoExterna : implementa
Usuario *-- Denuncia : compõe
Feed -- Denuncia : exibe
OrgaoResponsavel -- Denuncia : destinatario
Denuncia ..> ClassificacaoIA : processada_por
IntegracaoExterna ..> OrgaoResponsavel : consulta
IntegracaoExterna ..> Denuncia : processa
Denuncia -- StatusDenuncia : possui

```
</br>
</br>

---

</br>

## 👤 Usuário

- Guarda: nome, e-mail, senha, foto, cadastro.
- Pode: logar, editar perfil, recuperar senha, ver histórico.

## 📝 Denúncia

- Tem: descrição, localização, tipo, status, foto, data, curtidas.
- Pode: ser registrada, curtida, compartilhada.

## 📰 Feed

- Exibe várias denúncias.
- Permite filtrar 🔍, visualizar 👀 e interagir 👍💬.

## 📊 StatusDenuncia

- Diz em qual fase está cada denúncia (ex: recebida, analisando, resolvida).

## 🧠 Classificação IA

- Analisa imagem 🖼️ e texto ✍️ automaticamente,
- Classifica tipo de resíduo, impacto ambiental e resumo do caso.

## 🏛️ Órgão Responsável

- Recebe as denúncias e age.
- Tem: nome, sigla, email, tipo.

## 🔗 Integração Externa

- Faz a ponte entre o app e órgãos.
- Gera e dispara e-mails automáticos 📧.

## 📣 Notificação (Interface)

- Define o padrão para notificações no sistema ✔️.

---

### 🔀 Relações Importantes

- 👤 **Usuário pode criar várias 📝 denúncias**
- 📰 **Feed centraliza todas as 📝 denúncias**
- 📝 **Denúncia sempre tem um 📊 status**
- 📝 **Pode ser avaliada por IA 🧠**
- 📝 **Pode ser enviada para um 🏛️ órgão responsável**
- 🔗 **Integração Externa conecta denúncias e órgãos**
- 📣 **Notificação dá a receita de como avisar (seguida pela Integração Externa)**
