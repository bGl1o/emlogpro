# Emlog pro introduce

EMLOG is a lightweight open-source blog and CMS website building system that is fast, resource efficient, and easy to use, suitable for building websites of all sizes.

### The affected version

emlog pro 2.5.x

## Vulnerability description

Storage type XSS

## Vulnerability recurrence

Publish article content and inject malicious XSS

```
test><script>alert("test")</script>
```

![image-20250301155108774](./emlog-xss-2.assets/image-20250301155206361.png)

Click Comment function

![image-20250301155122060](./emlog-xss-2.assets/image-20250301155122060.png)

![image-20250301155501231](./emlog-xss-2.assets/image-20250301155501231.png)