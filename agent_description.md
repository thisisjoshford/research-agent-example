### Research Agent

The Research Agent is an AI-powered service that conducts comprehensive research and generates detailed reports based on user queries. It leverages the GPT Researcher library to gather information from various sources and synthesize it into structured reports.

#### Main Functions

*   **Conduct Research**: Takes a user query and a specified report type (e.g., research report, resource report, outline report) and performs in-depth research.
*   **Generate Reports**: Produces a comprehensive report based on the conducted research, including a summary, relevant findings, and cited sources.
*   **Provide Research Metadata**: Returns information such as the number of sources used and the estimated cost of the research.
*   **Health Check**: Offers an endpoint to verify the agent's operational status and API key configurations.

#### Inputs

*   **Medium**: HTTP POST request
*   **Endpoint**: `/research`
*   **Payload**: JSON object with the following fields:
    *   `query` (string, required): The topic or question for which to conduct research.
    *   `report_type` (string, optional): The desired type of report (e.g., "research_report", "resource_report", "outline_report"). Defaults to "research_report".

#### Outputs

*   **Medium**: HTTP JSON response
*   **Payload**: JSON object containing:
    *   `report` (string): The generated research report in Markdown format.
    *   `sources` (list of strings): A list of URLs or identifiers for the sources used in the research.
    *   `costs` (dict): A dictionary detailing the estimated costs, including `total_cost` (float) and `total_tokens` (int).
    *   `num_sources` (int): The total number of unique sources identified and used.

#### Environment Variables

*   **`OPENAI_API_KEY`**: Your OpenAI API key, essential for the GPT Researcher to access language models.
*   **`TAVILY_API_KEY`**: Your Tavily API key, required for search and information retrieval during the research process.