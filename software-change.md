# Software change process

```mermaid

flowchart LR;

request --> saa --> valid

saa --> not_a_request

saa <--> additional_engagement

valid --> pipeline

valid --> complex

valid --> standard

valid --> emergency

complex --> assess_endpoint
complex --> assess_serversstorage
complex --> assess_security
complex --> assess_ig
standard --> assess_third

subgraph Assessment
assess_endpoint --> assess_outcome
assess_serversstorage --> assess_outcome
assess_security --> assess_outcome
assess_ig --> assess_outcome
assess_third --> ato
end

ato --> packaging

assess_outcome --> denied
assess_outcome --> resourcing --> fulfil

emergency --> third_line --> packaging --> fulfil

third_line --> emergency_install --> fulfil

%% Styles
classDef c_valid fill:#0f0,color:#000
classDef reject fill:#c00,color:#fff
classDef service_mgmt fill:#3ff,color:#000
classDef technical fill:#47a,color:#000
classDef c_request fill:#ee4,color:#000
classDef c_assess fill:#d7e,color:#000

%% Assignment of styles to nodes
class valid,fulfil c_valid
class not_a_request,denied reject
class saa,additional_engagement,resourcing service_mgmt
class third_line,packaging,emergency_install technical
class request,pipeline,complex,standard,emergency c_request
class assess_endpoint,assess_serversstorage,assess_security,assess_ig,assess_third c_assess