OpenAI 관련해 들어가기 전에 Python asyncio를 훑고 감.
- All your methods and functions start async
- Anytime you call them, use await

```python
async def do_some_procesing -> str:
    return "done!"

result = await do_some_processing()
```
위와 같이 구성할 수 있음
- javascript랑 비슷한 형태

매우 Lightweight 하다고 함
- 실제 OS 레벨의 스레드가 아니라 파이썬 내부적으로 굴리는 듯
- Like coroutines
- 내부적으론 event loop 두고 async function(corutine)을 넣고 돌림.
- 강의에서 async def 붙으면 그냥 함수가 아니라 coroutine으로 인식하면 된다는데, coroutine이라는 이름이 python에도 적용되는 거구나? 코틀린꺼 아니였나?

OpenAI 같은 LLM을 사용하다보면 Network I/O Waiting이 엄청 큼. 그러다보니 이러한 async 하게 구성하는 것이 필수적인 듯.
- 멀티 에이전트 형식에서는 더 크게 다가올 것.

```python
results = await asyncio.gather(
    do_some_processing(),
    do_other_processing(),
    do_yet_more_processing()
)
```
위와 같이 모아서 처리도 가능함.
- CompletableFuture.allOf 느낌

---

OpenAI Agents SDK
- Lightweight and flexible
- Stays out of the way
- Makes common activities easy

Minimal terminology
- Agents represents LLMs
- Handoffs represent interactions
- Guardrails represent controls

Three steps
- Create an instance of Agent
- Use `with trace()` to track the agent
- Call `runner.run()` to run the agent

첫 번째 궁금증이 OpenAI Agent SDK이니 OpenAI 모델만 사용 가능한가? 였는데
- 당연히 아니라고 함. 다양한 모델을 지원하는데, 차차 배워가기로 함.