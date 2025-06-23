# Divisao_de_Trafego_na_AWS
🚦 O que é Divisão de Tráfego na AWS?
👉 Basicamente é quando você faz um deploy (implantação) de uma nova versão da sua aplicação, mas NÃO JOGA TODO MUNDO NELA DE UMA VEZ.

🧠 A ideia é dividir o fluxo de usuários entre:

✔️ A versão antiga (estável)

🆕 E a nova versão (que tá sendo testada)

👉 Tudo isso pra garantir que, se a nova versão der ruim 💀, você consegue voltar, ajustar, e ninguém (ou quase ninguém) sai prejudicado.

🏗️ Onde isso aparece na AWS Developer?
Quando você faz deploy com:

AWS Lambda (com aliases)

AWS CodeDeploy (pra Lambda, ECS e EC2)

API Gateway (stages diferentes)

➡️ A AWS permite que você divida o tráfego entre versões, fazendo deploy de forma mais segura.

🎯 Exemplos práticos:
✨ Lambda + Alias:

Você tem a versão v1 rodando.

Lança a versão v2, e define:

"Manda 90% dos usuários na v1 e 10% na v2."

Se tudo der bom ➝ Aumenta pra 50/50 ➝ Depois 100% na nova. 🚀

Se der ruim ➝ Volta pra v1 FACIM, FACIM.

🚥 Modelos de Deploy que usam Divisão de Tráfego:
Tipo	Como funciona?
Canary	Envia uma parte PEQUENA pro novo (ex.: 10%), testa... depois o resto. 🐦
Linear	Aumenta aos poucos de forma constante (ex.: +10% a cada 1 minuto). 📈
All-at-once	TACA-LE-PAU! Joga todo mundo na nova versão de uma vez (mais arriscado). 💥

🧠 Pergunta que AMA cair na AWS Developer:
Você está atualizando uma função Lambda e deseja que apenas 10% dos usuários usem a nova versão enquanto testa se ela funciona corretamente. Qual abordagem você deve usar?

🅰️ Canary deployment com divisão de tráfego usando Lambda Alias + CodeDeploy.

🐝 Analogia pra gravar na mente:
👉 Imagina uma balada (sim, a AWS tem balada).

🎶 Tem a pista antiga tocando Rock (versão v1).

🎧 Abrem uma nova pista testando Techno (versão v2).

A galera começa assim:

90% no Rock 🎸

10% no Techno 🎧

Se o DJ do Techno tá BOM ➝ Aumenta o povo pra lá.
Se tá RUIM ➝ Fecha a pista e todo mundo volta pro Rock! 🤣

🔥 Na prática, essa é uma estratégia BRABA de DevOps, Serverless e CI/CD, porque evita que um bug derrube tudo.
