# 🔖 IIIT-Knimbus Access Bookmarklet

Access subscription-based academic resources through the **IIIT Kottayam Knimbus proxy**—with one click.

This bookmarklet automatically rewrites URLs like IEEE, Springer, Nature, etc., to route through IIIT Kottayam's Knimbus proxy server, allowing seamless access to full-text papers if you're a student or staff of IIIT-K.

---

## 📚 Supported Sites (Examples)

| Original URL | Redirects To |
|--------------|--------------|
| `https://ieeexplore.ieee.org/document/10420491` | `https://ieeexplore-ieee-org-iiitkottayam.knimbus.com/document/10420491` |
| `https://link.springer.com/article/10.1007/s12525-025-00796-6` | `https://link-springer-com-iiitkottayam.knimbus.com/article/10.1007/s12525-025-00796-6` |
| `https://www.nature.com/articles/s41586-024-07242-0` | `https://www-nature-com-iiitkottayam.knimbus.com/articles/s41586-024-07242-0` |

---

## 🔗 Add the Bookmarklet

**Drag the link below to your bookmarks bar:**

[🔓 IIIT-Knimbus Access](javascript:(function(){const%20current=location;const%20domainParts=current.hostname.split('.');if(domainParts.length<2){alert('Invalid%20domain.');return;}const%20knimbusHost=domainParts.join('-')+'-iiitkottayam.knimbus.com';if(current.hostname==='ieeexplore.ieee.org'){const%20match=current.pathname.match(/\\/document\\/(\\d+)/);if(match){location.href=`https://${knimbusHost}/document/${match[1]}`;return;}}const%20newUrl=`https://${knimbusHost}${current.pathname}${current.search}${current.hash}`;location.href=newUrl;})())

> 🧠 Tip: If the link doesn't drag properly, right-click → Bookmark this link

---

## 🛠 What It Does

- ✨ **Automatically rewrites** domains like `ieeexplore.ieee.org` to their Knimbus counterparts (e.g., `ieeexplore-ieee-org-iiitkottayam.knimbus.com`)
- 💾 **Preserves paths, query params, and hashes** – so you'll stay on the same document, article, or page
- 📖 **Optimized for academic resources** used by IIIT-K students and staff

---

## 📌 How to Use

1. Go to any academic page (e.g., IEEE, Springer, Nature).
2. Click the **bookmarklet** from your bookmarks bar.
3. You'll be redirected to the Knimbus proxy version of the same resource.
4. If you're within IIIT-K network or logged into the proxy, you'll get full access.

---

## ❗ Notes

- Requires access through IIIT Kottayam’s proxy (e.g., logged in via VPN or campus network).
- If a page doesn’t work, make sure the original domain is supported by Knimbus and properly mapped.

---

## 💡 Want More?

- Add support for more domains? Open a PR or issue!
- Want a browser extension? We can build a version that automatically redirects on page load.

---

## 📄 License

MIT License
