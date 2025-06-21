# XSSer – Automated Cross-Site Scripting (XSS) Tool

**XSSer** is an open-source tool for detecting and exploiting Cross-Site Scripting (XSS) vulnerabilities in web applications. It automates XSS discovery and supports multiple attack vectors including DOM, GET, POST, and even custom payloads.

🔗 [Use the XSSer Command Generator on SploitHQ](https://sploithq.com/xss)

---

## 🔍 What Can XSSer Do?

- Detect reflected, persistent, and DOM-based XSS
- Test GET, POST, and custom parameters
- Encode payloads in multiple formats (Base64, HEX, etc.)
- Bypass WAFs and filters using tampering techniques
- Use custom scripts and fuzzing options
- Export results to reports or log files

---

## ⚙️ Basic Usage

```bash
xsser -u "http://target.com/page.php?query=test"
```

This scans the `query` parameter for possible XSS vulnerabilities.

---

## 🧰 Commonly Used Options

| Option                      | Description                                                  |
|-----------------------------|--------------------------------------------------------------|
| `-u <url>`                  | Target URL with parameter                                    |
| `--data "<post_data>"`      | POST data for testing forms                                  |
| `--cookie "<cookie>"`       | Include a session or auth cookie                            |
| `--auto`                    | Automatically use all available payloads                    |
| `--all`                     | Use all tests including persistent and DOM XSS               |
| `--fuzz`                    | Fuzz parameter locations to find injection points           |
| `--payload "<script>"`      | Use a custom XSS payload                                     |
| `--Hex`, `--Str`, `--B64`   | Encode payload in HEX, STR, or Base64                       |
| `--WAF`                     | Enable WAF bypass modes                                      |
| `--file <file>`             | Load list of URLs to test                                    |
| `--timeout <secs>`          | Set timeout for each request                                 |

---

## 🧪 Examples

### Basic GET scan
```bash
xsser -u "http://example.com/search?q=term"
```

### POST form injection with data
```bash
xsser -u "http://example.com/login" --data "username=admin&password=123"
```

### Use custom XSS payload
```bash
xsser -u "http://target.com/page.php?input=1" --payload "<script>alert(1)</script>"
```

### Fuzz and use WAF bypass
```bash
xsser -u "http://testsite.com/page.php?id=2" --fuzz --WAF
```

### Encode payload with Base64
```bash
xsser -u "http://target.com/input" --payload "<img src=x onerror=alert(1)>" --B64
```

---

## ⚠️ Notes

- XSSer is aggressive; use only with **explicit permission**.
- Encoding and tampering may help bypass WAFs or poorly filtered apps.
- Use `--auto` or `--all` to run wide scans, but expect slower performance.

---

## 🌐 Live Command Generator

Want to create an XSS test without remembering all the flags?

👉 [Use the XSSer Generator on SploitHQ](https://sploithq.com/xss)

- Select method: GET, POST, fuzzing
- Add payload or choose encoded options
- Generate and copy your full command instantly

---

## 🔗 Useful Links

- [XSSer GitHub Repository](https://github.com/epsylon/xsser)
- [XSSer Official Documentation](https://xsser.03c8.net/)
- [SploitHQ XSSer Tool](https://sploithq.com/xss)

---

## 📄 License

XSSer is licensed under the GNU GPL v2.0.

This page is maintained by [SploitHQ](https://sploithq.com) for educational and professional testing use.
