To enable GenAI PremBridge for Pega GenAI services in Client-managed cloud or on-premises deployments, follow these steps:
________________________________________
1. Ensure Prerequisites Are Met
•	Pega Platform 8.8.3 or later is required.
•	Your environment must be able to access the internet (outbound) to reach the Pega GenAI APIs.
•	You must have an active Pega GenAI license and access to API keys from Pega.
________________________________________
2. Obtain API Credentials from Pega
Request your GenAI API key and endpoint configuration from Pega through your account manager or via MySupport.
________________________________________
3. Configure PremBridge in Pega
You’ll be setting this up via Dev Studio:
a. Enable the PremBridge
Navigate to:
Records > SysAdmin > Dynamic System Settings
Update or add:
•	genAI/premBridge/enabled → true
b. Set API Endpoint and Key
Use DSS entries:
•	genAI/premBridge/apiEndpoint → your endpoint (e.g., https://genai.pega.com/api)
•	genAI/premBridge/apiKey → your provided key (store securely)
________________________________________
4. Validate the Configuration

https://docs.pega.com/bundle/platform/page/platform/data-integration/integrating-client-managed-cloud-pega-genai.html




