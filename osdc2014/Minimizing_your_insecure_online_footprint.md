## Embrace the impact: minimizing your (insecure) online footprint
### Peter Mosmans

* Panopticlick EFF
 - generic browser, OS - but it still shows as unique
 - browser plugins, timezone etc - permutations to achieve uniqueness
 - therefore, you can be uniquely tracked

* Evercookie
 - extract.pw | evercoockie
 - is NOT removed via: 
  - remove all cookies
  - clear cache
  - remove all offline content, OR
  - close bwoser
 - mitigation
  - generic OS, browser
  - disable JS
  - private browsing
  - (methods may not be feasible or realistic)

* SSL Strip, removes HTTPS, uses HTTP
 - able to get POST form password from HTTP interception - live demo proof on banking website :/
 - mitigation suggestions
  - VPN
  - check for HTTPS, ensure it's typed in
  - use EFF force HTTPS app (everywhere plugin). Has option for HTTP nowhere, prevents any insecure connections
 
Stopthespies.org

mitigate government data retention by not storing it

* SSL certs
 - certificate authorization/authorities may/may not be trustworthy
 - certificate revocation mechanisms
  - live confermation
  - revocation lists
 - both can be insecure in themselves

OCSP 

* encrypted.google.com - 
 - google reverts https to http once you click a non httpslink
  - because RFC2616 referer handle content cannot be used on http/s switch 
  - google will do switch then refer, so google referer links work for advertising, addworks etc
  - data leakage!!!
 - mitigation  
  - Disable OCSP in browser (firefox defaults this ON)
  - enable SSL/TLS standard when developing sites
  - OCSP stapling

Reduce footprint - Tor

More tools:  
 - Tails - the amnesic incognito live system 
  - live cd iso, all encrypted, Tor
 - defectivebydesign.org
 - duckduckgo



