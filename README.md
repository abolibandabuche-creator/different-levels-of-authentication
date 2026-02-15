# 🔐 API Authentication Demo

A Node.js/Express app that demonstrates four common API authentication methods using the [Secrets API](https://secrets-api.appbrewery.com/).

---

## 📁 Project Structure

```
API-AUTHE/
├── public/
│   └── styles/
│       └── main.css
├── views/
│   └── index.ejs
├── index.js
├── package.json
└── package-lock.json
```

---

## 🚀 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v14 or higher)
- npm

### Installation

```bash
# Clone the repository
git clone <your-repo-url>
cd API-AUTHE

# Install dependencies
npm install
```

### Configuration

Before running the app, open `index.js` and fill in your credentials:

```js
const yourUsername = "your_username";
const yourPassword = "your_password";
const yourAPIKey = "your_api_key";
const yourBearerToken = "your_bearer_token";
```

You can register and get these credentials at [https://secrets-api.appbrewery.com/](https://secrets-api.appbrewery.com/).

### Run the App

```bash
node index.js
```

Then open your browser and go to: **http://localhost:3000**

---

## 🛣️ Routes & Auth Methods

| Route | Auth Type | API Endpoint |
|---|---|---|
| `GET /` | None | — |
| `GET /noAuth` | No Authentication | `/random` |
| `GET /basicAuth` | Basic Auth (username + password) | `/all?page=2` |
| `GET /apiKey` | API Key (query parameter) | `/filter?score=5` |
| `GET /bearerToken` | Bearer Token (Authorization header) | `/secrets/42` |

### Auth Method Details

**No Auth** — Fetches a random secret with no credentials required.

**Basic Auth** — Sends your username and password via Axios's built-in `auth` config to fetch paginated secrets.

**API Key** — Appends your API key as a query parameter to filter secrets with an embarrassment score of 5 or higher.

**Bearer Token** — Passes a token in the `Authorization` header to retrieve a specific secret by ID.

---

## 🛠️ Tech Stack

- **[Express.js](https://expressjs.com/)** — Web framework
- **[Axios](https://axios-http.com/)** — HTTP client for API requests
- **[EJS](https://ejs.co/)** — Templating engine

---

## 📦 Dependencies

```json
{
  "axios": "^1.x",
  "ejs": "^3.x",
  "express": "^4.x"
}
```

Install all at once with `npm install`.

---

## 📄 License

This project is for educational purposes.
