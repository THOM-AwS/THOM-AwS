# My IT Philosophy

**First I drink the Coffee, then I do the things.**

## Before I Build Anything

**Ask the questions first:**
- How many users? Where do they live?
- Does it need eleven-nines uptime or can we restart it Tuesday afternoon?
- How many engineers maintain this? (2 people shouldn't babysit 50 microservices)
- **What's the budget?** If I wouldn't spend my own money on it, why should the org?

**Then build the simplest thing that works:**
- Monolith first. Microservices are a tax on complexity - only pay it when you must
- Can it still vertically scale? Modern boxes are beasts. Don't distribute prematurely
- Pick your database by query pattern, not hype. Joins? SQL. Key lookups? K/V. Everything else? Probably still SQL
- SAGA pattern only when distributed transactions are unavoidable. Spoiler: they're usually avoidable
- Do you really, REALLY need to have kubernetes or will a lambda do?

**Make it observable:**
- If you can't see it, you can't fix it
- If it's broken and no one knows, is it really running?
- Alerts wake you up. Metrics let you sleep

## How I Ship Code

**Git is the source of truth.**  
If it's not in git, it doesn't exist. Complete history, complete audit trail, no arguments.

**Pipelines, not people.**  
Automate everything. Manual deployments are just future incidents waiting to happen.

**Peer review, always.**  
By someone who actually understands what they're reviewing. No rubber stamps.

**Test in non-prod, deploy to prod.**  
Zero config drift between environments. If prod is special, you're doing it wrong.

**No humans in production.**  
Read-only access is fine. Write access requires a very good reason and an even better audit trail.

**Run it securely:**
- Patch it
- Back it up (and test the restore)
- Monitor it (alert if critical)

**Document it like you'll forget it.**  
Because in 10 years, you will have.

**Spend it like it's your money.**  
Because cloud bills compound like credit cards. If you wouldn't pay for it personally, justify it to the org.
