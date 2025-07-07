Agentic AI Frameworks
- LangGraph, AutoGen
  - heavy weight
  - 큰 만큼 여러가지 많은 기능을 제공함
- OpenAI Agents SDK, Crew AI
  - 가벼운 Framework
- No framework, MCP
  - MCP는 framework 아님. Protocol임.

19번 강의
- 단순히 채팅 앱을 구현할 때, LLM으로부터의 답변을 바로 사용하지 말고, 다른 LLM Model을 사용해 Evaluator를 구현하면 좋다.
- System Prompt와 답변을 함께 주고, 이거 합당한 대답이야? 만약 그렇거나/안그렇다면 그 이유는 뭐야? 를 같이 물어보고 대답을 받아온다.
- `gemini.beta.chat.completions.parse(model="gemini-2.0-flash", messages=messages, response_format=Evaluation)` 여기처럼 `response_format`을 명시하면 따로 어떤 응답 형태로 답변을 줘. 같은 것을 명시하지 않아도 알아서 넣어줌.
- 이 대답을 이용해 rerun 등 여러 액션을 취할 수 있다. 이러면 애플리케이션 자체의 안정성이나 품질이 올라갈 수 있음 (훨씬 좋음)