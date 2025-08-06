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




When evaluating whether a Pega application is simple or complex, there are several parameters you should consider. Complexity in a Pega application is influenced by technical, functional, and operational factors. Here’s a categorized breakdown of the key parameters:

⸻

🔧 Technical Complexity Parameters

Parameter	Simple Application	Complex Application
Case Types	1–2 primary case types, minimal sub-cases	Multiple case types, complex parent-child relationships
Integrations	Few or no external integrations	Many integrations (REST, SOAP, MQ, databases, etc.)
UI Complexity	Basic UI, minimal customization	Heavily customized UI, dynamic layouts, custom JavaScript
Data Model	Flat, few data types and properties	Deep data hierarchy, extensive use of data pages, inheritance
Decisioning	Basic routing and flow logic	Advanced decision strategies, Next-Best-Action, AI/ML
Ruleset Structure	Few rulesets and versions	Multiple layers (e.g., Framework, Implementation), many versions
Performance Tuning	Minimal optimization required	Performance optimization critical, indexing, caching needed
Security	Basic role-based access	Complex role-based access control (RBAC), attribute-based access control (ABAC), data masking
Deployment	Simple deployment cycle, few environments	Multiple environments (DEV, QA, SIT, UAT, PROD), CI/CD pipeline


⸻

🔄 Functional Complexity Parameters

Parameter	Simple Application	Complex Application
Business Rules	Few, mostly out-of-the-box rules	Hundreds of complex business rules
Workflow	Linear process flows	Multiple stages, conditional paths, parallel processes
SLAs	One or two SLAs	Multiple SLAs across stages, escalation rules
User Roles	Few roles with clear boundaries	Many roles, cross-functional access needs
Reporting	Few standard reports	Complex reporting, real-time dashboards, custom analytics


⸻

🧠 Operational & Governance Parameters

Parameter	Simple Application	Complex Application
Change Management	Low frequency of changes	Continuous changes and enhancements
Team Size	Small team (1–3 developers)	Large teams with multiple skill sets
Stakeholder Involvement	Single department, limited stakeholders	Multiple departments, high stakeholder interaction
Testing Effort	Minimal manual testing	Automated testing, performance testing, regression
Compliance Requirements	Low or none	Strict audit, compliance, data privacy requirements


⸻

✅ Summary: Indicators of a Complex Pega Application
	•	Multiple integrations with external systems
	•	Complex case hierarchies and dynamic routing
	•	Custom UI components and non-standard UX patterns
	•	Advanced decisioning, AI models, or Pega Customer Decision Hub
	•	High-performance and scalability requirements
	•	Multi-layered security (RBAC + ABAC)
	•	Heavy use of data transforms, activities, and custom Java code

⸻

Would you like a template or checklist you can use to evaluate a Pega project’s complexity?




