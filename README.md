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

:wave:  Este repositório é mantido por [@giseladifini](https://twitter.com/GiselaDifini) e [@swyx](https://twitter.com/swyx). Estamos muito felizes que você quer experimentar React com Typescript! 
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
  - [Forms e Eventos](#forms-and-events)
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
