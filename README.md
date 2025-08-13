# 🔐 Public API with OAuth2 + Spike Arrest (Apigee X)

This project demonstrates how to secure a public API using **OAuth2 Client Credentials** in Apigee X, combined with a **Spike Arrest policy** for rate limiting.

## ✅ Features
- **OAuth2 (Client Credentials Flow)** for token-based access
- **Spike Arrest** policy (10 requests/sec)
- Secure token endpoint: `/token`
- API Product + Developer App setup
- Tested with **Postman** and **curl**
- Optional CI/CD with GitHub Actions

---

## 🧪 How to Use

### 1. Import Proxy
1. In Apigee UI, go to **Develop → API Proxies → +Proxy**
2. Choose **Upload** and select the `apiproxy/` folder.
3. Deploy to your `dev` environment.

### 2. Create API Product
# From Apigee UI → Publish → API Products
# Or import `api-product.yaml`

3. Create Developer App
Follow developer-app.md to create your app and get Client ID & Secret.

4. Get Access Token
bash
Copy
Edit
curl -X POST https://ORG-ENV.apigee.net/public-api/token \
  -d 'grant_type=client_credentials' \
  -u CLIENT_ID:CLIENT_SECRET
5. Call the API
bash
Copy
Edit
curl -i https://ORG-ENV.apigee.net/public-api \
  -H "Authorization: Bearer ACCESS_TOKEN"
📦 Files
apiproxy/ – Proxy source (OAuth2, Spike Arrest, routing to backend)

api-product.yaml – API Product config

developer-app.md – Guide to create Developer App


