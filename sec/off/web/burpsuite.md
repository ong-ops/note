# Burpsuite

## Proxy

- Firefox uses FoxyProxy
- Chrome uses Proxy switchyOmega

### Setup - HTTPS on Firefox

1. Manually to add `Postswigger Certificate Authority (CA)` to trusted certificate authorities list.
2. Access to the `http://burp/cert` and auto download the file `cacert.der`
3. Go to `about:preferences` into Firefox
4. Search `certificates`
5. Go to Option `View Certificates`
6. Click `import` and select the downloaded `cacert.der`
7. Select `Trust this CA to identify websites` and click `OK`

### Setup - Burp Browser

- Built-in Chromium browser
- Be aware run on root user may be compromised entire your machine

### Intercept

- `Ctrl+U` shortcut for URL encode to make it safe to send
 
## Scope

- Click tab `Target`
- Click sub-tab `Site map`
- Right-click to the website that needs to scope it
- Open `Settings/Tools/Proxy/Response interception rules`
- Click `And URL Is in target scope` to ignore any response isn't in the scope

