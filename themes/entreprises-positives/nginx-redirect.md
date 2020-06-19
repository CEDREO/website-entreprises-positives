# Nginx redirect
The *config.toml* must include the following section:

```
# Add redirect media
[mediaTypes]
  [mediaTypes."application/redirect"]
    suffixes = [ "redirect" ]

[outputFormats]
    [outputFormats."redirect"]
        mediaType = "application/redirect"
        notAlternative = true
```

And in content, create a redirect section with an _index.md:

```
+++
sitemapexclude=true
outputs=["redirect"]
+++
```

Content item must have a source, a dest and a code:

```
+++
source="/test-source"
dest="/test-dest"
code="301"
outputs=["redirect"]
sitemapexclude=true
+++
```

## Use output in nginx
The directory *redirect* from website dist should be move to nginx 
config directories and be include as a server configuration.
