# Redis — No Persistent Dump

Redis in dev-ben is used as a cache/session store only.
It uses ephemeral storage with no RDB/AOF persistence configured.
There is no meaningful data to snapshot from Redis.

To restore Redis: simply start the Redis container. It will rebuild its cache
as services connect and populate it.
