# Dashboard Engagement Project

Author: Omer Ansari

Initialize date: 5.27.24



### Summary 
The code repository where I document the experience and learnings from developing a medium complexity software project using an LLM-based multi-agentic framework. 
Specifically, this software project is focused on building out an API which serves engagement statistics of dashboards used by a firm for useful operational and analytical purposes.

This project has been opensourced under the Apache license.


### Business Goal: 
I want to be able to easily pull real-time or historical, usage activity of visualization dashboards being used, such as the number of users logged in, or the names and other metadata (org,title etc) of the users. Operationally this is helpful to know when we need to make administrative changes to these dashboards, or when there is an outage going on we can pull from histoical data to see the details on counts and peoeple who were last logged on before this issue started. 

Analytically this has use cases in identifying what are top N dashboards and the bottom N dashboards in terms of engagement and importance. This helps reduce dashboard sprawl, and also helps identify which dashboards are the most important for any firm so internal customer workshops can be run (based on top users) , get their feedback for improvements, gripes and other enhancements. Another analytical utility is to tie this dashboard engagement metadata with data lineage in any data warehouse. Typically, lineage stops at the target table and many mid/large companies are unaware of the exact importance of the data being pulled from the source in terms of which dashboards are using them, who is actually consuming that data, and the changing usage and demographics of the dashboard's internal customer base.

### Technical Goal:
The application is not that complicated to build. However, I want to build this application differently!

I'll be using (generative AI) LLM-based multi-agent frameworks (MAFs). The reason behind this is to experiment and measure the gaps in developing software projects using the state of the art generative AI frameworks today. The only way to deeply  understand these gaps is to attempt a real-world project. 

I anticipate that there is specific amount of pre-work required to be done by humans to make these MAFs actually useful, which can include setting up a backing database for persistent storage, setting up the MAF (such as crew.ai, agentlite, autogen), choosing the appropriate LLM (GPT4, Gemini, or Open source LLMs), writing tools (helper functions) for LLMs to access the various systems human developers and product managers typically interact with, and also identifyng the level of grain needed for prompt construction to get decent work output including the appropriate AI agent team roles required to be set up. This is an initial up front cost of setup for sure, but I predict that once this is set up, this "team-in-a-box" approach can start yielding multiple applications with relatively lower lift.


Back to this project:

### Hypothesis of this project
If robust APIs exist for the dashboard, the backing database and the API platform (and the pre-work has been done to to make these LLM MAFs useful), we can let these MAFs explore, test, and deploy these APIs themselves with a little human tuning along the way. 

Then, replacing the technologies with any others would be straightforward since the actual interaction with these back end systems will be coded by these brilliant LLMs.

However, we have to start somewhere, so I have chosen a few backend technologies to ground this testing. I have however done some rudimentary assessment on where this project can be expanded into other technologies and linked those below

### Tech used

- **Dashboard platform:** Tableau. _other [possibilities](dashbard_platforms.md)_
- **API platform:** Mulesoft. _other [possibilities](api_platforms.md)_
- **Backing database:** Snowflake.  _other [possibilities](db_platforms.md)_


### API spec and Software Design

I interacted with the Software Architect GPT (By V B Wickramasinghe) available as one of the many fine-tuned models within chatgpt.com (available if you have a paid subscription) . I suspect I'd have gotten similar output interacting with the generic pre-trained model as well, but likely would have had to spend a lot more turns to get it right.

- API [specification](api_spec.md)
- Software [architecture](sw_arch.md)

To create the diagram in the software architecture, I used Tim Kitchen's [video](https://www.youtube.com/watch?v=YaqXF5UeRQE) where he shows how to use GPT to build software design documents using plantuml and then feed them to draw.io.

