# potential-engine
GitHub の最初のリポジトリ


```python
from langchain.chat_models import ChatOpenAI
from langchain.agents import load_tools, initialize_agent
from langchain.agents import AgentType
from langchain.tools import AIPluginTool
from langchain.agents.agent_toolkits import NLAToolkit
from langchain.memory import ConversationBufferMemory
llm = ConversationBufferMemory(memory_key="chat_history", return_messages=True)
tools = NLAToolkit.from_llm_and_url(llm, "https://0d86-103-227-97-4.ngrok.io/openapi.yaml").get_tools()
initialize_agent(tools, llm, agent="chat-conversational-react-description", verbose=True)
agent_chain = ChatOpenAI(temperature=0)
print(agent_chain.run("Show me some memes along with their corresponding url"))
agent_chain.memory = memory```
