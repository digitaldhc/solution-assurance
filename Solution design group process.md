# The solution design process

![Adoption flag](https://img.shields.io/badge/DHC%20adoption%20state-Unadopted-blue) ![Document flag](https://img.shields.io/badge/Document%20state-Draft-blue)

<!-- Initialise a top-down graph -->

```mermaid

graph TD; %% initialise a top-down basic graphic

%% Top level structure
request -- New solution --> newsolution
request -- Change to an existing solution --> existingsolution

%% New software request structure
newsolution -- Request for software --> soft_lifecycle 
soft_lifecycle --> soft_dimr --> soft_publisher --> soft_assurance --> soft_ics --> soft_exit

%% New internal development structure
newsolution -- Request for internal development --> devel_type

devel_type --> devel_tools --> devel_audience --> devel_access --> devel_prem

%% Change to existing solution structure
existingsolution ---> ex_minorormajor
ex_minorormajor -- Minor --> ex_normalchange
ex_minorormajor -- Major --> ex_lifecycle --> ex_sevenrs

%% Common path to workload assessment and return to P&P
devel_prem --> devel_workload
ex_sevenrs ---> devel_workload
devel_workload --> devel_pp

%% Node text labels and shapes
%% ([]) produces a stadium-shaped node
%% () produces a node with round edges (default)
%% [[]] produces a subroutine node
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
devel_workload(Workload assessment)
devel_pp[[Return to P&P]]

ex_minorormajor(A minor or major change)
ex_normalchange[[Exit to change control]]
ex_lifecycle(Alignment with technology lifecycle)
ex_sevenrs(7R assessment)

%% Node formatting
style newsolution fill:#00f
style existingsolution fill:#00f
style request fill:#0f0,color:#000
style soft_exit fill:#c00,color:#fff
style ex_normalchange fill:#c00,color:#fff
style devel_pp fill:#c00,color:#fff


```