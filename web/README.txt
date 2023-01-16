
// Sphere.ini Settings

// Use the built in http server
// 0 - disable http server and webpage generation
// 1 - disable http server and enable webpage generation
// 2 - enable http server and webpage generation (default)
UseHttp=2

For enabling the modern status page copy paste the following entries in the sphere.ini in the WEBPAGE SETTINGS block.

[WEBPAGE 1]
// Determines what html file is used as base for the status page
WebPageSrc=scripts/web/base/index.html
// Determines where the status page is saved
WebPageFile=scripts/web/outputs/index.html
// In seconds, how often the status file is updated
WebPageUpdate=60
// Required PLevel to view this page (0 = anyone, 6 = admins only)
PLevel=1

[WEBPAGE 2]
// Determines what html file is used as base for the status page
WebPageSrc=scripts/web/base/guilds.html
// Determines where the status page is saved
WebPageFile=scripts/web/outputs/guilds.html
// In seconds, how often the status file is updated
WebPageUpdate=60
// Required PLevel to view this page (0 = anyone, 6 = admins only)
PLevel=1

[WEBPAGE 3]
// Determines what html file is used as base for the status page
WebPageSrc=scripts/web/base/clients.html
// Determines where the status page is saved
WebPageFile=scripts/web/outputs/clients.html
// In seconds, how often the status file is updated
WebPageUpdate=60
// Required PLevel to view this page (0 = anyone, 6 = admins only)
PLevel=1

[WEBPAGE 4]
// Determines what html file is used as base for the status page
WebPageSrc=scripts/web/base/items.html
// Determines where the status page is saved
WebPageFile=scripts/web/outputs/items.html
// In seconds, how often the status file is updated
WebPageUpdate=60
// Required PLevel to view this page (0 = anyone, 6 = admins only)
PLevel=1

[WEBPAGE 5]
// Determines what html file is used as base for the status page
WebPageSrc=scripts/web/base/chars.html
// Determines where the status page is saved
WebPageFile=scripts/web/outputs/chars.html
// In seconds, how often the status file is updated
WebPageUpdate=60
// Required PLevel to view this page (0 = anyone, 6 = admins only)
PLevel=1

[WEBPAGE 6]
// Determines what html file is used as base for the status page
WebPageSrc=scripts/web/base/skills.html
// Determines where the status page is saved
WebPageFile=scripts/web/outputs/skills.html
// In seconds, how often the status file is updated
WebPageUpdate=60
// Required PLevel to view this page (0 = anyone, 6 = admins only)
PLevel=1

[WEBPAGE 7]
// Determines what html file is used as base for the status page
WebPageSrc=scripts/web/base/spells.html
// Determines where the status page is saved
WebPageFile=scripts/web/outputs/spells.html
// In seconds, how often the status file is updated
WebPageUpdate=60
// Required PLevel to view this page (0 = anyone, 6 = admins only)
PLevel=1



[WEBPAGE 8]
// Determines what html file is used as base for the status page
WebPageSrc=scripts/web/base/areas.html
// Determines where the status page is saved
WebPageFile=scripts/web/outputs/areas.html
// In seconds, how often the status file is updated
WebPageUpdate=5
// Required PLevel to view this page (0 = anyone, 6 = admins only)
PLevel=1


[WEBPAGE 9]
// Determines what html file is used as base for the status page
WebPageSrc=scripts/web/base/rooms.html
// Determines where the status page is saved
WebPageFile=scripts/web/outputs/rooms.html
// In seconds, how often the status file is updated
WebPageUpdate=5
// Required PLevel to view this page (0 = anyone, 6 = admins only)
PLevel=1