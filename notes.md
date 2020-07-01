---
title: Pub Notes
permalink: /notes/
layout: page
excerpt: Contains my short public notes.
comments: false
---

#### Dictionary instead of switch in enums

Instead of using switch in a computed property of an enum it's possible to use dictionary

```
enum DisplacementType {
    case linearGradient, radial, perlinNoise

    var name: String {
        return [.linearGradient: "linearMap",
                .radial:         "radialMap",
                .perlinNoise:    "perlinMap"
               ][self, default: "default"]
    }
}
```
