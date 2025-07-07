AI Solution / Agent
- Multiple LLM calls
- LLMs with ability to use Tools
- An environment where LLMs interact
- A Planner to coordinate activities
- Autonomy

Agentic Systems
- https://www.anthropic.com/engineering/building-effective-agents
- Workflows are systems where LLMs and tools are orchestrated through predefined code paths
  - 보통 사람들이 말하는 Agentic system은 사실 이 Workflow를 말하는 경우가 많다.
- Agents are systems where LLMs dynamically direct their own processes and tool usage, maintaining control over how they accomplish tasks

---

Workflows
- Prompt chaining: decompose into fixed sub-tasks
- Routing: direct an input into a specialized sub-task, ensuring separation of concerns
- Parallelization: Breaking down tasks and running multiple subtasks concurrently
- Orchestrator Worker: Complex tasks are broken down dynamically and combined
- Evaluator Optimizer: LLM output is validated by another

---

Agents
- Workflows에 비해 가진 3가지 특징
  - 1. Open ended
  - 2. Feedback loops
  - 3. No fixed path
  - `while (true)` 문 같은 것
    - 특정 조건에 맞다고 판단되면 알아서 LLM이 멈추는 것
    - 멈추기까진 액션 & 피드백의 무한 반복
- 무조건 좋은 것은 아님
  - Unpredictable path
  - Unpredicatable output
  - Unpredicatable costs
  - 예상 불가능하고, 비용도 얼마나 나올지 모르고, 결과 퀄리티 보장도 못하고, 언제 종료 될지 모름
  - 이런 것을 생각하면서 막도록 개발하거나 보완책이 있어야 함
- 보완책
    - Need Monitoring
        - 뭐가 진행되고, 에이전트 간에 어떻게 인터렉션을 하고 있는지... 등등 에이전트 시스템에서 무엇이 일어나고 있는지 알 수 있어야 함
    - Guardrails
        - 모델이 해서는 안되는 것들을 정의하고, 그것들을 보호하기 위한 것