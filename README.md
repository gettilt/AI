<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(f"# {config['name'].title()}")
]]]-->
# Ai
<!--//[[[end]]]-->

## Mission

Tilt's mission is to map every theme to a basket of stocks for anyone to invest in. Mappings are AI generated and expert curated.
Expert improvements are accepted if they provide a better representation of a given theme.

## Theme Prompt
<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(config['prompt'])
]]]-->
Artificial intelligence is the next big technological innovation that will have a positive impact on chip manufacturers, data companies, data centers, and power generation companies.
<!--[[[end]]]-->

## Theme Stocks

<!--[[[cog
import cog
import csv
import json

with open('context.json') as file:
  contexts = json.load(file)

def _get_context_str_for_ticker(ticker):
  try:
    context = contexts[ticker]
    context_str = context['chat_gpt'] or context['claude'] or ""
  except KeyError:
    context_str = ""

  return context_str

cog.outl("| Ticker  | Context | Source |")
cog.outl("| ------- | ---- | ---- |")

with open('theme.csv') as file:
  reader = csv.reader(file)
  next(reader) # skip the header
  for row in reader:
    context_str = _get_context_str_for_ticker(row[0])
    cog.outl(f"| {row[0]} | {context_str} | {row[1]} |")
]]]-->
| Ticker  | Context | Source |
| ------- | ---- | ---- |
| ADBE | Adobe integrates AI into its creative software suite, enhancing user experience and productivity. | chat_gpt |
| AMD | Advanced Micro Devices produces high-performance processors and GPUs that are critical for AI workloads. | chat_gpt,claude,twitter,google |
| AMZN | Amazon benefits from AI through its AWS cloud services, which offer AI and machine learning tools, and its AI-driven logistics and recommendation systems. | chat_gpt,claude,twitter,google |
| BABA | Alibaba employs AI in its e-commerce platform, logistics, and cloud computing services. | chat_gpt |
| CRM | Salesforce uses AI to enhance its CRM software, providing advanced analytics and automation for businesses. | chat_gpt,claude |
| GOOGL | Alphabet's Google is heavily invested in AI research and development, with applications across its search engine, cloud services, and more. | chat_gpt,claude,google |
| IBM | IBM is a pioneer in AI with its Watson platform, which offers AI solutions for various industries. | chat_gpt,claude,google |
| MSFT | Microsoft is a major player in AI through its Azure cloud platform and AI-driven products like Cortana and Office 365. | chat_gpt,claude,google |
| NVDA | NVIDIA is a leading manufacturer of GPUs, which are essential for AI processing and machine learning applications. | chat_gpt,claude,twitter,google |
| PLTR | Palantir Technologies offers AI-driven data analytics platforms for government and commercial clients. | chat_gpt,claude |
| SNOW | Snowflake provides cloud-based data warehousing solutions that leverage AI for data analytics and management. | chat_gpt,claude,twitter |
| SQ | Square leverages AI for fraud detection, customer insights, and financial services. | chat_gpt |
| TSLA | Tesla uses AI for its autonomous driving technology and energy solutions, making it a direct beneficiary of AI advancements. | chat_gpt,google |
| AI | C3.ai provides enterprise AI software for various industries, offering a comprehensive platform for developing and deploying AI applications. | claude,google |
| AMAT | Applied Materials supplies equipment used in the manufacturing of AI chips, benefiting from the expanding production of these specialized processors. | claude |
| ASML | ASML Holding offers advanced lithography systems that are crucial for the production of cutting-edge AI chips, making it a key beneficiary of the AI chip boom. | claude |
| DLR | Digital Realty Trust owns and operates data centers that host AI workloads and support AI-driven businesses, benefiting from the growing demand for AI infrastructure. | claude,google |
| EQIX | Equinix operates data centers that support AI infrastructure and connectivity, providing the foundation for businesses to run AI workloads and collaborate on AI projects. | claude,google |
| LRCX | Lam Research provides chip manufacturing equipment, experiencing growth as chipmakers ramp up production of AI-optimized chips. | claude |
| MU | Micron Technology manufactures memory chips that are essential components in AI systems and data centers, seeing increased demand as AI adoption grows. | claude |
| QCOM | Qualcomm produces AI-enabled chips for mobile devices and edge computing, benefiting from the proliferation of AI in smartphones and IoT devices. | claude |
| ARM |  | twitter |
| CRNC |  | twitter |
| SMCI |  | twitter,google |
| TSM |  | twitter,google |
| ANET |  | google |
| CRWD |  | google |
| PANW |  | google |
| SOUN |  | google |
| DELL |  | experts |
| CEG |  | experts |
| ETN |  | experts |
<!--[[[end]]]-->

## License

<p>
This project is licensed under <a href="./LICENSE">AGPLv3</a>.
</p>


## Contributors

Thank you for your improvements! We appreciate all the contributions from the community.

<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  repo = config['github_repo'].lower()
  cog.outl(f'<a href="https://github.com/gettilt/{repo}/graphs/contributors">')
  cog.outl(f'  <img src="https://contrib.rocks/image?repo=gettilt/{repo}" />')
  cog.outl('</a>')
]]]-->
<a href="https://github.com/gettilt/ai/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=gettilt/ai" />
</a>
<!--[[[end]]]-->

## Join Our Community

<a href="https://discord.gg/4vYMhRpaMY" target="_blank">
<img src="https://discord.com/api/guilds/1179775688421683220/widget.png?style=banner3" alt="">
</a>
