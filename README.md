# Jekyll-manifest.json
Output manifest.json to the _site directory of a Jekyll installation.

Add the following to the config.yml file:

```yml
manifest_name: Web App Full Name
manifest_short_name: Short Name # Appears in "Add to home screen" dialogues and may have other importance also
manifest_lang: en
manifest_background_color: white
manifest_short_name:
manifest_display: standalone
```

Create manifest.yml file in the root directory containing liquid tags to pull values from the config.yml file:

```json
---
permalink: manifest.json
---

{
  "lang": "{{ site.manifest_lang }}",
  "background_color": "#{{ site.manifest_background_color }}",
  "name": "{{ site.manifest_name }}",
  "short_name": "{{ site.manifest_short_name }}",
  "display": "{{ site.manifest_display}}",
  "icons": [
    {
      "src": "img/144X144-icon.png",
      "sizes": "144x144",
      "type": "image/png"
    }
  ]
}
```

Resources:
- [Manifest Generator](http://brucelawson.github.io/manifest/) 
- [Installable Web Apps](https://dev.opera.com/articles/installable-web-apps/)
