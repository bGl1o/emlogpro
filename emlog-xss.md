# Emlog pro introduce

EMLOG is a lightweight open-source blog and CMS website building system that is fast, resource efficient, and easy to use, suitable for building websites of all sizes.

### The affected version

emlog pro 2.5.x

## Vulnerability description

Storage type XSS

## Vulnerability recurrence

Publish article content and inject malicious XSS

```
test
<script>alert(document.cookie)</script>
```

![image-20250301145217619](https://cdn.jsdelivr.net/gh/bGl1o/Pictures@img/202503011456382.png)

Click Review article

![image-20250301145622391](https://cdn.jsdelivr.net/gh/bGl1o/Pictures@img/202503011456753.png)![image-20250301145624749](./emlog-xss.assets/image-20250301145624749.png)

![image-20250301145626230](https://cdn.jsdelivr.net/gh/bGl1o/Pictures@img/202503011456003.png)