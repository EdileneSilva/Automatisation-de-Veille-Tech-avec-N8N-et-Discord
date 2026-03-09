# Tech Watch Automation with n8n

### Project overview

This project is an automated **tech watch system** built with **n8n**.

### Technologies used

* n8n (workflow automation)
* Docker (to run n8n locally)
* Discord (for notifications)
* RSS feeds (data sources)


### Project architecture

The workflow follows this logic:

Schedule Trigger
↓
Read RSS feeds
↓
Filter articles published in the last 24 hours
↓
Format article data
↓
Send the articles to Discord

This allows the Discord server to receive the articles within the last 24h automatically


### RSS sources

RSS feeds used in this project:

* https://www.stat4decision.com/fr/feed/
* https://blog.octo.com/feed/
* https://medium.com/feed/tag/data-engineering
* https://practicaldataengineering.substack.com/feed
* https://towardsdatascience.com/feed


### Running the project locally

The project uses **Docker Compose** to run n8n locally.

First make sure Docker is installed.

Then start the container with:

docker compose up -d

After that open n8n in your browser:

http://localhost:5678

You can then import the workflow and activate it.


### Repository structure

```
project-folder
│
├── README.md
├── Screenshot
│   └── Screenshot.png
└── workflows
    ├── llm_worfflows.json
    └── rss_workflows.json
```

### Workflow export

The workflows can be exported directly from **n8n** as JSON files and stored in the repository.

This allows anyone to import the workflow and run the same automation.


### Discord integration

Articles are sent automatically to a **Discord channel** using a webhook or the Discord integration inside n8n.

Each message contains information such as:

* article title
* link to the article
* short description
