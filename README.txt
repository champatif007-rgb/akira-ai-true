AKIRA AI — NETLIFY DEPLOYMENT

WHAT'S INCLUDED
- index.html: your app, updated to call a secure Netlify Function
- netlify.toml: tells Netlify where the site and function are
- netlify/functions/ask.mjs: server-side AI proxy
- _headers: basic browser security headers

IMPORTANT
Your original project had no AI provider connected. The included function connects
the chat to OpenAI using the OPENAI_API_KEY environment variable. The key is kept
on Netlify's server and is not placed in index.html.

DEPLOY
1. Extract this ZIP.
2. Go to https://app.netlify.com/ and sign in.
3. Choose Add new site > Deploy manually (or drag and drop the extracted folder
   into Netlify's manual deploy area).
4. After the first deploy, open Site configuration > Environment variables.
5. Add OPENAI_API_KEY with your own OpenAI API key as its value.
6. Trigger a new deploy so the function receives the variable.
7. Open your Netlify site URL and test a normal text question and (if needed) an image.

SECURITY / COST
- Never put your OpenAI API key in index.html or any frontend JavaScript.
- This is a public endpoint. Before sharing widely, set API usage limits/budget
  with your AI provider and monitor usage. Add authentication or rate limiting
  if you expect public traffic; this starter does not include per-user quotas.
- The site can be publicly viewed after deployment, but AI chat needs the
  OPENAI_API_KEY environment variable and an account with API access/billing.
- Chat history and preferences are stored in each visitor's browser localStorage;
  they are not synced between devices or users.
