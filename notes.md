---
title: Pub Notes
permalink: /notes/
layout: page
excerpt: Contains my short public notes.
comments: false
---

### #1 Using flatMap instead of unwrapping with if or guard

Before
```
guard let urlValue = getUrlValue() else {
    return
}
let url = URL(string: urlValue)
```
Aflter
```
let url = getUrlValue().flatMap(URL.init)
```

#### #0 Dictionary instead of switch

Instead of using `switch` it's possible to use `dictionary`, for example in an enum:

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

This might be useful when you have a lot of cases, so instead of the worst complexity with switch <kbd>O(n)</kbd> you would get <kbd>O(1)</kbd> with dictionary.
