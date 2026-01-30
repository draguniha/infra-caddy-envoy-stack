# Caddy + Envoy Docker Stack !! :*

das my docker compose setup with caddy for edge proxy and envoy as internal proxy for small production!

this repo is not a tutorial and not a framework ofc and just a reference setup for a small service running without k8s

## how does that work? no worries mamas

1. Caddy handles edge traffic and TLS
2. Envoy sits in front of the application and handles routing
3. Application runs as a plain container (not included here ok?)
4. Postgres is used as a primary database (who would've known)
5. Loki is used for centralized logs

The goal is to keep things explicit and boring (and easy):
- no auto-discovery
- no dependency on k8s

#Why this setup you may ask?

This stack is useful when:
- Kubernetes is overkill or it's just too complicated 4you
- you got tired from maintaining nginx configs (me too!)
- you want retries / timeouts / routing logic without service mesh
- infrastructure should stay understandable by a small team

Envoy is used intentionally even for a single service to keep the path open
for future traffic control without rewriting everything later.

so be my guest!
