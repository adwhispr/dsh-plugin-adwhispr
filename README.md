# AdWhispr for DeepSeek Harness

See who is running ads in your space, clone a winning ad for your brand, and launch and manage campaigns on Meta, Google and TikTok, all from a DeepSeek Harness chat.

## Install

1. Open DeepSeek Harness and go to **Plugins**, then **Add plugin**.
2. Enter `dsh-plugin-adwhispr` and click **Install**, then **Enable now**.
3. A browser window opens. Sign up for AdWhispr (it is free to start) or sign in, then click **Allow**.
4. Quit DeepSeek Harness and open it again.

From the command line:

```sh
dsh plugin --profile <name> add dsh-plugin-adwhispr
```

## Try it

- Who is running ads in my space?
- Clone a winning ad for my brand.
- Optimize my ad spend.
- Launch a new campaign from my creatives, paused until I OK it.

New campaigns are always created paused. Launching needs your own ad account connected in AdWhispr first.

## Requirements

- DeepSeek Harness 0.2 or later
- Node.js 18 or later on your machine (the plugin starts a small bridge with `npx`)

## How it works

DeepSeek Harness talks to MCP servers but does not handle browser sign-in on its own. This plugin adds one MCP server entry that runs [`mcp-remote`](https://www.npmjs.com/package/mcp-remote), which signs you in through your browser and connects the harness to `https://adwhispr.com/api/mcp`. Your sign-in is stored on your own computer in `~/.mcp-auth`. The plugin stores nothing else.

## Troubleshooting

**AdWhispr shows as disconnected.** Finish the browser sign-in, then quit and reopen DeepSeek Harness. The harness stops retrying after ten failed attempts, so a restart is needed if sign-in took a while.

**The browser window never opens.** Check that Node.js is installed (`node -v` in a terminal) and that nothing is blocking `localhost`.

**Sign-in loops or you want to switch accounts.** Delete the `~/.mcp-auth` folder and restart the harness to sign in again.

## Remove

In **Plugins**, switch off or uninstall `dsh-plugin-adwhispr`.

## Support

hello@adwhispr.com · https://adwhispr.com
