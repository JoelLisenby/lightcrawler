# lightcrawler
Crawl a website and run it through Google lighthouse and output results in html file.

Upon completion the output will be saved in results.html file in the directory the command is run from.

```bash
npm install --save-dev lightcrawler

lightcrawler --url https://atom.io/ --config lightcrawler-config.json
```

where `lightcrawler-config.json` looks something like this:
```json
{
  "extends": "lighthouse:default",
  "settings": {
    "output": {
      "destination": "result.html"
    },
    "crawler": {
      "maxDepth": 2,
      "maxChromeInstances": 5
    },
    "onlyCategories": [
      "Accessibility",
      "Performance",
      "Best Practices"
    ],
    "onlyAudits": [
      "accesskeys",
      "aria-allowed-attr",
      "external-anchors-use-rel-noopener",
      "geolocation-on-start",
      "no-document-write",
      "no-mutation-events",
      "no-old-flexbox",
      "time-to-interactive",
      "user-timings",
      "viewport",
      "without-javascript"
    ]
  }
}
```

Enjoy!