

  <h1>🔖 IIIT-Knimbus Access Bookmarklet</h1>

  <p>
    This bookmarklet allows you to redirect academic URLs like
    <strong>IEEE, Springer, Nature</strong>, etc. to the <strong>IIIT Kottayam Knimbus proxy</strong>,
    giving you full-text access via institutional login.
  </p>

  <h2>📌 How to Add the Bookmarklet</h2>
  <ol>
    <li>Select and copy the code below.</li>
    <li>Create a new bookmark in your browser.</li>
    <li>Paste the copied code into the <strong>URL or location field</strong>.</li>
    <li>Name the bookmark something like <code>IIIT-Knimbus Access</code>.</li>
  </ol>

  <h3>🔧 Bookmarklet Code (Copy This)</h3>
  <pre><code>javascript:(function(){javascript:(function(){
  const current = location;
  const domainParts = current.hostname.split('.');
  if (domainParts.length &lt; 2) {
    alert("Invalid domain.");
    return;
  }

  // Replace dots in domain with dashes, append the Knimbus suffix
  const knimbusHost = domainParts.join('-') + '-iiitkottayam.knimbus.com';

  // Special case for IEEE: force ieeexplore path format
  if (current.hostname === 'ieeexplore.ieee.org') {
    const match = current.pathname.match(/\/document\/(\d+)\//);
    if (match) {
      location.href = `https://${knimbusHost}/document/${match[1]}`;
      return;
    }
  }

  // Generic case: preserve full path, query, and hash
  const newUrl = `https://${knimbusHost}${current.pathname}${current.search}${current.hash}`;
  location.href = newUrl;
})()})();</code></pre>

  <h3>💡 Or Use This Pre-Encoded Link</h3>
  <p>
    You can also copy and paste this version directly into your bookmark URL field:
  </p>
  <pre><code>javascript:(function()%7Bjavascript%3A(function()%7B%0A%20%20const%20current%20%3D%20location%3B%0A%20%20const%20domainParts%20%3D%20current.hostname.split('.')%3B%0A%20%20if%20(domainParts.length%20%3C%202)%20%7B%0A%20%20%20%20alert(%22Invalid%20domain.%22)%3B%0A%20%20%20%20return%3B%0A%20%20%7D%0A%0A%20%20const%20knimbusHost%20%3D%20domainParts.join('-')%20%2B%20'-iiitkottayam.knimbus.com'%3B%0A%0A%20%20if%20(current.hostname%20%3D%3D%3D%20'ieeexplore.ieee.org')%20%7B%0A%20%20%20%20const%20match%20%3D%20current.pathname.match(%2F%5C%2Fdocument%5C%2F(%5Cd%2B)%5C%2F%2F)%3B%0A%20%20%20%20if%20(match)%20%7B%0A%20%20%20%20%20%20location.href%20%3D%20%60https%3A%2F%2F%24%7BknimbusHost%7D%2Fdocument%2F%24%7Bmatch%5B1%5D%7D%60%3B%0A%20%20%20%20%20%20return%3B%0A%20%20%20%20%7D%0A%20%20%7D%0A%0A%20%20const%20newUrl%20%3D%20%60https%3A%2F%2F%24%7BknimbusHost%7D%24%7Bcurrent.pathname%7D%24%7Bcurrent.search%7D%24%7Bcurrent.hash%7D%60%3B%0A%20%20location.href%20%3D%20newUrl%3B%0A%7D)()%3B%7D)()%3B</code></pre>

  <h2>✅ Examples</h2>
  <ul>
    <li><code>https://ieeexplore.ieee.org/document/xxxxx</code> → <code>https://ieeexplore-ieee-org-iiitkottayam.knimbus.com/document/xxxxx</code></li>
    <li><code>https://link.springer.com/article/yyyy/xxxxx</code> → <code>https://link-springer-com-iiitkottayam.knimbus.com/article/yyyy/xxxxx</code></li>
  </ul>

  <h2>⚠️ Notes</h2>
  <ul>
    <li>You must be on IIIT-K campus or connected via VPN for access.</li>
    <li>Only works with domains supported by Knimbus for IIIT Kottayam.</li>
  </ul>

  <h2>📄 License</h2>
  <p>MIT License – Free to use and share with your peers.</p>

</body>
</html>


<h2>🚀 Use an Online Bookmarklet Maker</h2>

<p>
Instead of manually encoding and copying JavaScript code, use this handy online tool to generate the bookmarklet link:
</p>

<p>
  👉 <a href="https://caiorss.github.io/bookmarklet-maker/" target="_blank" rel="noopener noreferrer">
    Bookmarklet Maker – by Caiorss
  </a>
</p>

<p>Here’s what to do:</p>
<ol>
  <li>Open the site above.</li>
  <li>Paste the JavaScript code below into the editor box.</li>
  <li>It will generate a clickable link.</li>
  <li>Right-click → Bookmark it (or drag to your bookmarks bar).</li>
</ol>

<h3>📋 JavaScript Code to Paste</h3>
<pre><code>(function(){
  const current = location;
  const domainParts = current.hostname.split('.');
  if (domainParts.length < 2) {
    alert("Invalid domain.");
    return;
  }

  // Replace dots in domain with dashes, append the Knimbus suffix
  const knimbusHost = domainParts.join('-') + '-iiitkottayam.knimbus.com';

  // Special case for IEEE
  if (current.hostname === 'ieeexplore.ieee.org') {
    const match = current.pathname.match(/\/document\/(\d+)\//);
    if (match) {
      location.href = `https://${knimbusHost}/document/${match[1]}`;
      return;
    }
  }

  // Generic case
  const newUrl = `https://${knimbusHost}${current.pathname}${current.search}${current.hash}`;
  location.href = newUrl;
})();</code></pre>
