# Tandoor Recipes LazyCat package

Source https://github.com/TandoorRecipes/recipes,2.7.2. Official candidate com.tandoor.recipes. Package community.lazycat.app.tandoor,minOS1.5.0,amd64 mirror delivery, community store only. Current version is AGPL-3.0; the MIT section in LICENSE.md only applies to versions before0.10, not a current dual-license grant. Intended category Tools/Kitchen63.

Two upstream containers: vabene1111/recipes HTTP80 and internal PostgreSQL16-alpine. Data and uploaded media persist separately. Preserve the native entrypoint waiting for the database, migrations and collectstatic. Do not bind an empty staticfiles directory over built assets. Do not force a container UID or invent extra healthchecks/smoke jobs.

First account creation at /setup/ is MANUAL; use deployment values and satisfy native validation. Parameters only fill /accounts/login/ through native login fields, no auto-submit and no account creation/reset. Platform authentication remains mandatory; default shared fill should only be given to trusted users. Native user/space isolation is managed inside Tandoor, not automatically mapped from platform identity.

Restrict ALLOWED_HOSTS to the platform domain/internal names and set CSRF_TRUSTED_ORIGINS to the HTTPS app domain. Stable independent Django and database secrets are generated per app; no external credentials are included. Back up PostgreSQL and media together before uninstalling; do not change DB major in place.

Build and independent artifact checks run on GitHub, no local source/image/LPK downloads. No file interception or smoke. Startup/migrations, first account, autofill, URL import, editing, shopping plans, mail and persistence have not been runtime-verified.
