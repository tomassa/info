
- system prompts - typically remain hidden from the user and tell the model its identity, behavioral guidelines, and specific rules to follow
- "Plan a two-week trip to Portugal, emphasizing local culture, hidden gems, authentic cuisine, and avoiding crowds."
  - "I have 10 minutes, teach me about a new topic"
  - "Compare the top-rated robot vacuums under $300, considering user reviews, battery life, cleaning ability, and ease of maintenance."
  - "Simplify and explain quantum computing and its possible impacts in everyday life over the next decade."
  - Breaking your instructions down into a list or steps.. provide examples
  - coding: "Add a new feature that accepts payments” or “Write tests for this code"
    Step 1: Write a comprehensive plan for a new feature that accepts payments.
    Use these relevant files and folders as context: < provide to LLM >
    DO NOT WRITE ANY CODE YET. JUST WRITE A PLAN.
    Step 2: Great. The plan looks good. Go step-by-step through each part of the plan and implement it.
    "Think like a { system architect or principal engineer"
    "As we plan this, ask me questions one at a time. I prefer yes or no questions"
    "Generate a spec.md that comprehensively documents all the requirements and a plan of what needs to be done."
    "Now that we have spec.md, create another file called prompts.md that provides the series of prompts needed to effectively implement the spec"
     what level of detail it should provide in documentation
     “Come up with 3 potential reasons why this bug is happening.” and once you picked "Provide a detailed plan for this implementation"
    add examples - "modify it to behave like the other admin functions"
    1.Generate a “migration_list.md” file with the list of files it needs to migrate. It should update and remove files as they’re migrated.
    2.Generate a separate “migration_context.md” file that stores all the key “before” and “after” patterns it needs to know to do the migration effectively.
    3.Ask it to go through each file from the “migration_list” file and use the information from “migration_context.md” to carry out the migration. It should add to the “migration_context.md” file as it encounters new problems and solutions it needs to overcome.
    push LLM to work methodically -> like updating references to migrated files, ask it to create an automated script it can simply call
- Summarizer:
	- “_Summarize this text in 3 bullet points.”_ 
	- “Rewrite this news story in under 75 words.”
- Rephrase:
	-  _“Rewrite this email to sound more confident but still friendly.”_
	-  _“Turn this paragraph into a tweet.”_
- Brainstorm:
	-  “Give me 10 blog post ideas for a productivity website.”
	-  “What are some unique ways to promote a book about burnout?”
- Compare:
	-  _“Pros and cons of switching from_ [_Notion_](https://www.tomsguide.com/ai/i-ditched-gmail-for-notion-mail-for-3-weeks-heres-what-its-like-to-use-ai-powered-email) _to_ [Google Keep
	-  _“Give me a chart comparing the cost of these three gym memberships.”_
- Role-play:
	- _“Act like a nutritionist. Create a 7-day meal plan for someone with no time to cook.”_
	- _“Pretend you’re an ultra-picky hiring manager. Review this résumé and list red flags.”_

- _"I am building an agent to analyze research papers and create consolidated summaries. I typically process 5 research papers at a time, each containing approximately 5,000-10,000 words. My input is only text (PDFs converted to text), and the output will be a summary in text. I'm fine with API-based models since these are public research papers with no privacy concerns. Processing time isn't critical - I can wait 30-60 seconds for quality results. Accuracy is more important than speed for this use case, also start with models having minimum cost. Based on these requirements, which model would you suggest?"_
- “Compose an effective cover letter for a marketing position, emphasizing social media experience and a beer campaign; the tone should be friendly and confident.”
- "Here's a list of random food left in my fridge, give me a recipe that doesn't require a grocery store trip."
- roleplaying: asked it to "mimic a Dustin Hoffman pirate voice to ask my boys to quickly put on their PJs and join the Captain for a bedtime book."
- "Based on what you know about my business, what do you predict an investor or potential buyer would critique about it? Take a hard, objective look at my business model, growth strategy, team structure, and systems. Identify the 3 biggest red flags that would make them hesitate. Then suggest specific fixes that would not only address these concerns but turn them into strengths that could increase my company's valuation."
- llama-prompt-ops - tool optimizing prompts for llama from proprietary models for better performance
- "make a table that included all of the items on the sushi menu, with price information, organize it into three columns: item, description, price"
- in google sheets: "calculate the weighted average of values in column E, where the weights are in column F, but only for items belonging to "category A" in column D"
- "what does this formula do?" "why isnt this formula working right?"