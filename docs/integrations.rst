Integrations
============

DefectDojo has the ability to import reports from other security tools.

Acunetix Scanner
----------------
XML format.

Anchore-Engine
--------------
JSON vulnerability report generated by anchore-cli tool, using a command like ``anchore-cli --json image vuln <image:tag> all``

Aqua
----
JSON report format.

Arachni Scanner
---------------
Arachni JSON report format.

AppSpider (Rapid7)
------------------
Use the VulnerabilitiesSummary.xml file found in the zipped report download.

AWS Security Hub
----------------
The JSON output from AWS Security Hub exported with the [`aws securityhub get-findings`](https://docs.aws.amazon.com/cli/latest/reference/securityhub/get-findings.html) command.

AWS Scout2 Scanner
-------------------
JS file in scout2-report/inc-awsconfig/aws_config.js.

AWS Prowler Scanner
-------------------
Prowler file can be imported as a CSV file (-M csv).

Bandit
------
JSON report format

Blackduck Hub
-------------
2 options:
* Import the zip file as can be created by Blackduck export. The zip file must contain the security.csv and files.csv in order to produce findings that bear file locations information.
* Import a single security.csv file. Findings will not have any file location information.

Brakeman Scan
-------------
Import Brakeman Scanner findings in JSON format.

Bugcrowd
-------------
Import Bugcrowd results in CSV format.

Bundler-Audit
-------------
Import the text output generated with bundle-audit check

Burp XML
--------
When the Burp report is generated, **the recommended option is Base64 encoding both the request and response fields** - e.g. check the box that says "Base64-encode requests and responses". These fields will be processed and made available in the 'Finding View' page.

Burp Enterprise Scan
--------------------
Import HTML reports from Burp Enterprise Edition

CCVS Report
-----------
Import JSON reports from [CCVS API](https://github.com/William-Hill-Online/CCVS-API)

Checkov Report
--------------
Import JSON reports of Infrastructure as Code vulnerabilities.

Clair Scan
----------
Import JSON reports of Docker image vulnerabilities.

Clair Klar Scan
---------------
Import JSON reports of Docker image vulnerabilities from clair klar client.

Cobalt.io Scan
--------------
CSV Report

Crashtest Security
------------------
Import JSON Report
Import XML Report in JUnit Format

Contrast Scanner
----------------
CSV Report

Checkmarx
---------
Detailed XML Report

Choctaw Hog parser
------------------
From: https://github.com/newrelic/rusty-hog
Import the JSON output.

DawnScanner
-----------
Import report in JSON generated with -j option

Dependency Check
----------------
OWASP Dependency Check output can be imported in Xml format.

Dependency Track
----------------
The Finding Packaging Format (FPF) from OWASP Dependency Track can be imported in JSON format.

See here for more info on this JSON format: https://docs.dependencytrack.org/integrations/file-formats/

DrHeader
--------
Import of JSON report from  https://github.com/Santandersecurityresearch/DrHeader

ESLint
------
ESLint Json report format (-f json)

Fortify
--------
Import Findings from XML file format.

Generic Findings Import
-----------------------
Import Generic findings in CSV format.

Hadolint
--------
Hadolint Dockerfile scan in json format.

Harbor Vulnerability
--------------------
Import findings from Harbor registry container scan: https://github.com/goharbor/harbor

JFrogXRay
----------
Import the JSON format for the "Security Export" file.

Gosec Scanner
-------------
Import Gosec Scanner findings in JSON format.

Gitleaks
--------
Import Gitleaks findings in JSON format.

GitLab SAST Report
------------------
Import SAST Report vulnerabilities in JSON format.

Github Vulnerability
--------------------
Import findings from Github vulnerability scan: https://help.github.com/en/github/managing-security-vulnerabilities

Github v4 graphql query to fetch data::

      query getVulnerabilitiesByOwner($owner: String!) {
      search(query: $owner, type: REPOSITORY, first: 100) {
        nodes {
          ... on Repository {
            name<br/>
            vulnerabilityAlerts(last: 100) {
              nodes {
                id<br/>
                securityVulnerability {
                  severity<br/>
                  package {
                    name
                  }
                  advisory {
                    description<br/>
                    summary<br/>
                    identifiers {
                      type<br/>
                      value
                    }
                    references {
                      url
                    }
                  }
                }
              }
            }
          }
        }
      }
    }


HuskyCI Report
--------------
Import JSON reports from [HuskyCI](https://github.com/globocom/huskyCI)

IBM AppScan DAST
----------------
XML file from IBM App Scanner.

Immuniweb Scan
--------------
XML Scan Result File from Immuniweb Scan.

Kiuwan Scanner
--------------
Import Kiuwan Scan in CSV format. Export as CSV Results on Kiuwan.

kube-bench Scanner
------------------
Import JSON reports of Kubernetes CIS benchmark scans.

Microfocus Webinspect Scanner
-----------------------------
Import XML report

MobSF Scanner
-------------
Export a JSON file using the API, api/v1/report_json.</li>

Mozilla Observatory Scanner
---------------------------
Import JSON report.

Nessus (Tenable)
----------------
Reports can be imported in the CSV, and .nessus (XML) report formats.

Netsparker
----------
Vulnerabilities List - JSON report

Nexpose XML 2.0 (Rapid7)
------------------------
Use the full XML export template from Nexpose.

Nikto
-----
XML output

Nmap
----
XML output (use -oX)

Node JS Scan
------------
Node JS Scan output file can be imported in JSON format.

Node Security Platform
----------------------
Node Security Platform (NSP) output file can be imported in JSON format.

NPM Audit
---------
Node Package Manager (NPM) Audit plugin output file can be imported in JSON format. Only imports the 'advisories' subtree.

Openscap Vulnerability Scan
---------------------------
Import Openscap Vulnerability Scan in XML formats.

OpenVAS CSV
-----------
Import OpenVAS Scan in CSV format. Export as CSV Results on OpenVAS.

OssIndex Devaudit
-----------------
Import JSON formatted output from [OSSIndex Devaudit](https://github.com/sonatype-nexus-community/DevAudit).

Oss Review Toolkit
------------------
Import ORT Evaluated model reporter in JSON Format. (Example)[https://github.com/DefectDojo/sample-scan-files/blob/master/ort/evaluated-model-reporter-output.json]

PHP Security Audit v2
---------------------
Import PHP Security Audit v2 Scan in JSON format.

PHP Symfony Security Checker
----------------------------
Import results from the PHP Symfony Security Checker.

Probely
-------
Synchronize Probely Plus findings with DefectDojo.

To setup this integration set the DefectDojo URL and API key on the Integrations page on Probely. Then, select which Product, Engagement, and, optionally, the Test you want to synchronize to. The API key needs to belong to a staff user.

Works with DefectDojo 1.5.x and 1.6.x. Probely also supports non-public DefectDojo instances.

For detailed instructions on how to configure Probely and DefectDojo, see https://help.probely.com/en/articles/3811515-how-to-integrate-probely-with-defectdojo

Qualys Scan
-----------
Qualys output files can be imported in API XML format.
Qualys output files can be imported in WebGUI XML format.

Qualys Webapp Scan
------------------
Qualys WebScan output files can be imported in XML format.

Retire.js
---------
Retire.js JavaScript scan (--js) output file can be imported in JSON format.

Risk Recon API Importer
-----------------------

Import findings from Risk Recon via the API. Configure your own JSON report as follows

.. code-block:: JSON

    {
        "url_endpoint": "https://api.riskrecon.com/v1",
        "api_key": "you-api-key", 
        "companies": [
            {
                "name": "Company 1",
                "filters": {
                    "domain_name": [],
                    "ip_address": ["127.0.0.1"],
                    "host_name": ["localhost"],
                    "asset_value": [],
                    "severity": ["critical", "high"],
                    "priority": [],
                    "hosting_provider": [],
                    "country_name": []
                }
            },
            {
                "name": "Company 2",
                "filters": {
                    "ip_address": ["0.0.0.0"]
                }
            }
        
        ],
        "filters": {
            "domain_name": [],
            "ip_address": [],
            "host_name": [],
            "asset_value": [],
            "severity": ["critical"],
            "priority": [],
            "hosting_provider": [],
            "country_name": []
        }
    }


* More than one company finding list can be queried with it's own set of filters. Company 1 shows all available fitlers, while Company 2 shows that empty filters need not be present. 
* To query all companies in your Risk Recon instance, simple remove the "companies" field entirely. 
* If the "companies" field is not present, and filtering is still requested, the "filters" field can be used to filter all findings across all companies. It carries the same behavior as the company filters. The "filters" field is disregarded in the prescense of the "companies" field.
* Removing both fields will allow retrieval of all findings in the Risk Recon instance. 

Safety Scan
-----------
Safety scan (--json) output file can be imported in JSON format.

SARIF
-----------
OASIS Static Analysis Results Interchange Format (SARIF).
SARIF is supported by many tools.
More details about the format here: https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=sarif

SKF Scan
--------
Output of SKF Sprint summary export.

Snyk
----
Snyk output file (snyk test --json > snyk.json) can be imported in JSON format.

SonarQube Scan (Aggregates findings per cwe, title, description, file_path.)
----------------------------------------------------------------------------
SonarQube output file can be imported in HTML format.

To generate the report, see https://github.com/soprasteria/sonar-report

Version: >= 1.1.0

SonarQube Scan Detailed (Import all findings from SonarQube html report.)
-------------------------------------------------------------------------
SonarQube output file can be imported in HTML format.

To generate the report, see https://github.com/soprasteria/sonar-report

Version: >= 1.1.0

SonarQube API Import
--------------------
SonarQube API will be accessed to gather the report. No report file required.

Follow below steps to setup API Import:

1. Configure the Sonarqube Authentication details by navigating to Configuration->Tool Configuration. Note the url should be in the formation of http://<sonarqube_hostname>/api. Select the tool type to SonarQube. 
2. In the Product settings fill the details for the SonarQube Project Key (Key name can be found by navigating to a specific project and selecting the value from the url http://<sonarqube_host>/dashboard?id=<key_name>
3. Once all of the above setting are made , the API Import should be able to auto import all vulnerability information from the sonarqube instance.

SpotBugs
--------
XML report of textui cli.

Sonatype
--------
JSON output.

SSL Labs
--------
JSON Output of ssllabs-scan cli.

Sslscan
-------
Import XML output of sslscan report.

Sslyze Scan
-----------
XML report of SSLyze version 2 scan

SSLyze 3 Scan (JSON)
--------------------
JSON report of SSLyze version 3 scan

Testssl Scan
----------------
Import CSV output of testssl scan report.

Trivy
-----
JSON report of `trivy scanner <https://github.com/aquasecurity/trivy>`_.

Trufflehog
----------
JSON Output of Trufflehog.

Trustwave
---------
CSV output of Trustwave vulnerability scan.

Twistlock
---------
JSON output of the ``twistcli`` tool. Example:

.. code-block:: bash

   ./twistcli images scan <REGISTRY/REPO:TAG> --address https://<SECURE_URL_OF_TWISTLOCK_CONSOLE> --user <USER> --details --output-file=<PATH_TO_SAVE_JSON_FILE>

The CSV output from the UI is now also accepted.

Visual Code Grepper (VCG)
-------------------------
VCG output can be imported in CSV or Xml formats.

Veracode
--------
Detailed XML Report

Wapiti Scan
-----------
Import XML report.

Whitesource Scan
----------------
Import JSON report

Wpscan Scanner
--------------
Import JSON report.

Xanitizer
---------
Import XML findings list report, preferably with parameter 'generateDetailsInFindingsListReport=true'.

Zed Attack Proxy
----------------
ZAP XML report format.


The importers analyze each report and create new Findings for each item reported.  DefectDojo collapses duplicate
Findings by capturing the individual hosts vulnerable.

.. image:: /_static/imp_1.png
    :alt: Import Form

Additionally, DefectDojo allows for re-imports of previously uploaded reports.  DefectDojo will attempt to capture the deltas between the original and new import and automatically add or mitigate findings as appropriate.

.. image:: /_static/imp_2.png
    :alt: Re-Import Form

Bulk import of findings can be done using a CSV file with the following column headers:

Date: ::
    Date of the finding in mm/dd/yyyy format.

Title: ::
    Title of the finding

CweId: ::
    Cwe identifier, must be an integer value.

Url: ::
    Url associated with the finding.

Severity: ::
    Severity of the finding.  Must be one of Info, Low, Medium, High, or Critical.

Description: ::
    Description of the finding.  Can be multiple lines if enclosed in double quotes.

Mitigation: ::
    Possible Mitigations for the finding.  Can be multiple lines if enclosed in double quotes.

Impact: ::
    Detailed impact of the finding.  Can be multiple lines if enclosed in double quotes.

References: ::
    References associated with the finding.  Can be multiple lines if enclosed in double quotes.

Active: ::
    Indicator if the finding is active.  Must be empty, True or False

Verified: ::
    Indicator if the finding has been verified.  Must be empty, True, or False

FalsePositive: ::
    Indicator if the finding is a false positive.  Must be True, or False.

Duplicate: ::
    Indicator if the finding is a duplicate.  Must be True, or False.
