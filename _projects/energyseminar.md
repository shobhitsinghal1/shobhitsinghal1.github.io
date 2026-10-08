---
layout: page
title: Energy Community Seminar
description: Online seminar series on local energy markets, across disciplines
importance: 4
category: work
mermaid:
  enabled: true
  zoomable: false
# Add a new entry here for each lecture. Leave `video` empty until the recording is up.
lectures:
  - title: Introduction to Local Energy Markets
    date: October 2026
    track: Kickstarter
    description: An overview lecture by an expert that maps out the field and sets the stage for the four tracks.
    video:
---

Local energy markets are studied by control engineers, optimizers, power engineers, economists and policy researchers, often in silos. This bi-weekly online seminar series brings these communities together around **one problem**, with every talk recorded so newcomers can learn about the parts outside their own field.

## Tree of knowledge

Each seminar fills in a node of this tree. It grows as the series goes on.

```mermaid
flowchart TD
    intro["Introduction to local energy markets"]
    intro --> t1["1. Power system dynamics"]
    intro --> t2["2. Dispatch"]
    intro --> t3["3. Capacity investments"]
    intro --> t4["4. Policy and society"]
    t1 --> a["Frequency & voltage stability"]
    t2 --> b["AC-OPF"]
    t2 --> c["Mechanism design"]
    t3 --> d["PPAs"]
    t4 --> e["EU regulations"]
    t4 --> f["Fairness"]

    classDef root fill:#fff3b0,stroke:#b59f3b,color:#222
    classDef track fill:#f8c8c8,stroke:#b55,color:#222
    classDef topic fill:#dcdcfa,stroke:#669,color:#222
    class intro root
    class t1,t2,t3,t4 track
    class a,b,c,d,e,f topic
```

## Lectures

{% for lecture in page.lectures %}

<div class="mb-4">
  <h3 class="mb-1">{{ lecture.title }}</h3>
  <p class="text-muted mb-1"><small>{{ lecture.date }} &middot; {{ lecture.track }}</small></p>
  <p class="mb-1">{{ lecture.description }}</p>
  {% if lecture.video %}
    <a href="{{ lecture.video }}" target="_blank" rel="noopener"><i class="fa-solid fa-play"></i> Watch video</a>
  {% else %}
    <span class="text-muted"><small>Video coming soon</small></span>
  {% endif %}
</div>
{% endfor %}
