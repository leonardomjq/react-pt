<div align="center">
<h1>React+TypeScript Cheatsheets em Português</h1>

<a href="https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/81">
  <img
    height="80"
    width="80"
    alt="react + ts logo"
    src="https://user-images.githubusercontent.com/6764957/53868378-2b51fc80-3fb3-11e9-9cee-0277efe8a927.png"
    align="left"
  />
</a>

<p>Cheatsheets para desenvolvedores com experiência em React que estão iniciando com TypeScript</p>

[**Web docs**](https://react-typescript-cheatsheet.netlify.app/docs/basic/setup) |
[中文翻译](https://github.com/fi3ework/blog/tree/master/react-typescript-cheatsheet-cn) |
[**Español**](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet-es) |
[Contribute!](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/blob/master/CONTRIBUTING.md) |
[Ask!](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/new/choose)

</div>

---

<div align="center">

:wave: Este repositório é mantido por [@giseladifini](https://twitter.com/GiselaDifini) e [@swyx](https://twitter.com/swyx). Estamos muito felizes que você quer experimentar React com Typescript!
Se você perceber algo de errado ou faltando, por favor abra uma [issue](https://github.com/typescript-cheatsheets/react-pt/issues/new)! :+1:

</div>

---

## Todas as dicas de React + TypeScript

- **Cheatsheet Básico** ([`/README.md`](/README.md#basic-cheatsheet-table-of-contents)) é focado em ajudar desenvolvedores React a começar a usar TS com React **apps**
  - Foco nas melhores práticas com exemplos para copiar e colar.
  - Explica alguns tipos básicos de uso de TS e configuração ao longo do caminho.
  - Responde às perguntas mais frequentes.
  - Não cobre a lógica de tipo genérico em detalhes. Em vez disso, preferimos ensinar técnicas de solução de problemas simples para iniciantes.
  - O objetivo é se familiarizar com TS sem precisar aprender _muito_ sobre TS.
- **Cheatsheet Avançado** ([`/AVANÇADO.md`](https://react-typescript-cheatsheet.netlify.app/docs/advanced/intro)) ajuda a mostrar e explicar o uso avançado de tipos genéricos para pessoas que escrevem utilitários/funções/props de renderização/componentes de ordem superior (HOCs) reutilizáveis ​​e **bibliotecas** TS+React.
  - Possui dicas e truques diversos para usuários profissionais.
  - Conselhos para contribuir com DefinitelyTyped.
  - O Objetivo é tirar _total vantagem_ sobre o TypeScript.
- **Cheatsheet de migração** ([`/MIGRANDO.md`](https://react-typescript-cheatsheet.netlify.app/docs/migration/intro)) ajuda a reunir conselhos para a migração incremental de grandes bases de código de JS ou Flow, **de pessoas que já fizeram isso**.
  - Nós não tentamos convencer as pessoas a mudar, apenas ajudar as pessoas que já decidiram isso.
  - ⚠️ Esta é uma nova cheatsheet, toda ajuda é bem-vinda.
- **Cheatsheet de HOCs** ([`/HOC.md`](https://react-typescript-cheatsheet.netlify.app/docs/hoc/intro)) especificamente ensina as pessoas a escrever HOCs com a ajuda de exemplos.
  - Familiaridade com [Genéricos](https://www.typescriptlang.org/docs/handbook/generics.html) é necessário.
  - ⚠️ Esta é uma nova cheatsheet, toda a assistência é bem-vinda.

---

### Tabela Básica de Conteúdos da Cheatsheet

<details>

<summary><b>Expandir Tabela de Conteúdos</b></summary>

- [Seção 1: Setup TypeScript com React](#section-1-setup-typescript-with-react)
  - [Prerequisitos](#prerequisites)
  - [React + TypeScript Starter Kits](#react--typescript-starter-kits)
  - [Importar React](#import-react)
- [Seção 2: Começando](#section-2-getting-started)
  - [Componentes Funcionais](#function-components)
  - [Hooks](#hooks)
  - [useState](#usestate)
  - [useReducer](#usereducer)
  - [useEffect](#useeffect)
  - [useRef](#useref)
  - [useImperativeHandle](#useimperativehandle)
  - [Custom Hooks](#custom-hooks)
  - [Componentes de Classe](#class-components)
  - [Você Pode Não Precisar de `defaultProps`](#you-may-not-need-defaultprops)
  - [Escrevendo `defaultProps`](#typing-defaultprops)
  - [Consumindo Props de um Componente com defaultProps](#consuming-props-of-a-component-with-defaultprops)
    - [Problem Statement](#problem-statement)
    - [Solution](#solution)
  - [Misc Discussions and Knowledge](#misc-discussions-and-knowledge)
  - [Types ou Interfaces?](#types-or-interfaces)
  - [Exemplos Básicos de Prop Types](#basic-prop-types-examples)
  - [Exemplo Úteis de React Prop Types](#useful-react-prop-type-examples)
  - [getDerivedStateFromProps](#getderivedstatefromprops)
  - [Formulários e Eventos](#forms-and-events)
  - [Context](#context)
  - [Exemplo Básico](#basic-example)
  - [Exemplo Estendido](#extended-example)
  - [forwardRef/createRef](#forwardrefcreateref)
  - [Portais](#portals)
  - [Error Boundaries](#error-boundaries)
    - [Option 1: Using react-error-boundary](#option-1-using-react-error-boundary)
    - [Options 2: Writing your custom error boundary component](#options-2-writing-your-custom-error-boundary-component)
  - [Concurrent React/React Suspense](#concurrent-reactreact-suspense)
- [Troubleshooting Handbook: Types](#troubleshooting-handbook-types)
  - [Union Types and Type Guarding](#union-types-and-type-guarding)
  - [Types Opcionais](#optional-types)
  - [Enum Types](#enum-types)
  - [Type Assertion](#type-assertion)
  - [Simulating Nominal Types](#simulating-nominal-types)
  - [Intersection Types](#intersection-types)
  - [Union Types](#union-types)
  - [Overloading Function Types](#overloading-function-types)
  - [Using Inferred Types](#using-inferred-types)
  - [Using Partial Types](#using-partial-types)
  - [The Types I need weren't exported!](#the-types-i-need-werent-exported)
  - [The Types I need don't exist!](#the-types-i-need-dont-exist)
    - [Slapping `any` on everything](#slapping-any-on-everything)
    - [Autogenerate types](#autogenerate-types)
    - [Typing Exported Hooks](#typing-exported-hooks)
    - [Typing Exported Components](#typing-exported-components)
- [Troubleshooting Handbook: Operators](#troubleshooting-handbook-operators)
- [Troubleshooting Handbook: Utilities](#troubleshooting-handbook-utilities)
- [Troubleshooting Handbook: tsconfig.json](#troubleshooting-handbook-tsconfigjson)
- [Troubleshooting Handbook: Fixing bugs in official typings](#troubleshooting-handbook-fixing-bugs-in-official-typings)
- [Troubleshooting Handbook: Globals, Images and other non-TS files](#troubleshooting-handbook-globals-images-and-other-non-ts-files)
- [Other React + TypeScript resources](#other-react--typescript-resources)
- [Editor Tooling and Integration](#editor-tooling-and-integration)
- [Linting](#linting)
- [Other React + TypeScript resources](#other-react--typescript-resources-1)
- [Recommended React + TypeScript talks](#recommended-react--typescript-talks)
- [Time to Really Learn TypeScript](#time-to-really-learn-typescript)
- [Example App](#example-app)
- [My question isn't answered here!](#my-question-isnt-answered-here)
  - [Contributors](#contributors)
  <!--START-SECTION:setup-toc-->
  - [Prerequisites](#prerequisites)
  - [React + TypeScript Starter Kits](#react--typescript-starter-kits)
  - [Import React](#import-react)<!--END-SECTION:setup-toc-->
- [Section 2: Getting Started](#section-2-getting-started)
  - [Function Components](#function-components)
  - [Hooks](#hooks)
  - [Class Components](#class-components)
  - [Typing defaultProps](#typing-defaultprops)
  - [Types or Interfaces?](#types-or-interfaces)
  - [Basic Prop Types Examples](#basic-prop-types-examples)
  - [Useful React Prop Type Examples](#useful-react-prop-type-examples)
  - [getDerivedStateFromProps](#getDerivedStateFromProps)
  - [Forms and Events](#forms-and-events)
  - [Context](#context)
  - [forwardRef/createRef](#forwardrefcreateref)
  - [Portals](#portals)
  - [Error Boundaries](#error-boundaries)
  - [Concurrent React/React Suspense](#concurrent-reactreact-suspense)
- [Basic Troubleshooting Handbook: Types](#basic-troubleshooting-handbook-types)
  <!--START-SECTION:types-toc-->
  - [Union Types and Type Guarding](#union-types-and-type-guarding)
  - [Optional Types](#optional-types)
  - [Enum Types](#enum-types)
  - [Type Assertion](#type-assertion)
  - [Simulating Nominal Types](#simulating-nominal-types)
  - [Intersection Types](#intersection-types)
  - [Union Types](#union-types)
  - [Overloading Function Types](#overloading-function-types)
  - [Using Inferred Types](#using-inferred-types)
  - [Using Partial Types](#using-partial-types)
  - [The Types I need weren't exported!](#the-types-i-need-werent-exported)
  - [The Types I need don't exist!](#the-types-i-need-dont-exist)
    - [Slapping `any` on everything](#slapping-any-on-everything)
    - [Autogenerate types](#autogenerate-types)
    - [Typing Exported Hooks](#typing-exported-hooks)
    - [Typing Exported Components](#typing-exported-components)<!--END-SECTION:types-toc-->
- [Troubleshooting Handbook: Operators](#troubleshooting-handbook-operators)
- [Troubleshooting Handbook: Utilties](#troubleshooting-handbook-utilities)
- [Troubleshooting Handbook: tsconfig.json](#troubleshooting-handbook-tsconfigjson)
- [Troubleshooting Handbook: Bugs in official typings](#troubleshooting-handbook-bugs-in-official-typings)
- [Recommended React + TypeScript codebases to learn from](#recommended-react--typescript-codebases-to-learn-from)
- [Editor Tooling and Integration](#editor-tooling-and-integration)
- [Linting](#linting)
- [Other React + TypeScript resources](#other-react--typescript-resources)
- [Recommended React + TypeScript talks](#recommended-react--typescript-talks)
- [Time to Really Learn TypeScript](#time-to-really-learn-typescript)
- [Example App](#example-app)
- [My question isn't answered here!](#my-question-isnt-answered-here)
  </details>

<!--START-SECTION:setup-->

# Seção 1: Setup TypeScript com React

## Prerequisitos

1. bom conhecimento de [React](https://reactjs.org)

2. familiaridade com [TypeScript Types](https://www.typescriptlang.org/docs/handbook/basic-types.html) ([2ality's guide](http://2ality.com/2018/04/type-notation-typescript.html) sempre ajuda. Se você é um iniciante em TypeScript, veja este [chibicode’s tutorial](https://ts.chibicode.com/todo/))
3. já leu [a seção TypeScript no doc oficial do React](https://reactjs.org/docs/static-type-checking.html#typescript)
4. já leu [a seção React no novo playground do TypeScript](http://www.typescriptlang.org/play/index.html?jsx=2&esModuleInterop=true&e=181#example/typescript-with-react) (opcional: fazer os 40+ examplos no [playground](http://www.typescriptlang.org/play/index.html))

Este guia vai sempre assumir que você esta usando a última versão do TypeScript. Notas para versões antigas vão poder ser expandidas nas `<details>` tags.

## React + TypeScript Starter Kits

Cloud setups:

- [TypeScript Playground com React](https://www.typescriptlang.org/play?#code/JYWwDg9gTgLgBAKjgQwM5wEoFNkGN4BmUEIcA5FDvmQNwCwAUKJLHAN5wCuqWAyjMhhYANFx4BRAgSz44AXzhES5Snhi1GjLAA8W8XBAB2qeAGEInQ0KjjtycABsscALxwAFAEpXAPnaM4OANjeABtA0sYUR4Yc0iAXVcxPgEhdwAGT3oGAOTJaXx3L19-BkDAgBMIXE4QLCsAOhhgGCckgAMATQsgh2BcAGssCrgAEjYIqwVmutR27MC5LM0yuEoYTihDD1zAgB4K4AA3H13yvbAfbs5e-qGRiYspuBmsVD2Aekuz-YAjThgMCMcCMpj6gxcbGKLj8MTiVnck3gAGo4ABGTxyU6rcrlMF3OB1H5wT7-QFGbG4z6HE65ZYMOSMIA) só se estiver debugging types (e reportando issues)
- [CodeSandbox](http://ts.react.new) - cloud IDE, inicia super rápido
- [Stackblitz](https://stackblitz.com/edit/react-typescript-base) - igual ao CodeSandbox

Local dev setups:

- [Next.js](https://nextjs.org/docs/basic-features/typescript): `npx create-next-app -e with-typescript` vai criar na sua pasta atual
- [Create React App](https://facebook.github.io/create-react-app/docs/adding-typescript): `npx create-react-app name-of-app --template typescript` vai criar em uma nova pasta
- [Meteor](https://guide.meteor.com/build-tool.html#typescript): `meteor create --typescript name-of-my-new-typescript-app`
- [Ignite](https://github.com/infinitered/ignite#use-ignite-andross-infinite-red-andross-boilerplate) para React Native: `ignite new myapp`
- TSDX para Criar React+TS libraries

Ferramentas menos maduras que ainda valem a pena checar:

- [Vite](https://twitter.com/swyx/status/1282727239230996480?lang=en): `npm init vite-app my-react-project --template react-ts` (nota - ainda não na v1.0, mas muito ágil)
- [Snowpack](<https://www.snowpack.dev/#create-snowpack-app-(csa)>): `npx create-snowpack-app my-app --template app-template-react-typescript`
- [Docusaurus v2](https://v2.docusaurus.io/docs/installation) com [TypeScript Support](https://v2.docusaurus.io/docs/typescript-support)
- [Parcel](https://v2.parceljs.org/languages/typescript/)

Setup manual:

- [Basarat's guide](https://github.com/basarat/typescript-react/tree/master/01%20bootstrap) para **setup manual** do React + TypeScript + Webpack + Babel
- Em particular, tenha certeza que você tem `@types/react` e `@types/react-dom` instalados ([Leia mais sobre o projeto DefinitelyTyped se você não esta familiarizado](https://definitelytyped.org/))
- Tem também muitos outros React + TypeScript boilerplates, por favor veja [nossa lista de Outros Recursos](https://react-typescript-cheatsheet.netlify.app/docs/basic/recommended/resources/)

## Importar React

```tsx
import * as React from "react";
import * as ReactDOM from "react-dom";
```

Esta é a melhor maneira [para o futuro](https://www.reddit.com/r/reactjs/comments/iyehol/import_react_from_react_will_go_away_in_distant/) da importação React. Se você usar `--allowSyntheticDefaultImports` (ou adicionar `"allowSyntheticDefaultImports": true`) no seu `tsconfig.json` você pode utilizar imports mais familiares:

```tsx
import React from "react";
import ReactDOM from "react-dom";
```

<details>

<summary>Explicação</summary>

Porque `allowSyntheticDefaultImports` ao invés de `esModuleInterop`? [Daniel Rosenwasser](https://twitter.com/drosenwasser/status/1003097042653073408) disse que é melhor para webpack/parcel. Para mais discussões, veja <https://github.com/wmonk/create-react-app-typescript/issues/214>

Você também deveria checar [o novo docs do TypeScript decrições oficiais entre cada compiler flag](https://www.typescriptlang.org/tsconfig#allowSyntheticDefaultImports)!

</details>

<!--END-SECTION:setup-->
