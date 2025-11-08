# Cloud Setup Checklist

**Time:** 9:16 AM CST, Nov 8, 2025  
**Mission:** Get Claude Code Cloud ready to work

---

## Step 1: Clone Repository in Cloud ✅

```bash
git clone git@github.com:u-dadashek/cloud-sprint-nov-8-21.git
cd cloud-sprint-nov-8-21
```

---

## Step 2: Copy Configuration Files from Local

### A. Copy MCP Configuration
**From local machine:**
```bash
# Location: ~/proof_state/.vscode/mcp.json
# Copy this file to cloud-sprint-nov-8-21/.vscode/mcp.json
```

**What's in it:**
- M365 MCP server config (Outlook, Calendar, Contacts)
- GitHub MCP server config
- Notion MCP server config (if configured)
- Taskmaster MCP server config

### B. Copy Environment File (SECURE!)
**From local machine:**
```bash
# Location: ~/proof_state/.env
# Copy to cloud-sprint-nov-8-21/.env
```

**Critical API Keys Needed:**
- `ANTHROPIC_API_KEY` - For Claude
- `OPENAI_API_KEY` - For OpenAI models
- `PERPLEXITY_API_KEY` - For research
- M365/Azure credentials
- GitHub token
- Notion API key
- Any other service keys

**⚠️ SECURITY NOTE:**
- Never commit .env to git
- .env is already in .gitignore
- These are YOUR credentials - keep them private

---

## Step 3: Install Dependencies

```bash
cd cloud-sprint-nov-8-21
npm install
```

---

## Step 4: Test MCP Server Connections

### Test M365 MCP (Outlook)
```bash
# In Claude Code Cloud, try:
# "Use M365 MCP to list my calendar events for the next week"
```

Expected: Should show your Outlook calendar events

### Test GitHub MCP
```bash
# "Use GitHub MCP to list repositories for u-dadashek"
```

Expected: Should list your GitHub repos

### Test Notion MCP (if configured)
```bash
# "Use Notion MCP to list my databases"
```

Expected: Should show Notion databases

### Test Taskmaster
```bash
cd proof_state
npx task-master list
```

Expected: Should show task list if tasks.json exists

---

## Step 5: Verify File Access

```bash
# Check you can see proof_state files
ls -la proof_state/

# Check key directories
ls proof_state/_0_inbox/
ls proof_state/_1_action_zone/
```

---

## Step 6: First Test Task

Create a simple test to verify everything works:

```bash
# Create test log
echo "# Sprint Day 1 - $(date)" > work_logs/day_1_nov_8.md
echo "## Setup Status" >> work_logs/day_1_nov_8.md
echo "- [x] Repository cloned" >> work_logs/day_1_nov_8.md
echo "- [ ] MCP servers tested" >> work_logs/day_1_nov_8.md
echo "- [ ] API keys verified" >> work_logs/day_1_nov_8.md
```

---

## Troubleshooting

### If MCP servers don't work:
1. Check .vscode/mcp.json is copied correctly
2. Verify .env file exists with all keys
3. Restart Claude Code Cloud session
4. Check MCP server logs for errors

### If authentication fails:
1. Verify API keys are valid
2. Check no extra spaces in .env
3. Ensure keys have correct permissions
4. Test keys locally first

### If file access issues:
1. Check git clone completed successfully
2. Verify you're in correct directory
3. Check file permissions

---

## Success Criteria

✅ Repository cloned  
✅ .vscode/mcp.json in place  
✅ .env file configured  
✅ MCP servers responding  
✅ Can read proof_state files  
✅ Ready to start Phase 2 (Outlook Cleanup)

---

**Once all ✅ are checked, you're ready to burn $247 on productivity!** 🚀

**Next:** Start EMERGENCY_CLOUD_SPRINT_NOV_8-18.md → Phase 2: Outlook Cleanup
