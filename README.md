# Star Wars App

Aplicativo em React Native (Expo) para registrar um usuario, escolher um personagem favorito do universo Star Wars via SWAPI e explorar fichas de personagens. Interface em tema escuro com navegacao em stack.

## 📱 Funcionalidades

- Registro simples de usuario (nome e e-mail)
- Seleciona personagem favorito consultando a [SWAPI](https://swapi.dev)
- Home com saudacao e atalhos
- Busca por personagens (nome) com listagem paginada
- Tela de perfil com dados salvos localmente
- Armazenamento persistente em AsyncStorage

## 🧰 Stack

- Expo / React Native
- React Navigation (native stack)
- AsyncStorage para persistencia local
- SWAPI como fonte de dados

## 📂 Estrutura

- App.tsx — configura o `NavigationContainer`, status bar e stack principal
- src/screens — telas: `Register`, `CharacterSelect`, `Home`, `Search`, `Profile`
- src/components — componentes reutilizaveis (`Button`, `SearchBar`, `CharacterCard`)
- src/services/api.ts — chamadas para SWAPI (`searchCharacter`, `getAllCharacters`)
- src/storage/userStorage.ts — persistencia do usuario (salvar, obter, limpar)

## 🚀 Como rodar

1. Requisitos: Node 18+, npm ou yarn, CLI do Expo (`npm i -g expo-cli`).
2. Instale dependencias:

```bash
npm install
```

3. Inicie o app (Metro bundler):

```bash
npm start
```

4. Execute no dispositivo/emulador:

- Android: `npm run android`
- iOS (macOS): `npm run ios`
- Web: `npm run web`

## 🔀 Fluxo de navegacao

1. Register → salva `name` e `email` em AsyncStorage
2. CharacterSelect → busca personagens via `getAllCharacters()` e salva `character`
3. Home → exibe saudacao e atalho para Search/Profile
4. Search → busca incremental via `searchCharacter(query)` e exibe cards
5. Profile → mostra dados salvos e permite alterar personagem

## 🗄️ Persistencia

- Chave usada: `@starwars_user`
- Estrutura gravada: `{ name, email, character }`
- Funcoes: `saveUser`, `getUser`, `clearUser`

## 🧪 Testes

- Jest configurado com script `npm test` (watch).

## 🌟 Melhorias sugeridas

- Validação de formularios e feedback de erro
- Paginação/scroll infinito real na busca
- Indicadores de loading e estados vazios
- Cache de resultados e debounce na SearchBar
- Temas claro/escuro via context

## 📜 Licenca

Projeto educativo/demonstração. Ajuste conforme necessidade antes de distribuir.
