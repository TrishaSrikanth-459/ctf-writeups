# RelayBoard CTF

RelayBoard is an original easy-medium web application CTF built around a shift
handoff portal for operations teams.

## What Is Included

- `backend/`: all vulnerable backend code, templates, static assets, and snippet files
- `solve.py`: proof-of-concept exploit script
- `Vulnerability_Report.md`: formal report in the format you requested
- `Dockerfile`: container entrypoint for public deployment
- `docker-compose.yml`: simple public-server launch configuration
- `PUBLIC_DEPLOY.md`: exact steps for making the app internet-accessible
- `run.sh`: local launcher
- `share_public.sh`: local launcher plus public ngrok tunnel

## Goal

Recover the flag stored in the private admin packet.

## Live Challenge URL

Players can access the challenge here:

`https://hung-concessible-overjoyfully.ngrok-free.dev`

## Public Deployment

If you want someone anywhere on the internet to reach it, deploy this folder on
a public Linux server. The project includes both a `Dockerfile` and
`docker-compose.yml` for that case. The step-by-step commands are in
`PUBLIC_DEPLOY.md`.

## Intended Solve Path

1. Register a normal user account.
2. Abuse the packet preview include resolver to read `backend/config.py`.
3. Recover the Flask secret key from the source.
4. Forge an admin session cookie.
5. Open `/admin/archive/1` and capture the flag.
