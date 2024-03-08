# LangChain-Exercise
The following exercise attempts to use LLM to perform information extraction. The webpage https://techcrunch.com/2023/10/27/x-is-launching-new-premium-and-basic-subscription-tiers/ was used as the context to retrieve:

1. Topic of the article
2. Related Companies mentioned within the article

### Goal
JSON Structure as follows:

{
"related_companies": [{ "company_name":"X", "company_domain":"x.com" }, { "company_name":"Bloomberg", "company_domain":"bloomberg.com" }], 
"topic":"X is launching two new subscription tiers, including a ‘Premium+’ ad-free plan"
}


### Setup
1. Model: TheBloke/Llama-2-13b-Chat-GGUF
2. BeautifulSoup - for HTML content parsing
3. LangChain - for inference pipeline and output parsing

### Approach
1. Extract content of the webpage via BSHTMLLoader from LangChain
2. Extract hrefs (URLs) from the HTML using BeautifulSoup
3. Get a list of companies mentioned within the article via Prompt Engineering
4. Get a JSON mapping of companies to company domain through Prompt Engineering by passing in hrefs extracted and the list of companies from step 3.
5. Get the topic of the article as a JSON structure via Prompt Engineering
6. Combine the company JSON and topic JSON into one and parse it as a Pydantic BaseModel Object.

<ins>Video below to demonstrate the output after execution:</ins>


https://github.com/lclementx/LangChain-Exercise/assets/55295757/c1e79679-4b23-4347-a8dd-533f3f8a94a4

