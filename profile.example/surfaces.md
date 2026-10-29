# Career surfaces

> Identifiers only: repo names, table names, doc IDs, URLs. **Never credentials.**

| Surface | Identifier | Read | Write mode | Notes |
|---|---|---|---|---|
| Portfolio site | <SITE_URL> | <yes/no> | write-with-approval | |
| Portfolio CMS/DB | <PROVIDER>: project <PROJECT_ID>, tables <TABLES> | | write-with-approval | read-only SQL during audits |
| Portfolio repo | <OWNER/REPO> | | write-with-approval | |
| Code-host profile README | <OWNER/OWNER> | | write-with-approval | |
| LinkedIn | <PROFILE_URL> | <API limits> | hint-only | |
| Resume doc | <DOC_ID>, tabs: <LANGS> | | write-with-approval (suggestions) | keep all language tabs in sync |
| Link-in-bio | <URL> | | hint-only | |
| Short-link service (if owned) | <OWNER/REPO> | | write-with-approval | |
| Company / team profile | <PROVIDER>: <TABLE> + <TRANSLATION_TABLE>, row <ID> | | write-with-approval | the user's own row only |
| Second brain / notes | <OWNER/REPO or path> | | delta-only (writer: <AGENT_NAME>) | follow its protocol files |
