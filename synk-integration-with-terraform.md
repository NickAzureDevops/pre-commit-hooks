# Synk Integration with Terraform #

This section outline the integration using Synk with Terraform. Snyk Code is an open-source static code analysis tool that scans for security vulnerabilities Synk can integrate with Infrastructure as Code (IaC) tools such as Terraform, Kubernetes and AWS CloudFormation.

Download and install Synk from the [Synk website](https://www.synk.io/downloads/. There is a Synk CLI for Windows, Linux and Mac. There are two ways to authenticate Synk CLI with Github action.

- Using a token is recommended to authenticate Synk CLI with Github action. Go to your [Synk account](https://app.synk.io/account) and click on the API Token tab to generate the token. Click on the Generate Token button and copy it. It will later use to authenticate Synk CLI with Github action.

## Scanning Terraform Code using Synk ##

On the Synk account, you enable the infrastructure as code integration. To do this, go to your Synk account and click on the Integrations tab. Click on the Infrastructure as Code to enable the integration.<https://docs.snyk.io/products/snyk-infrastructure-as-code/scan-terraform-files/configure-your-integration-to-find-security-issues-in-your-terraform-filess>.

If the integration is successful, you will see a message that says, "Integration test successful". The second way is to run the Synk CLI command locally on your machine by using the following command:

```bash
snyk iac test terraform.tf
```

## Integration using Github Actions ##

Integrating Synk with Github action is the same as integrating Synk with other CI/CD tools. As described on the GitHub Repo here, <https://github.com/snyk/actions/tree/master/iac>, there are several options when incorporating it with Github action:

### First Option ###

The first will show how you can incorporate it using Git Pre-Commit Hooks with Synk. This option will scan the Terraform code before committing the code to the repository. 

Set up Scan to scan on all Pull Request. This option scans the Terraform code on all pull requests. <https://docs.snyk.io/integrations/git-repository-scm-integrations/test-your-prs-for-vulnerabilities-before-merging>



![first approach](/diagrams/synk-terraform-first-approach.png)


        
 






## Second Option ##

- Set up the GitHub Action to scan on all Pull Requests or enforce a GitHub Policy to trigger a workflow after pushing to the main or master branch.

## Synk Results ##

The Synk CLI command will return the following results:

- The number of vulnerabilities found in the code
- The severity of the vulnerabilities found in the code
- The vulnerable paths found in the code
- The remediation for the vulnerabilities found in the code
- The Synk policy for the code
- The Synk project for the code
- The Synk CLI command to run the test

## Synk Remediation ##

Synk provides remediation to control the security of the code. The remediation information includes the number of vulnerabilities, severity, vulnerable paths and how to remediate the vulnerabilities.


