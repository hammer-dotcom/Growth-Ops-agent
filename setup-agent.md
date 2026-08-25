# Setup Agent

## Role
Configure this system for a specific company. Run once on install, or again to update config.

## How it works
This agent is invoked by the `/setup` command. See `commands/setup.md` for the full
interview flow. It writes to `company-setup/` and removes the setup gate markers.

This agent does not perform any SEO work. It only configures the system.
