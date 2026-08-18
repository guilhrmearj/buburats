# 🎀 Bubu Rats Race

Pista de corrida kawaii pra registrar os lanches da turma — Cams, Dada e Gui.

---

## 🚀 Deploy em 3 passos: Firebase → GitHub → Vercel

---

### 1. Firebase (banco de dados em tempo real)

1. Acesse [console.firebase.google.com](https://console.firebase.google.com)
2. Clique em **"Adicionar projeto"** → dê um nome (ex: `bubu-rats`) → crie
3. No menu lateral, vá em **Firestore Database** → **Criar banco de dados**
   - Escolha **Modo de teste** (libera leitura e escrita por 30 dias, suficiente pra começar)
   - Escolha a região `us-east1` ou a mais próxima
4. Ainda no console, vá em **Configurações do projeto** (ícone de engrenagem) → aba **Geral**
5. Role até **Seus apps** → clique em **`</>`** (Web app)
6. Dê um apelido (ex: `bubu-web`) e clique em **Registrar app**
7. Copie o objeto `firebaseConfig` que aparecer. Exemplo:

```js
const firebaseConfig = {
  apiKey:            "AIzaSyXXXXXXXXXXXXXX",
  authDomain:        "bubu-rats.firebaseapp.com",
  projectId:         "bubu-rats",
  storageBucket:     "bubu-rats.appspot.com",
  messagingSenderId: "123456789",
  appId:             "1:123456789:web:abcdef"
};
```

8. Abra o arquivo `index.html` deste projeto e **substitua** o bloco `firebaseConfig` lá dentro pelos seus valores reais.

#### Regras do Firestore (para funcionar em produção)

No console Firebase → Firestore → aba **Regras**, cole:

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /entries/{doc} {
      allow read, write: if true;
    }
  }
}
```

Clique em **Publicar**.

---

### 2. GitHub (repositório)

1. Acesse [github.com](https://github.com) e crie uma conta se não tiver
2. Clique em **New repository** → nome: `bubu-rats-race` → **Create repository**
3. Na tela seguinte, siga as instruções de upload. A forma mais simples:
   - Clique em **"uploading an existing file"**
   - Arraste os 3 arquivos: `index.html`, `vercel.json`, `README.md`
   - Clique em **Commit changes**

---

### 3. Vercel (hospedagem gratuita)

1. Acesse [vercel.com](https://vercel.com) e faça login com sua conta GitHub
2. Clique em **"Add New Project"**
3. Selecione o repositório `bubu-rats-race`
4. Clique em **Deploy** — sem configuração adicional necessária
5. Em ~30 segundos o site estará no ar com uma URL do tipo:
   `https://bubu-rats-race.vercel.app`

A cada vez que você atualizar o `index.html` no GitHub, o Vercel faz o deploy automático.

---

## 🎮 Como usar o site

- **Registrar lanche:** escolha qual Bubu lanchou, informe quem foi o lanche e a data
- **Corrida:** o carrinho avança automaticamente com cada ponto registrado
- **Placar:** os cards mostram a pontuação em tempo real
- **Música:** clique no 🔇 no canto superior direito pra ligar o som kawaii
- **Cronômetro:** conta regressiva até 31/12/2026 no canto superior direito
- **Histórico:** todos os registros listados, com opção de apagar individualmente

---

## 🗂 Arquivos do projeto

| Arquivo | Função |
|---|---|
| `index.html` | Site completo (HTML + CSS + JS num só arquivo) |
| `vercel.json` | Configuração de roteamento do Vercel |
| `README.md` | Este guia |

---

## 🌸 Personagens

| Bubu | Personagem | Cor |
|---|---|---|
| Cams | 🐰 Coelhinha | Rosa |
| Dada | 🐱 Gatinha | Lilás |
| Gui | 🐹 Hamster | Verde |
