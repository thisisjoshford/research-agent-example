### Research Agent

The Research Agent is an AI-powered service that conducts comprehensive research and generates detailed reports based on user queries. It leverages the GPT Researcher library to gather information from various sources and synthesize it into structured reports.

**Main Functions:**
*   **Conduct Research**: Takes a user-defined query and a specified report type (e.g., research report, resource report, outline report) to perform in-depth research.
*   **Generate Reports**: Produces well-structured reports based on the gathered information.
*   **Source Citation**: Provides a list of URLs for the sources used in the research.
*   **Cost Estimation**: Calculates and returns the estimated cost of the research operation.
*   **Web Interface**: Offers a user-friendly web interface for submitting research queries and viewing results.

**Inputs:**
*   **HTTP POST /research**:
    *   `query` (string): The topic or question to research.
    *   `report_type` (string, optional): The type of report to generate (e.g., "research_report", "resource_report", "outline_report"). Defaults to "research_report".

**Outputs:**
*   **HTTP JSON Response from /research**:
    *   `report` (string): The generated research report content.
    *   `sources` (list of strings): A list of URLs from which information was retrieved.
    *   `costs` (object): An object detailing the research costs, including `total_cost` (float) and `total_tokens` (int).
    *   `num_sources` (int): The total number of sources identified.

**Environment Variables:**
*   **OPENAI_API_KEY**: Your OpenAI API key, essential for the agent's language model interactions.
*   **TAVILY_API_KEY**: Your Tavily API key, required for searching and retrieving information from the web.

**Note:** Both `OPENAI_API_KEY` and `TAVILY_API_KEY` are mandatory for the agent to function correctly.