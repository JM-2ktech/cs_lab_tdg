---
title: 용어집
nav_order: 12
---

# 용어집 📖

이 과정에서 쓰는 핵심 용어를 처음 등장 순서대로 정리했습니다. 각 항목에 고정 id가 붙어 있어 다른 페이지에서 `../glossary.html#id`로 바로 연결할 수 있습니다(id는 각 항목 제목 옆에 회색 코드로 표기).

### Agent Builder `#agent-builder`
{: #agent-builder }
Microsoft 365 Copilot에 내장된 선언형 에이전트 제작 도구. Copilot Studio보다 쉽고 빠르지만 기능은 제한적.

### Copilot Studio `#copilot-studio`
{: #copilot-studio }
에이전트를 만들고 지식·지침·커넥터·토픽을 붙여 확장하는 전문 도구.

### 오케스트레이터 `#orchestrator`
{: #orchestrator }
사용자 입력을 보고 어떤 지식·도구·토픽을 쓸지 결정하는 판단 계층. LLM과는 역할이 다르다.

### LLM (거대 언어 모델) `#llm`
{: #llm }
실제 텍스트를 생성하는 모델. 오케스트레이터의 판단에 따라 호출된다.

### RAG (검색 증강 생성) `#rag`
{: #rag }
질의 → 검색 → 그라운딩 → 생성의 4단계로, 업로드한 지식 문서를 근거로 답을 만드는 방식.

### Indexing (인덱싱) `#indexing`
{: #indexing }
업로드한 문서를 검색 가능한 형태로 처리하는 과정. 완료까지 대기 시간이 필요하다.

### Tokenizer / 토큰 `#tokenizer`
{: #tokenizer }
텍스트를 잘게 쪼갠 단위. 길이 제한과 비용(Copilot Credit) 계산의 기준이 된다.

### Copilot Credit `#copilot-credit`
{: #copilot-credit }
토큰(또는 이미지·페이지) 사용량을 환산한 과금 단위. 1K 토큰을 올림한 뒤 모델 등급별 요율을 곱해 계산한다.

### 지식 (Knowledge) `#knowledge`
{: #knowledge }
에이전트가 근거로 삼는 업로드 문서. "기준"이지 실시간 개인 데이터가 아니다.

### 지침 (Instructions) `#instructions`
{: #instructions }
에이전트의 역할·말투·답변 원칙·경계 규칙을 정의하는 텍스트.

### 커넥터 (표준 커넥터) `#connector`
{: #connector }
SharePoint·Excel·Outlook 등 외부 시스템에 미리 만들어진 방식으로 연결하는 도구.

### MCP (Model Context Protocol) `#mcp`
{: #mcp }
외부 서버가 제공하는 도구·리소스를 표준화된 방식으로 에이전트에 연결하는 프로토콜. 온보딩 위저드로 기존 서버에 쉽게 연결할 수 있다.

### 커스텀 커넥터 `#custom-connector`
{: #custom-connector }
OpenAPI/Swagger로 API 스펙을 직접 정의해 만드는 나만의 커넥터. 표준 커넥터·MCP보다 제작 난이도가 높다.

### 생성형 오케스트레이션 `#generative-orchestration`
{: #generative-orchestration }
사용자 입력을 보고 에이전트가 알아서 지식·도구·토픽을 조합해 응답하는 방식.

### 토픽 (Topic) `#topic`
{: #topic }
정해진 트리거 문구에 정확히 반응하는 결정론적 대화 단위. 생성형 오케스트레이션과 대비된다.

### 트리거 문구 `#trigger-phrase`
{: #trigger-phrase }
토픽을 실행시키는 정해진 입력 문구(또는 유사 표현).

### Question 노드 `#question-node`
{: #question-node }
토픽 안에서 사용자에게 질문을 던지고 응답을 변수로 받는 빌딩 블록.

### 변수 (Variable) `#variable`
{: #variable }
토픽 안에서 사용자 응답이나 도구 결과에 이름을 붙여 담아두는 값. 문장 속으로 사라지지 않고 다음 노드에서 다시 쓸 수 있다.

### Adaptive Card `#adaptive-card`
{: #adaptive-card }
평문 대신 구조화된 카드 형태로 응답을 보여주는 메시지 형식.

### 연결된 에이전트 `#connected-agent`
{: #connected-agent }
다른 에이전트를 도구처럼 등록해 호출하는 방식. 부모 에이전트는 자식의 내부(지식·지침)를 보지 못하고 **설명(Description)** 한 문단만 읽어 호출 여부를 판단하므로, 이 설명이 사실상 라우팅 인터페이스가 된다.

### 에이전트 흐름 (Agent flow) `#agent-flow`
{: #agent-flow }
토픽의 액션 노드에서 호출할 수 있는, 실제 시스템 상태를 바꾸는 트랜잭션 실행 도구. 초급에서는 존재만 확인한다.

### HITL (Human-in-the-loop) `#hitl`
{: #hitl }
자동화 과정에 사람의 승인·확인이 개입하는 지점. 비동기(승인)와 대화형(확인) 두 패턴이 있다. 중급 과정 주제.

<!-- 저작 메모: 중급 용어집과 겹치는 항목(HITL, 커넥터 등)은 정의를 최대한 맞춰서
     학생이 2일차로 넘어갈 때 위화감이 없도록 할 것.
     id는 kramdown 헤더 IAL({: #id })로 명시 지정 — auto_ids(한글 텍스트 기반 자동 id)에
     의존하면 URL이 퍼센트 인코딩되어 깨지기 쉬워서, 전부 영문 kebab-case로 고정함.
     다른 Lab 페이지에서 링크할 때: [지식](../glossary.html#knowledge) 형식으로 사용. -->
