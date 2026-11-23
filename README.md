# Clipwright MCP

Check a clip job or see how much of your monthly allowance you have used.

Use your Clipwright customer key. Take the job ID from a clip request you already submitted. A job that another account owns returns the same response as an unknown job. Check the unit on your plan. New plans count finished clips. Older plans can count source videos.

[Product account or API docs](https://clipwright.eliteaiempire.com/customer/login)

From the GitHub repository, run the first command below and enter your product key at the hidden prompt. The second command lists the tools. The last command revokes the read key and removes the local file.

```sh
python3 client.py --key-file ./clipwright.key connect
python3 client.py --key-file ./clipwright.key list
python3 client.py --key-file ./clipwright.key revoke
```

Choose Streamable HTTP in your MCP client. Paste the endpoint below. In its private header settings, enter Authorization with the value Bearer followed by a space and the read key from your file.

https://auth.eliteaiempire.com/mcp/clipwright

To issue a read key directly, POST to https://auth.eliteaiempire.com/mcp-access/clipwright with your product key in the Authorization bearer header. Use the access_key from the response. To revoke it, send DELETE to the same address with the read key.

## Tools

- `get_job` — Read the status of one clip job you own.
- `get_usage` — Read your job count and monthly usage, including the unit and limit your plan reports.

## Try it

Has my clip job finished? How much of my allowance have I used this month?

## Access

The read key works for 24 hours. Each product key can make 60 MCP requests a minute. If you get HTTP 429, wait for the number of seconds in Retry-After. Revoke a connection as soon as you finish with it.

[Connection guide](https://auth.eliteaiempire.com/mcp-docs/clipwright) · [Server manifest](https://auth.eliteaiempire.com/mcp-docs/clipwright/server.json)
