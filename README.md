# 🚀 InquisitorAI - An AI-powered Search Engine 🔎 <!-- omit in toc -->

![preview](.assets/inquisitorai-screenshot.png)

## Table of Contents <!-- omit in toc -->

- [Overview](#overview)
- [Preview](#preview)
- [Features](#features)
- [Installation](#installation)
  - [Getting Started with Docker (Recommended)](#getting-started-with-docker-recommended)
  - [Non-Docker Installation](#non-docker-installation)
  - [Troubleshooting Connection Issues](#troubleshooting-connection-issues)
- [Using as a Search Engine](#using-as-a-search-engine)
- [One-Click Deployment](#one-click-deployment)
- [Upcoming Features](#upcoming-features)
- [Support Us](#support-us)
  - [Donations](#donations)
- [Contribution](#contribution)
- [Help and Support](#help-and-support)

## Overview

InquisitorAI is an open-source AI-powered search engine designed to dive deep into the internet to find precise answers. It’s inspired by Perplexity AI but offers an open-source alternative that not only searches but comprehends your queries. Leveraging advanced machine learning techniques such as similarity searching and embeddings, it refines results and delivers clear, source-cited answers.

Built on SearxNG, InquisitorAI provides up-to-date information while ensuring your privacy is maintained.

For more details about its architecture and functioning, you can read the [architecture documentation](https://github.com/YourRepo/InquisitorAI/tree/master/docs/architecture/README.md).

## Preview

![video-preview](.assets/inquisitorai-preview.gif)

## Features

- **Local LLMs**: Utilize local LLMs like Llama3 and Mixtral through Ollama.
- **Two Main Modes:**
  - **Copilot Mode:** (In development) Enhances search by generating varied queries to find more relevant sources. It explores top matches and extracts relevant information directly from those sources.
  - **Normal Mode:** Processes your query and performs a straightforward web search.
- **Focus Modes:** Specialized modes to address specific types of questions. InquisitorAI currently includes 6 focus modes:
  - **All Mode:** Searches the entire web for the best results.
  - **Writing Assistant Mode:** Assists with writing tasks without web searching.
  - **Academic Search Mode:** Retrieves articles and papers for academic research.
  - **YouTube Search Mode:** Finds YouTube videos based on the search query.
  - **Wolfram Alpha Search Mode:** Answers queries requiring calculations or data analysis using Wolfram Alpha.
  - **Reddit Search Mode:** Searches Reddit for discussions and opinions relevant to the query.
- **Current Information:** Unlike some tools that use outdated info from crawling bots, InquisitorAI uses SearxNG for real-time results and re-ranks them to ensure you get the latest information.

Additional features include image and video search. Upcoming features are listed under [upcoming features](#upcoming-features).

## Installation

There are two primary methods for installing InquisitorAI - with Docker or without Docker. Docker is highly recommended for simplicity.

### Getting Started with Docker (Recommended)

1. Ensure Docker is installed and running on your system.
2. Clone the InquisitorAI repository:

   ```bash
   git clone https://Github.com/Kelasbawah-official/InquisitorAI.git
   ```

3. Navigate to the project directory.

4. Rename `sample.config.toml` to `config.toml` and configure the following fields:

   - `OPENAI`: Your OpenAI API key. **Fill this if you wish to use OpenAI’s models**.
   - `OLLAMA`: Your Ollama API URL. Set it as `http://host.docker.internal:PORT_NUMBER`. Adjust the port if necessary. **Fill this if you wish to use Ollama’s models**.
   - `GROQ`: Your Groq API key. **Fill this if you wish to use Groq’s hosted models**.
   - `ANTHROPIC`: Your Anthropic API key. **Fill this if you wish to use Anthropic models**.
   - `SIMILARITY_MEASURE`: Default similarity measure (you can leave as is if unsure).

5. Ensure you’re in the directory with `docker-compose.yaml` and run:

   ```bash
   docker compose up -d
   ```

6. After a few minutes, access InquisitorAI at http://localhost:3000 in your web browser.

**Note**: Once the containers are set up, you can run InquisitorAI directly from Docker without using the terminal.

### Non-Docker Installation

1. Install SearXNG and enable `JSON` format in its settings.
2. Clone the repository and rename `sample.config.toml` to `config.toml`. Complete all required fields.
3. Rename `.env.example` to `.env` in the `ui` folder and fill in all necessary fields.
4. Run `npm i` in both the `ui` folder and the root directory.
5. Build the project with `npm run build` in both directories.
6. Start the frontend and backend with `npm run start` in both directories.

**Note**: Docker is recommended for easier setup and environment management.

For additional installation details, see the [installation documentation](https://Github.com/Kelasbawah-official/InquisitorAI/tree/master/docs/installation).

### Troubleshooting Connection Issues

If you encounter issues connecting to Ollama, try the following steps:

1. **Check your Ollama API URL:** Ensure the API URL is correctly configured.
2. **Update API URL Based on OS:**

   - **Windows:** Use `http://host.docker.internal:11434`
   - **Mac:** Use `http://host.docker.internal:11434`
   - **Linux:** Use `http://<private_ip_of_host>:11434`

   Adjust the port number if needed.

3. **Linux Users - Expose Ollama to Network:**

   - Edit `/etc/systemd/system/ollama.service` to include `Environment="OLLAMA_HOST=0.0.0.0"`. Restart Ollama with `systemctl restart ollama`. For more details, refer to the [Ollama docs](https://github.com/ollama/ollama/blob/main/docs/faq.md#setting-environment-variables-on-linux).

   - Ensure the port (default 11434) is not blocked by your firewall.

## Using as a Search Engine

To use InquisitorAI as an alternative to traditional search engines or set it as a browser shortcut:

1. Open your browser's settings.
2. Go to 'Search Engines'.
3. Add a new site search with the URL: `http://localhost:3000/?q=%s`. Replace `localhost` with your IP address or domain name, and adjust the port number if needed.
4. Add the search engine. You can now use InquisitorAI directly from your browser’s search bar.

## One-Click Deployment

[![Deploy to RepoCloud](https://d16t0pc4846x52.cloudfront.net/deploylobe.svg)](https://repocloud.io/details/?app_id=)

## Upcoming Features

- [x] Add settings page
- [x] Support for local LLMs
- [x] History saving features
- [x] Introduce various focus modes
- [ ] Finalize Copilot Mode
- [ ] Add Discovery features

## Support Us

If you find InquisitorAI helpful, consider starring us on GitHub. This helps others discover InquisitorAI and supports our development efforts.

### Donations

We accept donations to support the project. If you'd like to contribute, you can use the following options:

| Ethereum                                              |
| ----------------------------------------------------- |
| Address: `...............` |

## Contribution

InquisitorAI is built with the belief that AI and large language models should be accessible to everyone. If you find bugs or have suggestions, please report them via GitHub Issues. To learn more about contributing, read the [CONTRIBUTING.md](CONTRIBUTING.md) file.

## Help and Support

For questions or feedback, feel free to reach out. You can create an issue on GitHub or join our Discord server to connect with other users and get personalized help. [Click here](https://discord.gg) to join our Discord server. For discussions outside of regular support, contact me on Discord at `Timkelasbawah`.

Thank you for exploring InquisitorAI! We are continually working to improve and expand its capabilities. We appreciate your feedback and contributions. Check back for updates and new features!
