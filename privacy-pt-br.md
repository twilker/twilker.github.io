---
title: DailyFlow – Política de Privacidade
layout: page
permalink: /dailyflow/privacy/pt-br/
---

# DailyFlow – Política de Privacidade

**Idiomas:** [English](/dailyflow/privacy/) · [Deutsch](/dailyflow/privacy/de/) · [Español](/dailyflow/privacy/es/) · Português (BR)

**Aplicativo:** DailyFlow / Alltagshelfer (`com.marvelsofcode.dailyflow`)
**Data de vigência:** 12 de agosto de 2026

## 1. Responsável

Tobias Wilker
E-mail: [tobias.wilker@gmail.com](mailto:tobias.wilker@gmail.com)

Controlador dos dados descritos aqui. Para dúvidas sobre esta política ou sobre os seus dados, escreva para o endereço acima.

## 2. Resumo

O DailyFlow é um aplicativo «local first». Suas tarefas, tarefas recorrentes, rotinas, checklists, estatísticas, histórico e configurações ficam **somente no seu aparelho**. Não há conta, cadastro nem perfil de usuário em qualquer servidor meu. Não coleto, recebo, vendo nem compartilho seus dados pessoais.

O aplicativo **não tem anúncios, rastreamento nem analytics**. O SDK do Firebase Analytics foi removido deliberadamente.

Dois recursos opcionais enviam dados para fora do aparelho, e apenas se você os usar: **compartilhamento em grupo / delegação** e **backup no Google Drive**. Ambos são descritos a seguir.

## 3. Dados armazenados no seu aparelho

São gravados localmente: tarefas e seus vencimentos, regras de repetição, rotinas, checklists e seus itens, o histórico de tarefas concluídas, estatísticas, perfis, a participação em grupos com as respectivas chaves criptográficas e as suas configurações. Esses dados nunca são transmitidos, exceto pelos dois recursos opcionais das seções 4 e 5.

O histórico de tarefas concluídas é limpo automaticamente conforme o período de retenção que você define nas configurações.

Desinstalar o aplicativo apaga todos esses dados.

## 4. Compartilhamento em grupo e delegação (opcional)

Ao entrar em um grupo lendo o QR code de outro aparelho, você pode compartilhar tarefas, rotinas e checklists com os demais membros e delegar tarefas a eles.

- **Criptografia de ponta a ponta.** Tudo o que sai do seu aparelho para outro membro é criptografado no seu aparelho com AES-256-GCM (um vetor de inicialização aleatório por mensagem e tag de autenticação de 128 bits).
- **A chave nunca chega a um servidor.** A chave de grupo de 256 bits é gerada no seu aparelho e trafega apenas dentro do QR code que você mostra à outra pessoa. Ela nunca é enviada para a nuvem e eu não a possuo.
- **O que o transporte enxerga.** As mensagens criptografadas são repassadas por uma Cloud Function do Google de minha propriedade (projeto Firebase `dailyflow-502909`) e entregues pelo Firebase Cloud Messaging. O relay vê apenas o token de mensageria do destinatário, o texto cifrado opaco, uma collapse key e um identificador do aparelho remetente. Ele não consegue ler o conteúdo, e o conteúdo não é gravado em nenhum banco de dados meu.
- **Retenção.** Mensagens que não podem ser entregues de imediato ficam no Firebase Cloud Messaging no máximo pelo tempo de vida máximo de quatro semanas e depois são descartadas. A fila de envio local correspondente no seu aparelho é limpa no mesmo ritmo.
- **Proteção contra abuso.** O Firebase App Check (Play Integrity) impede que outros clientes abusem do endpoint do relay.
- **Operador.** Google Ireland Limited / Google LLC para o Firebase Cloud Messaging e as Cloud Functions. Informações de privacidade do Google: <https://firebase.google.com/support/privacy>.
- **Base legal.** Art. 6(1)(b) do GDPR — tratamento necessário para prestar o recurso de compartilhamento que você solicitou. Se você não entrar em nenhum grupo, nenhum dado é transmitido.

Lembre-se de que os demais membros do grupo podem, por natureza, ver o conteúdo que você compartilha. Compartilhe apenas com pessoas de sua confiança.

## 5. Backup no Google Drive (opcional)

Ao iniciar um backup, o aplicativo solicita autorização para um único escopo do Google Drive: `https://www.googleapis.com/auth/drive.appdata`. Esse escopo dá acesso **exclusivamente à pasta oculta de dados do próprio aplicativo** no seu Drive. O aplicativo nunca pode ver, ler ou alterar os seus outros arquivos do Google Drive, e não solicita seu nome, e-mail ou perfil.

O arquivo de backup contém o seu banco de dados local, as suas configurações e um retrato da sua configuração de grupo. Ele fica **na sua própria conta do Google Drive**, sob o seu controle, protegido pela criptografia em repouso do Google. O aplicativo não o criptografa adicionalmente. Eu não tenho acesso ao seu Drive nem ao arquivo de backup. Você pode excluí-lo a qualquer momento no armazenamento de dados de aplicativos da sua conta Google e revogar a autorização em <https://myaccount.google.com/permissions>.

**Base legal.** Art. 6(1)(a)/(b) do GDPR — é você quem aciona o backup expressamente.

## 6. Permissões e por que são necessárias

| Permissão | Finalidade |
| --- | --- |
| Notificações | Alarmes de tarefas vencidas e o resumo diário opcional |
| Alarmes exatos | Tocar exatamente no horário definido; um alarme de lembrete impreciso seria inútil |
| Intent em tela cheia | Exibir e dispensar o alarme pela tela de bloqueio |
| Serviço em primeiro plano (reprodução) | Manter o som do alarme tocando enquanto ele soa |
| Executar na inicialização | Reagendar os alarmes pendentes após reiniciar o aparelho |
| Internet / estado da rede | Apenas para o relay criptografado (seção 4) e o backup no Drive (seção 5) |
| Câmera | Ler o QR code de convite para um grupo. Nenhuma foto ou vídeo é armazenado ou transmitido |

## 7. Crianças

O DailyFlow é um aplicativo de produtividade para o público em geral. Não é direcionado a crianças e não coleta conscientemente dados delas.

## 8. Seus direitos

Sob o GDPR, você tem direito de acesso, retificação, exclusão, limitação do tratamento, portabilidade e oposição, além do direito de reclamar a uma autoridade de controle.

Como não guardo dados pessoais sobre você, na prática não há nada que eu possa fornecer ou apagar. Você exerce esses direitos diretamente: desinstale o aplicativo para apagar todos os dados locais, exclua o backup no Drive e revogue a autorização na sua conta Google, e saia dos grupos dos quais participa. Em caso de dúvida, escreva para [tobias.wilker@gmail.com](mailto:tobias.wilker@gmail.com).

## 9. Alterações desta política

As alterações são publicadas nesta página com uma nova data de vigência. Mudanças substanciais também serão indicadas nas notas de versão do aplicativo.
