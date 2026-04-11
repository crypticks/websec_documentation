### Subdomain Enum

```
subfinder -d $target -all > domains1.txt
```

```
assetfinder $target -subs-only > domains2.txt
```


```
sort -u domains1.txt domains2.txt > domains.txt
```

If you wanna see number of domains, `cat domains.txt > wc -l`


### Finding live Domains


Finding status codes, services, etc
```
cat domains.txt | httpx -sc > status.txt
```

Finding hidden directories, etc.
```
ffuf -u https://FUZZ.$target -w wordlist -o ffuf.txt
```

```
sudo feroxbuster -u https://$target -w $directorywordlist -x php,html,txt,jpeg,png,jpg
```

Find XSS:
```
xsser -u "<FUZZ-style XSS-replaced link>"
```

See active subdomains:
```
cat status.txt | grep "200"
```


Subdomain Takeover tool
```
subzy run --targets domains.txt
```