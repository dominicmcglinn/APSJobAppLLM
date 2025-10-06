APS JobAppLLM Agents Guide

This Agents.md file complements the human‑friendly README.md by giving coding agents clear instructions and context for working within this project.  It provides a predictable location for information that would clutter a regular README but is essential for AI tools ￼.  You can adapt and extend it as the project evolves.

Project Overview

APS JobAppLLM is a multi‑stage AI system designed to assist Australian Public Service candidates through every stage of a government job application.  The repository contains a series of markdown prompts (stages/) that guide a large language model through job analysis, application drafting, interview simulation and reflection.  The workflow is orchestrated via the aps_jobappllm_pipeline.yaml file and produces plain‑text outputs in the outputs/ folder.

Repository Structure
	•	/stages/ – Prompt definitions for each stage (1 through 4).  Each file begins with a header describing the agent’s role and step‑by‑step instructions.
	•	/outputs/ – Automatically generated text files from each stage of the pipeline.  Running the workflow will populate this directory.
	•	/library/ – Reference documents used to ground the agents (e.g. APS Work Level Standards and APS Values).
	•	/aps_jobappllm_pipeline.yaml – YAML workflow file that chains the stages together.  When using an orchestrator like LangChain or CrewAI, load this file to run the entire pipeline.
	•	/Agents.md – This file, for coding agents.
	•	/README.md – Human‑focused overview of the project, with installation and usage instructions.
	•	/.env.template – Template for environment variables such as API keys.

Setup and Execution
	1.	Install dependencies:  The pipeline does not require compilation, but you should have a compatible language model API key available in a .env file.  Copy .env.template to .env and populate the required fields (OPENAI_API_KEY, MODEL, etc.).
	2.	Run the pipeline:  Use your orchestrator to execute aps_jobappllm_pipeline.yaml.  For example:
bash
langchain run aps_jobappllm_pipeline.yaml
Each stage will read the relevant input and write its output under /outputs/.

	3.	Run a single stage:  You can run individual stage prompts by loading the corresponding markdown file into your agent.  This is useful for debugging or extending the system.

Coding and Style Guidelines
	•	All stage prompts are written in Markdown.  Maintain clear headings (#, ##) and numbered lists; avoid excessive tables, and keep sentences short.
	•	Stage outputs must be plain text with no markdown formatting, as specified in the prompts.  This simplifies ingestion by subsequent stages.
	•	When modifying the YAML workflow, preserve the existing stage order and update the next pointers accordingly.
	•	Keep this Agents.md concise and focused.  Follow the guideline to provide only the context and instructions needed by the agent, leaving human‑oriented details in the README ￼.
	•	There are no required headings or fields; feel free to add sections that improve agent understanding of your project ￼.

Testing and Validation

This repository does not include automated tests.  To validate changes:
	•	Run the full pipeline using your orchestrator and ensure that all stages complete without errors.
	•	Inspect the generated files in /outputs/ for accuracy and compliance with the APS guidelines.
	•	When adding a new stage, create a new file in stages/ and append its definition to the YAML with proper ordering.

Pull Request Guidelines

To maintain consistency:
	1.	Prefix commit messages with the stage being modified, e.g. [stage3] Refine follow‑up questions.
	2.	Ensure that any new stage prompt includes:
	•	A clear agent role description.
	•	Step‑by‑step instructions.
	•	An output structure that downstream stages can parse.
	3.	Before submitting a PR, run the pipeline to confirm that the changes do not break other stages.

Security and Confidentiality
	•	Never commit API keys or sensitive user data.  Use the .env file for secrets and add it to .gitignore.
	•	The pipeline may process candidate resumes and interview transcripts.  Treat this information confidentially and follow APS privacy requirements.

Extending the System
	•	To add a new stage, create a new Markdown file in stages/ with a descriptive name.  Update aps_jobappllm_pipeline.yaml to include the stage and specify the correct input and output files.
	•	Use nested Agents.md files if you add sub‑projects or separate packages.  Coding agents will read the nearest Agents.md first ￼.

FAQ
	•	Are there required fields in Agents.md?  No.  Agents.md is just standard Markdown; use any headings that help an agent work effectively ￼.
	•	Can this file be updated?  Yes.  Treat Agents.md as living documentation.  Update it whenever you change the repository structure, workflow or coding conventions.

⸻

This Agents.md file is intentionally scoped to agent‑facing instructions.  For human‑friendly details, see the README.
