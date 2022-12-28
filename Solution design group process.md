# The solution design process

![Adoption flag](https://img.shields.io/badge/DHC%20adoption%20state-Unadopted-blue) ![Document flag](https://img.shields.io/badge/Document%20state-Draft-blue)

```mermaid

graph TD;

request -- New solution --> newsolution
request -- Change to an existing solution --> existingsolution

newsolution -- Request for software --> soft_lifecycle 
soft_lifecycle --> soft_dimr --> soft_publisher --> soft_assurance --> soft_ics --> soft_exit

newsolution -- Request for internal development --> devel_type

devel_type --> devel_tools --> devel_audience --> devel_access --> devel_prem

existingsolution --> ex_minorormajor
ex_minorormajor -- Minor --> ex_normalchange
ex_minorormajor -- Major --> ex_lifecycle

request([New request])
newsolution(New solution)
existingsolution(Change to an existing solution)
soft_dimr(Alignment with DIMR)
soft_publisher(Publisher assurance)
soft_lifecycle(Alignment with technology lifecyle)
soft_assurance(Alignment with IG and security assurance)
soft_ics(Alignment with ICS standards, aims, objectives)
soft_exit[[Exit to software process]]

devel_type(Type of development)
devel_tools(New tools or existing)
devel_prem(On prem or cloud)
devel_audience(Who is the audience)
devel_access(Is the solution accessed over \nthe internet or HSCN)

ex_minorormajor(A minor or major change)
ex_normalchange(Exit to change control)
ex_lifecycle(Alignment with technology lifecycle)

style request fill:#0f0,color:#000
style soft_exit fill:#c00,color:#fff
style ex_normalchange fill:#c00,color:#fff

```