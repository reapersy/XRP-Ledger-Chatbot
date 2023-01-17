
# XRP Ledger Chatbot

This chatbot is powered by GPT-4 and trained on the [XRP Ledger](https://github.com/XRPLF/xrpl.js) codebase. Use it to ask questions regarding the operations of the XRP Ledger and receive specific answers with code references. The project aims at enhancing the experience for developers working with the XRP ledger.

![ChatbotUI](https://i.postimg.cc/MTRgpsBN/XRPL-gpt-ss.png) 

### Prerequisites

- [Node.js](https://nodejs.org/en/download/) (v16 or higher)
- [Yarn](https://classic.yarnpkg.com/en/docs/install/#mac-stable)
- `wget` (install on macOS with `brew install wget`)

Once the above steps are complete, load our data source.


# Data Ingestion

For data ingestion, start by running the command below:

```bash
sh download.sh
```

This command downloads our data source (the Langchain docs in this case). Next, install dependencies and run the ingestion script:

```bash
yarn && yarn ingest
```

Remember, if you're using Node v16, use `NODE_OPTIONS='--experimental-fetch' yarn ingest`.

The script parses the data, splits text, creates embeddings, stores them in a vectorstore and saves it to the `data/` directory. The Next.js server needs the `data/` directory to function. Ensure you execute this step before moving to the next.

### Starting the Server

To run the development server:

```bash
yarn dev
```

Now, open [http://localhost:3000](http://localhost:3000) with your browser.

### Deployment

To deploy your server on Fly, employ the provided `fly.toml` and `Dockerfile`. The production version of this repo hosts on [fly](https://chat-langchainjs.fly.dev/).

## Attribution


## Running on Your Example

To chat your data, you need to:

1. Create a similar `data/` directory with a vectorstore in it using your own ingestion pipeline.
2. Customize the prompt used in `pages/api/util.ts`. The current setup only answers questions about LangChain. To adapt it to your data, update accordingly.

Rest assured, the server will work perfectly after these changes 😄