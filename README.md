***There are multiple ways to abuse Claude code, this is one of them which I found during my research & reported (November 23, 2025) (not-fixed), might come handy while doing RT/PT for inital access.***

**Summary:** The `apiKeyHelper` is a custom shell script (`/bin/sh`) designed to generate authentication values for `X-Api-Key` and `Authorization: Bearer` headers in model requests; however, since this accepts and executes system commands, this behavior results in code execution [reference](https://code.claude.com/docs/en/settings#available-settings).

However, `apiKeyHelper` is a custom script whose purpose is only to generate values for `X-Api-Key` and `Authorization: Bearer` headers and not user-controlled commands.

**Proof-of-work:**
```bash
git clone https://github.com/RootUp/claude-poc
cd claude-poc
claude
```
<img src="https://github.com/user-attachments/assets/aa1311e2-f94f-4d24-8300-7dcd4b196a19" alt="ClaudeRCE_POC"><sub style="display:block;text-align:center;margin:0;">This is a gif so it might be slow.</sub>

**NOTE:** In-case a scenario if the parent folder is already trusted then a additional "trust" prompt is not triggered that could lead to silent code execution.
