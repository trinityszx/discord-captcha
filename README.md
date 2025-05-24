# 🛡️ Sistema de Captcha para Discord Bots

Este projeto implementa um sistema de verificação por **Captcha** para bots de Discord, com funcionalidades robustas como:

- Geração automática de imagens com código de verificação
- Validação por menu suspenso interativo
- Atualização periódica da imagem sem poluir o chat
- Persistência com banco de dados (Sequelize + SQLite)
- Sistema de logs detalhado com Winston
- Armazenamento de informações do usuário verificado

## 🚀 Tecnologias utilizadas

- [Discord.js v14](https://discord.js.org/)
- [Sequelize ORM](https://sequelize.org/)
- [Canvas](https://www.npmjs.com/package/canvas) (para gerar a imagem do captcha)
- [Winston](https://github.com/winstonjs/winston) (para logging)

## 📦 Instalação

```bash
git clone https://github.com/seuusuario/sistema-captcha-discord.git
cd sistema-captcha-discord
npm install
```

## ⚙️ Configuração

Crie um arquivo `.env` com seu token do bot:

```env
DISCORD_TOKEN=seu_token_aqui
```

## 🧠 Como funciona

1. **Comando de Setup:**
   Use o comando `/captchasetup` para definir:
   - Canal de envio do captcha
   - Cargo a ser atribuído ao usuário verificado
   - Intervalo de atualização da imagem

2. **Verificação:**
   - O bot envia uma imagem com código aleatório
   - O usuário escolhe a opção correta no menu suspenso
   - Se correta, recebe o cargo e as informações são salvas

3. **Atualização periódica:**
   - A cada X segundos (configurado no setup), a imagem e as opções do menu são atualizadas **na mesma mensagem**

4. **Banco de dados:**
   - Configurações do captcha por servidor
   - Informações dos usuários verificados (ID, nome, avatar, data, etc.)

## 🧪 Comandos disponíveis

| Comando         | Descrição                                 |
|-----------------|-------------------------------------------|
| `/captchasetup` | Configura canal, cargo e intervalo        |

## 🗃️ Estrutura do banco

O projeto utiliza Sequelize com modelos:

- `CaptchaConfig.js`: configurações do captcha por servidor
- `UserInfo.js`: dados de membros que completaram o captcha

## 🧩 Exemplo de uso

```bash
/captchasetup canal:#verificação cargo:@membro intervalo:120
```

## 🧠 Recursos futuros

- Validação com botão além de menu
- Integração com anti-raid
- Painel de estatísticas

## 🧑‍💻 Contribuindo

Pull requests são bem-vindos! Sinta-se à vontade para abrir *issues* com melhorias ou sugestões.

## 📄 Licença

Este projeto está licenciado sob a **MIT License**.
