# FlowMaster Database Snapshots

Snapshot date: 2026-03-02T04:30:58Z
Source: dev-02 (65.21.52.58), namespace dev-ben

## Databases

- **ArangoDB 3.11** (databases: _system, flowmaster, flowmaster_dev) — see arangodb/
- **PostgreSQL 16** (databases: crm, dxg, flowmaster, postgres, procurement) — see postgresql/
- **Redis 7** — in-memory cache only, no dump needed (see redis-note.md)

## Files

| File | Size | Description |
|------|------|-------------|
| arangodb/arango-dump-20260302-083015.tar.gz | 827K | All ArangoDB databases (arangodump format, gzipped) |
| postgresql/pg-dumpall-20260302-083039.sql.gz | 478K | All PostgreSQL databases (pg_dumpall, gzipped SQL) |

## Restore Instructions

### ArangoDB
```bash
tar xzf arango-dump-*.tar.gz
arangorestore --server.endpoint tcp://localhost:8529 --server.username root --server.password <pass> --all-databases true --input-directory arango-dump/
```

### PostgreSQL
```bash
gunzip -c pg-dumpall-*.sql.gz | psql -U postgres
```
