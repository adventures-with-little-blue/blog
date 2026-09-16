# Motoblog om Lilla Blue

https://adventures-with-little-blue.github.io/blog/

### Kommandon

Starta DEV-server:
```PowerShell
hugo server -D
```

Ny post:
```PowerShell
hugo new content content\sv\posts\2025-07-18-kalajoki
```

Publisera:
```PowerShell
hugo --cleanDestinationDir --minify
```

### YouTube Shorts

Embed a YouTube Short using its 11-character video ID:

```go-html-template
{{< youtube-short id="dQw4w9WgXcQ" title="Optional accessible video title" >}}
```

The positional form is also supported:

```go-html-template
{{< youtube-short dQw4w9WgXcQ >}}
```
