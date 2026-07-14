# Password Reset Agent with Human-in-the-Loop Approval

This repository provides an enterprise demo runbook for building a **Password Reset Agent** using **Microsoft Copilot Studio** with **human-in-the-loop manager approval**.

The demo shows how an employee can request a password reset through a conversational agent, how the request is routed to the employee's manager for approval, and how the workflow can proceed through a controlled, auditable reset process.

## Why This Matters

This demo showcases a practical enterprise AI pattern:

- Conversational AI as the front door
- Manager approval before sensitive action
- SharePoint-based audit logging
- Outlook and Teams approval experience
- Optional production path using Microsoft Graph
- Reusable pattern for access requests, software approvals, finance approvals, and service desk automation

## Architecture

images/password-reset-agent-architecture.png

## Included Assets

| Asset | Description |
|---|---|
| `docs/Password_Reset_Agent_HIL_General_Runbook.docx` | Full enterprise runbook with build steps |
| `images/password-reset-agent-architecture.png` | Architecture diagram |
| `snippets/agent-instructions.txt` | Copy-paste Copilot Studio agent instructions |
| `snippets/approval-email-template.html` | Email body template |
| `snippets/graph-resetpassword-http.txt` | Microsoft Graph resetPassword HTTP example |
| `snippets/powershell-validation.ps1` | PowerShell validation snippet |

## Demo Scenario

1. Employee says: `I forgot my password`
2. Copilot Studio agent collects user details
3. Agent invokes an Agent Flow
4. Flow retrieves the employee's manager
5. Approval request is sent to the manager
6. Manager approves or rejects
7. Workflow updates SharePoint audit record
8. User and manager receive notifications
9. Optional production path resets password through Microsoft Graph

## Demo-Safe vs Production Path

| Version | Description |
|---|---|
| Demo-Safe | Logs request in SharePoint and emails a generated temporary password. Does not reset real Entra ID password. |
| Production | Uses Microsoft Graph `resetPassword` API after approval. Requires delegated permissions and appropriate Entra admin role. |

## Prerequisites

- Microsoft Copilot Studio access
- Power Automate / Agent Flow capability
- Office 365 Users connector
- Approvals connector
- Outlook connector
- SharePoint site for audit logging
- Microsoft Entra ID manager relationship for test users

## How to Use

1. Download the runbook from the `docs` folder.
2. Follow the pre-flight checklist.
3. Create the SharePoint `PasswordResetTickets` list.
4. Build the Copilot Studio agent.
5. Configure the `PasswordResetHIL` Agent Flow.
6. Test using the live demo script.
7. Extend for production using Microsoft Graph if required.

## Feedback and Contributions

Feedback is welcome.

Please use GitHub Issues to suggest:

- Improvements to the runbook
- Additional Copilot Studio patterns
- Better security controls
- Production implementation guidance
- Alternative connectors or ITSM integrations

## Disclaimer

This repository is intended for educational and demonstration purposes. Do not use the production Microsoft Graph password reset path in a live tenant without security review, least-privilege access design, audit logging, and appropriate administrative approval.

## License

This project is licensed under the MIT License unless otherwise specified.# copilot-studio-password-reset-agent-hil
nterprise demo runbook for building a Microsoft Copilot Studio Password Reset Agent with human-in-the-loop manager approval.
