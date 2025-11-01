# Answers to Part 3

Add your answers to the questions in Part 3, Step 2 below. 

## Vulernability Remediation:
### Vulnerability 1: 
1. Which package or library are you addressing?
	Scout-report.sarif: "pkg:pypi/pyyaml@5.1"

2. Which CVE is linked to this vulnerability?
	"CVE-2019-20477: Deserialization of Untrusted Data". Basically this vulnerability can allow for
	an attacker to trick the application into loading malicious YAML content.

3. What remediation steps do you suggest?
	Based on what I see in the text and affected versions, I would upgrade the PyYAML to 5.2 or better
	since it says the affected versions are >=5.1, but <5.2. It also says it has to do with the load and 
	load_all functions so I think using safe_load would be a better option.

### Vulnerability 2:
1. Which vulnerability are you addressing?
	Trivy-report.sarif: python-gunicorn. It does not show a specific version for this but I assume a 
	version that is less than 22.0.0 since that is what the fix is.

2. Which CVE is linked to this vulnerability?
	"CVE-2024-1135": "LanguageSpecificPackageVulnerability". This is an HTTP Request Smuggling issue 
	due to improper validation of Transfer-Encoding headers.

3. What remediation steps do you suggest? 
	The listed fix is to upgrade the gunicorn version to 22.0.0 or higher which should take care of the 
	problem immediately. However, if for whatever reason someone is not able to do that right away, they could
	try putting Gunicorn behind a reverse proxy so that it can reject requests that have multiple or invalid 
	transfer-encoding headers.
