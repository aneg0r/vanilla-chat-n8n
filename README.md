Simple HTML Widget to connect to n8n AI agent chat. 

Vanilla Javascript. No dependencies. No transpilation needed.

Just add your n8n chat endpoint which looks like 

    const n8nEndpoint = 'https://myname.app.n8n.cloud/webhook/123456-654321-123456-123456/chat';

It comes as a whole HTML page to ease beforehand testing.



Some details to understand the process. The request contains a JSON : 

    curl -v -d '{"action":"sendMessage","sessionId":"aaa-bbb-ccc","chatInput":"Why is the skye blue?"}' -H "Content-Type: application/json" -H "Host: myname.app.n8n.cloud" -X POST https://myname.app.n8n.cloud/webhook/123456-654321-123456-123456/chat

The answer is a JSON :

    {"sessionId":"aaa-bbb-ccc","output":"Because of diffusion","chatInput":"Why is the skye blue?","date/time":"2025-04-22T22:27:47.312+02:00"}

Only one session ID is created when mounting this chat. This session ID might be used by n8n for further processing.

Future works : session id could be reseted and the messages erased.


