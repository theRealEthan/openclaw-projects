# Errors

## [ERR-20260307-001] builder_reference_path

**Logged**: 2026-03-07T14:06:59Z
**Priority**: medium
**Status**: pending
**Area**: docs

### Summary
Builder reference path from prompt did not exist on host.

### Error
```
ls: cannot access '/home/ethan/.openclaw/docs': No such file or directory
```

### Context
Attempted to follow provided path `~/.openclaw/docs/BUILDER_REFERENCE.md`; actual file found at `/home/ethan/.openclaw/BUILDER_REFERENCE.md`.

### Suggested Fix
Use fallback path discovery before section extraction.

### Metadata
- Reproducible: yes
- Related Files: /home/ethan/.openclaw/BUILDER_REFERENCE.md

---
## [ERR-20260307-002] builder_log_permissions

**Logged**: 2026-03-07T14:12:15Z
**Priority**: medium
**Status**: pending
**Area**: infra

### Summary
Could not write required builder progress log to /var/log/openclaw/builder.log.

### Error
```
mkdir: cannot create directory '/var/log/openclaw': Permission denied
```

### Context
Runtime user lacks permission for /var/log path.

### Suggested Fix
Grant write permission for /var/log/openclaw or configure builder log fallback path under ~/.openclaw/logs.

### Metadata
- Reproducible: yes
- Related Files: /var/log/openclaw/builder.log

---
## [ERR-20260315-001] root_nginx_edit_blocked

**Logged**: 2026-03-15T11:49:00+02:00
**Priority**: high
**Status**: pending
**Area**: infra

### Summary
Could not apply required nginx proxy fix because elevated/root execution is blocked for this session provider.

### Error
```
elevated is not available right now (runtime=direct)
Failing gates: allowFrom ... provider=webchat
```

### Context
Mission Control static assets were returning 400 HTML responses due to reverse proxy behavior. Fix requires editing `/etc/nginx/sites-available/mission-control` and reloading nginx, which needs root privileges.

### Suggested Fix
Run the provided sudo commands in a shell, or enable elevated tool usage for webchat provider in OpenClaw config.

### Metadata
- Reproducible: yes
- Related Files: /etc/nginx/sites-available/mission-control

---
