
# n8n Jira Ticket Automation

## Overview

This project demonstrates how to automate Jira ticket creation using **n8n** and **Webhook**.

Instead of manually creating Jira issues, an external application can send a POST request to n8n. The workflow automatically creates a Jira ticket using the received data.

---

## Features

* Webhook-based automation
* Automatic Jira issue creation
* Production-ready webhook endpoint
* JSON request support
* Easy to extend with additional integrations

---

## Tech Stack

* n8n
* Jira
* Webhook
* REST API
* curl

---

## Architecture

```text
Client (curl/API)
        │
        ▼
Webhook (n8n)
        │
        ▼
Process Request
        │
        ▼
Jira Create Issue
        │
        ▼
Jira Ticket
```

---

## Workflow

1. A client sends a POST request.
2. n8n receives the request through a Webhook.
3. The workflow extracts:

   * Summary
   * Description
4. Jira node creates a new issue.
5. Ticket is created automatically.

---

## Sample Request

```bash
curl -X POST http://localhost:5678/webhook/jira-ticket \
-H "Content-Type: application/json" \
-d "{\"summary\":\"Docker issue\",\"description\":\"Container not starting in production\"}"
```

---

## Sample JSON

```json
{
  "summary": "Docker issue",
  "description": "Container not starting in production"
}
```

---

## Result

A Jira Task is automatically created with the provided Summary and Description.

---

## Future Enhancements

* Web-based issue submission form
* Auto Priority assignment
* Slack notifications
* Microsoft Teams integration
* Email notifications
* AI-based issue categorization
* ServiceNow integration

---

## Learning Outcomes

* Webhook integration
* API automation
* Jira automation
* n8n workflow development
* Event-driven workflows

---

## Author

Mahesh Kuruva

DevOps Engineer | AWS | Azure | Kubernetes | Docker | Terraform | CI/CD
