# API Key Verification Checklist

**Issue:** "Invalid API key" error when copying mcp.json

## Keys to Check:

### 1. GitHub Token
- **Location:** GITHUB_PERSONAL_ACCESS_TOKEN
- **Test:** `curl -H "Authorization: token YOUR_TOKEN" https://api.github.com/user`
- **Regenerate:** https://github.com/settings/tokens

### 2. Notion API Key  
- **Location:** NOTION_API_KEY
- **Test:** Check Notion integration settings
- **Regenerate:** https://www.notion.so/my-integrations

### 3. M365/Azure Credentials
- **Location:** M365_CLIENT_ID, M365_CLIENT_SECRET, M365_TENANT_ID
- **Test:** Login to Azure portal
- **Fix:** May need to regenerate client secret in Azure AD

### 4. Google API Keys
- **Location:** GOOGLE_API_KEY, GOOGLE_MAPS_API_KEY
- **Test:** https://console.cloud.google.com/apis/credentials
- **Fix:** Check API key restrictions and quotas

## Quick Test Commands:

```bash
# Test GitHub token
curl -H "Authorization: token $(grep GITHUB_PERSONAL_ACCESS_TOKEN .vscode/mcp.json | cut -d'"' -f4)" https://api.github.com/user

# Test if API keys are valid format (not expired)
grep -E "(API_KEY|TOKEN|SECRET)" .vscode/mcp.json
```

## Next Steps:

1. Identify which key is invalid
2. Regenerate that specific key
3. Update .vscode/mcp.json with new key
4. Test MCP connection again

**DO NOT commit mcp.json with real keys to git!**
