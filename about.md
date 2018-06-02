---
layout: page
title: About
permalink: /about/
---
Cyber@UC is the official student-led Information Security OWASP Organization for the University of Cincinnati. We spread the knowledge and importance of Information Security across all ages by doing outreaches or by collaboration with companies and organizations.

Our faculty advisor is [Prof. John Franco](http://gauss.ececs.uc.edu/franco_files/franco.html).

## The Team
<div class="row">
  {%- for usr in site.data.team.executives -%}
    <div class="col-sm-6 col-md-4 col-lg-3">
      {% include user-card.html username=usr %}
    </div>
  {%- endfor -%}
</div>
<div class="row">
  {%- for usr in site.data.team.members -%}
    <div class="col-6 col-sm-4 col-md-3 col-lg-2">
      {% include user-card.html username=usr small=true %}
    </div>
  {%- endfor -%}
</div>
