### Research Agent

The Research Agent is a web-based service that conducts comprehensive research and generates detailed reports using the GPT Researcher library. It provides a user-friendly interface to initiate research queries and visualize the results, including the generated report, source URLs, and estimated costs.

**Main Functions:**

*   **Conduct Research**: Takes a user-defined query and a specified report type (e.g., research report, resource report, outline report) to perform in-depth research. It gathers information from various sources and compiles it into a structured report.
*   **Report Generation**: Generates a detailed report based on the conducted research, summarizing findings and providing relevant insights.
*   **Source Tracking**: Identifies and lists the URLs of all sources used during the research process.
*   **Cost Estimation**: Provides an estimate of the cost associated with the research, including total cost and token usage.
*   **Health Check**: Offers an endpoint to verify the service's operational status and API key configurations.

**Inputs:**

*   **HTTP POST to `/research`**:
    *   `query` (string): The research topic or question.
    *   `report_type` (string, optional): The type of report to generate (e.g., "research_report", "resource_report", "outline_report"). Defaults to "research_report".

**Outputs:**

*   **HTTP JSON from `/research`**:
    *   `report` (string): The generated research report content.
    *   `sources` (list of strings): A list of URLs for the sources used.
    *   `costs` (dictionary): Contains `total_cost` (float) and `total_tokens` (int) related to the research.
    *   `num_sources` (int): The total number of research sources found.
*   **HTTP HTML from `/`**: Serves a web-based user interface for interacting with the agent.

**Environment Variables:**

*   `OPENAI_API_KEY`: Your OpenAI API key, essential for the agent's research capabilities.
*   `TAVILY_API_KEY`: Your Tavily API key, likely used for search and information retrieval.