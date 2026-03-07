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
