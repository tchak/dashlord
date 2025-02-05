
# ZAP Scanning Report

Generated on Wed, 21 Apr 2021 12:41:00


## Summary of Alerts

| Risk Level | Number of Alerts |
| --- | --- |
| High | 0 |
| Medium | 4 |
| Low | 4 |
| Informational | 3 |

## Alerts

| Name | Risk Level | Number of Instances |
| --- | --- | --- | 
| Cross-Domain Misconfiguration | Medium | 12 | 
| CSP: Wildcard Directive | Medium | 11 | 
| Reverse Tabnabbing | Medium | 3 | 
| Source Code Disclosure - PHP | Medium | 2 | 
| Cookie No HttpOnly Flag | Low | 2 | 
| Cross-Domain JavaScript Source File Inclusion | Low | 10 | 
| Feature Policy Header Not Set | Low | 11 | 
| Incomplete or No Cache-control and Pragma HTTP Header Set | Low | 11 | 
| Base64 Disclosure | Informational | 11 | 
| Storable and Cacheable Content | Informational | 11 | 
| Timestamp Disclosure - Unix | Informational | 112 | 

## Alert Detail


  
  
  
  
### Cross-Domain Misconfiguration
##### Medium (Medium)
  
  
  
  
#### Description
<p>Web browser data loading may be possible, due to a Cross Origin Resource Sharing (CORS) misconfiguration on the web server</p>
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/images/favicons/favicon-32x32.png](https://aidantsconnect.beta.gouv.fr/static/images/favicons/favicon-32x32.png)
  
  
  * Method: `GET`
  
  
  * Evidence: `Access-Control-Allow-Origin: *`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/images/favicons/manifest.json](https://aidantsconnect.beta.gouv.fr/static/images/favicons/manifest.json)
  
  
  * Method: `GET`
  
  
  * Evidence: `Access-Control-Allow-Origin: *`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/css/home.css](https://aidantsconnect.beta.gouv.fr/static/css/home.css)
  
  
  * Method: `GET`
  
  
  * Evidence: `Access-Control-Allow-Origin: *`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/images/favicons/apple-icon-180x180.png](https://aidantsconnect.beta.gouv.fr/static/images/favicons/apple-icon-180x180.png)
  
  
  * Method: `GET`
  
  
  * Evidence: `Access-Control-Allow-Origin: *`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/css/main.css](https://aidantsconnect.beta.gouv.fr/static/css/main.css)
  
  
  * Method: `GET`
  
  
  * Evidence: `Access-Control-Allow-Origin: *`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/images/aidants-connect_logo.png](https://aidantsconnect.beta.gouv.fr/static/images/aidants-connect_logo.png)
  
  
  * Method: `GET`
  
  
  * Evidence: `Access-Control-Allow-Origin: *`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/images/Marianne_logo_1120.png](https://aidantsconnect.beta.gouv.fr/static/images/Marianne_logo_1120.png)
  
  
  * Method: `GET`
  
  
  * Evidence: `Access-Control-Allow-Origin: *`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/images/aidantsconnect-illustration.svg](https://aidantsconnect.beta.gouv.fr/static/images/aidantsconnect-illustration.svg)
  
  
  * Method: `GET`
  
  
  * Evidence: `Access-Control-Allow-Origin: *`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/css/template.min.css](https://aidantsconnect.beta.gouv.fr/static/css/template.min.css)
  
  
  * Method: `GET`
  
  
  * Evidence: `Access-Control-Allow-Origin: *`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/images/favicons/safari-pinned-tab.svg](https://aidantsconnect.beta.gouv.fr/static/images/favicons/safari-pinned-tab.svg)
  
  
  * Method: `GET`
  
  
  * Evidence: `Access-Control-Allow-Origin: *`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/images/favicons/favicon-16x16.png](https://aidantsconnect.beta.gouv.fr/static/images/favicons/favicon-16x16.png)
  
  
  * Method: `GET`
  
  
  * Evidence: `Access-Control-Allow-Origin: *`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/images/key.svg](https://aidantsconnect.beta.gouv.fr/static/images/key.svg)
  
  
  * Method: `GET`
  
  
  * Evidence: `Access-Control-Allow-Origin: *`
  
  
  
  
Instances: 12
  
### Solution
<p>Ensure that sensitive data is not available in an unauthenticated manner (using IP address white-listing, for instance).</p><p>Configure the "Access-Control-Allow-Origin" HTTP header to a more restrictive set of domains, or remove all CORS headers entirely, to allow the web browser to enforce the Same Origin Policy (SOP) in a more restrictive manner.</p>
  
### Other information
<p>The CORS misconfiguration on the web server permits cross-domain read requests from arbitrary third party domains, using unauthenticated APIs on this domain. Web browser implementations do not permit arbitrary third parties to read the response from authenticated APIs, however. This reduces the risk somewhat. This misconfiguration could be used by an attacker to access data that is available in an unauthenticated manner, but which uses some other form of security, such as IP address white-listing.</p>
  
### Reference
* http://www.hpenterprisesecurity.com/vulncat/en/vulncat/vb/html5_overly_permissive_cors_policy.html

  
#### CWE Id : 264
  
#### WASC Id : 14
  
#### Source ID : 3

  
  
  
  
### CSP: Wildcard Directive
##### Medium (Medium)
  
  
  
  
#### Description
<p>The following directives either allow wildcard sources (or ancestors), are not defined, or are overly broadly defined: </p><p>frame-ancestors, form-action</p><p></p><p>The directive(s): frame-ancestors, form-action are among the directives that do not fallback to default-src, missing/excluding them is the same as allowing anything.</p>
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/faq/donnees-personnelles/](https://aidantsconnect.beta.gouv.fr/faq/donnees-personnelles/)
  
  
  * Method: `GET`
  
  
  * Parameter: `Content-Security-Policy`
  
  
  * Evidence: `script-src 'self' 'sha256-FUfFEwUd+ObSebyGDfkxyV7KwtyvBBwsE/VxIOfPD68=' 'sha256-dzE1fiHF13yOIlSQf8CYbmucPoYAOHwQ70Y3OO70o+E=' 'sha256-DkGfInBE1PdVNgl1fcJGI5vAFLJWY82M/J2EaQVIsdc=' 'sha256-ARvyo8AJ91wUvPfVqP2FfHuIHZJN3xaLI7Vgj2tQx18='; object-src 'none'; img-src 'self' https://www.service-public.fr/resources/v-5cf79a7acf/web/css/img/png/; style-src 'self'; default-src 'self'; frame-src https://www.youtube.com/embed/hATrqHG4zYQ https://www.youtube.com/embed/WTHj_kQXnzs https://www.youtube.com/embed/ihsm-36I-fE`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/habilitation](https://aidantsconnect.beta.gouv.fr/habilitation)
  
  
  * Method: `GET`
  
  
  * Parameter: `Content-Security-Policy`
  
  
  * Evidence: `script-src 'self' 'sha256-FUfFEwUd+ObSebyGDfkxyV7KwtyvBBwsE/VxIOfPD68=' 'sha256-dzE1fiHF13yOIlSQf8CYbmucPoYAOHwQ70Y3OO70o+E=' 'sha256-DkGfInBE1PdVNgl1fcJGI5vAFLJWY82M/J2EaQVIsdc=' 'sha256-ARvyo8AJ91wUvPfVqP2FfHuIHZJN3xaLI7Vgj2tQx18='; object-src 'none'; img-src 'self' https://www.service-public.fr/resources/v-5cf79a7acf/web/css/img/png/; style-src 'self'; default-src 'self'; frame-src https://www.youtube.com/embed/hATrqHG4zYQ https://www.youtube.com/embed/WTHj_kQXnzs https://www.youtube.com/embed/ihsm-36I-fE`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/ressources/](https://aidantsconnect.beta.gouv.fr/ressources/)
  
  
  * Method: `GET`
  
  
  * Parameter: `Content-Security-Policy`
  
  
  * Evidence: `script-src 'self' 'sha256-FUfFEwUd+ObSebyGDfkxyV7KwtyvBBwsE/VxIOfPD68=' 'sha256-dzE1fiHF13yOIlSQf8CYbmucPoYAOHwQ70Y3OO70o+E=' 'sha256-DkGfInBE1PdVNgl1fcJGI5vAFLJWY82M/J2EaQVIsdc=' 'sha256-ARvyo8AJ91wUvPfVqP2FfHuIHZJN3xaLI7Vgj2tQx18='; object-src 'none'; img-src 'self' https://www.service-public.fr/resources/v-5cf79a7acf/web/css/img/png/; style-src 'self'; default-src 'self'; frame-src https://www.youtube.com/embed/hATrqHG4zYQ https://www.youtube.com/embed/WTHj_kQXnzs https://www.youtube.com/embed/ihsm-36I-fE`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/](https://aidantsconnect.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Parameter: `Content-Security-Policy`
  
  
  * Evidence: `script-src 'self' 'sha256-FUfFEwUd+ObSebyGDfkxyV7KwtyvBBwsE/VxIOfPD68=' 'sha256-dzE1fiHF13yOIlSQf8CYbmucPoYAOHwQ70Y3OO70o+E=' 'sha256-DkGfInBE1PdVNgl1fcJGI5vAFLJWY82M/J2EaQVIsdc=' 'sha256-ARvyo8AJ91wUvPfVqP2FfHuIHZJN3xaLI7Vgj2tQx18='; object-src 'none'; img-src 'self' https://www.service-public.fr/resources/v-5cf79a7acf/web/css/img/png/; style-src 'self'; default-src 'self'; frame-src https://www.youtube.com/embed/hATrqHG4zYQ https://www.youtube.com/embed/WTHj_kQXnzs https://www.youtube.com/embed/ihsm-36I-fE`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/accounts/login/](https://aidantsconnect.beta.gouv.fr/accounts/login/)
  
  
  * Method: `GET`
  
  
  * Parameter: `Content-Security-Policy`
  
  
  * Evidence: `script-src 'self' 'sha256-FUfFEwUd+ObSebyGDfkxyV7KwtyvBBwsE/VxIOfPD68=' 'sha256-dzE1fiHF13yOIlSQf8CYbmucPoYAOHwQ70Y3OO70o+E=' 'sha256-DkGfInBE1PdVNgl1fcJGI5vAFLJWY82M/J2EaQVIsdc=' 'sha256-ARvyo8AJ91wUvPfVqP2FfHuIHZJN3xaLI7Vgj2tQx18='; object-src 'none'; img-src 'self' https://www.service-public.fr/resources/v-5cf79a7acf/web/css/img/png/; style-src 'self'; default-src 'self'; frame-src https://www.youtube.com/embed/hATrqHG4zYQ https://www.youtube.com/embed/WTHj_kQXnzs https://www.youtube.com/embed/ihsm-36I-fE`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/robots.txt](https://aidantsconnect.beta.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  * Parameter: `Content-Security-Policy`
  
  
  * Evidence: `script-src 'self' 'sha256-FUfFEwUd+ObSebyGDfkxyV7KwtyvBBwsE/VxIOfPD68=' 'sha256-dzE1fiHF13yOIlSQf8CYbmucPoYAOHwQ70Y3OO70o+E=' 'sha256-DkGfInBE1PdVNgl1fcJGI5vAFLJWY82M/J2EaQVIsdc=' 'sha256-ARvyo8AJ91wUvPfVqP2FfHuIHZJN3xaLI7Vgj2tQx18='; object-src 'none'; img-src 'self' https://www.service-public.fr/resources/v-5cf79a7acf/web/css/img/png/; style-src 'self'; default-src 'self'; frame-src https://www.youtube.com/embed/hATrqHG4zYQ https://www.youtube.com/embed/WTHj_kQXnzs https://www.youtube.com/embed/ihsm-36I-fE`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/faq/](https://aidantsconnect.beta.gouv.fr/faq/)
  
  
  * Method: `GET`
  
  
  * Parameter: `Content-Security-Policy`
  
  
  * Evidence: `script-src 'self' 'sha256-FUfFEwUd+ObSebyGDfkxyV7KwtyvBBwsE/VxIOfPD68=' 'sha256-dzE1fiHF13yOIlSQf8CYbmucPoYAOHwQ70Y3OO70o+E=' 'sha256-DkGfInBE1PdVNgl1fcJGI5vAFLJWY82M/J2EaQVIsdc=' 'sha256-ARvyo8AJ91wUvPfVqP2FfHuIHZJN3xaLI7Vgj2tQx18='; object-src 'none'; img-src 'self' https://www.service-public.fr/resources/v-5cf79a7acf/web/css/img/png/; style-src 'self'; default-src 'self'; frame-src https://www.youtube.com/embed/hATrqHG4zYQ https://www.youtube.com/embed/WTHj_kQXnzs https://www.youtube.com/embed/ihsm-36I-fE`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr](https://aidantsconnect.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Parameter: `Content-Security-Policy`
  
  
  * Evidence: `script-src 'self' 'sha256-FUfFEwUd+ObSebyGDfkxyV7KwtyvBBwsE/VxIOfPD68=' 'sha256-dzE1fiHF13yOIlSQf8CYbmucPoYAOHwQ70Y3OO70o+E=' 'sha256-DkGfInBE1PdVNgl1fcJGI5vAFLJWY82M/J2EaQVIsdc=' 'sha256-ARvyo8AJ91wUvPfVqP2FfHuIHZJN3xaLI7Vgj2tQx18='; object-src 'none'; img-src 'self' https://www.service-public.fr/resources/v-5cf79a7acf/web/css/img/png/; style-src 'self'; default-src 'self'; frame-src https://www.youtube.com/embed/hATrqHG4zYQ https://www.youtube.com/embed/WTHj_kQXnzs https://www.youtube.com/embed/ihsm-36I-fE`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/guide_utilisation/](https://aidantsconnect.beta.gouv.fr/guide_utilisation/)
  
  
  * Method: `GET`
  
  
  * Parameter: `Content-Security-Policy`
  
  
  * Evidence: `script-src 'self' 'sha256-FUfFEwUd+ObSebyGDfkxyV7KwtyvBBwsE/VxIOfPD68=' 'sha256-dzE1fiHF13yOIlSQf8CYbmucPoYAOHwQ70Y3OO70o+E=' 'sha256-DkGfInBE1PdVNgl1fcJGI5vAFLJWY82M/J2EaQVIsdc=' 'sha256-ARvyo8AJ91wUvPfVqP2FfHuIHZJN3xaLI7Vgj2tQx18='; object-src 'none'; img-src 'self' https://www.service-public.fr/resources/v-5cf79a7acf/web/css/img/png/; style-src 'self'; default-src 'self'; frame-src https://www.youtube.com/embed/hATrqHG4zYQ https://www.youtube.com/embed/WTHj_kQXnzs https://www.youtube.com/embed/ihsm-36I-fE`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/sitemap.xml](https://aidantsconnect.beta.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  * Parameter: `Content-Security-Policy`
  
  
  * Evidence: `script-src 'self' 'sha256-FUfFEwUd+ObSebyGDfkxyV7KwtyvBBwsE/VxIOfPD68=' 'sha256-dzE1fiHF13yOIlSQf8CYbmucPoYAOHwQ70Y3OO70o+E=' 'sha256-DkGfInBE1PdVNgl1fcJGI5vAFLJWY82M/J2EaQVIsdc=' 'sha256-ARvyo8AJ91wUvPfVqP2FfHuIHZJN3xaLI7Vgj2tQx18='; object-src 'none'; img-src 'self' https://www.service-public.fr/resources/v-5cf79a7acf/web/css/img/png/; style-src 'self'; default-src 'self'; frame-src https://www.youtube.com/embed/hATrqHG4zYQ https://www.youtube.com/embed/WTHj_kQXnzs https://www.youtube.com/embed/ihsm-36I-fE`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/faq/mandat/](https://aidantsconnect.beta.gouv.fr/faq/mandat/)
  
  
  * Method: `GET`
  
  
  * Parameter: `Content-Security-Policy`
  
  
  * Evidence: `script-src 'self' 'sha256-FUfFEwUd+ObSebyGDfkxyV7KwtyvBBwsE/VxIOfPD68=' 'sha256-dzE1fiHF13yOIlSQf8CYbmucPoYAOHwQ70Y3OO70o+E=' 'sha256-DkGfInBE1PdVNgl1fcJGI5vAFLJWY82M/J2EaQVIsdc=' 'sha256-ARvyo8AJ91wUvPfVqP2FfHuIHZJN3xaLI7Vgj2tQx18='; object-src 'none'; img-src 'self' https://www.service-public.fr/resources/v-5cf79a7acf/web/css/img/png/; style-src 'self'; default-src 'self'; frame-src https://www.youtube.com/embed/hATrqHG4zYQ https://www.youtube.com/embed/WTHj_kQXnzs https://www.youtube.com/embed/ihsm-36I-fE`
  
  
  
  
Instances: 11
  
### Solution
<p>Ensure that your web server, application server, load balancer, etc. is properly configured to set the Content-Security-Policy header.</p>
  
### Reference
* http://www.w3.org/TR/CSP2/
* http://www.w3.org/TR/CSP/
* http://caniuse.com/#search=content+security+policy
* http://content-security-policy.com/
* https://github.com/shapesecurity/salvation
* https://developers.google.com/web/fundamentals/security/csp#policy_applies_to_a_wide_variety_of_resources

  
#### CWE Id : 16
  
#### WASC Id : 15
  
#### Source ID : 3

  
  
  
  
### Reverse Tabnabbing
##### Medium (Medium)
  
  
  
  
#### Description
<p>At least one link on this page is vulnerable to Reverse tabnabbing as it uses a target attribute without using both of the "noopener" and "noreferrer" keywords in the "rel" attribute, which allows the target page to take control of this page.</p>
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/faq/](https://aidantsconnect.beta.gouv.fr/faq/)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a href="https://www.impots.gouv.fr" target="_blank" rel="noopener">impots.gouv.fr</a>`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/faq/donnees-personnelles/](https://aidantsconnect.beta.gouv.fr/faq/donnees-personnelles/)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a href="https://www.cnil.fr/fr/professionnels-du-secteur-social-comment-mieux-proteger-les-donnees-de-vos-usagers" target="_blank" rel="noopener">
            https://www.cnil.fr/fr/professionnels-du-secteur-social-comment-mieux-proteger-les-donnees-de-vos-usagers
          </a>`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/faq/mandat/](https://aidantsconnect.beta.gouv.fr/faq/mandat/)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a href="https://www.cnil.fr/fr/professionnels-du-secteur-social-comment-mieux-proteger-les-donnees-de-vos-usagers" target="_blank" rel="noopener">
            https://www.cnil.fr/fr/professionnels-du-secteur-social-comment-mieux-proteger-les-donnees-de-vos-usagers
          </a>`
  
  
  
  
Instances: 3
  
### Solution
<p>Do not use a target attribute, or if you have to then also add the attribute: rel="noopener noreferrer".</p>
  
### Reference
* https://owasp.org/www-community/attacks/Reverse_Tabnabbing
* https://dev.to/ben/the-targetblank-vulnerability-by-example
* https://mathiasbynens.github.io/rel-noopener/
* https://medium.com/@jitbit/target-blank-the-most-underestimated-vulnerability-ever-96e328301f4c

  
#### Source ID : 3

  
  
  
  
### Source Code Disclosure - PHP
##### Medium (Medium)
  
  
  
  
#### Description
<p>Application Source Code was disclosed by the web server - PHP</p>
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Usagers-sans-FranceConnexion%20_%20Impression%20noir%20et%20blanc.pdf](https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Usagers-sans-FranceConnexion%20_%20Impression%20noir%20et%20blanc.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `<?=_ý\x0012^hCÀ\x0013wú~õ@w\x0011£ïi4ÛÜÌ7ÅÓgúóðé\ûVªh9ºô_	[\x000f;\x000f·«ïÍ\x001fÑI\x001bj©³Ý\x0007y\x001få>ÚsynQ¿\x00084Æø=]ÞI\x001d-Æ«E>ÀÁ¿\x0014	Âp\x00111ú$jj&\x0004\x000bvbü|¯¨ø\x0000rîå^q\x0011òòk¾\x000cº+%]ýû5þåC½Ü*èEË¤À¡s}oØ\x001c\x000fãoP_13¢ë
ówèò&rÞ0ÎÏêRß\¼Èå-(fr2äúâ®z\x0002Ço\x0004ÊBdwròã'È\x0015YO¤È¯«ø1È·\x001em; ÜW5òÏ\x0015e\x0002ôê\x0014\x0015·Å¨ûu¥\x001fÀÑaõU\x0010«\x001726ôVËh¸£°\x0001î2JûôõA/Î1W·{UPåH\x0006ÏÅa@,P\x000eÅ×\x000e­­û ·³©Ø%J\x001bm>8]\x0005½|\x0005\x0017·{M\x0010\x000b£PÖ¨oÇA?\x0011\x001fp
\x0014.Õ©F¦6­ÞîÈñ\x000es+BÐ'Â\x001a.¯|áyÈ\x0007=\x0019ði$If/¯Se\x0001J\x00154Í*ÏÝ2ýÑYö\x0013[\x001dþê\x0013É\x001e|ñIyú?|úëÿ,Æ-ÝÒ\x000b¢Äö*Æ¢lÇj¶\x000cT^Î¤':äÿM³aQ@"i9Ò\x0004ðèå\x0016áÐÃdÅr<ïh!{9vð3¶y\x0016¾Ô\x0015\x0002! àI°çq\x0010vívþV\x000e/ÆÞ°GHÓ	ö6¨¢ Þh¸"#û Ñ\x001dä°vû:\x0005#0r¨Áê¨3Ä\x0018k¾?µOÚ\x0014\x000b¤Ü\x001bËÄëU,\x0008.\x0015LäÖËp\x0002N\x0000ñù­ÂF±z NÃátv\x0002lâ\x0003çâ\x0011\x0008û$Ùa?:
\x000e³HÚ}\x0001f©8z(wÚ\x000bDÎÔcÓ\x0015ûº
Ü\x0018 nÃH/élG©+¿ñurR\x0011×âc»¿WF\x000e]\x0007ÝÁ
*±Þÿâüôl\x000cTï\x001f¼ôÙ\x0016³ÜRxyÐ¼}at×vDCç|\x0005$^1Ú?|ò¿µóÔ\x001füÉÿo¿ýþó/þû{úÝçßþîéÛï¾yªøäô(v¬\x0000%Ð\x0011ä\x0008Ðbã\x0003£ÔmÈ­\x0011\x0011Ä[G\x0006\x001b-Õ§?B'\x0017\x0006\x0019²{ÈSû§_üö\x0013¤}iÁuyÛ+â/ÿ­Qø¼aº		¡ê×*\x0006­;\x0003íÒ³9ö×ß|Bw\x001dH\x0005©Áëý\x0011'vøu8Ò¤)\x0018}wµ_|xÃöWÿ4&\x0002ÿ=\x00046N)/ÙßÙúõ_\¯ÏK~öëï~ÿ/?|÷ý\x0017_~1µm^ùu¤·ð\x001f?·¥õÿ²¿öô\x0007ýüWÿ£
¯¾üö÷ùwß}ÿÍøW[\x001fáç_|÷·_þÍÏÕ)úßÿ×¯¿üóC¦^\x0002\x0015AÛÑú+\x0013:Ïm#2¼Õ\x001cÿÛ\x0006ÞÞÚ
¦6ý5ûO\x0019Ú\x000bâ\x0000\x0003DÛmOm8Ê)â\x001b\x0005á¿\x000bZ¿N¢°¦%zu.µÑ>\x00119Y	\x0017$ÃÓ³;µ!+7f%bv2Ö\x0011CÔ_!\x0011³Ô\x000cûr,æ6B\x0001ðØóÆú"¤\x0015Ö\x0000û\x001bÛµÜÒ«çÍï­ñéyH\x000e÷\x000f\x001dòó;M	ËÛWã\Ë÷/®m-ø\x0015Ä(¾èzÝ>v(á>Ä×§W|§ÝÖKÁ _~ýõWÿð»7\x000bz&Æ2¯úé§þÕ¿üö\x001bañûÏ¿ÿýM ¿ÕkÙwj-Èº\x0003ä²åt¸]]ü\x0004\x0010N\x001fJ'\x0012.Nþ\x0007þÂ4²\x0001
ð\x0003\x000b\x001fü¾/ÿÂ#M\x001d°fûóçÛÊ;;îRwçö\x0017ØÐ(w¸ùgI»¨~\x0019mn½2½ìs19ÿÍM­­¿·ÿö\x001b[dÆÿüÁoþ8>ýÏlçÉ_üq\x000b8Ô¸þ-qÿô\x001d\x000fß\x0005\x001bÌQvÞ\x0003Ó\x0014©ûÊ¢MÃ\x0016 O\x0007\x0018Î-Ö ãÌÁd³¤r\x001d\x001c¾W\x0005Ýßîýk~ÓûOþöGL°·UäÂ \x0018Ã`Û\x0005JúI*rµ.e\x000cÖ×SäúWVäÂZ\x001enZÇ©\x0018ÃàU®Xeèm\x0000zÈÍo,Ðåò\x0002]°º=\x0000Raã#A¼ÿ\x0005º`¶`ÇðªUüßýüWùo~ñåo¿úöÏ¿þüÃü»÷ï¿úZ>ùOþWÇÆ\x001fOò©\x001duÂ¿üã?ê.â"\x0006w»XZX>.{MZÏ1ýoO(¥>ÙQÒ=5ÊOÝVYOg³?¡\x0001«æì\x000eÏ#Ùÿ¸Oþàgõ»/¿ÿÝÏ¾ùüûß~÷ûß}þý÷_þþgò=­ ¿ûÙ¿ÿÍ/ÿßÿç?ýÕ/ýÙ/~ùÙ½ÿå_üìOõëÿÕo~þ³ÿêO~þë¿|úìÏ~ýë_~ö?û»\x000fóõw¿ýî)¼ûoûÿ»=æ¯¾ýðõ?~ñ%OûéGïòãïñÉÿ=^­¥>óÅ^m\x0017;ùøÍç¿³\x0015ñÉ"þìû¯ìkØ\x001fþÅÏ÷ýeáô³\x000bÿÓwOÿq\x001d,N%hé±ýÃ³=ãB\x0018Zîé²ÿòØ\x001fÍKD¥\x0006Í\x0012¦6= h¶tÄb§v¦%¡èÓãÛt\x0015ôþ2è¥+ÌË»½&æÅÍ>.:û½MÁò7þæ¬{;Õ\x0004D<³ð;:\x001eyüW\¤Í\x0004ÎrÃc¢¾k\x0015,\x0003;³\x0016ajC\x0013Î\x000böJPá,\x0000Ýi¶á\x0016 Îm'Z	$£8jÿÞÞ
Ê+$:a«ìt+Kr05ðMð§0y%r%_¹U¤°.\x0013e½kG{Y\x0013VCÀhÖGq.£p\x001dç\x000cõhËã®¢.\x001b\x0017Ó­\x0004÷°þ­³JGP*Xò¥\x0017\x001c!ªÄR<ÞÏ\x001d!\x0001­ANYÌc5ØfHÀy
ªòTHn0æ<\x0002ømz\x0011d¹Ç¬>ëx±i¹õk<v9°µq+)\eÙKÍ\x0010,»ð@ó\x0005v;Øa\x0016;ýÂÈ3éxV)LWØéöD² ]¯Ø÷\x001eí"éB\x001dm1~«¥¬\x0010¦\x0012%·ïd?\x000e\x0008[¿\x0018¤	¸$ú
è=æj?eõ^°ÆÀÞ\x001855áY;
] )sOó>Î2¬\x0006w\x00106ôvu§Lÿ\x0017 b_è­¤®4"8pw\x001a¨SÑ)(« \x0016\x001cðÅq'Ùrþ\\x000bJ\x0018øZ\x0012ìüøÁö¶ÇNÝ\x0006´µeçÕÇË³;g\x0015¤òÀt\x0005YjBmo|y+ì¡\x000b2½i\x0005¡D\x0003©A]'H \x0000´[-\x0007\x001båà\x0018Ä²P\x00080\x0006jK~·P±LìÉ^qñóVÐB2Ð§ºîd*¦\x0016º½½\x001dû«o±\x0006m7g8pc*@³ö7úâÓ¡½âé\x0012ô2\x0017vP\x0005\x0001/¢®c\x0012\x0015LôvÓ\x0017P//qE@%´ÏÖ¦gn0D
=óF¥A²\x001fôÖ\x0015yJö\x0012%³GP\x001feHçýÂr¾2´ã\x000eBÎ\x0012ÍMßãº[t\x000f\x001dñ}¥L\x001c6;þqP¦:Fû·Æ~\x0011¤\x0010è¥ÞÉJd` h_<÷ú0ÄF7mÌ0X#×A	Rºcá\x001eß\x000b\x0012;æõa
òðdñ. ¯\x0010¼à²õº>\x001dÌm
@æ\x000e\x0008 a\x001bx\x001e\x001d¨­ H\x001cÍeÉ#D³v=x¤ON°Í¿ey%À$]!ïCÏw-ý%`ab©ÜÆ&ØXC«?4.\x00039Q|\\x0010H\x0018JmnÞ\x0006!dj$Þæü¤ppV<ÎqÄJ\x0014ñ§Õ\x0014fé!õ¹\x0014Îì\x0017Û<\x000e{)@D\x000eâS³\x0006°í®%ÅÑÞ³Õ6¬Å\x000b÷ñ %þmEæºÃEú÷\x0017ð\x0003OÀµzQ%Ì\x000e£1p0­\x0004ÛÚ^\x0002m=ÉÔãÀÓÏÙÇË´\x0015å`\x0005U\x0006ÏXYhTtÐ\x001e\x0015ãõàEvCòp\x000c-Æ°\x001d÷ÂÂø±#	³\x0012ã~!#Þ\x0001gx\x0005Ùz8xã2\x0008j±íeÒ6UÛ°û ÷hzÚ\x0007·\x0005\x0003ÀÛ
©.bt\x0012ýº\x0013\x0003½Hs1\x0015Y$g[ÇRQQP7?¯/3\x0010ã(õ8oecÄ\x0012
ª4{ñ÷üût~=Tu\x0014÷@k,àK\x0003\x001bõ6Ö$§»k_V0ìEôØþ\x0005E\x001dkm)@\Wêrßrh¼¹×ùNl»\x001b»ÐvãÅñ~¢\x000e=$v½d1ªp/©;±x\x0011èø½7¢¯Æé¹[y[\x0001²|Aê\x0000¬Env\x0019Àñ\x0013t»¯sÅ¹¡\x0015N:Ïü%V°)¬=$ÖÎ«¨óÛ\x001e\x0004Á\x000cÁºp\x00112î\x001a\x001a¬Ó\x000fýâ:1ZSdÊ´²\x0013URÒ±N!ø\x0005¢q6ûFÊq"x¾\x001cÛÚEpÀ±ÍjçÎ*æÏHÔ¹íÙY±J<À¯\x0004P\x0004pyÌ\x0010Ð
\x001cH§ \x0012_\}\x0011\x001fYË()\x0010hQË\x001aÖSáe
ýª¢|ªÄ
AØ1­V\x0008\x001e6aÖþP®n£±¥Ä|$¡;KPÎE8«TýÎ qK~Óäsùz¬ßà\x0005Ýú\x0014ÑËÙFÓðAîr\x0002q¶Ë®Ë\x0004\x0017=KãI&È\x001e7YÛò¦ç7£|
`I]öÏø¼dÛÝæNu4F=j»2\x0001Å!Ú\x0016@À~n§6Ùà@#Í ÀÇê:Íüí	åÖ\x000e_VnÔ¬ùxo×¼É!øÕ.Ê¢B,æd\x0000ËÍ_û÷¸õ57íaÑ2°%Ææ9or¯o4g°Giº\x000e\x001e7¨33mv\x001aH\x001eÖÐS\x001d·r\x0001ì/\x000e0{{µUL:\x000co)~2VGÕrC³mïgÇB0Bo9\x0003üDßb^\x0010mC\x0008æ\x0010-Ûv:\x0014ä\x0003¸\x000f¢)ü2n\%wRÄXBiÙ¤-T}\x0018IC°(¸ÎïÈ(Ìú\x001eÒ¸Í1\x001czqY!\x0015Ð£Ç8}¹cã\\x000bP¬®	p\x0001\x0004ÞE2~r\x0012|4g\x000e0ø®RÚ\x001b!ö

¸\x0001i\x0000\x001fg8 ®Û\x001dMñËdöí
ODó\x0001í \x001cÜÛ\x000f\x0003\x0013\x000eT.Ìç+½¾\x0016\x0014?<Ûmø/wì¬ôÀÑ[ó\x0001õ´\x0002¤¹
sl¸×¶¨ÔÙM$\x0004ïi\x001bObKâXM.`?0´²Öö\x001a«Ð4Ç0¯½@éÎÏAá\x0002n¼\x001bþÄPÁ!þ¸µ¿"Ü\x0018ûq<·d;ÊÚ8­)ï_c{²\x001d:±õZ·â\x000cÐIZú>(ÛaQ©G×AgÞ[&\x000e¸Çðl®®¥\x0007"´®\x0002ÂÏ>\x0015Ûðr\x0017a©í{µ¥V!\x0019OewâüÅ	g¯¼;¶\x000c?ÜÅµº!5ÛN\x0011áfuûì5Kà
;Ë>r.s%úµÆsqrÇ¢ý1'*û
ûi\x000e®(côÿÖdÀ±ø[§¶N\x0007\x001dúm\x0019^¶ÔxÓ¿þÙG\x001eÆR\x0004Þ¶¦Dâ+ O{½\x0000Rds\x00129¯±JZ>Ûq`­\x0004¶of,­×âÅâäÏµ9.6l\x001d>Â\x00187Å«@bY.{mÇ\x001e´j5\'éèpèðH³ê·ØÿefoÞïÊpÃ³{í!\x0011Ð\x0003~¯ýä5\x00086æ¹°Ë`Âi\x000bçÎ³\x001b\x0016ÌØ]¥ë#é­@|ò\x0002Hx²Ù\G\x0011ö\x0007\x0007pëDÒ>Ø\x0011ÄvCÚ+nÃQ\x000f£qöáD]ÀkèKGaP8PÄºFbË\x00086Ôm\x000b+m=<µ\x0019ÛsNaÁ­\x0018°þÜ>ØªD!?~"\x0004$\x000eÜþ\x001cÓ\x001a\x0018à¥º-ÜÈ^+\x0005Î&ivÑ_[\x0015VX]ô.ÞÏ 6:\x0010\x0019n=\x0017î/íÅõ\x0013d£\x001bS·¸¶bK¢\x0010rô\x0008\x001f)\x0004!%O±b\x001f5x*;ÖØÈ\x001a!pðçi7û\x0011ù9ö¦u½:\x0002ÿ}Ý©÷bÛf\x0019¯\x0007GûÊPûÇ´Ôm§MüáÃ\x0010\x001dx\Ì[½\x000cR\x0006\x0004¶9·ùäIÕ58><\x000c²Ùg'Îl«]ÿQAMd4Ä9 Æ\x0016 µÒüò6X:þwÔö\x000bÊ,×hàÊáÛvÞ¡í\x0014 >Ý(^X\x0010µa\x0019ö­<*p\x001eR]Çäá×°ç{«íÆA,IúMçs·\x001f«i^·â³OÞ\x0017\x0011ãE\x0017Ô?\x0008$\x0012\x001a\x0002ÜûìmÛ,çy\x0011\x0012\x000c¹-\M\x0002r\x000f¨\x000b;êHýiÿ\x0016ÒÕSñszodØçù-eðùZ¯ïþÝà#Û%ôRÛ\x0018ó
K'u8ürü\x000c÷¢dÓ7\x0013\x0012ÝäÆñl½=Ë@P>,\x000bIÊÚ4,ÒÓÍ°	\x001c¿V\x0008\x001d
Ûèc\x0008\x000fC,ÅÈ
K¯ï"¨âÊFû¼\x000e\x001d 6¡ýk*>Ò\x0018¡\x001c~³-K¦\x0010-
7Ç2Hí\x0013YîÖåÝ:PpO	@\x0016ÜD±Stü¸/,©í¡>(Ä~m"\x000e´Ûâµr@ðTu%ÍMÐØ/µ\x0003äý\x00190¶S\x0004\x0015Dß´ç³pï½\\x000cÜ§\x0015b\x001b@K¬®Í\x001aí¤2È¼Ua\x001c9NcyU
)Ëá\x0014ë¸N\x0006¢OR6ùå:±$fðºS\x0004OÐù°.ÂÉ:g\x001eFÖ¼\x001cü\x001fÁOÏ\x000clTd\x0014çÒ.[¬\x0014|Ñ~\x0011ºnb\x0019"\x00085ñ"@U7\x000b½¹SÑj
ÚÑïÝ®Ø\x001eÚ0ñcpqëHÃ\x0001Ç¼µØ_CF:t}ñN\x0001'ëëF\x0001\x0006ô3\x0014R(Ü¡uZ\x001e¢\x0003rÇ W·¢"Ë}.§hGm|ÞªÁUL8ìê\x0010@lhÈy<\x0012K\x0000	nNö+\x000f\x0004;ovm3\x0013\x0007dÆFWäãÙÅ¦¸%Æ\x0017øS½ì¶\x00076ä¶çáÍÅØ +§æ}Âfædc\x000c³r\x001a\x000bqfr2¬«Êø¦\x001e,\x0000'Þ¶Ç2Ë$:ßV2c_¯h¦»¸J$\x000e
ËØ;^\x0012t2Z¤D]ÃÈe({Qà([\x0013(Cñ\x0013ö³T\x0006×è}\x001fÛ¹\x00118â÷1Tõé>\x0016Ò´1¶,ÙrÒq1\x00155_\x0006á©ýÛ^ÛÉ¨)T \x001b×\x0016U#\x0012A7A\x0012©H3\x0007Aµäg×ì©DzÕÐÆ¢¬ÏYcÞÛ\x0015ú­\x001f¾¸\x001fÿæo5ÄF¾\\x0011«ä1Å">#º¢ÇMçã\x001b\x0005¡J)O7\x0008æ²ítèñê0j!ð¹\x0011F¶»Ë\x0006Ôc\x000bjâ%:X\x0000TFâ)bpÜ·ídæ)tèdæK¶p:	î\x0017\x0010Û%ìvPÕ×­Phó \x0012¨U*D\´SaNk2Z_·²ÕTîáñ¦/bN§qDë{·ÃÊ\x001ebì\x0013´ÌñØ\x0010Al=Xú®Á6\x0016ÝuÞ'HÛ:bKÐº:h\x0015Äq'ô\x000bi/z\x0006!J¨Ü¤\x0015B¡\x0008h17-ú|,\x0014¦,ªuûi{aB:`ßÊ¦¥$\x0019ú\x001dbÛ®cµ\x001f
O:@n³\x0000oCÆ­È[+U|y>±;]¯ª½-+©ïÌÕÛzbóÓãÙcBAAú)ûí\x0004\x001bÌBÀ)t99îïî\x0011ð4ÆD'£B§ÕíÙmÈx*ûq¢Å\x0007×Aí\x000fÇoÖ¸ýÉsG5¡øñ\x001bå\x001fÜ­§·²\x0007p|¶é¬QAa±\x0010éyýÈ\x0001Ü>r\x0019>r×A´\x001b\x0013y»÷Ô=bRç¢U%ò\x001f7\x0005¬
D¶/iþfd\x0002Rõª\x00194Z5ôþæ&k
»x·nUé}×Ì\x000c¶¡õN\x0012'SÑ\x001dk6õimÆ
N\x0008"jZów\x0001oÄ8ê)l#­ê\x0008ìów²¤ 8®c¯\x0018kí\x0012ö\x000fÖÀ²Ï¬<æSÁ×
r?uDð\x0007÷Á¾ny\x0014\x001d^m\x0006h\x000f%\x0019#¤CA}x8x\x0014´\x0019bYN+´Hv\x0012ÇlÙóìÔ ô}óR¡¦«ý*¾ge¼=\x0012oû-­I\x0005g"²üâh\x0010è\x0003X~\x0001\x0002
.ì§\x0002«\x0003Ð¢ìV>\x001a?õãåP[·ÅEyW£(Ùþ3ïÄ\x0002·ûfJ¡ÖÍ\x0012\x0013çì©º6ÅøÇ|±'lÐÇel-rH\x0004\x001d\x0003ª¥ÐzI¬\x001exµLÉÙÇiå:HnD \x0019Ê¸\x000eº°n(½K\x001aµ§ÆÁ.\x0004_ï"dÜ	2¥JÈÚ§\x0007×±-Lçâ÷\x000b¾ÿ1W!/\x001eê"È^\x000eõd²ý§ùk*ÕÚ¸\x001aÞzÅ¥[¦!\x0018\x0018!È«\x0008}	Ú¸ìGÏ#X{§½BX¸\x0006\x000e{\x0019hÐÆwh¶ÄR²Aê{ox½Õ¢y¨\x0010'Óù\x0016Ë¤t\«¸Ò@®Y\x0010'\x0013;Nûåm¨å\x0006N#\x0004¤\x0001%´ 
~Hï"\x0013Ù\x00085ï>JÖcáÌº«£ Áÿ\x001b\x0013Bz9ÈKí\x0013
W`å\x0012UÅÄ>enQç sÐ¨ aC?:0\x0019îµV.Õ(ËÂÜBèx8µ\x0012n\x001aÈ(íÊÓÎ§HS{9U&^+kU\Ëè\x000f']o×,ï\x0006;W\x0012^×é\x001d\x00064òñy\x001d¶¡G¼ÑÈÁF$oì;sÌnN\x001dBÒÎ\x0011%hã _Í\x0008WìÓY²m©Ð¸àý\x0011Î \x0010§°×ýÑ/³33$A\x001bw@vÖ\x0010F½Æ×u+\x0017Éî+g()kÕ§ADôÔã(úî
r¥\x0016Ûñcl\x0015\x000bSI7x±Ûì\x0018ô`\x0002ZoaÇÜfwxû\x0002Äo\x0012ÀÛìn\x0004´ÉýMûà&»·\x000ec{\x0005KàUvG-nÐo¼«·²ñ¡,¹ýfYÙUâöAÃ&XiK?èËË\x0010a@ÄxÜ\x0015)ã96ú\x0019\x0002§^¬WsªÒW/LAèP´½åñ|v«NoX!\x0001\x0015`´âY\x0001©b;}\x0018
sF°áÈèZÌ;Ù$\x0015Æ&Ýde­r÷x(ªÙ`âùÞµÍ¿4~Ë$%Ú¹e'QÓS+sÓ\x0004´ùÓoÙd\x0014.ÂN²¡Í>!§
ZÛë·Øþ9\x000eÓ³\x0003H\x001bHVH;§Ðö×üXÓ\x0015cc\x001e
xÐGxà\x0019y\x001fBh7ï\x001cú#Û\x001a¥\x001aLÞzgRXpè¬'ÂÖÉwùªí/^5^\x0019¦\x0005\x0014vÔ5oä- Ø"¤vXvÜ\x000eeã©*ÍRùnûp6éJ N®\x0015ÕHfcÕe\x001aìáfçÌ\x0003NÒ¤Dç~Þ©©ddokÕ\x0012©\x0011Eû?];Ò¾UõÚBØ\x001f	ÓÈ.8Ï¸ôtp\x0018ßK\x00045ô*Î²\x000b8Ã%>È\x0008\x0002´HòßúeÄû³¿a\x001föÀUt\x0019qN\ÇÜf%ã§x{]Ô¬N\x0016uÛXHWÖ-\x0010à\x001c)ë8
\x0012\x0012ÐV»¼dNv6°¦Ðëø5xïYr_\x001e°r 
iÝêeP°£zèóV´\x001cÀøÿ\x0014|rh\x0017(Se
ÔÐË9µ\x0002{>\x0004>Ää6 SÎ1¼R¤\x0019ØÇuhªØÍâIâ#°\x0000üfÆ3a\x0006c'\x0015Nh{\î\x000b`zÚº£ÝOßo'ceÐ,£Ì«ëØêgÿ\x0008De\x0017í
V¡3n¥3\x0019IH·É\x0018Xê4jÇ\x0004\x0001ÁÎÔÄÏ
à*Ýªéöû\x0011äipwÚþ+d\x000c\x000fx\x000eïï5º(ä\x0005j¦í PHÆl\x0019«iÎ<\x001fÁ¢¥pÓ$cø©¯åÆÆlb\x0005·»d,clMI5ãÝ\x0019Òm2Æ®@%\x0004õÛdl%?j Êðódì£\x0019ÒåbE\x001d\x0018¦ÜARÔdÄÇü\x001b\x0005Ù
8\x001f©»7
"ÀÆ )7!}Îöp\x0006Ý>@c[XGQHj\x001cÑïØûväf-Àá^ð8é6%êiQYÒ;ìåº¬\x000fÇ­\x0002ò3\x000esL¿C°¸(¬qXÀ.íN¹°7\x000fë\x001ab8FR\x0000.'«ÃÝ*?óO3\x0002\x001a¸
;¢\x0002Þ2Ö\x0010,$ñ¾â×}øäAPÅxL\x001bi\x001d×\x00019A¯Ñíb\x0008öã\x0005n\x001d\x0003½\x0019\x0001«á}ìí¾\x00185§>)Æ\x0002\x0018­ù³!\x0016ê2ðÝu\x0011Z:óRß§F(\x0000\x0019è\x000fC\x0004ÄA\x0011m}¦ \x0001Ý\x001c­\x0002uñø\x0000/a\x0003(\x000f
É
Ùí\x00198¯
ºýMx64"|f3r¿ \x000f+\x0001s(\x0016=ýÈI0BÜ'\x0006¶;áI4Dh+"sÚà`\x001dFmLÈõè"hrjÛÊg@~ÁÒw¢\x0006ÉS&[\x001bêé}>wµç­ Ã>{\x0000\x000f¦ËÐS[AÑÑÉF"y\x0007Ñ]ÏP\x001bno\x0014Q<\x000cguFBl\x0010Û®MÐU)òÃø\x000eM\x0015§¹çÕuî?ª§
9Ï´>ÕE\x0008Öð^öap\x001dÄËò\x001fìã:Yë	ËÙñí{Ù\x0016ÂxpHxÌØ2Í°ÆÉ£y÷#_âSÀ<¢ÆßÏÙ"ÂEthÞIìhZæ\x0015w»g¶\x0011ê\x0006SÀæ
àXÒÍU´9ËÈ çZÊ\x0013Æt\x001fc}»\x0018ê\nU±¦kö­¨wvp*cª'ÕD^Ù'[\x0014½@\x0018k\x001eC
Dý\x001blâ\x001e\x0016f\x0019Z°º\x000eQøÏì¦i¤	\x0011¥¼*ÊÚe\x0008µJ;\´4<&®*\x001c\x00138\x001dsÁÅà\x000f\x0013·­LiÙ¦x¯ÐFÆSafÀÎ²V\x0014\x001bõ\x0015ÖW {!T¿r§²â\x0004µüÃwcÛ\x001bm\x0002ºB8zW	ã±í4Oû\x0018\x0016Þ\x0006IuZÀ`ü|&~ë\x0000!í:\x000fdà'ÚüRT\x000cµN·\x0011,ö¾Ù<u\x0012ÓcÃ+ìôíb\x0004 ßÃè'£Ú\x0004Ò\x0011P»©,\x0017N\x0010]0Ï¢1R]í°W·\x0008h \x000cÚºQ¬v³\x0000\x000fº}[è\x0012¶\x0001üà:È\x000eÑ>²\x0003ÆA\x001b\x0005h*CéVx!à`p\x0014")ÚUZµ£ÝUD?k°ÐYA$]4÷fÖ`=5çºó%f¡ÜéÒÓÎa¨Ü ½orÏ^è¼id'Ê\x0011ÄÚf\x0019QZD \x001ay\x0015¸ ÆÓ²\x00020]zÃ\x00105`Ímåª\x0019P]Ö`\x001e©ìM×<\x0002Ü¼RÖ¤H,Û'õ»^!ó1äËçHeaâL(BðèX.Mp`\x0004w\x001aÎIÃRx¼è\x0001²|Xé\x001e°ë\x0008v\x001c¥É1`ê,vÒÀã±ßô«ÀO3%æ¯¡\x0006ÓY\x001cò9
\x000f\x000e\x0013@ÏÏ®\x0013+bd	bc|ì|ApOD«cî`Ê;9øb'X¯\x0000#È\x000e(ÑÎB,@á"Hï\x0007PKOí\x001c\x00161M\x0019\x0011{ð4V§½gið\x0000pë~d½iS¾z8\x0001T@ð»qe[\x0000`rû#\x00049eRöª V*zý6U-\x0004ÝÌ¤¹|N\x0012$qUä\x0008ñ^­Ó·Å\x0014\x0005½f\x001e õh\x001dDï®¤\x000bh	'0\x001dB\x0012{\x001b\x0004Î~ª?_ìu"!ÄryWçÝ:,ÐÍÙ\x000fýº\x0003\x000bÍÒ¿;b®sÞ\x0018GUýfH\x0005\x001dk}\x001cÔ¡2Ùh\x00085]\x00047èlg\x0000ü·I)@ÂÉ=\x000eÁâ\x000fÐdÒã:('z6V»®\x0003É\x001e;Íï^¦\x0013L\x001aEw.
¶IðI«\x0006»ã:\x0006\x0015O2ÊN^É;éÆ!ÔV[Ûc\x0008ÉB·Ø±ýæ:¨Þr\x001ak+ÄÆX\x0017\x001bt;tÕÑ!Ì[IÄ	Ç\x0006··@Û\¢H×ã2	¾\x0008Ö£#=\x0017<µa
è÷ÂÀ¶¿wv@8-vLÈ£Å»¡ikù_\x0008M2\x0008F»p|ã3då«æ3)10Ku+wæ"5¾²é°Ô`
`¤¼WÂa\x001b¥Å].\x0001\x001d\x0007\x0019S$B(X*\x00177\o`Ø Þ;Ur=¯ÃÄ^¹)Ýã#\x001aÖid\x0006TxãY#¸;\x0010{qØD®¯KV¦Ð­U"Cëoª\x0003íÛöÖóKy\x0008ù\x0011©Ö]Õò\x0010Z3|LÜ\x0013¬¼ÓTVicg|)Jð´\x001céKí;E5ÂÃÀj[\x0010\x0002Ó\x0008¤÷S\x001c·ñÛ\x0018NA|ÏË\x0018È\x000c\x0003ÑòuÈá\x001eV\1\x001e<\x001f\x000c£}\x0018{\x0019T°&¯l\x0012ñ"F\x0011ðº( kqWÏ\x0002ØéyÅÒIÕ;ÛnR¨ö\x0003R=åùèlû\x0011Ö^ñ§u¯ÍÏ®=§£ò¥Kíí:@]Ê8¾eè©Bæ:5v\x0001®¬¡\x0013¨ÆËt0;¿\x000bÊÈü\x0000\x0001Ks9Ñ8¢\x000f´o\x0005R;5\x0018]Å\x0001N¦"º?¹\x001dº|¨kê!\x0010>máì¿O	\x0002Ö\x001d§
\x0000\x0012h]ÕÝ/oðH\x0015æCAÅØw²Óé\x001ey°\x0010k\x0016\x0018P´Åü®N\x0000V4}\x001f\x001dl4À¼]÷ÇÓÇÆåhmY\x0000­¯\x0006Phy Úc\x0017\x000c¶MÆ!ðP\x0005?¤7P;m\x000eßãFÀÖP9ðàæáW\x0006Íªñ-%\x0007ÙnâBÙ2Þ\x0006s¾Wá.f{¬Û$\x0012­HÖ¡Ë?&°ÍÕ\x0002$\x001f¹\x000e¼¦`\x0015®-æÁV\x000f^rÀ!?\x000f¼Y2ÙÊKC¾Ù\x000e.dgA\x000e^hÀë Øì\x000eb(\x0004<tÔþD	ú°\x0016 ¥,l]\x0002\x0010^@oñ"ânÄ\x0015¨Ô«yp\x0015Z°Ú
©\x0001_#P\x000c\x0008\x001eÜnºJ	 ¡DÕ,Aêú\x0006k\x0004­\x0000<`Mê0±ÎÙ
zÀ
";
\x0000ø(\x0004Õ2ÀÊöçó^\x0004±f!\x0015\x000c\x0018"ëà\x0001°Ímß¥\x0008Ë\x0015ò\x0018s(A¸â|8Ý\x0003Ø\x0005ýp>£{àPùÙë\x0008pçyØ¸\x0013Ì¼¿­¿iKÁ°eõ\x0019wòä)POÜB`ðP-·Â¬Ï¦)
S\x0007àèÑK\x0004Õõt9f8×Ú\x0012\x001aiB?\x0008¸1ùìzäQÑa#4ð¼J­Èâk¥?\x0008BÝÈvÑÙ^ú^\x0015ÑGèÉÿ@0\x0004ÔÃÝ
¢ý\x0003S\x001e®ê
â,Ètw\x0010\x0019*ð¾öND®º(g(%ÑtyDíüÄVl:Ò¢è@líT¾ÛÆ©«9Q¡ä*\x0019ëía®BI 8Öu\x001d\x0007÷
ÈjÞpIùGä8aGÌúL\x0010nÊÆX¨Xa~^sËòi¦£mç§\x0017\x001e\x0010Â\x0003)Íov\x0011TÔè¶/âÛã :sb8Ôu%±'\x0003}¿VQX´BMe\x0006!¼\x0003Y9hQ\x0016iIA9ðø\x0016!ëpteØÃX¯Ø-\x0015\x0002"ÆBÝÇO[×\x0003YV\x0018\x00052½FÛe\x0003ÅÌv0ß^øH'ì*nP,Z
«½­\x0014\x0004èª¥\x0013åádisº°ÆÊ5ï¤\x0006\x00126ýT/ì\x0006°§\x000fÅþ« UÂ\x000b5u_üã @WÁ:*áü$áln¼ä4WWÐ£@}\x001b\x0010±o\x0011
3à?uïíí9:ìZÂ¯#$Ø\x0004\x00120Í\x0011}\x0011ä\x0011
¨Iý¸Wm¼d`GZÒeJ\x000cpM\x0018ê(\x000fBÈÝq4\x0014ÀÜÆúp°âfM\x0019\x0004Ë¸ð8\x0008Ô\x001at|NÀ#D®¢¤"ç`wCeî\x0006º"¢õö"dÎx	\x0015¹zÓy~\x001dxê\x0010à<\x001de9d
y.?Ð4-ÎqNð¶¶(ú\x0005wG\x000eþäè¯££hà`\x001dÆu"àn\x0017ÉíT\x000e38Ðíë\x0005\x0003\x001dÆ\x0016Ê\x0017\x0007\x0015\x001cCiÞIEc'=sò¦Å®2¾9g;Võ\ü~70Ê¨§`îÙÉÃ9TÓõFj³¬¹\x0015\¡^ç÷\x0019¿\x000fÈc^Ï¯ÉKgú~ª%1ÿÝþäÚÂÀG\x0011Æ°cNì±=\x000eb/\x0013Â¦öþz3|«½]Z8@y¼B{¼S\x0001²!Ú³ªüß<\x000c²@Û¦w=ð!l|Åè	RGëi¬»¤K\x0010Üí{Ýt^EIq~&6N !Z!N\x0003È§\x0011\x0001®Ûù
ó%ë£Ñ\x0012Ä5S\x0008¾x¢wÄ=Ó\x001d\x0014\x0011ªÄóF<JD\x001f6»\x0003\x00050t}¤C£ËSe>ÄÞÞ<zF\x000e	ñHÄ
\x0005Á}ì\x0013`IÕ<oe[¿cõT®¸r(\x001b\´ÿâØ'Ð) \x001fWÒMÅÀ.pSÉ+æ}¿ÑCa3qY³FßI²rñtÎl\x0011²?£ZÁà*ä^¨\x0004ð\x0016;¨Ûä\x00177c\x0006ÁAèð\x0003º?\x0010@NpÓ§\x0010µl\x00128«Ó;«¬ï-9|u\x0000Î	\x0013Ç0z^\x00130K%D½>·ß²}p.C\x0015CÀ[\x0018Û\x0000,kÝRÂ\x0015NÂ"Jwpºl7²|aÕm\x000fãp\x0006\x0011N·âç5¥z¹[Å\x001cÒá(È\x0017]jÊîkvã\x0007©gpÁA\x0012öèéU%îlV»8ïDö	G\x000b{\x0015D(¦ \x0012Ú|ÇÒH¢Mîî\x0019ªe	C20àj´ÍÛ\x0006ów­\x001etÓºR\x0011B×ò×¾3£F\x001d`}Ò\x0004(N2#7\x001a\x0002¸F8\x0006M2}¿Ú+°·,l\x001d\x001fÝfY@ÓKÈªU4)ä©Í§2<}®]|\x0000´ÂLwã-\x0016é\x0015\x0005¶¾Ýl¡Ô
°[Ä\x000bBl
KöiWïí¿\x0003«,\x0011ÇsU\x001fe
\x001e[í1?®ãF\x0019Dåá\x0010l/lìû%ìç\x0007X\x001b{\x001b5&ÞÃ¸S q\x0008ë¯ì£\x001bf`\x0008\x0007=TAÒH%³?¨°\x00158´ô\x001d\x0003<bßÆ8¢\x0006ã,§§M©\x0010ü§Å\x0004:{W©K\x0015¡
yVd!¼ Jõùð<ö:R¸ÁiXÊÚ$	¨À¹E'#÷ã92§ÖUÈÐD
D\x0019$øí!vøÎ£\x000c¿êAÐÚk:þýÇ\x0004Ýþ¦÷¯ÙÚÞn\x0017í6:l^s¸¯7ï\x00085I`ljy\x001ddy\x001a\x0018\x0004e:çof@&\x000b»ªtl5w\x0014ÛË\x000fã>]HQ\x0017\x0015þÊ\x0003/vp5¶`Y\x000bÞ`P\x0011²ÖO·6#Ø\x001b7v¶þ!Ê,ý{mcÅq¯#wêª"R§!\x001dßÛ1ïE;×\x000cB×jÊ9f¤Ç\x0000I>«\x0014 º)\x001dtLØ³ñyu\x0011ÚtÞU\x000c\x0007Ë£è31}\x000bö­\x00081àºÕ\x0012°\x0010æ+¾ÿLÚ+"N¹G!¬%\x000bº¾>ÃE\x0010l>{NÉdé×àl*\x001fÄ\x000c\x0004%\x000eþóV(,!&Ý\x000b·=\x000f!I\x0003þÃpD:Ã6ä\x001bö\x0000µû¦B7!\x00113ÇbJ'¨6À­ ³²>\x001dëP½Aº°Â¢ó\x001bæ­è\x000baRÊaQRT¦=HRDHÏtY@í
\x0004kJ#£©
\x0001\x0001ÖV<{\x0011FR@BXOeÙ£$;âLªËÛI
[×éÔ5ú\x0016'µ=\x0002"0ÛBã\x0013b#.!\x0012°oÅ\x0003\x0002Û\x0007LÉ\x0006­½}NÏ\x0018ë¡\x001b\x0011ÇÛ\x0005ZS`ÊÜù#WàÇ;§\x001aå4»Ö`ø±´Ýßâ.ÍÀ\x0014ê¡¸XR4 ×áJ8\x0007VâSêhAtÃ±X?\x001aqì\x0002Ù¯E^4ÆÃ#ÚØè_í2+²T\x0019\x0000Ôx,\x001e	%¹\x0003µ¥À'l`AH>Ñ¦KûYÐ\x0005JëÆ\x0017¥õÖ-µ#õ^
Ø÷ØXû\x0008DKärcÒ"é*¤Ùæõ ÃdÙV\x000f\x0007ú=\x001a¢\º
\x0005Ò"´°?/Õ\x001bS\x0006
hK\x0012ñÊ'"!\x0000×F\x0017tÍN;®Ûº¹\x000c£ÆOùË\x0018­êÝAG¿
z¼ô¿­4Mu;GÖMÆ·Á¤\x000fF;þ9ÆX^qÖ<L{\x001aK\x0014\x001bÜ¤²Íò4Ød,ü\x001e\x001dØ²4\x000cKç+\x0007´50TpJÜ\x0011»Ý&¡r\x0006o\x0012­¥IÁ¸F=q¹G)Å¢W\x0008È\x000bHsk!\\x000fV\x0011>«P~\x00114>\x0006°(å/{«A\x000f\x000cQ\x0012Ö~\x0003XD6÷pâ
ðå\x0008Åel\x0001\x0015æeÊu¿c\x0012WrÚ±Õà¹2\x0015³M\x000eÚjík±´Ò&«a';6¥*Bû¡Ù	ÎqX\x001eð\x0000íÌTÝ\x0000Ý?üÜv\x0008¬³\x001fðñ1ñvC~²\-í<²Ï²Ì³Ê$wa
?;¢ ç\x000e\x0002
\x0005Gt½\x001bctQ5 ´\x0019¿x
pPîãÉA»ØN\x0003°c\x0017ß)ÂÙ15NV
âaÖÛ\x0002¶³^uèÜ"<TÁ(\x001aÇÉî33²ø\x001cTB;%ØÛ9üàø£ª\x001eJ¾\x0008zÿ((Ë ¨ô0
£tÁïfÍBØ]5ÆÝ\x0001t\x0003j8§\x0015Ôa\x001er;ý\x0000æ£-D\x001d¥\x0012}/êÓ¢Ën\x0016£~\x0002(ªõ\x0019Â'õ\x000cö
þ½ý¤½æ»¿)JÊngk
µ=\x0016"ûaßà\x001cf\x0004e¾?(Ì×\x0000ðÌ±YØÞ[8n\x001c\x0001©p\x0012Ð&ÿÁj	ÙùàÏI
\x0008øÍ±+Y\x0010¥\x000eÌ7o\x0012ó =v´*\x0004Ïf¼0T\x001b&
68Ø\x0016\x0002BuÇ\x001fý\x0004©é`úàç¨\x0017Zê´SizI\x0002¥\x000e±I"Ð\x001bE8uÿ`Ú\x0005\x001ckTw¹\x000eqêç\x0000Î\x0019² Ð\x0011\x001d·\x0008ù(\x0004b(½z4\x000b\x0010 ûIÛ\x0010¸Nã${Tù$X×ë\x0013¨T]÷SDïþI\x001b¯O\x0008IØcG\x0008\x0004ø¯\x001fÚ0|K\x0013ÈíN+\x0012}oÎØ1$
0a:fùô49è\x000chñ\x001e5xV\x001bÅ$\x000cÎÁ\x000fB¼ÀEvøòiÝê"H:rQÝçWxJÔ\x001c,WNW!ãKiÃÌ¿_ñýeþY\x0011wt\x0015c3\x001eÀ
\x0003}\ÅI \x0014rû3-\x0016'\x000e¹BN¸4äÞ.BÆ\x0010Y¡oç{
®c««ïò\x001a>¥U\x0011¢],cìeAZ¤2¶\x000fs7J\x001a{ Ã\x0008²ü­A\x0018¼Á-qC¹2=Ð¬Ç%Ö
÷\x001c\x0010ô8AN
\x0014î°íhÞdz\x0012£¨G\x0010òÉ¶H×³rYÂ\x0011t\x000eCß [_ÀÈ´\x001a6ò£­ÈR/µ¤@mpfþq\x0000 ø\x0016\x0015©sh$G}\x0015ý"ÐKiÍ¼>:'È\x0013Ia !]èQÉ\x0002stCê¥S\x0011ÍB¼\x001crñ«9Ì}x»¼ÚA\x0004ËÒQ,Ã·û\x000f¸LfEDnØdc}ñg\x0011Mªkr#¤h¯¦Ï¸\x00128¡2É½&å\x0016\x0006½6È¯7\x0012¸ðØ$³<¯Ã¬kT\O3K-Ä.Z\x0007\x0011#b\x0005[Ênû\x0014ð)I\x0019yÞ	v:\x0003¿\x0011ñè®`Ö\x0011ç<¶÷DÝ°"x¤|Þ\x0011RÐ[tí÷\x000eCã\x001aáÀ!D\x0010\x0002äT o¸TNhêkÜX®
Sky«6ÿaé4¬:\x00158n=ÌHþ
§^ÂMÐ\x000fl°o2\x0006	á0±ò\x0001ÏÜÎ¾y\x0018tK:#\x0004ÅJ¡ôFOöu\x0001w9(áªßlÓuÁû5Ñ¸v\x0016SÀcS«
\x0015ð\x001eH­\x001f
#´¯±G+y¶§FÇ\.¢\x0008\x0010y)+S­ì»rPuÀ\x0015Â¼NBÊÎÎÎM±\x000e\x0019Ôk=\x0011À¿¨É
x@ÀNóF6sÁ÷\x0003\x00139Ë ¨-J\x001aã*²çåÊ\x0018
çÍY\x001eÐ\x0001\x0003m±^B\x001cr5ðëæX\l`\x0005r¸Ø^àÈ<ïôâ;²PEÁþ§=
ñT
´ñ~\x001d$Ý\x001c ´c9IRt'.ÕÎ,\x0004]\x0006,\ °^|è¶\x001f²²ý&µ}~\x001d1Ý¼8ÛGêóù¯¹\x000e¹{ªË Ü:²\x001eyèS·ëª\x0003ÛwlÂÊ?BXG)v¶\x001bµ³çº\x0004ñ\x001døè
endstream
endobj
69 0 obj
<</Length 65536>>stream
a\x000b¾Õ­\x0008\x0014!\x0010ª°²û\x0014\x0011NUC\x000b±t´¨\x0017p\x0012Àà$~®\x000em\x001cñÌ¶\x001bÀèñ\x0002"H!Ô\x0011¢p¬}Ï`û\x0010|\x001d"NZK](sX\\x0004±qÚK.n®¶\x001cõ»\4Nï|\x0004\x0001Ý6<+X\x001f Ä|4\x000f\x000f¤3ZKú\x0010\x0011¾vtå\ç¶¡}õ9µhA@ÉëaÈs\x0016ðuÐ\x001dw÷j,_\x0005],£¯
zÎ\x0002~«µ¿ÚÂCzïâ\x0018ê\x001cÈFµê:È\x001d-%7\x00192-m)\x0003õó-T"²Ø#\x0004ê¿:âù|ÒÛ\x001f½oLiËß²ò;õ/\x0004~6´ØÝ¦Ã c\\x001aõîð ²5@¬0W1t´³Gë-¥u\x0015\$ÁÛ¸0,`Kb\x001dê×þA»ÿ\x0006M\x00039úÒ\x0000B\x0014ð\x000fëGÈ\x000eQÑFx1ò9þf­h\x0005R\x0000|\x000eþ%\\änºFóFYe×Îrg¼9º¦óF÷Qj?¸\x0011\x000cÕÍë\x0010°äUL³¥Ôq\x0015ô\x001c¿ñaB(BúéU¼\x0008âd¼YnÄ¯\x0008"\x0001EQ\x0001`ÃÃ ADBë\x000e!A¤÷pèÚÏñ\x0008±#@ªÃëã"änË¡GÕ"\x001aÒÝu
 ¬\T¿iP:³\bü\x001aª@\x000c~:Ä+\x0004\x0015ZÊm|T\x000cÎ\x0012¸a'Àÿ|tak@Á\x0016]\x0007H(¬ñ4á\x0006Ü¢0¡ÊGa\x000e=\x001d>\x0007PQyN¸6o\x0005\x000e¬Öò\x0015ó'å;?ß2»©pB8
(f\x00186+æ%.dá+\x0002¸+³¢_¬&\x0016úÏaO­\x0002\x001e
`j
BªH-ìßû2VÊÐ?ió×°wÓ\x0016)ùÀ%\x001c2õcA0m|6¾\x0005©¢¤>Ñx	\x001d>p\x0007/Ñ`è\x0007ÉÐï\x0000ö\x001e ;bãß¥t°¾'u*Á1mª-_E`kÚº\x0000í26~CTÛ®k·jIbÐ\x001bõ<d\x000e\x0008eËÖå¸¿çmÐûë Hµá\x001c\x0003\x0014Å²®\x001ex¯PéÛã\x0018HÓ\x0018øæÝ\x0018¿\x0019¯\x0010¢.\x001bDYy}@Tö¦÷3ÄöÁäÊË"A·\x0013ÇR\x0015UL¥+D3sí\x0000Ã2\x0016{\x001eßS¥AÞßþ-·\x00004
\x001d\x00169¸±\ÌAHêÃv/BÖ\x0000Ã	\x0014hwWÀvd{¡íyeÇÃæÕ&Ûµ\x0004z¸×1%²d`í\x00109À` 0\x000e¶¹ô<À3_|C\x0005\x0010ßÉc4qw\x001dVLø2ëä
Z
)ì<^ ûi\x0004¢}$Éì,}¬u½\x001d;IqLêi×8ÑÑ·5-æ-s?HËg<Q\x0002ðÉ`F·\x0004åmÈx$f¶Ó±
n=ûë4¬\x0018\x0011¬\x0003¨9p×\x0019Ñ;¢½9ßÐMq\x0006fZç\x0013!¤ÛàÖoTF\x0006nºêÙmÀ¨ìlÂx[)\x000cº\x0013ä\x0001nn2:\x0006:LG\x0012DzÞ~>Òh?gnì4\x0011Í,T¾í°\x001eàõ)ù0}\x0000ÙI=\x0018Ý§\x000c-ÔÖHÀr[
K»¹
ãzìÍ W[2.K£÷&"\x00014p\x001fÏ%ß.mí°\x001fè!e²:\x0002Ây@ÁJ[¯r\x00165èôn!X&{tÒOÅ\x0002\x0012\x0012§¨²íý9\x000bØ?Éç3Ý	J`Á½4úÓ[ý\x001dq»x²Õ\x00074&
É=Åù6gó\x0008m[î¸¿yy¤//2¼{'½,x[u\x0008\x0014 ,p\x001e\x001a!
\x0008.X­ \x000eG3\`aû4êpCÇä"\x0008#\x0000<à(9¯S\x0011
aXá' ²1HØñþT<\x0017\x001d|EP¢	?UÒø
ß³|\x000cF\x0010×QB\x0002W\x001f\x0012Ï\x0015ôµñC\x000e\x000fCdFÈ$®û¼\x000c~Ô°\x001c\x0012L MÀ()¹(\x000fÔ\x0015ðÈ\x0003}\x0010'zôí\x00105JîÚ\x0016ds\x001c
Û÷\x000fÐùe\x0010R[e+ÆÜuQ	p¨\x000e±ç\x001d¡Î\x000eÚ
 v[!\x0018yÛþw\x000bG\x0014\x0004\x001c.ÓT\x0008\x001c\x00034ûM°\x0006L1!·q+)Iß±p±¡MÇ#B Ûl4û\x0010F¿\x001en@\x001e|BK	C&»Ì¶\x0018²éhTO#\x0010¹\x001b2,¬ÝÖøÂ[
Ãð0æCU\x0003OZê\x000e¼î(­Ì\x001b±å)ëq\x00079\x000fpCãE\x0010D\x0007\x0011\x0008÷ã àº¼´	ñ¶ {Dí~;[\x001b¹Ó	t\x0004Ù\x0012P­¿qXBSú²vÈØëýWÙ\x0018 èå\x000bkïYj\x0002.m±
NF¸ÞÑfmóò² ÛÎ±©wÄZ\x001a×©Ã°ªú
\x0008r÷:\x001a¯N¡DìÎ|\x00112n%8ºí\x0012Íå«ë¼\x0014Ô¤_éåó D/C@Î\x000cy\x001b5Ñ-\x0016ä\x0003â6\x001e\x0006g£¶Eùa.ÃmæõCoV\x0008»¥ñ\x00060B\x000cÀ0ß4\x0015\x000fûÐ"(Î|°âg`\x0019ÀÒ\x000cs\x000e<\x000c\x000bÞ~E8Iø£·9¤\x0003­	¥iëÙA}«3F=.VZzßeéÛ9¤\\x000fººÎ\x001a­\x0005ä\ìWF
e\x0007\x000c÷Èm°ö%'¥\x0013/=
ÖL\x0004.<«÷ÖUp6G¼l\x0015¸l.%±½Õ¢OBW­®Ý­¨íÆß \x0001 \JcaÌfY±÷û×Po¸¦vÿ0Dçq¸eÞê"è\x000eÅ\@OyD!Ð|h×AkW±­2¤Gxèë %,H$Qÿñ¬æíä0ÕGP8#Õ\x00089/ckê~\x0010¤²@.C \x000b\x001f\x000cÐ°<2ßjh50UyüEÈ\x0007Ý
É\x0005Ü\x0008;n|w×¡03¼ 	¦c3B²eñBÙÒ\x000b)Njqiq\x0001ó¢|nviªX9\x000519\x0004WT(\x000b»ËÚ\x0006é©`\x0017(\x000bûË\x0010p"*æÃÖ ìPq\x0007wRY¦ê\x0015®\x0008(.\x0012ò
¢JQ,m@pP ¼i,à0Îñ1¡ã©¤\x0015T\x0010s\x001cT¢\x0003
\x0017²<Â\x001dÌXsHnÌ ú¸0"â\x0001íØR`Z¦\x0002¯_ÔObb³%ÏjwÝö\x0014Ú
±BTß×÷DZ\x00155©¾\x0019¢\x0019UöÆ_±è14Ýa\x000bcÄÜ\x0004lZ!%¨×æ+¼
AB\x0018âù!.b£è*¹¼/SÑCýêv\x001ao¡ø\à"W\x0016\x0005Á¾\x0008_\x0002\x0005\x0011ão5mOÐûGAªð\x0017. \x0008m3Ø}¼f¨>,-Þ8TÞ
}¢Ó\x0001þFHÌ\x001bdT`÷óG'ú­vâléø8\x0019M\x0006=\x001e~ú{ ó|ª\x000bxÚØ/tc\àÎì¡/¦>\x0003E\x001a°ûõ@ö\x0000=¼OJ\x0002¹à_ÝÓ|p4Ð\x0005\x0003\x001fù ê\x001ab(òK,Gäb[\x001fWR¼R\x0015/3\x0008Æ\x000bÚðµoØ\x0017ÈsÊr(\x0004Öº=k?à XsüW\x0008
iE`+w\x0008âf4ÉÂ\{ª8rø\x0014\x001f^\x0007y\x0018+Ô¼U;½ìzÓh'\x001fp¢Í>\x0008\x0001ª\x0002ò+¯;½a\x0018Â¼G<b<¹Nõ\x001f~ÅÃ ]àUAÚO(6NmÖn:o+MüHÏB´¶#|l¹\x0017@MÌÙ\x0007Av4  ó´FÎ¯\x0019÷_¢B\x0005\x0006¬QFg·I"'`n\x0004¢g9\x0018^_# Q\x000e¢á¸å\x0001Á\x0012R;NTË)§CàÐ*ì\x001e`(	²\x001a´zÌ¨ÚtMD\x0018N\x001d>\x0013ÝKØØä1Q\x0005£\x001cØÊ^\x000eHHÖBØû(sÏ!ûµÅ²¡(UÁb×\x001aæ\x0006\x0016æM}\x0018¤tu®ìýä6èá·ìh\x001bBQy\x001cr>÷·DÀ\x000cl\x001eÂ{\x0015;çf	?¨\x0007A ßuöe{GË\x0001ÃAsnºØ3E£'\x0000íZ>ÆAS5¡XèG:E\x0005 ÍÃáa/à\x0011+y¸®±:¶\x0000KÖ\x0002ÆlÓV=C@Q\x0019Ý!N%O*PmÝ*GBèÈç\x0017ÌÌÔ\x001f\x0011Ô`wu×\x000eè\x001c£gñP(mÝ?ãc¥0ïä\x0011|ëQÏ\x000bèFô§Ë\x0017<¹`ÔA½\x0014".\x0018@A?Îe×A$E^Gú5\x0005Ít{ô
]å¸H^\x000fNá\x000bUÅ\x001bÑ8\x0004\x001c½Àó©
`\x0011j´G¹ ú\x001a\x001c
ß+Ö¹\x001dÕÐE:¸"Î²ØL\x0019Ô8ql;´z\x001c~ö8ý#³OÆæè\x0016Ü¬.õ
ñí{\x0004c·vÜ#ßb\x0008\x0000CÁ-(\x001dJwd\x000cRv~@\x0015ìwLgN\x0008R ¬4=[Ñá±¯Ûq
Âøáî;v®BßÞC©ioÇ0Ëàh[	BÄ
WÁ~È^è2¡éWÝ\x0006N®¢Ý¡Gq"(C\x001a¿5g5·\x000fÛ]\x0003Ù\x0014`IÃÇ?Bà\x001d\x0019Tvç/F?\x0012~SêÏ-F\x0018S \x001fx,\x000cï¢ðb¬\x0005Äë£\x0010Ð M3l£\x001f\x0004á,@\x000eÒ~
XO·Wæ ¯ç>\x001e6)¯ªÖÝÎ¼
\x0019wb)CW\x0005ÔÐë¦@\x000fô¦\x0010\x0008k\x0001w£T\x001eô:¨ðqßêep=TÚx\x0010ÿ\x001a¥#\x000e\x0019\x0008k}\x0016½ Û\x0011\x0004\x0013?ÐçLÕ¨Ï:WÀ*°T)¬®F"ÑV\x0008þÕIýê£ªµSæ«\x0010ù¦eYö®qô`\x0007Òäç­*uT;uly\x0006*ÈK©Ý©
_/´\x0003£@Ò\x0008BüFG¸¥¤³\x001eÛ\¶C0jëCEq©§ô,\x0003]ë×|)jB9\x0010Eþa\x0010\x0005XC|\x0006sZAcÞAÔ\x00043rl£ñújÈû¬uÀ6+ðå7X Zi´A§Ìwà2(Ét\x001aJ$32\x0016ÓÃgÚxÍY&v#*|Ú8ö+ä\x0014\x0006Èss`a³³VÛa\x0002îÝò=\x0002l5\x0002y
ªâÑ\x001d4G\x0013}\x00160_wéÔ\x001a]7\x0005®H9¯ûpr×Ï\x0018\x001fûB±:ë°vãxcláú×Bü±7$êæà9«)\x0011Lníe8Â8¥\x0012[Ñøznüb^
DÿnqoM\x0005©ø0¢I\x001d\x001fg¡y§ ûAßQ×KT\x001fòn7½\x000cB®\x0007\x0016/Ïjd\x001f
ºýMï_v½]¬ÁUâX\x0006ùüç5²ë ºûðà%åßH\x0019Pêºî\x000fv[Û¢±LvÄ¶«\x000fº\x0015NÍ²U½9<>¿N\x0007\¯?N`ò)êÜ,"\x0018|ª6¬\x001e?ù*
>|ç%3±°ô;N`EZ­Î©\x0008½\x000c5+oÙ$W\x00060O#\x0004¸ÇþØ\x0013XÂ\x001f5ï»}\x001d×ÁöFIiyêw´n Cå83\x001cåA\x0007Ô\x0019DÝÊÞ1(á½ïÝ Q­µ\x0011\x0000ú\x001c¹C,¯Mýj§c*åt¥ªS·¬ BØ¾Ö.õ5ß\x0002Çµ
Y¿fÉ-÷ÃQ-§ N?\x0004g\x001dô
hkÈ´\x001dà8{AE'\x000bÉÚç¤k¯¾:!{|õVÝ\x001eª\x0010h\x0000\x0011\x001f^\x0007ëIÜì\x000fD\x0007\x000f/à\x0017ù\x0007BnæÄxª ;+o9@\x0017¶\x001fþØYÎ0l\x0014¯Rÿ1AÏË
\x0012vc°íÆ«Æ\x001eMt.çW'ùvT¸zãM£¼ÚÔ:\x0015·»7m\x000bÂÀ¾-£@6Ò\x001cM;-ÜÑN×õqZæiC\x001f2~r##wØ¯m!p¶VÞkYN±¶\x0013HÕAÀô!>Ör\x0014~_\x0006%i
£\x0004w`4ä\x000c¸Éæ\x0019Ä\x0004¢ÚÆTT£AÐ£¾¢ylæïß3|K¹ï÷s¿\x001eò¥ÀÎ\x000e{½\x001eÚ*åPÃªÈ¹Ý(ºô\x0006FJ'Èëç#ú:èå8Ä\x000eêG*ýÑ`½Ü/^\x0015ô¯W(C\x0001 Gî7V\x000e\x0018â´åy@\x000cö\x0016ÐÀX\x000b'´)KÈåNÌ0«\x0002HÚº}$9á\x001cýø\x001c\x000c@	¼OÙ§\x000c67\x0004PEÞæÙQûf|Ù`(qâ9++®_R©y¡\x0018ÊÜxì\x0008	 "\x0018ÿ\x000f¦[S'#QA\x0015%\x001c%IÎ³^54\x0018Af}»Á\x000c05í\x0015\x0012Q<qe{½yÔ\x0003úV}\x000eÔL¼\x000fâ\x0012ØcÙÐÃ|È~
ºÕ$ÀùØÁ=+u4>TöÇ:í6d.\x0008\x0008\x001fÁÇGå¶}î·õÓP£êç×YÔ ÖØ\x001ae\x0016¤\x0010è5´£^fQØ%@\x0004ÄôhÕ \x0008\x0019\x001e[Y]¸\Â	i°¨ð´<"s´àD>A[\x0010<ß¢8ÖØ\x0008ô¶\x0006N\x0018D3¢\x0013\x0007iY%/Ý<EThíø½\x001c¤%òãö/òØþåê$\x0019³A¦<TM|°Ñ¥Þ¿uà¡\x001cÊ\x000bÍÏË$êq\x0005Ñ·®\x0001õåä\x0013ö\x0001\x001c;Ù>\x0003!Á:W\x0004Ù\x0012Ày$\x001e\x000bSÉ¨"\x0017\x001cçu¼¢ôïn)Þ:Ì7\x0010«\x0014ú°\x000b\x0017!óC\x0005X_ANJ®ãU\x0007V
\x0007\x0008Ê!×^Ncjm@ú-¯ú³=ü\x00108Ä\x0016üä\x0000âíX½nÅY<ðÔLn\x0019ÜÕK\x001bÐv\x0008Nbý"äääÀª\x0011sÍòà:Ð	ñ¾\x0013³yÔäQ\x0002Ïix\x001c,© ·y5"g\x000eýG"9P3gNµq\x0015ªÔKn¹'`\x000f\x001c&5||Nï\x001böB\x0016¹bFû²óÚ\x0013Mô\x000b8ÌÛ×\x001c\x001e!;FÛoóÔPe\x0016\x000eo\x000fXm\x00001eÇ0#è\x0017Ùq/»åív§§Ó¶'¨;¹T	\x0014ØàqÇÙ²®Q\x0002\x0010\x000cN×à¼áÝ\x001a¹	+ï¥îºQE·£\x00086²g&Ä\x001ed%ç\x001ag\x0004róSOÏ\x0008·áß<Ý\x00121<Ö<6Í(é§´ß\x001eç:>fºYmìÎy\x0000«ô\x0015Ð/ w.Q\x0016tT´){ÇGk\x001fúk7.Ð÷×Ñ¨ÑfÐoòdÞúÂ»3ÀeÐý\x0019`Ì\x0018R*×bz\x0010t1É_\x0019tw\x0006øøVôfµ
\x0011\x0007Ýp~\x000fî®\x0011ñ¦o\x001eÆ\x0000½$ÇXaOÐRy½é
âZmÎ~À3\x000bd`:\x001e]\x0006Ä7hK\x001a\x000f{\x0014ºJ\x0017EöËu¬¾è\x0017lSäiç@ur,:Q\#û7\x001c_Ù9$Þñx&mÐòt<\x0015\x0008ì\x001cè\x0014úþ(Dv\x000eh7\x000c\x001dý« içJÎÎñÝè Ê a\x0017j±spqh\x0008\x0013Â\x001b Ý»®A \x00082Ï\x000f\x0015(ÿ"ÚsD¢æ<H\x0012j·'©\x0003,¢0"l\x000c8\x0007\x001e\x0001\±\x001dá(øu'zhëp8rs\x001eÇ\x000f~1j¦-;U{Þe(F\x0010\x0006{·º
\x0012:\x00084&\x000cð	\x0019tÖ\x001bÒù]ô»¨:m_¯\x0003JòÑ?\x000e\x0003|X1±Ð\x0006	Gq\x0010/\x0007LEóº\x0010ýn\x001a\x001cµoÖ¼\x001c"a|.4ö¨ÆÅ!Ñ8CP E\x0019SF?ô®ì\x001eJÞÎ-äå[Ý\x001cîI½ÙèTÚm:¼\x001c0\x001d×\x0014æÄ`$²}Ë\x001bÊË!aÝ<f\x0004Û\x0013ò;È=®\x0010Ê®TÖ\x00076²"Xl»,\x0012ðÞA³í~Cùþ:¨ÈÕþ3J¨×A°FÀñMB%½¸ï3\x0014¾fr·\x001d]¸:\x001cÿ*ÈÎ²¥»@^áçgeÞfN.ç,Æ¹2v\x0018!âè±Ãì\x001ee\x001dÄ2Ñ\x0006¼Fá\x0011Ý\x001büh±)ÏÀÒª\x000e^¶ÊÉ\x000cr;5ðqpÎ-óc \x0013
Öç$\x0019\x0016"gZ¤íÆ­ÂÀ\x000b¶vHzCÉ\x0010VóEÌ´r(tµëÃ\x0018\x0011ÞPÑ\x001bg1ý 4,î{ßR\x0010ÞÜnM\x001fÐô4¢{NÁD\x001cç³3\x0007\x0010
;ú8(_ÒaýS-'Qµâ®°r e{ ÏäÉ#ÎÚ)°rjY×jyG0BëõXâY#"TéÑ\x001eV\x000e8qF\x001eÕiåÀÑ9>\x001cõÃÊ!ÛVÕçH#G=¼,Y0ÐG\x0008óGS_§\x001d\x001cwqë6d¾\x001f|Ópn¼¼\x000ek\x000e?Ð¼üW¹\x001cÝÁ±a2¶ÞNùO
h\x000cC
\x0018Ð®ó)- ¼\x0019è\x000eU]&áÌ0ÚQ:ÇÊ¡¶ØGH\x001aìà£¨CHRê¼Q=l\x0013\x0002\x0012ÿþ5p%\x0014Ïj]ýÑNCÆ­v\x000c\x000b R~P8wVXAçÀ6Xë%å\x001fÐÙíVZ\x00086-é¸\x001e~>~îFºúá ®®í+ÓÜ\x0018óÒZöÓæ2F9$RÚmÌÃDí-ý½hÁ\x0014ôÆÎU\x0000U9\x0003õ\x0019þ^Ø\x0003\x0014i0mb\x0011\x0008ðì \x0007\x000eESôª:Ö?¶LÄ\x0006}@Sí%nG\x000c[¿é££¼nÇALLDÌKPn¯\x0012\x000fI3^§$,ò°ð\x0002×]Ë°l;!0N4úlXú hØÐ~Û\x0004.8\x000eù°Ð©õ\x0012]×Å\x0002Ã«\x0006÷G08\x0019Mºe¦´\x000eGDò2R¡âÀ¯åu#Ëº&@\x001cÏ$ÒéHê÷\x000b$ÉàÇåa4\x0003I\x001cZ{wû±»4\x0017é\x0004¬gªrÎ¡\x0012sBª¬`úx3³\x001fÎ~æÐã8\x0002½Í\x0007_\x001c ¦ß6?<,Þn\x0004â]q\x0018\x0004ýY:µc\x001azË Ü4·egýi\x0007%lù<èý£ "q{G\x0019B#pÞ\x000e¯Ä\x0005~eÐÝí>þÃßY*\x00078D]·r°u£êÅ,eBÐÃ¾ØÒÉ©n=H!\x0013\x0004:A\x0016ïÈAHDÇUéº¥ÍBÎËÍJ$¼0¶\x0016¿A-\x0015\x001e<¶u\x0006±UP».º
¥R	e]\x0005#	ÛüPSVä X-Ð\x0010ÝÉ\x0006\x0018Õ¶è0o\x0014E\x000f#ëº\x000eV
øÙ.\x0001\x0008Þ\x000ec\x0013°_W¨h9:ð}\x0005aêÓ³$éV\x001bhVÑFøÑY·½a©H\x0012ÙÃþêçuDäT\x0005\x0011Mú:\x0008[ä}ÇSewãú-\x000egKRI\x001fáA\x000f]ä¬\x001a?\x000f\x0019wÂ*Ä±0f\x001f]f\ðçì\x0006¥\x0017µ8\x0000ãCÎ!ìÝ\x001f¨×QØ@,oðÇ\x0008\x000c4!§'ÅTðx\x001coÏv0Tc[O}døî>IÊ\x0010ú	2B9\x000c3Ä~\x0011:	0ÔçÐÞ\x0001\x001eeËÿú9\x0000ø8d
a\x001f\x0001á\x00056óyÿ\x0008\x0008\x000c¨\x0018¾¸µqfCYµ­[±\x00027\x0004\x0016G:ã^Á')NÚ¿Çf\x0006ÒÐC¸G\x0010ÖÂy\x000bÑ\x001d\x0002}Õö\x0011úGº
Ö\x001dÔNHjÒl
S	\x0017¿?\x0004²IöÆN\x0010]*N8T5\x0015âaüÙë\x001a#\x0017èà>Ò+DN3~fq
éj´a6?ÀøôåA\ù\x001c\x0008q\x001d0`(D¤\x001cö·U
n3)Ä«×bM\x0017!ãV }ß|ñ\x0013ò~ ùa<ÑÓ3"K«Ø£­ \x000cü\x0014ÂÁú9 É ®¯Õ\x0002¨\x0016«_]e\x001egkT[¼\x001e4p\lx+'Ä~?/}è3e\x001a¬òïÉéýø}Cü\x0018Ú	8àÆÞ!  ìµÖ¹\x000e$´nóèý¬\x0010ÁÉ0 *ëVoKO>Ô5=©ÝÊrì1!Ø¬ C.ý\x000cêíóK³|ü\x001a&wBKd3Ð¸î4?\x0003Îï0\x0014«:ßZÜèç°¹ñÉ=evr¤ÅÛ±å6)oNzu8Â\x0015àd`j×U@®¡b\x0005ÉjÞ*±ýÜz;èLh¸_ÌÃ°$[þ³÷¡
\x000c,õ¡B²Sa¡Ø´®g?Ë\x0013/ëýå\x0004N\x0001åZW\x00106Ìüà\x001eæÒ\x0005²¥\ï'\x0004aW
ôO?´u²÷\x000cËï¯o«ÆÔ5@ ëzCÌY\x000fM(Íí\x001cZ¬íÅXU¯×\x0016\x0001_i¾hÚ/û\x0017
_DNX®¥;§ºÖøb£D\x001f\x0017ùÃ±4\x0001Ágí½Ú\x0016<jERT\x001a\x000b·+òGZj×6x¢Ä\x0008\x0004ÝÔhÇµ=ãCú\x001e_ðlP5óVyG³1îqJ\x000b\x001dhz?\x0006\x0012È~ö¾Dªf)æ9°aeëó
\x0005\x0007Ø©+äÚ\x0001 ú´n;E"\x0005\x0018ÏD~U\x001e]9\x001e%!mËØg\x001e|'ìX&Æòã\x001fó-Ó@à!ê/k-íèÐÐËu\x001b´A¨\x0006Øi©Ì \\x001d¡%7\x001e½Û2\x0001a1OIÖdD§)ËÌ\x0015\x000eÃ
;H\x0000ßÝ\x0011è\x0019´¤ú~t\x0000i¨:NÑ\x0018m²2\x0010(:ðÚËàúûºUÖÙÎ©O\x0004L\x000e
eoÂÐ{\x0013@~.\x0005\x000c|Õç1^Ïd?q:Ç
jòzkëF
OÉ0[\x0005Y¾ßX¿u?õ}y}tÝ\x0004Ï;ýÀ\x001d\x001c\x000bï¼s3¤+!ñø8ÓÊY\x0014/­9\x0019eÚø\x001e\x0013æ#_ê³7\x0015¾Ï\x0007ià c;»0Ùìâ\x001b\x0005QlB¶¡Ö½iQ\x000eüØ$pGÌ'/ë\x0012Òmúså\x0008\x0001[)Õä¾÷#{ÁîÿcïÝv6I²ó¼+{¨CJ0K±ßÈGDÛ0\x0008´}"Éð\x00191*5@Bì!1\x001c
öÝ;wE¬Èªú¾®6ü\x001fR\x0010\x0004õÔú3¿ÌÍµÞ
öÞõl\x0012k`æÐ@\x0008xJIa\x001d±XKeØ¦ÂL÷ÁLæa¿f=ÐÄW\x001eÂ§§+w\x0006\x0001Q-±j\x0010>\x0010±Ç\x001fý|÷Ìx\x0004p/ýÀÆª³ò(¶\x0005Ïv²f9ÖVI!
\x0017ÊGðï\x0005Ó@Öw[\x001e¢\x0008¯bçä\x001dÄ\x001bY0ÎuDwD/ÕsALaîÒDüÇ\x001f2
\x000bÇ\x0016[vñ\x000cØªSßÍ'û8=eÛì©è¿\x0006DÛö\x0019cÆÁf(vo\x0000s++îùÈ¡6÷6Ë­ \x0002£ò±IékIü¾!2I{\x0016`GÈ¬ò³=TEÊ\x001a	1?{&\x0014\x0002ª¬£Îûc\x001e¡|ÔèHeÐghl\x000bö+Ò=(Ee;ÈW´XíÇ 9\x0013×\x0018Ç3.|V¹Äyg)lÐd\x0007\x0012\x0015ý´Ç PV4í:¼Lxx\x0008)'\x0006éÉB
¢\x000f\x001f³oÁk!ír)´îÿ
J,¦Ñä×Á1­fá hm 9\x0016\x001e©\x0017\x0010V\x0000OöÜ"Ý(÷jþc\x001aÌõ0}ø¡¯#®Û~ñà\x001c<`¨\x0005\x0014Óa\x0017(Ê×ìgáB)\x0007\x001f£n³Rt< ª\x001fÎQÖá»iêõHã\x0000Vt>J 9Cº\x001d{Þ¬9°|°núé÷,L\x001fXU,±¢:\x00037ßAØÝ\x0004\x0013m\x0000êT-ã=¯%\x000caæ\x0019m8\x0003ÜGü\x0011\x0015nÏïe\x001eÛë	Y\x0015«~þ¢#=¦ÕùdÈ¥aaq~
,ÞÌú°GÌ?&Íbß¬ù~\x0019BÐÜ!\x001a§\x0003\x001f \x0002\x0018ÆõkBòAhÊð¥ú*X\x0019Ê4\x001dë¾\x001aUHú¦¿uª\x001f{\x0016Gz@\x0015¡ _*Âm¸>GÂ\x000194Â9ôÑ\x0000(RÒ\x001f\x001a\x0019Ð·eÂ\x0011|ÝV¢ÀÑ£íñµ\x000eevòôB\x0004\x001aÙ;îuEC¬	ås\x000c\\x0003bLë3Ì5ìíV
a4|¾o\x0005$i¬\x001cdf\x001fÊko¾vÉº±¢\x0008¡o#F\x0008RP¬vÃ~¦>×xk\x001a
Ï9qS¬ÞßÛÕo\x000f¾\x000fÝó!Q¸Ô?>`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf](https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `<?==ÈaÅ\x0011\x000eTøìÐ\x0015Lm0CÎÅáÌWfI·!\x0006ÓØ\x001cÒy\x0015î5L\x0000=?Ý;VØÀSÞO¾­\x0011µ'*+mî`ò;¹øÂÙ[vÇnd\x0017ÃîBl@ac¤þ"?#ë¸ÚBØ²âõnÖä©ìNëÌÒä\x00117å\x001cÑ\x000fÌ°/\x001aÁ\x0000* ø¸ºOêyªû÷BR²3\x0000m&ªJÍð'?a¤g¡²$¥ó&\x0013WäIv\x0013/Ýør¦ä¡®<:¦ÇH9ZG¡÷®$\x000b\x0008]}êÏç³PÀÙÎè\x000fªVEr 21_ÞUBÄ+u^â<ô³%\x0008\x0002[ÿÊ\x000cªrûF¿ªê)*\x000etylÔ(e²Ù\x0010JÜ\x0018õ\x001et¨àÜ*J\x0001\x0012Æ²î±ùÙ\x0007 I\x0011?0J
úzýÛ\x00011ÓSë
÷!²;\x001eevf\x0011ÞºØ«M_e¤j©³\x0018b×ÆÎB¤}9Ý\x0008<Ûnkg\x000c&Iè\x0016»¶ß<'!Y\È\x0007
\x00133ªºX Sój\x0012³\x001aMVî \x000ck\x001db~§èº?Æ®4\x0012»_')9ïúûRm¿wÔ´ <j´è\x001b¶æ\x001føÐÄ`¶\x000bÇ×ÁimÛl>W1!\x0006V©Âyg-\x0012ãË«\x001c6\Ë^ÑîxqK@ÇQ©@\x0012&EÌ;\x0016\¯cØ(¼ï-\x0015|=¯ËÄÚ¹\x0004\x0017IP*A\x0012OÑÚÑÐ\x0015bïèsâ¨*®WÊØ½Ð¨pöI(ë¯\x0003-ÛÎ\x0006Cu\x001e#å)È·»cEµ)y\x001aP©\x0019\x0006Ó£ÖMUÞWis§\x0014!xRä¥VK\x0012á¡cµ\x000b\x000c¡ÉÜ/J\x0000Ö\x0005n\¦SP½çÖb\x0004\x0000XZ{\x001b\x0015{`ZÇ´ñàù¨0Z±«"¶H8$,¨ëÎ*\x0001»r\x0016ÀNÇÊËæN*ÞYWB±\x001fê1OçØGÖJ²9è\x000e?{öXVÈ\x001eµë@é2¥}\x001cÌ«à¤k(ça\x0012µËsê\x0004¢ñ\x0019!Ýäü
(ÛÐ /ÂÕ^SGó<ÐjbbBíÄ`ô\x0014\x00078è\x001aòf¶]\x0011æÒ3£è(\x0013áî¿n	\x0002Öà\x001d÷¯Ä\x0018Þ\x0012	uE\x001d\x0012®Âø(
d©blËÙA8Æ\x0016}.yNÒL\x0005\x0014i1¿¢\x0013kTm´\x00036\x001a`ÞûÛõ\x0000$_Om\x0001©¯
PÈ×¹ïÓL°còè\x0004\x000fEðCr\x00039º\x0013ò\x0001miÕå»7\x0004l
\x0003\x0016¸yê+VU\x001fKk\x0008åô¶®, ì¸\x0002ü<;Á¦w«\x0004ÊkX!bè½ÇZÍ¤®£0Tmüézð\x001d\x000eù!à£E(Qq !_í¿g5;YÈÆ\x001c¼Ð{#ªÙ\x001d¡\x0000\x0012PÉQúÓÄuÍÒµC§0W ·ccñ¬x\x0002Zp5\x000fBjê£zSÔP(Æ÷¡[1T¡kgQ\x0003d«¸\x0002\x001d¯\x0010Ð³K_¼Á\x001aQV\x0000\x001eF°&eØçl\x0007=Á
*v\x0014\x0000ð£\x001aÓ¼¦ éò­\x0011{V!|äÀÉ$E.qÕTá÷ãlæÔÃä\x0010¯cv>Ù\x0003ª\x000b\x0012çáø&Gö\x0000áìs\x001f\x0001îlg[\x001b-QWÜñ7i)*lÙ}zK\x001e?\x001bê$GC×\x0015\x0002ÿ³)W¥ë\x0001ÅÔ	pô	
¹,@æfÎp¯hkÄãÁ-É§ûGDº¤çk\x0017\x0007
F{`\x0004»\x0011RÐ>èb÷#lØèÉÿ0\x0004ÄÃÝ4"ýC¥<µªÓ»\ÄÓ]Fx¨ÀûB\'\x0011qj²ê*9)	\x0006àÞº¡BäÉH«DÂÖ&Hen+ml®\x001fÉÄ!ó¬¦<<,¶1Ü^æ
%	\x0004Çã¨}\x0003²\x0016\êR
mÓXå5&ò1GÕ¡`9úi®-ó§Yv¹p¤ä¹¬\x000cöÖ(+Ñm#âëc#2sªp(óIª\x000cäý[E`ÑV
1a\x0004ñ\x0012j\x0008ùD²I

ÏÏ´\x0008ZW3ýÓR& bH,uý´}=àe\x001e S7Ú)\x001b\x0008fÖ\x0013óítÂ®"\x0006À¦eÇr]å(Ôª\x0003;T,\x001d\x000483¥º¢¼X &{]¨\x0006^¼.\x000e\x0017÷4ÔÇ­0çØ½"áºÏþ±Q «Ædíp^I8b \x000bï#£\x000c\x0011RFND#\x0000õ­QÄbô"\x001cfÀÊ
ß[ï92ìÚÂ÷\x0016"l\x0002	\x0018ÇÞ\x0018!T\x0005¶áäbâ\x0015ÛÁ/Y& Øm©®oSª\x0000§²é,\x000cu\x0007)\x0018ÈÝÍ<*Ü!yòp²ÂQJ\x0018ÄÛ\x0018\x001e\x001bZ£\x001c\x001bp7!Ä\x000fléÌ¹\x0013hm\x001e§\x0001ölÙì·\x001b±âETäÊM:æås¨S§P§\x0019¦Â#[B\x001aÛ\x000feæ?§c
'x[Û\x0014ý»C@GýdÏÏ«£ÊÀÁ:ôç\x001c»»ÆêºÂãIqsô}\x001bã\x0007@³\x0010Ó|^4jÎjÄgsÞ¼	eqªô1çnÇ®²_}CE\x0019ñ°þÕ\x0007{Nòp^ªÉzÛõÜå¹¶\x000e(W×ùuÇo\x001dòãQ4TÜ¸t§ogÔ\x0013%>nusÈu\x0015ñôßT\x0010?ÚQ\x001f\x001bq\x0016R\x0013Â¡ön\x0018¾ôÕ>[ØAytasî\x0000ID@Qþ¯\x001e\x001aQ²@Ú&÷¾îø¿\x0010\x0016¾¢ç\x0004£µØ÷]Ü%
Üm¼n2¯*Ç\x0018ªjC4M&2OÝ\x0002\·ó\x000bæ×G¢%¨ÖL&íàÒÞ&$î(\x0011!J<\x001aâS*EôaUwÀ\x0000\x0006¯xhô\x0018|ªÄ@¬ãÍÃgä àéTpÜ`\x0010\×>\x0001\x0014ÝI£);ú\x001d»§|ÅéCÙä"ýwôs\x0002\x0002òq9ÞD\x000c\x0010\x0011\x000b$¦	ÉûvÃ\x0017\x0007Ã
wâ<WÆI´rÇ9³MÈ~v¸¾qg|/XA\x0002xeÔlñ«6c\x0018QÐ¨\x000fhþ\x0000r\x0013fòI&JÙDpVgî¬°¿×CC°î'
 âyÃå1ô×\x0000Ì\x0012	Q®Ï­^¶\x0001ç1D1\x0004¼¥b\x001be)j\x0010R¸ÌMXÒù-5]v\x001a¿°Àêvq9£\x0010NMñ:`M^®T1tjÏT(È\x0017YjÂîsuã³1\x0013
Ê(ÈõÌUÙÕ;&(ÖÞ\x0012Þ\x001f\x001a®5¬]\x0010¢\x000c/J¨£Å\x0019\x0011U6¹²g°!\x000bò0BÖ®6¯\x000bÌß´{\x0000ÒóIY\x0008]ó_Ûò*\x0019*N9¤\x0011PhFn8\x0004*eL\x0008}hú(þª']õ\x0006¼°¥\x000fº­²\x0000§U3h@¥'.6¾^t½Nb¦+ø\x0000hE:4½\x0017³øB4í0!Ô
°[\x0017Ø\x0012\x0016íÓÞÛ?\x0003«Ì£"8S¦«<";Ë<¶Û;
RzC	Dùá,0²³°rîçÐMh¯\x001f¨ò\ØÛCs2«\x001fzKÄ!Uy]ÝB#Ö£\x001cæ`#*5 ÂVx¸\x0006
ðL}\x000bã\x0008\x001b34¥L\x0012\x0000\x0015*Î3BÌ«Ä%úÊBwXµgSU\x0008/
¥Úxç(<uG\x000c78
sY«(\x0001e\x0012¸·è\x0006sÒýx.á9¥µ3é¨a\x0016Ño\x0004?±3Ä.ßãÓ\x00198âÈÔW=0gMÈ×1º}§w¯9Ú>Þ)ÚÐ¼>t¹/7}\x0004$0¶^j¹7BgË
««qÿh:^Ø.*b\x0016dÛí³í¼^-{;MHQ\x0017Û\x0008M{KäÀ\x0017;q5\x0015y¨Ä\x001d8v\x0013"¢¬µ3Û@\x0011ìë'\x001bbÛæzz\x0012Öë}í`±]ÛI÷¢ÄipÇ×q\x001cùp\Ã\x0008^[¢)ç4A=\x0006Hò©?%\x0003Õé<!qÇ=ëoL×AF(=»±B\x00135X\x001eFñÆä-8\x0017\x0016#Dë\x0016sÀB\x0018]|?L:\x000b$N©åG&\x001e¯%	º>acD5}§h²ô6HæØP¥\x00131C\x0012\x0017ÿÑ\x0014\x000cKIWwrÀ&á¶
&2÷Öã Ù\·ûëY=@ì¾*ÐÉ\x0001Åc³?C'°6P[ge&\x0011~:ö¡rtaç7¦È\x000b%¯ßê\x001dÊ¤\x0007q0Aûú\x0010"lE ØS*\x001eM	\x0008\x0008¸¶ó,Jø×¨ùU\x0019]G§\x001bÜ¬(.oG&1l=§\x0011×hÔÎHu_zz7±\x0019\x0017!	XMÑs@`[¯ßãÉ/\x0015\x0014À\x0016fË:!1Á¼ÈÓ â\x000f$Á\x0008SÆÉ'\x001cº\x0002ßû:Õ\x0003\x0000þ*U cìRXcEpd ºÓ\x0008l\x001fÔ^k'o
C?g;h]\x0018éàÇëFÐ@YäÝBÈ/Býã!m¬ä¯V\x0015Zª\x0004\x0000ª\x0016\x001e\x0011&¹\x0013jK"!¬£\x0016Á |òRP_!Rx\x0001)¥u}DI½5ó`íJ½¶\x0002Î=\x000eÖÖM(¢m@ÈC>isP}VúÝ\x0003\x000fy[-Ð_ÛôÀ{÷\x0017&@\x0016ögÁbÅÁõ%C	h"ñJ§E\x0000®ö,è\\x0019Aøpó\x0018f\x001fô\x0001[\x001bíêÍQ~kôxëÿ¸Ôh¶Ô!\x0006n\YW1~	E²¶ô9Æöj&ñ¬´'±D°ÁõE
óäáEi°±\x0010u`ËâØ2Ì/\x0012C\x001e\x0013Ã\x0005'·Q;b
Y3\x0011sbø*Ùk_\x0014ÌkØCk\x0012Éò\x0018éB@^@¡Úô\x0001+\x0010^P¾1ê\x0001,JþË:jà\x0003'y\x001eb\x0017"hsÏ8PÍÁkÚ,er\x0010"ðeõ±Äíª²Ö¼p°	­Bè ³©6'\x0018[+i²\x0012³cKª@´\x001fZ_à\x001ctöNð\x0000éÌX\\x0007Ý?\x001cî&ÍÇµýÿðøx5¼r\x0005o÷ue!@É¡6¦ÝKaÐs'\x0002
\x0006Gx½ës\x000bwQ1 ¸*~Ñ\x001aà¢ÜúvAt°Äu\x001a%pvM=FU£\x0014ÄSYo\x001bØò
  9#ÂS*x¨ãôî\x0013+°øDB=C°·\x0016cúQã\x000f«zÈicôîQ\x0000AP*é¡\x0011\x0007\x0006:ìæ\x000e#[Tw\x0015°ÇËÈzÙ.;)N£Få!÷¹3\x001fÀz´¨ÁT¢ñ">\x0008º¬d1ì'¢j\x001b&\x000c©g²/ðïí~úqÿ¨()kÎö*\x0005j[:SH¶:¦\x0019Fó'
3¢5\x0000<³\x001f\x0016vöfî§\x000bG+\x001c\x0005´9Tÿêíí\x0010âåæâÏ\x00148\x0011ðýT2#B\x001då "l=']$­2AÊÞ\x0001Y=7\x0005¥\x0019Bó"\x0013\x0010òì;þäO\x0010\x000e¢\x000f~´D¼Ð\§EJÒK\x0014(¥Mb\x0001ß¨Äº\x0017Ú
«¦ï#\x0013§|\x000eà^P¶1\x0002\x001dÑPL(\x000c%²WNÎ\x0002\x0008H¨ý$m	µNãtöòeQ°Îî\x0013¨TY÷\x0013§\x0008ß\x0003ùÚ»O\x0008IªÇN"\x0010à¿¾sÃ0¶& Û\x000f9©Hø½=<cÏ}Jd`ÂdÌÒÓìº¨ÇðB4k
Ì%7#Q PG&^à"»|ù8Ú\x0018GîPöùU&È\x0005.Gæ+ÇI\x001f)\x001dX\x0014ó¯.¾Ì\x001fdq÷I;\x001b[ñ\x0000nèý)N\x0004¡\x0014·¿àbqª!	Ð	\x0017;ÝÛÆ¤·\x0004É
y;ßJxô\x001cÛ]=Ìñ\x001c'ÕT´Çe\x0004i\x0011ËØºÌß(jì\x000cÃÈü·JÁà
nÇØÝ2w¸)FpÖ£¿r\x0005÷\ ô8\x0018(ÜYmGò&èA= O¶Mº;9ü	BçÐù­0²ý\x0005L½aC?ZAxöñÊbK
äØ\x0016	'BÓ¡\x0003 \x0018\x0002Õ9e$'û*üE â\y
~tn7¯sà\x001aS}\x0016¤´\x0008Üü39ø3ÔkI&Ô^ÃóY¹OÝ.]Û\x000bÁx\x00143áð¥þ\x0003.«YV!7Õd}ñç&\x001a\x0015×ä\x0006st¬³<ãtàÊÄ÷\x001a%·TpY·QüzCK\x001dhÇsXuëÌR
±©¬\x0003\x000bó\x0011m¾Ã9C \x0019<cbF\x001e-Q\x000eæÀ/D<¼+u\x001c£%»Ì\x0003ªRdå=²êH\x0019Þná[=ÈÚ¯\x0013Ä5Ä\x0008	#\x0008È@ÞÔ*\x00129\x0011¢©Íyc¾6Z°
M#ÈR=ì~\\x000bÙu
pÜrVFòK6Z\x000e7F?pÀ~<1\x0008NðÌmÑÙW\x000fnÎ0± \x0010(½á½©:K»nÔªß\x001cÓgÕY\x0002ïW\x0001F£Úu¦\x0002ÒÀÚU¨X\x0001ï\x0001ÕúÉa\x0004÷5úh9M\x0013í)Ñ1¶C\x0005\x0010i2Ë[íì+r\x0013auÀ\x0015ÂxNÊÌÎòM\x000eé¥×ú"R&Óà@\x0003úè8\x001a²\x000b¾\x001fÈ¹
Ú"¤Ñ8J¥sÎÈ\x0018\x000cgÏ\x001fÐ\x0000\x0003-²^L\x001ct5Ô×Ø\l \x0005rÖb{#Óhé2!DQÿ©L<\x0002(m|¯Aß\x001b7\x0007\x0008mßN¢à\x000e²\x0013[¶33\x0001	\x0017JX7&Ï"ÝöV¶Ý¸¶/£J7¯íêóåÛìMî¾jk\x001aPÖ#upâvMqàpÛÇö\x0013vþnÂ>J°³Þ°½ä%8Þ&_oÆê\x0004
\x0013
ª²:Ö5
&),¢fbîhV.àt\x0000\x0013}ú¹u5ÊÆ!Ï¬+\x0011\x0008\x001e- dB\x001cá\x0010µ­µ\x0010ì\x001c"Rö&ªIkR©\x000byL\x0011\x0007§urvc·åªß¤¢qæÎñG Ð­]³ýò#Ð\x0007\x0012Äé©%
ÄA½öáòùÛön8µiAÉë¡ÉË*à½Ñ]íîn.ï6Ûè«^V\x0001¬½¿ØÆ{ïÁ1Ø\x0005¹õhÕÞÈ¦\x001d)%×\x0019\x0012)m1\x0003µs,\x0014"=$±	¥ÿÊ§sHow~\x0014ö:¾1ÆEËÎï¿ìT\x0012èÙbw«\x001c\x0006\x001aã\w\x0007\x0016­\x0001b±£\mÈh'\x000f×[ó)¨HB·pav\x00067¦ªC½­Ê?H÷ß ðiÀG\\x0013@\x0002úaí$r#Ã`sTe#tLò¿Ù+*·!ad@=K\x0003ÿ\x0012O_\ÅÝdFCIa×Ær^Ïè9²¦£¡ûa\x0014Û\x000fj\x0004uso\x0002¼¨Òl2uì^â7\x0013:L\x0010\x0005\x0013H?s\x0015\x0017#þMÂù¦ø\x0015F8 0*\x0000lxhÄ5¨àHhßÁ$¨è=åÚ/ñ0±+@,]ëccò¬¦P9ô°Z\x001cg\x000céî9\x0019PV.ªÝ$F\x0008/Ñß(\x0010\x000cñ4gríÀY\x00047ì\x0004ø\x001f.l
(Ø¬ç\x0000	õ8ð@E\x0003jQP%Ä£À0\x0016Ïz\x000e ¢Òpu4E5\x001dX\x0015íåÓ\x0008åOÂw~ô2§©ÝpB8\x0013P¬0d\x0014§\x0005É's\ðÂ§\x0005pWVEëo¬$\x0016üÏa-­\x000c\x001e
`j	LH5¬÷½Jéü'u¼
g7iN¸\x0004CþÑ\x00116UºK\x000bß\x0002UQT¨÷`\x000fæ¨Tè\x0007ÑÐ÷q\x0000ûK\x000eÐdã¢ß%t0Ç\x0013Ä:à#®R\x001fÛ¾²ÀÖ¤u1\x0001ÚIÉt\ø
\x0001Rí¸.a4U£È \x0017\x0006ë¥É:\x0007%[¶/\x001fk<oÞí:"Õ¦s
þ±
0R\x0018Gò|\x000e|à­PJ_\x001fÛP4oZñ\x001bÞ\x0014êr@äé×\x0007HeHoz?Lì\x001c.tY8èvã¬¢²)dHfÎ\x0013 KfbO}<\x0015\x001a¤ÿÖ»Ü\x0002Ð4uØä\x0000â\x001eyg2&!®\x000fÇeÚÌ\x0005\x0001\x0013(ÐÊ®íH\÷B]ëÊ®Õ+M¶b	ä \x0013TW&¢=¢ÚlH\x0001\x0006\x0001>uÍ%ç\x0001ycò<¦ \x001b º§ÐÄÝsØ1Q.bdæÍ\x001b´\x0014TØ©w çé\x0001Dû¤$³K\x000e´ôG)³wì&Å5©Å\x0015ãGßö´k\x001c[2²ÌíDZ¾¨\x0013Å\x0000M\x0004ftQPÞôO²ef'\x001d»àâC¹NE\x0011rÉ²j "1g\x001cî2,Z´7¥rSÔñE\x0010éVjë\x0017*#\x0001·B]ñìÚaTv7a¾M\x0017\x0006Þ	ü\x00007\x000eH\x001c\x0003\x001e¦\x0012DrÞ~|RO?'n,7\x0011Í$TFÉNX\x000fðú\x000cù°|\x0000Ù3\x0018Þ§D1[:=RÛ#\x0001Ë-6,æ6Ë)oFyµ9ã4z÷ÈHn"\x0014@\x001d·øa_òã¹­ê\x0007rgP¬ p\x001eP°ÜÖ½QJB³\x0006ÝÞÍ\x0004Éd\x000fOú\x0019±¢\x0004ÇéEÙDÛöêfî\x0002öoãùT-Q\x0012Q/=ü[§úû@íâÉv\x001b>¢1qH®%Î\x0008ÚMÝ"\x0008¶m¾ã\x001aó"!ó¼¼áÝ[ñeQ·UÖ@PH\x0001Ê\x0002å¡nRà%Y\x000c\x001að\x0000xh9ÃÞD\x0005\x0016vNÃ\x000e×yL6F\x0008\x0001ðå\x0001EÉñ\x0002Ñl\x0008Ä
=\x0001AÂöþSð\åàÓ\x00105ð%Q\x0000ü¤cÐm¸>D$°\x001bH4Wà×F\x000f9<4\x0018!wc¶s5¢ü8*aÙ)@Qs\x001f\x0018)+à¡\x0007\x0004ÿþz#nôðÛAj\x0014\x001f\x001bÝ¥-ÍÈÖ8\x000c\x0015vî@ç«\x0011T[y1ÆÜeQ1p°\x000eqæD
´\x0015@ì:M\x0010ò¶ó!­\x0014J\x0010P¸!âÐ\x0014(³_\x0005ÖÀ	&¤Úò0âô\x0012.6µÉ8q¥\x0013tf]ÂÈ×S\x001bz=C&¥ =fI\x000cÙr´É«§\x0019\x0008Ý
\x001e\x0016Òns~¡­`xèë¡(\x0001Ææ²L(^wVFC\x001cyòßÚ±ÀJ\x0007¸©q1"S\x0011É \x0002á~l\x0004\N\x001b\x0010o3²OthhÙé·¼E©;Ý@»m1\x0010Õú\x001b%¸9ÅÏ(i\x0007uì\x0017¼Êæ\x0000A¯$]Xëg±	¸¸È*¸\x0019¡zGµ!¥³(\x0014·cFzú\x0010µØSº`Uñ\x000b\x0010 \x0015åæu5ì£N DÕicÒ\x0012\x001cÝNêÒî9ï\x001e\x0019UñWz)å<0ÂÑKK g\x0018I¼è"\x000bò\x0001òE\x000f\x001dÍÅ·\x0011[B¢ü¬\¦¶î§¼Y&
æf\x001e7q\x0018b\x0000.ÑÓD<l U 8üÁy\x00003Ì9ð0lx« q\x0012ñG«cJ\x0007R\x0013rÓæ·úV2§ÏzT¬\x001c±ô¶ÂÒ·&cJC¹|>h÷9[3È-©ØO\x001d0ÜËF$·\x0007\x0005\x0008ó\rb:ñâ£`Ïà2J³z\x001d]\x0019esÈûûQÊVhb\x0012[G-ü$dÕÊ<Ý²Òn|ø
\x001aKq,ôÕ\x000c1+²ó~½
\x0011øjjó\x000fMt\x001f§V3¦6Fw(æ\x000czÊC
\x0001çCÝ\x001bÍSÅÊ\x0010\x001fá¡÷FrX Hî³þÃ^ÍÇ£ÃTb\x001eBáOªFó\x0012²¦^xè\x0007F
[\x0008äÒ	²Ð±H\x0000
ó\x000b(ó-V\x0005cXäÇoLÕ\x0014\x000b¨\x0011\x0006wªñÝ=lÂðPNä\x0005N0\x0019nÌ'ì\x0014òÊ\x0006THQR;&\x0017\x0017ð7¯ÏU]Z(U,ÜXÉ\\x000b,Óe\x001eäT\x000býÖ\x0004yý²õÀ\x00089TÔ\x0001GK
Ë\x0014uá´ ÄE¤R^&¨\x0012\x0014;Îc@pP ¼±oàT£c&AÇ3aALG/UÉºÐð ó#ÜYRÕ\x001c\x001bÃ<.\x0015\x0011Ç	Ú±­À6µD\x0004^oTåO"b³(ÏJsÍÎ\x0014Ò21@XßçxB­
\x001bÎ`Eß\x000cÒÆ.{£¯õ\x0019ZîT\x000b#Ä\\x0005l&9(WG\x0017îL`¢\x0010x\x000cÄÆ5
¯Kë1\x0005Þ9Ø¯n1ø\x0016ÏzPèÊ\x000eA°7&c$`\x00109þÓö4z÷ÈH\x0011þÌãÓ\x000f\x0018ÁmFµdëÝL©\x000f[c=n\x0014*o>áé\x0000#$æ
2ê\x0010`óã¥#ùV»qÖxê8¨2\x001a\x000fºüÐ÷æù. icoèú¼@ÙS¾|&õ(â]ÝC±\x0007èáuS\x0012È\x0005ýê\x0016ÇÃé\x0004/\x0018øÈ\x0007FD× C^b~l$<"\x000f[ü¸¢â\x0015«x\x001eFT¼À
_Ú}<'L((L¨Z·omgÅFp\x0014Xsý		iE`+	äf$ÉÂØ{jäÐ)>ë:ðÃØ¡FSELîä²ËM¢\x001dÀ©lö	P\x0015_i¶tµa\x001aRy\x000fyDÿr\x0019è?õ\x0015\x000f6§À«t\x0010l\x001cÜ¬\x001f<t>.5!ô#-	ÑZOâcó%¼\x0000jª}`dW\x0003ò\x0008ºOÛläþ(ò^ðKX¨Àà÷=Ð\x0008PòäVÈi0\x000e\x0002')\x0018î\x0011 (\x0007Ñpªå\x0001Á\x0015\x0013R\x001d'Î¡Sg	\x0004NXa×\x0004IÝ S\x000c¨MÓBÔìié\x0004Ùá\x000bÒ½Mês\x0019V0Â5¯í\x00007\x0008g-u²ö\x001c´_,\x0012¥"XìÜÃ\¯£¥ò¦<4»Ë>×yrkôp,\x001bÜ¨<69ûùc"`s\x00026OÁ{QuÎÍ\x0016~¢f\x001e\x0018~×Ýã\x001d.\x0007\x0004\x0007!Î¹Éb\x0013ÎT\x0019=\x0006p×2\x0018'ª
uÄFßÝÙ¤R\x0000Ò<\\x001eÖ\x0006~Pâ\x001f®ç ¬\x000e¡-À¹Ã1[uT\x000f\x0013 PDFSÈ\x0008TM\x0005ððP\x0008ôù\x001913%â»\x0005$5È]Ýàµ\x0003<¹ûèIuK0Öæ_ÔácÅ0Zò\x0010>ÄõdÏ¤\x0016,hOÛ\x000e\x001eµ`ÄA½d¢Z0¾ßËöF¢$=²´ô6\x0019Îtûô\x0005]åG<$Í\x000f'ð\x0005«â
i\x001c\x0004^IàñU\x0019°\x00081Ú¹\x0005#ò\x001a\
ßÉÔ¹]ÕàE:qEÜe
Ã¨r\x0005ãÚ|,O¢%ØãÐÓ´\x0011âö\x000fÍ6:\x0019«F7£f\x0005u©lßC\x0018»¸K¤ö|0\x0016\x0000\x0012Ü\x000cÓ¡xGæÌÀeGèG\x000eTF~7Ktæ4
¦Þ\x0014\x0019\x001e\x001bTOEÙ \x001fê¾ýäÊämÉ=ä\x0012×q\x000c	³\x0004Æ½\x0015#H¬P\x0015lg±\x0017¼LpcúidÍPk³heèa\x0008òú\x001b\x0011±æ®æÖe[´k`0«,"UÒÔãDà
\x0019XvÇ\x001bÃ\x001fI}Sl/%FS \x001fè¿\x0017vÑðb®\x0005ÈË#\x0013ÐÀMÓe£\x001f\x0018¡,@¢\x0015½
XÎl¯ÄAÌ_O­4iRºªÎ¼5é-±Á«\x0002jèÁsT¦@\x000eô&\x0010HÕ\x0002êF1?4i¥Â\x001f«©«p=ÜTjï?
ÿ*¡\x001c\x00121\x0010öú,.z3¶#\x0008&~B\x0013Q£6â\Y\x0004«ÀRÅ°:m*LoZ&èWGå«ON\x0004X­<_H7-I²wÎ+¨\x0007\x001b&?*ÄQíÖ±è\x0019$B/¥t§\x000c
õz¡0
(à)Dß¨x[r<÷c[Ëv	FPm~\x0013t¨0.µ\x0018_8q ký\/YI(\x0007¢È?4Bs2\x0003k8^À¦Q_w\x0014j\x00199e£ÑúªÐûÌ}À\x000e+ðå7X Ri¤A\x0007Íw\x0016á2(Éx&pf$,¦O\x0000µÑ3OìT\x0002ú\x0008µG?¯ Sè ÏU£D\x00182;s·í"àÞMÝ#À\x0006H#È\x0018Ï *~¸\x0013ÍQU>\x000b\x0018ÂÏV\x001a±F×\x001bÇ\x0002ÕL¨g;Ü\x001c©kMç\x0018\x001dûL°:õç°w£x#lá²ò×Büq6DâæàyW#\x0018Ý<\x0015sW
¥jâ\x000cØÆè¹þÆt
þ)ÞâÞª\x0002RÇC*v|FK\x001b£ûIÞ\x0012×D\x001fÒJ7] ë¡
Äç\x00171²\x000f\x001aÝ¾Ó»×¸]\x001f/FV©UâZ\x0006ù|1²½\x0011Ù}êàEå_qPÊº®\x0001»mXÆ;âKëÎäYM¡Ô|\x0010¶*7ÇÏi+Ñ5ð§\x0012tf²2÷¹AH \x0006ª\x0005«GO¾¨\x0004G\x0003ßèd\x0016\x0016~§\x0012X\x0016W«'sj&B/S\x0016íI*\x0003§n\x0002Ü£S¬\x0005,âLgP·ã:±½\x0007Î¤¸<5æ
®\x001bÈ)å8\x0001g(Ê\x000e(Ã¸õ1(áuîÝ a­µ\x0019\x0000ú\x001c¹\x0013%\x0007%\x0019^^\x001düÕN×TÂ#ñ\x0004*N]0á,
\x001a­\x0015êWÕ(z\x000b\×
Åú%n¹5ª\x0019ò\x0014Øé;á¬£¼²5hÚNàjöNftÎ9Q×îF\x001d\x0013È½q¾Úr«îf\x000fFE\x00084\x000fô$jö'D\x0007
/à\x0017é\x0007LnÖDÿªÑ\x001dÈ^\x000e\x000bÛ?VÖ!3L5
ÊW±ý\x0018£aGF\x0011¹1ªí£æ«ÝÆ¡\x001ed¶ë«½\x0015}E;*ì:±÷4Ì«UY¨3âv×Ó¶!tìkX4Z\x0010dCÍQuÒR;ÚÈº°±bæyÚáÐ: W®xä\x000eùµE\x0004ÎÑJ¿æùé\x0004ûH;T}h\x0004LÂÇOß«Q\x0014×0Lp'\x0006\x00015Ù4XàbT[\x0002R³p5\x0008ú4ÐWD1Oùû~¦ÞRê;gÿÜï¼²\x0018Ø9a÷û¡íR\x000e6¬\x0002Û
£K«`¤tÜ¼Ñ{£ë<DÒÛ£Éº=/^eô/\x0017(\x0001 Gj7R\x000e\x0008¢´¤y
\x0005í5À17NÊ¦Ì!:1Ó¬\x0008 iûöIÉÉ
ç:ìûp\x00102\x0000%Óºea°q *ò¶ÎN¶oæM|ôÙ=w\x0005|Åù&\x0017,!Ç®`	ê\x0019\x0004ã/*ÕÜ\:	
¢(ádä>kîeS)\x0018$Ö·\x0012Ì\x0013Æ³=M\x000e\x0018O\^Zo\x001eöâ\x0000¿U\x001b\x00135B\x0013o÷ã\\x0012ÈcÙÔ=ºø½
¼Õ8Àé{\x0011\x0002kp|(
íOé´[±!@|\x0007<
·}h¸?®\x0012­D<ß{Q\x000fØcË!± P^Óp;ÊÖÂÄ\x001e\x0001"àv
 á±Õí\x0016I¥
MËd\x0014OàÖÃ\x0004Íw¡(Nil\x0008zk\x001d'
D¢	Ò\x0013iYD/Þ<Y\x0014ÊÚÑ{9ÐÛ\x001f¤~üK5Õ2fL	y\x0002©\x001a\x0014ù\x0018!£K¼ñÀSr(-4?\x001e\x0013ÇeHß¦»\x0006ÔOX/\x00038\x0000u²u\x001fÅ\x0007µ\x0007¯0²-ûÈqJF\x0015ºàc<\x0007È+Lÿî¶Äû,\x001df\x000cTUJù°\x000b\x001b1Pª¯ %¥GÏñÍ\x0003«?\x0003\x0007\x0010ÊA×O\x0013ÇÒZôÛºêO×ôà\x0010YðÓw\x0004\x0010o×êÙ\x0014wqüÀ3fr[Á]¼¸\x0001íà&Ö6&Ï¢\x0002«\x001ekæ\x0007Ï¡\x0010í;U6O\x0012=Là).\x0013Å)*!èmÈa£KÿI\x001c³¦j
ÑCâ%·µ'`¡\x000fì"5\x000c>·÷\x0005{!N\x000b]1³}JÇPóÚ"Uè\x0017P·Ñ\x0013\x001d\x001e&Ü;zÚoÕ©A¡Ê*ìÚ\x001eTµ\x0001Ä\x001cÃ° _d×½ä¦¶\x0007Ü:ºè<AÝ\x0011Ì%J È\x0001:Îâu\x0010`pz\x0006÷
÷ÿ°÷n»$IzÞ\x0013ô;äåÐ$ý| ®\x0006%A\x0018 ¤\x001bî\x0006­d\x00013àTÏ §Þ^þýæn\x001eµVf	Ú$H\x0002Õi;"V\x001fÌÍþ\x00032³®[°ò\x001eXê\x001but;`#>3!ö +¹o48#ßzzE¸
ÿfûMìx­ÈkÍ³¦\x0019%ýRüíq®ãcÇj³î\
X¥¯æ|\x0003¹ó\x0012eAÈDE²w~·ö1ø¨ïñpþö:\x001a5Ú\x000cæ#OæíE©/¼	ùæ\x000cð2èÛ3Í\x0018Rª0ry\x0013ôbÿÎ oÎ\x0000?Þ>¬vÐa0ó ±îóàî\x0011oúõm\x000cÐKr|Ø\x001d&)ø\x0004-¯7=[¨ ®õñîì\x0007<³áI\x0006¦ãÝe@|¶¤ñà£0tº(²_î¶ú¢_à¦ÈÛÎê¤-:Y\£õ/\x001c_¿²s(¼cûMÚ åéx+\x0010Ø9Ð)ó]ì\x001cÐn0\x001dýWAÛÎ\x00016ógë Ê Á\x000bµØ9l\x001aÂð\x0006h÷úÒe\x0004$ó¬ý£\x0012å_D{®0S\x0013Ó¾S\x0004IBíö&U²sE,bí	çÀ++¶#\x001cxîD\x000fq.§Pn\x000epÐ³=ðoFÍvsXËN×÷2D\x0014#\x0008³î[½
\x0012:\x00084&\x000cð	\x0019tö\x0007éü\x0018éwQ

Ú¾~Ì\x001cPÏñ}Ì\x001cÈäÓá6Hºx9`*ZÏèwÓàèÓY_òrÈñ¹ÐØ£\x001aM¢q @2¦~è]­{4*y[ÈË\x0001·º=Üz³9¨8åm:¼\x001c0\x001d×\x0014æÄ°\x0012I4e§Ë\x001bÊË¡`Ýl3í	ù\x001dä\x001eO\x0008eW*ëìÈ&¶µ]6	x{\x0010çìu?S¾\x001dÔäÊºþP_\x0007Á\x001a\x0001Ç·	|z6*öâég(|Íänk]¸n\x001ddgsé.W`¸åùÙ·$¡Ë=q®§,D\x001c=v\x0018ïQv#´6à5
W ¬wnð£Å¦¼\x0002Kë:x­UNfîÔÀÇÁ9·íL4Xd¬\x00109Ó"mg·J\x0017\x001cãô(!VómåÐèj÷·1"¼¡¢gg1=\x0010\x001aO+¾o)\x0008oîp¦\x000fhzM9|MÁD÷og\x000e \x001avõqP¾¤5#Ãú7!\x0019§ZN¢jÅ½\x000eÂÊ	î>W''8g§ÀÊ\x0001ªe?\x0003:«åÁ\x0008×³\x0012Ï\x0011¡*ï\x0006´Y9àÄCy7V·\x0003GçüvÔC][ÕÜK"=2\x001cýò²dÁ@\x001f!í¦¾N;8{që\x0019²ß\x000f¾ÇÅ\x001b_^µE\x001fhÞWþkÈ\î -c\x000c¡­ç)\x001fR\x0010ðIÁ\x0010Ù0¤\x0001íºÞÒ\x0002ÊîP×e
ÎÜ\x0008£]¥s¬\x001chÓB±¯¢:N\x000e\x001d"IëûF\x0005öð\x0010øýiàJ\x000e9%)\x0004Õ*»ú«1[­
\x000b RÑ(\x0015vÐ9°
ÎzIù\x0007ôd
ÞJ\x0012Á¦%ÏÒÃãã×\x0018\x001e*ÔÍêF]=ÛW%§y\x0018óÒZÛæer0I¤gÌÛDí#ý½hÁ4ôÆÎU\x0002Õ9\x0003õ1/ì\x00014X\x0004\x0002¼\x0006È¦h^ÕÄúg-#\x001b±g\x001fÐÔõ\x0012Ý\x0011c­ßôÃÑQ>·cÁ M&&"æ%(·w\x001dB¯S\x0012\x0016Õ,¼Àu÷fm7\x0004ÆF?¥\x000f\x0003í7'pqÄ	pÌÍB§SÖ+t]\x000f\x000b\x000c¯\x001aÜ\x001f5Â\x0014\x0012d4\x0019.Ò:\x001c\x0011\x0011jªÇHfJ\x0000¿VÏV¾45\x0001²ý&N-©÷\x0017HÁÃU3$\x000e­}\x0006ÿÙSt\x0002ÎoêrÎ¡\x0012sCº¬`¦½ÆÙ\x000fç¿¸sKèq\x001cÉÞvÈ/\x000eP3º£Í÷ÅÇ@¼\x000b1\x000e ¿K§ë\x0006¢~ePaÛ²³Àþ\\x0007#lùuÐÏïÄí\x0003e\x0008À};¼\x0012\x000f\úw\x0006}s»\x001f?øÇ1Kå\x0000Q¨ËûV\x0001¶nS½¥ìS\x0008z¬/vtòaª¡[\x000fÀd@Ç2\x0008Ëá\x001d\x0005\x0008(ð.]·bØ,ä¼Â®DÂ\x000bck!ù3j©\x0000ôà±Íì;­ÚuÓUð,Jxnç*\x0018I¬Í\x000f5eHÞ	Õ\x0001
Ñ\x001cQ×\x0016ö²èrd=×ÁJ\x0001?Û#\x0000ÁÛal\x0002ÖçJ\x0019\x0015­@\x0007~ L}f$Ý	
f\x0015mÌúÚ\x001b:$#ì\x000f©~¾ª ¢I¿\x000eÂ\x0016e\x0014yßñ«*ÅIÈ»ù<KÀÙ¤TÒGxÐC\x0017¡"¹«Æ_Ø°
	,5Ôw×¡\x0019â=»AéE-\x000e\x0000¥}\x0008pÐ9½û[\x0010õ'
\x001båY	ßF`¢	¹=YVLWy\x0008G{{k\x0007C5vÌ2OHï\x001e¤Ì\x0008¡°RF(i¬'B'\x0001ú¾\x0013Ú;À£Öò\x001e\x0007\x0000\x001f,\x0013ö\x0011\x0010^`³Xýi2 0 NbøâÖÆ
eÕqnÅ
<\x0010X´
uÅ½
ORâÏ³f\x0006ÒÐ&Ü#\x0008kã¼Ë¨@_]û\x0008ý#]\x0005ë\x000eJj7¤\x000ci¶¦­ß\x001f\x0002Ù${¶£\x0013D\x0013\x000eUMD\x0018ëuÙ\x0008å\x0005\x0006¸ô¤ó	ÓLÜYB¦\x001a%ÃÌæ-\x0008Ï<~\x0019\x0004É/P±ë\x0001C!¢Ôäß
V5¸Í¢¨b\x0016^½¼\x0008±[qþöýøâ7äg\x000bAó¿Âx¶1Ò3"KëØ£ 
ü\x0014ÂÁy\x001cÐd\x0010×Ïj\x0001TÕ¯2OXkT[¼\x001e4pBløh7d=?/ÝôÀ2\x0003KVDù}rÆhÏgâÇÐNÀ\x0001\x000fæ´Z¯µïu  u[­÷sB\x0004'Ã¨[­|[zò©)\x001cImÖ­Vm\x0013Í
2äÑÏ@¨~}~iÛÓ0¹\x000bZ"Æõ¤ù\x0001\x001cp\x0007S¬2u¾³¸ÑÏa\x000f\x000böÉ#evr¤ÃÛYËmQ"?ôêpkÀÉÀÔ«\CÅ
Õ¾\x0015Uâõ<µóvÐÐp³'æÇ°$¯üÇ÷¡\x000e\x000c¬LSL!Ùé°PÖ´îw?«\x0013KlçýÕ\x0004N\x0003åÚO\x00106Ì<ðL{é\x0002Ù2@®Ï\x001b°+\x0005úOßÛ:Ù{ÌòæÇûëÇªñ\x0017u
!P"èzÞ\x0010s6B\x0013*{;\x0016»öb¬ªÏkD\x0000Ï¯²_4í\x0017ÊýÎ/C!'A¬A×ÀÒS].g|±Q¢ü¡í"C@pàY¾W¯\x0005Z\x0014lá\x000eMþHGíz
,1\x0002A75Úqm¯øéã\x000b
ªFyß*3ïh6f\x001f§´Ð¦÷ýÈ4@ö³÷yþ©\wæÀnm¬'D\x0012\x0016\x001c`·®lwê\x0004\x001aË¹\x0015î\x0014\x0014À~\x0013ù]Uyôäx\x0014´m¶Ï¼ùNØ±lå?æG¦ÀC&ÕØÎZ:Ñ¡¡5Wû\x001e7hP
X§¥¶pu\x0016Výô¹	\x0008u»L²&#:MYf¯p\x0018n¬\x0004ð]ß@Ï %5ý§\x0003HCÕqÆh@Ó·Ô^\x0005×?Ï­ªÎvA\x0005|"`rTh¾	sBC\x0000ù½\x00140ðQVßÇxý¦õøÓ=nTP×Û87\x001axJ¦Ý*¨òýÆúmÆ­ïËë£ë&Ø|õô\x0003wp,¼«çfHWBây§\x001f³(^Z\x0005\x0019e®ñm\x0013æ\x0007_ê§\x000f\x0015¾¯\x0007\x0019à ó¸»0ÙìâW\x0005QlB¶¡wß´¨D@(Ñ6	Üâ\x0011ó©ÇºtþÜ¤fi!`+¥<}?Z/8`ï]Ï&±	f\x000e
§\x0014Ö\x0011µT\x0006-h*Ìt\x001f\x0018Ì$h\x001eö4ë\x0007M|å!|zº¸rg\x0010\x0010Õ\x0012«\x0006á\x0003\x0011{üÑÏwÏG\x0000÷Ò\x000fl¬:+b[ðl'kcm\x0014RÙp¡|\x0004ÿ^0
d}·õè!Ðù*vNÞA¼q\x0005ã\GtGôR=\x0017Ä\x0014\x0018\x0018æ\x000e)MÄÏxü!£°pl±e\x0017/xdÀVún>Ù×ÄéY,Ûf¿þk@´mQ9fL\x0019l6Éb÷\x00060·²âÏ\x000c\x0019jCyo³Ü

)0*\x001f;´¾Äï\x001b"´g\x0001xÌ(?ÛªHY#!ægÏB@uÔyÌ#\x0014\x001a\x001d©\x000cú\x000cmáÓ~ÅQú²\x0007¥¨l\x0007ù\x0016«=\x000c3qq<ãÂg\x001bIw\x0002É\x0006Mv QÑO{\x000c
eEÓ®Ã»ÉÔrb,¤ ú\x0000ù1û\x0016¼\x0016Ò.Bëþ¯ Äb:\x0019M~\x001d\x001cÓj\x0016\x000eÖ\x0006cáz\x0001a\x0005ðd¿[¤\x001bå^Í\x001f¦Á\\x000fÓ\x001fú8âºí\x0017?\x0007\x000c\x0015³b:¬ó\x0002Eùý,\(åàctÒmV\x0007TõÃ9êÒ:|7M½\x001ei\x001cÀÎçS	4pH·cÏ5\x0007\x000fÖM?ýéc\x0013«%VTgàæ;\x0008ûO²`Â±
@Ýªe¼çóµ!Ì<£
gû?¢Âíù½Ìc{=!+³bÕïÑ_t¤GÐÔ±:\x000c¹4,,ÎÓÀâÍ¬\x000f{ÉücÒ,öÍï!\x0004Í\x001d¢q:`9ù\x0001*a\O\x0013\x000fBS/ÕWÁÊP¦éX÷uÔ¨BzÔ7ý\x0015¬SýØ³8Ò\x0003ª\x0008\x0005ùÒT\x0011nÃõùü$\x001c\x0018\x0003I#C\x001f
"%ý¡\x0001}[&\x001cÁ×m%
\x001c=Ú\x001e_ëP6ih'O/D ½é^W4ÄP>ÇÀ5 Æ´>Ã\ÃÞnÕ\x0010FÃçûV@¦ÉÊAfö¡¼6ùæk\x000c8©+\x0019+\x0010ú6btø \x0005Åj7ìßÔç\x001a/qM£á9'nUÒû{»úþàûÐ=\x001f\x0012%+Hýã3LNNF\x000b»oª/\x0019r
8]ª\x0002æRI \x0001ø¼«\x000e+ÖOÖ¸ð	b¿ù¬+µ\x0006a.e÷»ºË%³ÃË\x0019fß\x001dG¸§æ¥\x0018\x001dB]f\x0006è'²±;#]»P¦kFÞ\x0003uÑg\ \x001fØy´ÓncF °VÆæÙ\x0005õ´5¾×2ZAÃQ^Dâ< ä0Ò\x0018
\x00030#RñQ*Á349úa[\x0011MxßÉu:z*cn\x001fÔ^=O<K\x0010SVÍR\x000b¡ø2T÷\x00072¶êHcw7×æè\x0013bå:hx!bjWY£Â\öI\x0005ê\x001dûÍ|\WãÀ\x000c\x0000Ô'\x0015çg\x0010ºõÐB\x0011ôl\x0018£g(è2Æ¦Ó1/\x0007\x0018É7#lmµ;Ä\x001dô­Ó-ÆÀü86\x000ec\x0016`:ÚÙáh=|ð6)ÁÖMî\x001b²ÂE{P\x0015Xr+aÀ²äC±WúùÊÙõåKè,ÐÄ=#O$s\x000cÜßÔ7'f¾ù&^dÚ×\x0001ÕíÃôsnF\x001b\>¢\x00162È#*V¨Ù÷WÕø#í×\x0003,Ý4Üd\x001c\x0004:½Ñ\x0006\x0016MÌÛFóý´\x0001\x0007Òê\x000e	bl÷Y?/Õ£È+têr\x0013\x0010O;_ººTÇ\x000b\x0018W\x000f²¾\x0016ý:_EÙ\x001d;¤(·ìõÖÏ\x001f!_6·9(a^\x0013<¾»\x000eJ'kÆÝÆÆvÚ²CÈä\x001aJ0í\x001eBÖºÁà\x001agbf XêôÛ`@P\x0015yÿ(:\x0016'5rÖÉh²å\x0006(¥{vW'\x0001é~¾\x0014ø©Lç°û§0\x001bÞÐ1\x001a$þÈ*r ß\x0012öÊöýåú£ âÞ\x001dòZÇPBÅIÐ7£\x001c'\x0014\x001eí\x000e8=7+ªÞÄýL½\x001f£ÍÊ&MÉ·(ÿu£»®\x0010d{Ñ\x001f*>¼Ö$×]cóð«AR)Ûo\x0011qþàLìV\x001cn ¸µQü\x0000¼\x001bn\x000fv'Lw`ÉÖMDe	äxÈ©µTåLÔìò¸\x000bôL¶ÖhÇsH³¼$MU=#üÛö@	""8çûÜÓ§ø\x0011çG±°o»O\Ð&=Xz½\x001cù±öÞP\x0004p¼8êaò£NØ0æ8w"áÊòÜ8£R÷:gÝË&²^¨X\x0011Øho"ñJ:ófT¶X}´Oü_8?Öõ\x0000\x00020n%Ä\x0015Q=ÃÈ\x0017¦z\x0010\x0006Kûý¡NSsyÌr¨-\x0003ð=_1çsøQ\x001dò%ð\x0007côC9\x001f\x0005ÛÀ\x0007ôªr®Ç .K$Ñùu\x0007QQîéîZÈ@ÖIf>X:\x0003\x0011êE\x0012R*ì\x001e:9Uþ|£\x0011Ûn×h\x0002þÇ-Ú*\x0017\x0005Û¼v\x0016l»}¡\x001aX,iÐ®AÙ«	@ò<«ìN$>À²ºWÆ*-­16\x0007¦ÐYé5ÝZ\x001e}·\x0006>Ã~R¡\x000b*õ{|\x0000µ]å\x0012ü&\x0012Ù-\x0018Â/x\x0017\x0004<6\x0000ûÚ·jr¸H³øüÄÛ\x001aÊc\x0016²¦TFSZ¼¨.Ñ-ÎRßØo\x0012	'Ô9O\x0010[Ä«|¨\x00002ljº¹_Êð(Op°\x0014ÒXÇ»NH\"b|ûN\x001d÷8Ä)Wª²¬mXVìN<WîO¿w
kn®ÉH\x000e¨õEÖEÒ¹\x000f\x0013¿Há\x000c\x0008lWù¡úÉª¯E\x000bei_»ã\x0010»ÜðZ©³'fråü"µiËð%g°U­»~êþN0%\x0010#Ï¾d\x0007\x0006ÃÊ-ò~\d}ÑA§ë\x0007+\x0005\x0018ç;C¼2ó-ç\x0017Î¾\x000bÜi}6ì¶C÷c\x0001\x0005Eét>ÓZ50ô¹\x0005\x0014ÔYdÊ\x001bl>ãµ0Àhó«ÀáeúX\x0007>ðëWøÔ]«\x000c\x0007!ø¬Bh Rw\x000c^¦\x0002àD\x0002"Á
AÈ\x0000#uÇ?Ð1f~eSk$rv¥mì-.T_\x001b	ÔÜL2.wuÏ\x0012QßEJx¼\x001czZ(¯Ð\x001c97Zs@Ê\x0015ýH\x0004r~be\x0008#ÏgP\x0001­a©íPfõ\x0001Ò²'T
J[öó-.¹kêPí:«5\x0005Bëð Yì%` Û^ E\x0004ôª\x0005ô{klëêÕÿô{\x0016â·Å*Ü:µÝçK\x000e@òsÞð6ÀÔ3Ã¼K~`a
ÃTàÛâ\x0014÷ê§ElzÁÍÍLòY\x0000³R\x0008\x0019N{A#\x0019Å´Ò\x0019Ú¶¢\x000fÔ_(.¬Cá³¨È ¨|Ì2	Áä´\x0002âÊ\x001bUP-!Û\x000cá\x0004\x0001Í\x000cÉh3XÑ\x000cý-§'%¨\x0004Ã¡ð¼ qÁÀn¦\x001f·B \x0013ÅÇy0g\x0010Ë;êmÍJ©\x0004aP6QºNJASvë¸($HB<Ð\x0014~\x001dÂ f=4\x001bÖ71\x0000'AÓh½\x000693°b¢]ÔwH\x0013iÍûl?
m¢õÕYÇ	i°ySß[/ÐWÎ~Íy}p\x0015\x0011A\x001bv£\x0006ü½°\x000e¿
Bk{®¡¿\x000b!3È6Töoz\x0015¦\x0014=SÞ·ªØ^¯9»K\x000c\x0003z%\x0008¸ÑX¯ Ù·KÕ\x001aV*ªb\x0017Ò¾\x0011{Äé\x0002LXà×\x001a²B,jaÍ'&ß¤ý`\x001c7!È{)\x0003é}«\x0017A2(ä\x0014WöG«*Ã[mÀ=ÖW(ªð«ÖØ\x0018r\x000b}Àf\x0002û(Êý¡r\x000c<\x001c"?\x000cÈQ }Ðï\x0002EäO¼àf1\x0018'â\x0016TÒÛ½UÅîÒàq\x0005Ð«ÉAEtz\x0011wB¸W×\x0001>\x001cÃö Ñ\x0011\x0005Ñ2¤®=
µ I«{\x0011Pf\x000eÏÙ¦Ô
ZçN4äzÊgÅ¸oÐ\x0007m¶N ee¬wáª*Piª\x000e*Åj\x0000ò»¶I\x001e%t\x0007rFàBØØyhedh½\x0008ÀÓ\x0001?JÉ`'ÍòóóUâ÷-32ã\x0011Î§úÁRû¡¥~~\x0018\x001e\x000eò\x0017ï·SvÆúÌõ\x0000qjaûóVà¹{§b?BvèôuM3ê*²\x0010a\x001dQh
~²2#-L\x0001\x000eÚx%\x0015\x0010-ñÆð\x001eXù)ý\x0013û¤2 ÷vÇ;\Þu°uTG\x001fÙfû¨¹­	å¬]URq\x001dßwÏ\x0001qç¨­ö\x0012\x0018Cc©÷qºf\x001dª8ë»Úz\¤ßIó-À\x0017ìZ:»\x000cF·k'jáB	PÒCè¹í-DÒ\î½4\x000cÜjÒÞÏ^D¬l;	éË ,\x0013¸\x0016Î,X/ýþpó¥¢f1Î¾7&@^7\x0011ß\x001f8\x001f{ê¬\x0008\x0010R¡WåÉN_+\x0013À!S¢¾{òH7é\x0004*32
a\x0014J©ëvÿVöMë8Ï\x001d>ð:¨ì\x0007S$¹gPùÿ§}+Èàr½ÌIuè¶Ì!±º¶\
lwñn@2qV\x0008v)Ê®öoxåúÃZ­N_(æ=½Î'wa\x0016.E:\x0015+ "ûCu2v¯Òã-\x000cúh*"¥®xÈàÚ²\x0004Ü©Ãþ>õ`9Ù|Ë!\x001b4\x00022Ê\x0017S<?»v\x0012<V«w!k\x000cstø\x0014}ùÃ ð&"\x0019ÁnEÑ1q\x0018KÞÀ@1F\x0017ÕtÞ\x001dà!\x001d±øB\x0000Ø\x0005\x0002k6MQK
\x0007\x0014hï\x000ed7;m|\x0014Bø­âÀ·ty4(b}Y²°%\x0012\x0001oSa8	Z¯\x0012 â"gÂíXÛ^y\x000f!ê2ûn\x0017idi\x0019qß\x000fôu¡Ôà/P3Ì=3àG± 4ÎÃ§p¶\x0011CDï&6Á%Â£\x000f\x0013\x001eöo6ð¨Ã OXoÍ¨@kÝ\x001b÷X«9,D\x001aþ÷y\x00110¤ÁöwRµ\x001d)ó«#U\x001f@\x0004ûK®Õ2Hº ùºµÖA@Õú®\x001aÁj	"dìu®¦ö{ÐWZ\x0011ÿa¥áÃñDd&¸)L\x00050\x0011)K·öèýãå(E½ýêÄGT\x001d3³Kc%\x0014LÈO¯\x000eb¯¹âÝóÛ Z0wrÒI\x0018d/û\x0010ËØé0ª.~´ýö2À	¤³Ú\x001c¾^$1J}Ç\x001f¬z\x001fÕ\x000b{e&°¨qô¢G¦ÄKÙá×½\x001ae\x0019µí%IÌJ`²U÷ à(±&Hò\x0002LQ\x0014ªlß
ú\x000c\x0014æ-\x001dKÂ\x0010«³î¡¶\x0010+Ëîm#]û±½ÂÉom]\x0010÷îÕs){¥ÛGì«D\x0005\x000b-	\x0005âlÍÒniªJ@L\x0012÷öÍ)I\x0018IÍ³\x0017L\x001bíSS°=×»k[>Ì
ïhÇ²uîQ±\x001e¥ <)nÛp\x0012!ýº/#vì<\x001aH\x000c\x00159`YY\x0008ê9 iâ|´Îjl­P  X©þn\x0008,d{¢x\x0004Ò¢äzñÒ-\x001aû7}D|h/¾Ð.\x0010Ø(\x001e
M&D\x0004«2Û\x001e/b\x0000ö3Quª}6uh\x000bùf&ë\x0017;\x0004S¸"\x0014\x001f/¨¢ÉÕëÞ¦Ð¨Áe'ÝÁ\x0005§¡Á(KH=<û¡3Ô×GZ\x0012µÄ\x0013(>¾õ6äC?¬d\x000b2ûÄP.\x0005\x0000$E¦©²\x001e&z©\x000fe¨\x001a1V?AA ¹pL\x0008T¤FgüÝ¦§Þ )?êØh¢ty¢¾	Y÷U\x0016»ÍAûÀ'¶&ó\x0007\x0013ÜãHJÃc
endstream
endobj
91 0 obj
<</Length 65536>>stream
¶=¬!(]Ðz7hi27Õ6÷ëAT\x000cÆF\x000fpb`(7\x0001mK_£-\x0006J2c\x001bRZé¸ëÅ·\x0011\x0012ªåà¾kj/ÛáÊG\x001dég\x000b\x0012Öÿ1ÞÓ=îX7|\x0005aÚTÌ÷\x00035\x0019:ÒCÓ\x0013­ÕO¦MiH)³\x0003\]\x0004u"\x0004k÷µ±#¸x¡ÁN5ÌàýÐÈo ·g\x0005}>\x0017\x0019BÖ7`mzæZ«¹#ÖºD=¨õ[G A\x0019èl;±sã\x0007»a@ÂÐNC£Ù\x00133m*'2Oîè	\x00003\x001c\x0014)oí\x0011òÅÞß\x0000 ×@×7×Á¢\x001câ~'D_g\x0012É%CÃ{\x001d²\x0004\x001e3(
[ý6\x0008·Fì_\x0006r7g\x001f\x000cÏod%8ë¥p°F\x0005cD±yB\x0008\x0004¶â9öäWEÌÇ½¼¡\x001dP}:\x0008aU¬6\x001d~2	aù·,6
¶ÝÑ8åf\x000cuÛØwÒ\x000e³è¨¯\x000cÑ§\x0002:©{î\x0015\x001féX3ÒûÏH©¦ÀÅÚ*{ðn;l?°l©u\x0012÷Ø\x000eYÖ)\x0002èY­±\x0006ZòåzbÙPÅZ\x0002ïBÖ@ç\x0012|ø¸w\x0017h\x000eQo\x001e_AùIk+Z14¨öÇv\x001b¸	o"\x000eÝ\x001a\x0014\x000e'\x0006°bµ\x0019ÎÆm\x001f \x0008ÀA`úg\x000eÂå¦zó%ôqÒ9Ë\x0012´\x001c[Gô2Ã 
ÞôvÒ\x0005\x0015>ôÌ¼ÇuJ7\x0019(îÈ\x0007ê3÷´z\x0011T\x0018ÆøB7»N7í1	Vr\x0002ý3Ð¯~\x0014rj\x0018>þ"Äî\x0004Ñ\x0010NL\x0018åÍe¦\x00146\x0004öCtDú\x0016´-\\x0013·:qÓÒY\x0000µ­GNÅh
\x0004­WñFÞ4\x0001|d\x001d\x0018Q\x001c\x0008.$¿U
\x000cI\x0012aBÀ\x00130\x001bï~FM\x001cug´\x001d¹Õñ·Ö1ùùÎ\x001bÄw\x00020£ë0Ã0%\x000f7 º!úÈ'$¢â¤\x0016µ?
	3©,+\x0008ñ`yMøO\x00078Éô=òºíÄ%l\x001bd¨.¾þdH7Å""V9r[÷W\x000c
úlÙ?
õ%ª¯­Þ&0\!ÙÞÚ\x0018\x001d(
ÀT¥ôß\x0006±h'fäVÆÿ&H!ë\x0003SDDìã¢\x0008VÅaZ!Ø ;îCOÀ_ÕVV\x0002~?¹\x0004P:JÈÑ®B)¬¡x×æËI5\x0010ùCÉ\x0019\x000eYz\x0011b·ZG\x0015ÚÃåñæ:\x0001x\x0008\x0016`ÓGi¤e±Îõ\x001a¢xvHdÞ#0°ûÉs¨-²nR&ðãô\x001cJ£ígCþÓYÊ³v%\x001cúZ·_\x001dè6`õ^c\x0000yiÓdæùÝk: lº'ãh´\x0001¶Ïöjð\x0005¥WÂ=üg(±h÷ì\x00100¨®ÜV'`®®Ú\x0019[\x0016¸¬7ñ\x000fç\x0011k¸¡\²\x0002ÌQÁg¥\x0000²Ã\x0019nwe¬þ>er`HgÞ
ò\x0015\x0001«	¯5À|\·fK$ôN\ç\x001c\x0002©áZ×ÛÎ)¾¿Å|ÔÙ`GÃ¢³ø¾I'r½:°DÚÍ\x0006ëF5ªE¯*Q²ÆÃÏjÐã³íò¶=ï EAï©À\S6oA\x001c\x001cVAÊÙ\ºKDlÔËHÂ~:ekÏªÙQæ(eÁ"ë°\x001e\x0011Í»\x001aE¦ôqþ`F­µ\x000eq>ÞxsõR=ØQR\x00017ý·Â2\x0006åMD\x0007ã¬lY²!î;Á\x0002DI®zú\kZí2ìsAÍQ?	¢ÁñGk(\x000fS×Ì\x0014\x001a]\x001f BIH\x0008èí±4#ÕÅÚ>çR´\x0012ªü5õfp[@
)ø"\x0001d#»\x0006\x0006R,|sò\x0010ûN+=³ÅñòÉ\x001f1?¿¡\x0000\x00180ÑÑ6ô6
0¤ê¨æí\x001a6m½á\x0002eð"Ah\x0014É2Ø\x0002J20ïø,\x0017Q\x0000-ûÝ\x0004
\x001axu>H)\x0001é¢h ]\x0004Ý\x0000¤\x0013|ÖE\x001c(°VûÞ\x0011%´F.ã©h\x001cø\x0003Ò\x001e/>²Ö»CÏ÷6	&J /¢]\x0006×\x0005R\x0007 gå\x0017 ý{ÞÏ\x0008ìt«½4á\x0001üõýðôý|»Ìõ®¤\x0003eÃý\x001ai'\x0008\x000f ;§¹¾ñbÈ
×¨JÇ\x0004R4­ê09\x0006ÅúI\x0012iN\x001by\x001eLº¬q¶6æ.úÁÍä\x001fuMÀ\x0006Mºõ)<ê_G×$\x0014tyÊëpÞ)ôFZ¾!~oÙÖµ\x0004Ö#ëÚO¿gñûØêzA\x0010\x000c!z\M\x0008\x0006	Hr\x0014§µa\x001a æ\x0001Ò½AÀ·Vbi/LÇ¾¦\x0003Z;nÏI,_ûì ¶9!§zal²Fã\x000c\x001fÎx
ålïa*\x0001[\x000bm){ôðQ"õÕ¢B
\x0002| "²JÚÏ 
½,B	\x001a
æ\x0006Y­'.°Ë\x0008xfÒÅw¯â\x0017°¨O9³¥cWn!\x0011\x001b?i¥\x0013¢a
=Ü;asÏûÉ"\x0007{\x0015°ð\x0016o·áß°vÎ²÷¡õÈHòÔû$4zo#dåèã\x0019¦¯\x000c
Ò¬DÃJÖ\x000b$ËÝCxS°HwÈ1!{îx~Ô÷\x0007Î6T+\x0011	µpqs\x0005\x0005SlµZÞ\x001c?ºÉIâ*®\x0005\x0002\x001c~ñá®W\x0003È\x001b\x0018_å°ìàº\x00152\x0005
Üã©:_0´«Õµ6½|,2¼g^U2ÆºTÄ">1[-I\x0008\x001fuGB\x0018ÁË\x0001|ºHàG|¸×ArB£­°oÕ8Zð\x0018\x0007LÔm1E{éÓ~`Y»#»v®¬óz]ÃÚ\x0004%\x0000Ä4yî­è$VK&-$!Rên²é:@Îñd(ïBºTÍ;Ð ý«^\x0005i\x000eØæU»\x000e¹D·î÷\x000e¡\x0015\x0018Iéb\x001b¯-jJ\x000bð\x0010¨Ø2)]<æ)¡Èî×É\x0010ÊéÙ\x000b,¨e-óEuÔ\x001fÑ\x0019y\x0017"\x001adsëþU¯Ànw~g×u ©\x0007en¦Hf\x0018©\f{Ô$¡\x000f4ÂëÐX
@8\x001fÑÅÀ\x00165õÐ.J\x0003xÄÙÍ\x0005\x001dª ´çå³RxC|k\x0010¬ÂÜ\x001f
R,>C}a{ß¢\x000cÃüdä¡å2û³R\x0010²³ýEüâË\x0019U\x0017ÚA¨!0îç\x0010ÜC©¯Óz=À\x0010»'½N\x0011±\x0016û\x0012\x0019(H]r1Æly7\x0000J\x0003cÂ@Zé½ÓÐ(\x0013jk©q¿e°ø:8´b%3hÑnõùIÆ^¥Í\x0006ë\x0002Ý±Ê%ÃTÔÕ|«|+Q\x00197ügâ¤\x001f´¯@×¯ÉÅÉÖ·¥å¼¹Ö7,þñ"øq¢#öà·L,/\x0014W§\x001d¨õv\x0005!\x001c¬\x0011u×Ûõ\x0011\x0012â
ÁÖ\x001dy¨à4\x001dóýäöð°\x000fA¯<n­p^Aæ³òÊl\x0015\x0000¦\x000ca×\x001fy¹\x001aÿEÞó\x00086tt²¦*d{+F}\x0002\x0018ÓÈ;\x00027bØÇÞó\Û\x0015:\x0003±ûÒ\x000e¬/\x0010\x0019îÍK\x0002\x0003mÁå\x0008ÕªËDEó®$,\x001eWÍUÈ1>i6\x000c#üN \x001cÉ ãMj7\x0014íõMu«Ó¥\x0003aDäUüÚ7!¨\x0017h\x001eÏ½Z¼\x0008*\x0018\x0004¬©hZ[|\x0006\x0010üô«½\x0003\x0018\x0006åaò}B0ÔiØ{ß\x0002^1Ä\x000e[nÇgv·ýô\x0018ê!DgxK|\x0007
\x001ca\x001bJ«\x001eÒ0$KïBÊ:\x001d'±
©oha\x000c)Øu0DÅR!yÈJHU[³\x0005\x0012G\x0016¤²xBD?ÅêûSavG
Õ®ª\x0017h»\x0008?íÁÅ&ØÐ,ºP­éIb´Û­dM\x0018Z÷ª¸W>Ò'\x0000>Æþ¥"ÞN~»
ü>áuæË\x000fHÀ\°Ô\x0000¤¬Ëx\x0004'6nµ\x000e\x0011ò*c*J
¡¨\x0016èÕ.Ü±Ð,v\x001dÆ\x001a@ÃÞ\x001fO¼Ri%ì¸ÅQ`ºçzLÕÒ\x0019\x0014\x0018µ®õ#×ú(vU\x0016Ä¡b\x00172±rúýj=ÆrïV\x0013åAöîV¾ZE÷8ï\x000fú`FQï*hË¢B¢\x00133³a}Z|\x000cJpÜa)\x0008¶Q`´QaÊ, »ïRËúÇyòÎßï®\x001f·\x001c\x000fV\x0000\x000cáüw5I²6\x0002Ð¹¿Z\x0010ZÙ\x0012!¹d]¬Ì\x0001«i{\x001dú©\x001aWÈ?\x00162xsêÝ\x000c2
6\x00148\x001f>üÖÎÄ¨Ý
PQ\lùôg
Ø\x0018N\x0013$\x0004\x0011 t\x001fSôv@ä5îü6\x0004Û\x000cdãLñAä©ÈùÙ­P°\·Ï\x0005ûY&\x0004íÁ"ÇW!_ö;Ö\å]Ä7×QM½¶7×2($£\x0001¹÷²\x0006BÿPgÒ\x0017.¤:q\x0008û\x0005®ä^`¾b1´½\x0012]Ë"î\x0010\x000c7%ùa\x0013¦¾\x0002\x0016ÞâÈÒ\x0006½o\x0004\x0014\x001aÑ\x000br\x001dDa(pójCbàçÀ¹üVñ­~ñ})\x00150&öó3Âî\x0004Æ¹¸\x001bó \x00154L®\x001dëoy\x0007QJ@ReúaäBµJû¨0jÿvv7Ô\x0007Û¨'$´JýçVd\x0007LÍýúYXØâíÉP£EíØn4I\x0001a^]ÒÃWm\x001bB@¡î^n}0¶¦Ôäè³¾¼\x000e!ÂWàÞ|\x0015%È£&(|\x000bi\x0012P<±\x0017$ÈP×¼¦·«jÇÑPgaÏNæ\x001a3\x000c)Qúèq0~ÕzÕ¯2Q\x001fNu¯zDû\x0005¢'2Ó\x001c¯ìsviA±NÿV\x0014î*Tµq¾y .:ZÎÆ
|Ð»e\x0004 \x0005°JaÂ	\$Û¶g!5)4y\x0008\x0017¨´^úæ´ãS5×ä³\x0004WÀ]É{b±\x0001âOzÓ~`\x0011
!\x0007ø eõ{\x0008IôR(\x0000Ô³LÒM¬"\¨.TÏHãàRR\x0002Sù©©!¬\x0006ë'½ þÁ\ô¶Ò\x0018nÑÅVÜ³AZå\x0011]ß\\x000b3ÎDö8?)öü¥ õ°~;³W×?5?\x000bò\x001e"(áÒ÷\x00062Ô\x001c»\x001f
0IC\x0016åßÛÌèÇ¶³Dþ`Çû¸Í\x0015\x0018¸X°ÿ09Å¬\x0014Ö\x0018âî1¯(TÁ	\x00020\x0000Ø\x0004Nj²Ð¼r¬r\x000cò,\x000cHÃ\x001b\x001c+Ôô©eO`¾\x001cnw3:\x0014£\x0000ôSºª0dË¨,\x0001Ëó69}Ã5ëÀD+¤"àQºXÓI:P[\x000bçV¢á\x0008yÙXX\x000eÁâ3IHpìØ¢|å¹:¥rSòPe¦âY\x001eÌ*÷­JFDÞ´hÿHÅ ÂC£Ôë\x0015À½$³Ãb«\x0010g¯M±5ãH\x000b\x0007¬>ÈH.<\x000fyðäÐ\\x001cö\x0002	Bµkí\x0003ÑÛud¾ÈZÂÖÂÄse\x0016\x0010Ï+î\x0014ðeÎ¦Æñ)KKÆûÒH\ÑF7öleó\x001f¬Q% ¾ =;]~\x0007\x0014\x001d\x0013­\x0006ß:<R¡:â\x0013ÛÎ\x001c¶\x0014áS3=*L\x000bç7VÎèÊpÖ×²®r" `t2Xp®b\x001fÝ£õ7¹Ù¯B>µhqÙk'í\x00028×}+j£Hô¡àâu#\{ÖV\x001eìÅ	Y)\x0017R7\x0013±Ò÷7!r\x0015R+oo/bcUI?ª´Äo\x000cÙZ@½¦qL>é
R#¾\3úh^~~ÓÚJ\x0011
DâÐ0ðÐ.½MÎ\x0003`C\x001e$ÞB\x000e\x0016Ñp?ùJ$Mõz
,<ã¾Ó÷WÕ¾ÀØuO»pÆå\Ïh²Å\x000b\x000e
f`\x0000Oñ\x0004g"ô(÷ \x0007äâ27l\x0017ÑdÚ#C6Ö¯àiÙÚ;p¿JóÌ\x0007D\x001e'Ð/-/\x0019Þ£}Nv7ÎÀe¼\x0004³¦QU!rÏ\x00113 ù¢£8Ðçð\x0007W\x000f	|IsCmgì\x0007L Ñ¿1ÛÅ¦¯\x000f*&]\x001b'\x0008ñu²õyoGHæ6±¨\x00047¤ËoÝ\x0008b	z·E8ß\x0001MôqòïðÓïùX\x001fÚ3i2L¯\x0000Äznwb¬í\x001dÐp\x0011*ðM\x0010öÒ¨÷2\x0005	èÙIIþJ,°#­ï&£í#
´ÏA@@þ)$Ñ­ÈjÔÈÌ\x0004\x000b¡N÷¼ªÕÏðZ×Â=ûtx¡\x0010êâ \x0013B\x000fUÊ!¾\x0005dIì\x0016{Ó\x0016Tº\x0000\x001bñå \x000e4-ù?ÿa?4Røi[QÄ
P1Ú¡äJÝg<T
\x0005\x0008jMï7Ñ\x001féìí\x0001&\x0014I¨¿¼
ít?_\x0007Ñ©[\x0013. ]l_"ã\x0015
rÂÏ\x0008Pp K
Sí\x000b¤­P(óÕÀ\x001btY¥Õ´_O\x0002®D)¯ûN\x000bó8D@\x001fö©]!úÂM
\x001a¬\x0013\SÞE|P\x001dô
B}\x0005eÙ SÕ¼ú1_\x0001ÔWÌJ\x0004I\x0006Ö4Ê·f0È²¼}Tì¾'""~(Är6\x0016E¬\·pÚ¸/\x0007U4eûÛ:ðQB¢éà\x00071àéhGv]GFe0êêEb È
Tç
éÂVÞOµF\x001a@c3
9A_·\x001a¥I"3gû\x000e:Ótn±9J¢Vgµ&Â¬ ¾\x0010¨è·m<?\x001d[­N\x001fÊgÖ\x0014øv¨æ@\x0008\x0014÷"\x0000µkr?1ì¼b$ºA_zYû\x001b(¼>C3 °Ä»Ë¬í\x0011\\x0010#ðPxæ\x0008Õê»o ð¯Öl\x0001÷" Æ
vKyÊµà £Hâ±G\x0014äy\x0019³Ü\x001aqËêû\x0018\ØÃGx|ª.·i©²f\x0015(Ë
ß&2ª;EÅÒå\x0005\x0000.rÄKþFCQæ\x0019¨d\x0000:º=0\x0010Ã\x00163Ã\x0001Ñe@¹é&"kzÐïheà\x001aÇ=òMu\x0001`Ü/\x0010¡\x0008¢º4\x000ekv¦¢ \x0019Ðß.K'sZ©:g¡w!(/t\x0016\x0003\x001b?Ü>ì@×ºNëCÆþ8Øm°à\x001aV Ñ!ìRvq¬\x0012\x001aK\x0012ã"´µ+LNßõh="OK\x0008ü+èñBÛp¦£7oÖë+¨T\x00196"ÄU¶\x001a6e¸?ku©R?8ß~ñ¶PWø:s\x0007)\x0004
Êe+'Ìó òî'RÛ èë§¾*IDÚÀû¡W\x0002²o<\x0016&\x0001³Å8\x000fÝá¦âqã!vaø+B\x0010z[ï\x0019}K_nW\x001e_\x0001vÑV'o¾vÔXây\x001aaÔgÖv`·b¢!aLÁi\x0007	.\x0006u*!+\x0013½¬ø¯)û¶},\x0018=\x0008Uk#:c4\x001fEÎÀøâ
\x0002FSÁ®#bn'¤S7¤új!\x0018\x0019d\x0019·OÅîZ¤Qzi\x0002nÛ:Ñ\x0010êë\x0007éÀ.\x0003r®Îgª,:íeéK\x0012Â¡EeÁtîa³\x001b!°\x001cD°ñ]
®q\x001c:k :vz¬oc&~v\x0011!þäí
RÈ\x0011£Lñ\x001dä+|:!zàµP^´÷¤é´FAªûáuy\x0000ÔATï\x001f\x0003\x001eév¼µdÕ\x0015×\x0007.û;
1\x001d\x0010tè¿øb\x0003Q%K××è\x0016»\x000fNAÓ«¹ùhüNé#ÎêÀTb¦øû÷T¶	ÜörzbÓ'6){\x001a¬/H6\x0017è%IÌð(k\x0005$½\x0008íjä\x0003³\x0005"\x000f*5\x0005Ã¾æ\x000bÞ·\x0014BHYÚn9\x000bIÄ\x000e`V0ºË-'rÆ\x0003h>Ïd\x0011ÂT¾Pz\x001b\x0015¥&\x001b\x000b@-ð$(ÁÓ ÓéÎ©ÊÇo\x0002·!ÞcÿÁÝ\x0006\x001eëü,=«8óðZD£=2Ê<XB\x0001Ö8!\x0015	¤Æ¤ÿäë}Vyy_\x0000½0\x0004:¿êûÂÇm?ãsÄá$#]±[Ü£é EÛ #sðo\x0005²<îøð\\x0012®¸íHâr\x0014à=:\x0001§ê±^øå¶\x0003^oÃÌÛUxb×WDÐ'î­×Wí:oç\x000bÖ\x0002³Ú/ºS§0\x0016Éx_!3«ÚÃmG'z\x0010ú\x0019ðB{\x001c½n?JÓÑÿ@¯\x0013AzMÒYï)ñ^×ÃÐ\x0001IÉuÐ~^oÂãa¾À\x0011Ì9ç|EÑ7{\x000cé\x0011ÞÕ\x0012zÂ×ù\x0008\x0002í\x0003ð\x0002Ì7ðu>'äuÖ¬áåu~¶ ¸³\x001c¢ë-Áp\x0000mTÍé \x000c\x0001Ù|g\x0000f¦\x000cÄG{ÍøÑ[¹^Ô>@²gV¶MS2<J_\x0001Ø50À·ÄùôÄ¯kTà\x0000Û÷f¼O\x0000;!@¬bFLÌå\x001f\x0000ö}'\x0019\x0005@\x001bðêÜW\x0008v¾U`Ñ@Ãÿ¶\x0008v\x000cUì£¿o\x0010ìÄ¬Å\x001a¥R|Áù
Á®\x001fU%ÅWÊk\x0004»F\x0005ãÓÇÕÂø\x001aÁ¾*\\x001f\x000cäæ\x0003Á\x000eÐ{­\x0001y\x000fµW"ú¨I>pç|lÖ9ZÇ\x0017[ö5|}Å$¨ù,-Ím+¾½\x000cÂÍ¤ôcø\x0016\x0004;R\x000bE°¬%z2\x0017ìõXÕ~ú=KßV?yÉ8ã®ì+w/ A7
nÛ¶Ò¢,Oú;¯ ,¿\x0001¶tÝ#p¬\x0007\x0005hRoB6\x0000HÅÙHÇNÓæú+ÂZ\x0013evÿüÎ'
át
$@Ó1ÖÙ«->¬!ú°z¸\x0018P\x0008P\x0004ªu\x0008&ìw*8ïÅ\ÏÀ\x0001ck\x0013àº³¼\x0001#í´Yó«q¡**ëÛÚßG¬¥\x0011G½ßÆLDÐ\x0012Ú¨ûqåÈÎáÝßÝ\x001aYë\x000c¶½ûL¹Hóì§ßó-?¶8J+\x000e\x0015õ"ï8\x0003å¯ðä\x0015G_\x0007![\x0000½_?
w
P½+\x0001\x0000¤\¾PÈ:\x000eU¾D×
ÔÃé\x001e\x0013A2¬4å¯\x001cK£¡#>!ÙØaî^i\x0012õêq\x0017S\x0008N$ÎÓe¾\x0010¸\x0010¸ÒoU°¾ä¹ó-ÁC\x0011VaºØu°oXG«A#\x0017ë"!\x0011ý$ \x001c~Ãã\x0012C½÷}6QË\x0014éo4$.\x0004\x001d\x0004Ø¨Ý'\x0001\x001eà\x00104¯ú"UÆd\x001dR(V1Nð<>\x0014Y­\x000eCb\x0011Ä\x0007Î4ùñO\x0007\x0013V«1ö­
ýy K^\x0007¢¢¤®ª«T\x000bó ß]/:¥$DÔ°¿çíÑû¬ÂÑß1Í±*»½½\x0001|å®ØRq»\x001cíV(WÑæÕ¤ß!
cçõ­mtm¥ë³\Û\à]S^Kó I\x001eÜE§\x0000\x0006\x0006\x0016ìg¯­\x0010Üv~X
\x0001kÃmN@^BÔ¾ç6ÕHÙ·ÏºÄ\x0004©¯õJ­è¶ý¥ºÔKiÛ?¸ïÃt>Æ¹Õ\x001a\x0000KðUðL\x0012Ñ©.d"L\x000f	\x0007Þ+3¥\x0002ïfÝ©£T\x0006¦}ýÕ\x0018÷°Êqºo®&ðúá+g\x000cWx\x0011%­)`ÛÏ	ê§Ât¾*ü½\x0001½Ç.í\x0004I§5ÊúÌ©I¢^í,O\x0008êâ\x0015y,?awa}WFU÷¯B\x0013¥£h{ÍÕ(âTÅ_Îº¨4ÐV.C¦Ý\x0006\x000eØ¸ÐöÍ\x000c\x0017Bt¥{\x0017\x0002Â~ àß¬Ùð2¨ l\x0013E¢¶ï		=Àñ8ÍÊ¯¤e
\x0013è\x0005²á4Çé1qFøÞ«=h\J4%m:\x000cÑ8@> \x000fJùYÍ,\x0004\x001d!Ú=¹ªÝdºR»</\x0010Ï\x0005Ë.§J:\x0007í¶_ ¼\x001aPÖ½ª¦K¦­-î\x0010n5$\x0005}È\x0002¶\x0011Ï\x00036OÖiW+c=·ì¿¥qv\x000fôµÓ#¥\x0002¿\x0015wv÷:]¬49ó­êÃ®b4a}<\x000f¾:²ýú6(òV6ÂØ!\x0004\x0016ÅUò5U\x000f3\x0003w·\x0010z('M÷àø\x0006+©Y} ë}Aþàxå\x0008ðËð¼ë:EÏ¶\x0002o²ûÆ\x0011î¶BÆÚ×bÐ/«> \x0010ÝgÁ``\x0007\x000c«³§:U5Ù"-m[\x000cÀÕGñn\x001eMpN¢ ~=úkWà¨ª\x000c²îÀ×+Dî\x0018pø55A¹rí¢Ò\x0002êò©ïp[ûmO\x0016@UJâû¡)ýP{¼®¥JëÛï;\x0015f;'ö	[¾PßîêìÝ\x0014y\x0014qqÎëáL\x0002\x001cQò­g¯ÑÞ¥®³¶¸\x0015IÍ\x000fä-Ã\x0011ÇBL¦\x0003\x0015&¿ÊP5°l\x0004ü
â¼³òG\x000c6}íPºò\x001c"XÊ²½\x0002ÑPÉ¸1Dþw!ÀpR\x000cê\x001f½\x000eBZy
n\x0019H\x0011Aõ\x000f\x0010Í\x0003D} ÊÆfà\x0013 úX\x0011²ïæ@àe\x001d\x0007ß^gÍp ã¹ÞvÙ(\x0012\x00132ØÍÁ)_ô\x0004Ì0ÌÃm±=~Æ3¾J-Oä+¢3ôº?\x0011BU\x0010vÑ
@ë0Çè
¡Ã¶\x0006\x000cí&1\x001c9*MO»UÆ(H®Í\x0017\x000fMA­b×¡ì\x000c\x0017 ß!J¥)c!ÍÌe}
ôg2\x001eVçNÌC\x0016ñæu¬*·vÆ\µË@ýì\x00186Ý\x0000Ú@=Ñ~7Þ!\x001e7Ëî\x0019×ù1­\x000fO\x0010ZË(H; ¨mÖì´Ë öcCq¹ïµ\x0017øo\x0008uZ\x0008)
\x0019ðµ¥ [\x0002þÓvF¢<(uÝUR>Ê0v?í\x0010ö\x0019ò\x0008\x0019Úò÷\x001b\x000eÚ¹×\x0011ã6ªºd³ÆgÛ;F18\x001cnO\x0011Î
[³ýª,\x0016ç\x0018\x000fýTñ+Aíu\x001b7üDhî,­çx\x000fh\x0014H\x0004\x0016\x0015Ð\x000cf¦;
½\x001bÍ÷R÷eÖ\x0011\x0014Gòä\x000fÃ\x000e³r¬\x0006§FèäÐÉ²ä\x0011<MNáûN¼Ê,@åm)âE#\x0007$M5hod»nj8I\x0012ÕB\x001a7@"\x001eá!\x0002kè\x0010D5-!8eÎ\x0007\x0008ô\x001cÓ^ý\x0018ñð¯[õÒGBõ87³ÐÌDE2õC¡¢T\x0010JÁSB\x001c´é5}êkyY»ÌØ\x001f\h\x000eòb*¶\x0013ùos# ;\x001c°ï5:W:zfTÀ¼\x0013¢^¸~xÞJ\x0012x/7`+Óð\x001b­\x0005.Þb=±há\x001a¸^è,×£Pì*\x0005\x001dHdÆ^å
±¬\x0019¥o\x001b\x0003mqé£Ý$\x0011në\x001a)ùl/UvÓ9;®\x0013<&^\x0007ÕºÌ\x0004EQrÑqw¢\x0016rðH¢=2]IX	ÔØÎÂº\x001a\x0018
ª:Ø\x001b\x0017\x0012íW83ë^Ò«`#ølÝ¶\x000e\x00074ÐäÕr\x001cè\x0006,÷á\x0012v(pR\x0008\%P¹×:¦
~ÝavÏM ¿­?mã¢ \x0005\x0007à\x0019?½KÊ(8T{Òñ:¹4üOFñ\x000cðãÍH³\x0015p¼Luü§Ó\x0008r¢ûu\x0007Yµ)Ï\x000b¹Äó}-2i¯\x0015]P+m{\x000f5zZ
Ø\x0010*dh.@wè@/M#Õ\x0018f>z
Çè&8>rA5Ùþ1áq¯¥+?Ü8UwÈj\x0019\x0012%\N
ã\x0005
¦]#tnD\x0016ØM¼
Ðó!Ãß®²vH>v	\x00173\x0010wP¡Íû\x0017ï/nÜc=\x0010öp\x0018óûN\x001cÅ ¾wBÊuÍÞ¶\x0017ÎºêÇ\x0015î¦\x0014Ë\x000eÁt<
<ò"Ä6M¹\x0015\x000b\x0000|\x0005Ã¾½N'ÃÉ8\¹°¢ã~HoCHÀø4\x0013Dx\x0013$OÈ¶gD4 y^¬*d\x0007\x0008»:OòjÀÒöëH¶Ö)¹"\x000c	/ÛY(©Ý¢/Ù\x0008üX;Lú\x000c\x0000Ò\x0018ÓÞ¿q(¹
Ó~ÔL·*\x000cÞ\x0006ßJoä{\x001d´¶2ë`sXÔÓ`Ò(á.÷î|òB\x0010\x0015Eô\x000bf¥=
a$î[\x0005\x0004ûA_C@í74\x001eìIx\x0002£<ïKä&\x0012,O@\x0011\x0018è<|·8\x000ft>Í¹ÌùtOTÐ\x0003Ã$å+\x0004\x0006\x0016]z7%Ã.\x0003\x0000xÖA1!\x001b´´!ü"r»ËÉgH°H LÖAÙµÛe\x0012Ýö¦#Ë\x0015&"MC§J9%¶5w/9?ÊhÍ\x001b	Ã\x0001é¹ßÄ\x0004u2\x0013S\x0003I\x0008úíê¨ÀA\x0005h\x000fP>\x0014(/sTË\x0018Ä{òþ`yü¸8}Æ%\x0013\x0016«ýýV\x0018õDÐ\x001f¿Z\x0010
ð@@\x001fê*k#¥cû&×É,mÆÓZ£:Zå_³B\x001a$eVÐ\x0007Ü\x001a­Ir0c ¬ A­i+æq±\x0019SVºòR\x0008uY¸_á;Øîj²§it3×÷L\x0017Ìó\x000cù²z[/\x0014½\x001cß\\x0007Ë;tnú¼5TÄ'áòw\x000bA¼£Kç<ÜÕ\x0004	ê(if»Õ]~\x0017\x0018	i\x0010.&©\x0008!\x0003Êd\x001f¡³>8õ0\x000b©\x0002-QÚ<!ôú
#Q*q¡¦ª½S6\x0001?sDN6ñ&¸st\x0001¯w
\x0001¡-\x0003kI\x0000¶ÂÍ¸"?\x001aØ½ÕÜzL¸\x0006ÅZáãÉ\x0002\x0012ãäJZ#	a¯ÃÙúÁ
Mð_É¹ìV\x0010±(*~SfY\x001cçWq¥'\x001cÇ\x0013¤4\x000cH\x001bK7Ã\x001b\x0005ü\x0015eóë riÚöñþ²g\x0010!ýP5-\x000f=\x0004!\x0012e\Ð\x000f\x0005²çÊ2S=ST\x001bq\t+Õ4ë®h'fsm#J¢3
ñ¨¶ZtÙl&@áx\x001b2e\x0001(å¾Õo*k`\x0000\x00183í:¨^%jÙW%ã«áå\x000eËQ^Ïý)@\x000fp³yÁó \x0015ã:§æêé\x0012jjkíZB´&!¶+\x000cpOøYUÛjF\x0004\x0006	\x0005ø²æÖP)(«U\x001bÌkP#µ\x001f<JÈ*\x00087Ö³Ã\x000e¨R+1Í7å2÷(â¯É^î\x0019\x000e=0zomf­U\x001d³íù{ák÷\x0013 ZÖÎHßÍ×AÜ¦&\x0010@{Ë\x0001E(\x001bc\x000fA9%ü&r}¡\x0004^Ï7\x0015ÔxÂÍìÔÜ¢Ô\x0012Åî9!øë\x0001ç³ÎÜ0=©ÖIEÒDñE\x0019É\x0011\x0004Ï. \x0018Éõ\x0006f%Ø\x000e*\x0006\x001aí½qe\x0001ó3Õ\x000ey³ÕÀê/çSý`?ú¸­/K\x001bb]»\x000bÓ	DR³/S>\x0003Âj¥\x001dÄ\x0016Ú.i\x0010\x0002â%IcÃC@Kðëç»\x0010\x001a\x0013\x0013áZCj¼\x0008â¤8^7\x0011×-¤ÈÀ»Ý¢%°±,G\x001f[Ð\x0004êê<\x0014\x0010²=íóNwÃFÓ$ÚS\x0018T7f%gYGyäû¥94\x001aÎ éléBÑ#w\x0003øB*©cÄq¸QY;\x000fS\x0017ïæ	_Ò$sÀO\x00007§$ÐË£[ñ\x0005¢v¤\x0010\x001dëK\x0012®À\x0008æX8É¾\x0014Å2±È\x001eÔÎÖ_©¢?£ú'Ï³á?{M\x0010ÐÆÁyYÊBEÐvó\x0010ªØ­£\x0016¯\x0006«ø¤\x001an-\x0007ónd}íC­\x0003:o$É\x00174\x0005ØËíFxb\x0007éK\x0012²¢
Ü~öï$}iüQ\x0002¹¦\x0001R£)(·å:V|Bòà,&Ú\x0019òÌ¨)Ö\x0002>[·XD³+ý¬[HsM>gã`Ç\x00119ÄDQï\x0006ö\\x0006DîOCFS&ÌR\x001b\x0013ì\x0000Ñ\x0015ñÓ\x0003Å]rÞ¾¿\x0014\x0007Sü³¯	=\x0007©&[³\x000f\x000eW³¡8tQ ã
ð
~\x00105´Æ[em\x0019px>#\x0002é\x0019ÎoíÂØ¶hjD\x0014ì}&\x00013_3éà©#¹\x0007ÍK\x0010^ëay¤¡W÷Û\x001bBç\x0016Y8U\x000bT\x0015Âi¯F\x001eô+	åÑï\x001b2Ô
Õ^ðúø&#0\O\x0007\x0019:Ôàk?I\x0005GÇ$S£ë×T8ë°ÔÚ­ì,\x000bÐß\x000f!YZì¡ï´LK±2üG±ö%¹^ï\x001fõýõñC\x0001]¼gå­Q\x0012\x0002gþ¥±FÑYù^ëå!|W.º\x001eÂ< Py¨ëò3£?ÄÀ\x0006zÜnìN	r
¼ló\x000cBªnÌ5A\x0015\x0011þ.À·\x001fDh¥`Ïc³|f¸\x001b¨G:\x001f@>´\x0014kìNì®Ô\x0019ð6÷ÜYenØ{ð`É»¶Éz¹\x00125¡e\x001bvó\x000c?l!M M;è\x000b{\x001fªñ±ïÁCjBJsmH&V\x0003À\x0011Î8äj#)ðÏT¾(Éö!¯Ý\x001e¿ÆÂé\x0004ÔQ:+'¨7éÍk}¼òõ\x000e\x001d:í-:U¹½\x0003G\x0010eAåÑj¿?üè\x001fkÛÄñ|%CA\x001crï> é¶ò\x0018Úû¿î Q¶)û?\x0008B\x0014©Ç|Rôe\x0001	zQ2P\x0003/Ã\x0008t\x0012,ã@w
.\x001b«ð\x000c[ñb\x001fE)è]W¶	~\x0001B2}]!*E\x001c/bk\x000bFýDòìlÈ¡\x0010(¹EÐ.\x001f'XNºÕ
\x0002KWI\x001e<y
²Í_ª®\x0003VL\x0003ÁIT¸>í}\x0002¬(ÇcØLa\x001c]õpn2*«ò<@4`µP1G2ßJ°o`ú~D\x001bDu\x0002µ\x0010**Ø¢Îá
 \x001d·DÎÞ[²\x0002\x0012H[ðCnð¢Ìê¦]\x0007Ñ3\x00145B<Ú§4\x0012Ù\x000bôÛ\x0013|'$ÿ©ã\x0017!_t'¾69üö:kÑ \x000f`ÊÃ \x0018<Ìp^F 1DW\x000bzÈ¾Ó :¸Ø¥Ëv ÖTÔºR£nòz7ö¡ºx_C*Æ'\x0004qc`\x0010i¿=öFPg=o)ÀÍðn°·Ú\x0010Û¬Ð:û{Ç¢ÕÓ\x000cº\x000ct\x0006IèMßPÇ¥å\x001còùPL2UìÝN(³l%EÂÍ	õO@\x0006$\x0017×"±IíÇn\x0005U¸Äåñä?±ÍùUv\x0014
Äë\x0015Ä\x0011}µ¶¹\x001fÆwÒ±ò!õªy+rÑ\x0005²ô«¤B¢÷ôµÜâ\x000bLÙË\x001d\x0016\x0018Æû¯õ\x001fY¸À\x001euB\x0010!BDeÿª"ú\x0004qõ\x00059L#©½oµz4 \x0016¯lLÉ\x0000\x0003Àbö\x0012Ò¤Âö¢î¹dÖ\x0000\x0004GPks \x0015 ¾J%4[\x0019\x0011z7Á9QK¶Ùu&ÚÊ,d\x0012ñ*¨ïFSPI(8>ä\x0005#m\x0018õ_ã¹\x0013-(Y\x0007®\x001fëÑj^ß\x001cq±lÂ»å)ë\x0013³^wRe(ÈÂ±ß5\x000bÐ©qFÅ:\x0018\x0008Ó/-ªBE¡A@¢Q\x0016JyöãkL\x0002ýl»Cs!«Î«\x000e\x0008þ±SæÒÝ\x0011¬U\x0017Ïl¯}ºûPfI¾=eÔ\x0014QM/{søÁfõq2HÌs5(cÜN\x001bõ]à¢&±ý:¨\x0003ÌÜ2¬Ý1\x001eCmÑ'\x0004+8Ý
	%¥Ïthµ3¤rë\x001a|bèÓ&MèlPaj]KÐ;£è¶B:R1l\x0019í:\x0016\x0008<Éí\x0016"ã6p!\x000f+pD¤\x0010\x001a\x001dûVìK ¦[½â\x0015(rdÆM×V-E£Í+ÔjÈGÝ!-\x0004xÜ\x0003×2¹<4ú­&\x000cZ°ª³Þ}\x0011q4Øiy_§c\x0016D]<¤Ò0J¦°Í@F>~\x001dí¦/ýk­Àåeý\x001fIë$\x0014ÊÖ\x0012\x000ecÇiV%3'\x001b~wRítë±_!YunH['ù&[­d»1)\x0007~µ/ÞëpPCA\x001d.u¾!Ð]éh×Oû*X
VÓó«"n\x000e³íu 
·*Øýé¨·ÀÁzvÙJS ìóþ8»w³\x0018RH\x000cjËõ~*²æ^]Ç'62q1\x0008´}ò5ð1\x0013|C!T](xN\x0006\x0007¡c~ çF\x0010,´\x0001¼ò\x001d 7Ù±u 6iìÛ<X/£\x0008\x0007M\x0006£\x0010ªðíDK·^âO/#8¹Pa1³\x00171H ®\x0015:W\ku\x0015A¥÷ãèÂËCS\x001fE\x0016\x000bAhN¢\x0019\x0007Qþuý$ù`\x001aV_Äü¬\x0018\x001dRëeè\x0018# 7Â8A4o/J·ÛQ$CZ±\x001e(Jè\x0000I°ë'\x000e6«n!°Í\x0010FI¾s·.;ýG\x001a8¬\x0004\x0017\x001cVäL\x0015\x000c:¢[UäÛG\x001fý%_/Q\x0006Î1oë7\x000e\x0006æ¼\x001eÖ-å\x0007åvÕð#FûU+»¦Øµ²Û~\x0010
ÝJ:©ÅðáÇOfih[\x00014^¦Òr9ø`<¶s>z²nùÃØ½Y«t*T \x0003ËU\\x000b\x000efë±ë¾Õ_cTuð\x0004=Q<
_nÝèáaaý¨V\x001a!xÂb¶\x0010\è¥\x0002Ñb{\x0018ç\x00052F¡£Ýö\x0016ø	©RÔ!\x0002Ò;O!*kb
ûMÔOñÞD*øEM\x0019Ê£2©^-üÍuD5Á®÷p_ xyKXðM\x0004Æsp\x0007°	×

J\x001a´é:6
D)(\x0016\x0018éäj'"Aæ"h¿\x001aÀ\x0017ãðÕhYÁ¦-çNpeÙÈÄÏ\x001b\x001e8d\x001a{{ ¯ÿ\x0010
ÍK¶ëLV86\x000bi²X¹0l©èÃÞ\x0018V\x0008À¦ºí}\x001a´ËYíì*p»ªHs\x000eÚ\»<¤ýµ1Ù³À/Ãã¹Eç¬G$'#ú?sÿ&\x000e{0
\x001d-\x0008`\x0017)î9ìÝád-½k_\x0006B\x0012&Ó°5Îz\x0006.}A×ïáî÷HØ\x0001§¸X\x0004S`NKÛ¯®PñWQ×
x*O[`ÑCî«í¡úYtækfòÍGjTæ8vÛôBX§^ÏÀ[ë\x0006¹?ïÚ0Ù8Ô+Ö4©Ò<^cÜ3\x001bUÈzöóÐíEô*Ô\x0007QfºÎtíl\x000b0²\x0010º\x0006Ô,\x0001éÀ¶\x0017Ü2é\x0013ÁL!K9³½\x001d\x001cz½ìu
B¢\x0017Ä¥]\x0006ÐÉ\x0010 ÆO'5\x0003©Õúé,3EÖNÏH2©­én@Ð'Ö\x000e\x0001ýì2^\x0019àB¬ïFäÆ\x0004ëð&ñ0HÀo©e`ö"Ä2­Æp
$;þÈ__çdÍ´Î½¹\x000e\x0015]I@x\x001b¢ì\x001bqºqÒÇ\x001f¤è\x001f'b°\x0006)\x0005M¸4ãaVE\x0001°c ~äë \x000e¢\x0000\x0017\x0008(~\x0019V9#\x00107I¯n­]Kð«d\x0011$©HdÖ«	_ë¡\x00113¢ß(ré?\x001b\x000b\x0015ã¢iSå\x0018´»¯\x0013Ô¾
b½Q!ë5C\x0017ÑáÅÝ¶N\x0004\x0003£q\x0013ðçä.\x0002{¯ä>Ûe \x0003 }§è]âr³U\x0008i­UßÆ­½°HÔ}+ \x000fSÜ\x0007Ïx©AÄlönèûÐþ\x000b~\x0004ç\x0017\x0001r{½`ú9³[5«\x0015RÕ¹\x000f»\x000fA:Y]Cíe-wU4}ýêB§;\x001e\x001aÇ\x0005´äA»Æ\x001f2ðJ°\x001cñ(3Ê´Õ]
&\x001cP\x00101]ô µ£g©Ø\x000cSâ%!?þ,ÆA\x001bX±®A7Ø]}:\x001f°ÇÕoÄÖ¹>²ãt\x0012HHÍfÂ|àB©\x0002PÊzu\x0012 dH{BÐ¹Ê7'\x0001\x0010´¦åáê_\x001d\x0004XWÁ\x0002&\ëÖçA\x0008\x001eôm8°çÀ
E(µÍp/Ó´u#Ý¦ë4\x0001\x0007\x0007b=¶\x0001E¶¶Oô^àd\x0006ò1HäîË\x001fÞ\x0004Ac36YßòòmD1ÜD:_gÚÙ¯Jü\x000e\x0011´ûAQ\x0017òßý£6¦\x0008e9?ò¢3Ç\x0016YçY$\x0019æ\!\x001f}¾@ô\x001a²\x0007!?»6ª~%\x0013FÈò{\x0018SgX+\x000f\x0007Wg}"aÐ\x000eáä9æ\x001bðÎx«\x0011K\x0010\x001a	^Ù*ª#y¹~;¶¢@TÚU\x0003å\x001e\x0010\x0014\x001a&QºYÃ¦_&5¥.¬J<ºh\x0005nÃ'çò|'cvT»\x000eM\x0006@=ã\x0002?±\x000c¡Ò)C"ó\x0019ns0W:»®¯s×Êd)ýàéybë(JíON\x001e ªã¤áUÔ1lp1»²t\x0011\x001cð°±¥Æ¸Öºð"fG`ÙÊ=$\x0007àvÔö»£Ê\x0010í\x000f\x000e\x0003T\x0004\x001c}kñ_´Þ\x000czïY
v\x000eÀ¸_\x001dû$éý4¡ü\x001dVÍÖïD$f ùUzz\x0011òe¥&x8.>ï®\x00030r½òzQ\x0003\x001d
"´ùmz´xP¥s§ß\x0006AríÐ\x0003÷\x000cOHÍ\x0000.W\x001fkmZxÿ\x0019\x0012Ç0KtAÛZPÛºª©:AaÔØZ3éÀÐÌ¹ Õòp\x0019pMuQä\x000b¨\x000bí RÅ5\x001d¨{\x0000Ã\x001céíÙ\x000eÌ¢N¢\x000fÉü&mÓ\x0004k½2öL\x0000]}9Yç\x00076q
õW¤I7µU1Ââug-²NM½mÐyhÌ+R!v\x00157l¿\x001eÔ\x00002¦ðá6ë£ú.dê<\x0001"ÝÞ]\x0018Pò>¿\x000by&R?ýlëãÊ¼á³jV \x0012O\x001aL'Xç»©S­ 5pÔÈ®i\x0003$ZÈ?\x0011B?ç|0Ú9ê\x0007¨#ù]HCV¸®ó}1A$=\x0008.\x0015Éæ\x00075ATó
Ïê\x0006¯ý)Qãg*ÇÀìivÝ	\x0004ô9~¦ì·
Á\x000b&°à:t¡¢ë ¦KUjÞ\x001e{aÝÄW¶\x001d²¥iï\x0006Ò 6Ã3ÛçD\x0005!âÒ9Ó¼\x000bª²\x0010ÂY¨ Æo#\x0006ßB
 û\x0005Ú·ê\x0008úÖ\x0017ßê§ßóA?îP\x0010?KÞ\x0006o ëÂ,Ù«.>ô¯\x0016St§\x000bå+åDç\x0003°¦L"tøø\x0016;J\x000bq\x0008ÅÊkW\x0008ò§ê\x0003yq\x0006\x000c#\x0006îÛÝ ¾#Ô\x0013\x001f
¸\x0010\x001bnÔeÞ\x0004/õ\x0001\x0015:0,D~%_Ù2VdRaXv'Ú\x0014tbº ^\x0014+*ÎY×A¸:
Å\x001d\x0003-»|~Ô×\x0010\x0016ð\x0004æ\x0019òE·ø¹ .p\x0007¾½\x000eý\x0002TþÓ\x000bU\x0004+"}V\x001f²Wô0V\x0018:[âð&\x001fÏê\x001f {r3]\x0005T\ÄÜÝ¯Ö\x001fþHô\x001eÝwäÞIWÊw´âmÜçõ¼pÄ\x001bêî!ÁÂ\x0012\x0011;Óá-Jt«\x0002\x000b¹Öçs¢\x0019\x0015Èøô~ð´Þý\x001f\x000eÐ\x000f
r|_i\x0008ò'× 	\x00002¾m\x000eOà\x0008^|Åí\x0003GÛ¾¾ëùÔ0áj\x0016Â2Ë0;ã0\x0006¨vÎxèÖ¢@ßÓ±\x0012ÇÆ\x0013±ÎS'§'k\x0013þ7ª¸cé\x000eUqM´-ñ%'YpÌMiÅ0î±c\x001c[üÂ:TCªÑlÀá{÷z2V2úAk)«ó&D&
­øõ\x0018\x001d2iìv®\x0012 5¿\x0002²¸@u¹É+\x0004\x0004r\x001dÉ§Ë3Äna\x0018t\x0007\x0003ë7×¡0¹¦\x0018\x0005Ô\x0013\x0012&íl(\x0007ûä\x0002\x0012^!1}rÒ³x|0.>Ò·f}GÊ¤à3Ï#)¼­\x001fÈÔ(o®j[uâcÔ¼-\x0010\x0010STBwÚ#´.×ál}s¬¯w\x0010¦y\x0011Þû\x001dMÞÃTÌ\x0012\x0011\x0002>"»g\x0010Úék[HWK\x000caÜW!_ÌÀ%KD\x001eçÁþæ:¬\x000b¨Nç2üpÅ¨"±\x0011\x0012è9\x0005Z8×]\x0019t2ã\x0015Ca\x0002d¼±ü\x001c¼v|Ûë$°31Ûî\x0007 Ä}í\x0005´\x0015dÒ®b<\x0000hAº-$éðÝá\x0015¥E(¡D\x0002¢:­(êøXÇ\x0000	¹Ü>}ïW\x001abîéóÝQñÐy¤ÏÐ\x0004¦µ{ï\x0004í{mì<èë\x0010èn¥Ç\x0000eä4Ð\x0005pÍ(MF(ý\x000eÀ"·ÂQw\x0010­/°ªkt<Ú\x0006B8àðãCÓ4pÔ&I\x0016B+?«¸X_|Ñ­ÄôG'º=\x0000\x001f×¡\x0000f=l³E
À\x000cêc¥\x0000mÐ"\x000bÈ*û\x0003(\x000ek\x0004\x0019>\x0019\x0012,Îêyä5nÄe=8h\x0011ì»Èç
vô±+z ìjÆà\x0005\î\x0000Ä´\x0000Ãe%c¦ï\x0018\¬CÇÈHß/\x0015ÛJ%k@gsR~ðÍ?
«	ìg\x001d(A%\x0014zO©KÜ_bµÃfÓ`\x0004w}Ä§hH@eÁÖ:c\x000c»h¾Ñ°r1\x0011rl®`À¾\x0008ù¢[
)Ó¥oñÍuèñe\¼ ÆæùÆÌïBÈ86yîôm\x000c|9¤\x0004 M{bµ_2F¶Õ\x0007\x0005\x000f\x0002ãÿÓïx}\x001fö¥ðe\x0005kÇv\x0011]J" f\x0003Î´\x0014ñeeÄV9²\(DÆF\x0019\x0001yEÈ\x0002\x0004Úâ\x0005\x001a& ªXïòá\x00153\x000e±µ\x0000B£6öÅÌf¡è!L3Ýð½:\x0004ÝÀL/Y($2ß§\x000cî\x0006tdy\x0017¢\x0016x\x0005f÷­~\x0013cð[Îæv\x0007âKtÈäÕ0¾$ãÂzg?|_>é\x001e*CåV¾T9 75\x0019ÚðEý	Hê&¼R_¢\x0017ÝN}éÉ\x0000o\x001bd:5ßL*èÔSR+%õüæ2YÞëíÌì%zvppÍÕBÄií8O)H
\x0001n\x0013ì)f\x0010y=ß\x0001!\x000eV£nö¼ä2ºÖÕ\x0013éT¥ôé{ïvÞ<L¹\x001f¼äË\x00013ÛÇ\x001aJ¼?O×%D!ÓÔ£Ãl¨\x0006áÁPIðSkð¢­|c;N\x0016\x00035;\x000f²|@hHS\x0019C/;9\x0018ø\x0005öÁ\x0007JÇB
÷\x001e§eh2!=\x0018\x001dÓ\x0003;\x0002RlI¾Ó{\x001fYÀ\x001d4a\x0008¯Áµ\x001eálÁ(B\x0017ò,!$
P\x0016ÃÃ¡±Áö<:RLý3¾X? 
¥vZí\x0013wá\x0016×V>üyÅMãFëÇ[ýb³°ß\x000fTN\x0008ÕÁ:×\x0014\x0002ðÒF°{È¹	ÞN=P/Ú$ø]x\x0010RNy%¡ÖÞFÚ\x0014µSr¿U27­1ÒG\x001fÒ½É/>úO¿gd|Ô üwÿùõeþýÿù¿ýüÿþþô\x001f>ýÍ¿þñ/ÿ8þ!çø\x001f>ýOþæïþ>Xñë\x001fí2Dþïÿò_~±?{q·ÿ¸®öÿúÏZÿü·üËzÒÿë¯ùåßöEÿîÏþão¢¾üã?ýóùó/ûùÓ§ÿ÷úËýWþ¿¿ü?ÿúýëß<ÿ3ä¿ýñÿzbþéOÿõß¾üñ_ù\x000f_þåOúåË_þåÏûå¯þoüË_ÿüË?ÿÓ\x001fÝ½\x001eìûÿ?þÿÿñ»¿ñÇ?ð?þ\x001fÿë?ü§ü§û_þù_ùÓ_~ÏoúÍð¿÷ý\x001cüãüÇõÿÓ}Ñÿ\x001fi<ë´ ãú)~
ºñ´ª¸ÈZ¬9WþW\x001dí ìM°RÇ\x0001º«_9E³j%òK,rkÎå]¡ék ºk°éé\x0007ú/\x001d/U`>
j0 H°ª\x0010
+8X¸°m¸m¶Ö\x0019ð\x0015y\x0006Æáp¥\x001arÈ\x0014Z6o¼\x0005éY±*":°cÖòK\x00166\x0005.ÎÅ\x000b
WCï\x000e:gT@î\x0001\x0007V~bE}\x0016«ºåq)â@tÀ¦Q\x0010á\x000f¯]\x0018\x0005}~v®³Þ(^<¥Æ±\x000b\x0003®"hü¹
ºøÔ\x001f½Îâ8ýc¶ºÄ\x0018mø©H«JÒýûK5y¤È¾Õ\x0019'êCÑêE£\x0013z\x001dÄÓÝEY(\x0000Ä×²"'Ë\x0001¡×ZL´\x001f$Æ}ö\x0015DáhÃ \x0017`Öç\x0006p"\x0002G\x001eJi\x0007"æLÇ0§ânÔpzÌüYÏMªhq\x0000³úî\x001e\x0003ßíêA\x0013"KvTóiØ\x0011]_\x0005KózaQ8¯Ùú¾Ú8aÛõq®Aïbþ\x000c·\x0011 é\x000b¹y.\x0002ÖjTÝbÓ:@Rw>,Ï\x0015Z\x001fp¯\wo\x000ew\x000f±û\x0018Çbàè´×ò(ü×`\x001c\x0007\x0015StøËÖ\x000c\x0002Fëñ½®\x0004d\x0007IÓQd\x001cë£¢\x0013aN?î?\x0005B\x0017\x0010¶QCÞ!¾«\x0013"\x0006]\x0005\x0010½o±\x000b*j¥\x0013R6·/c\x001c\x001f#+îLîK6°\x001fFVY±\x0000£\x001b\x001e ;½ô~¾S¥°þê\\x0014DÓªn4ZÔHDéÏaN\x0016¹ZØg÷\x0014äú	©h à:v (ÿX<ÈM`\x0008È?dúu\x001b&AB\x0006?.\x001eáXÞ:Å©±ù\x000eÕM/\x0016I½\x001d\x0014QÝ¦|¾Ãl\x0008QÎ\x001aý;`hÈÏ\x001fû\x0013\x0002l>y\x000e$È\x001aÚ¯ªTXËÁI¬ü¢Û»n(¨ Âáx8í/XWFeu\x0010\x00107h*ÕáT\x000f4G>wjMÃ=ÿ\x000bR9Tá¢Ò-\x000bgTö\x0001]©\x0019\x0004ÂpG 5ÔpIÊ\x0007}´¶(56P\x001e¤	Q
x\x001e^X$
GaCºc\x0006qè
\x0019î¨i?F¼ÎÓïÆ<\}ÓÌ\x0008wª3+µ\x0007\x0001ªhq\x0000\x001cç7QË0¤øT\x0001\x0013]Ã+ùÁ¨0 ¸0ÎØ"p[\x0007Áª;®\x0019³ýG¡ë\x0005¡rê	Yk\x0011$xé\x0003\x0010\x0012Ð{M\x0008©´\x001d\x0002ë¼x35A­¢«\x0006\x0014k\x0007uZúx7nH\x0015õµHN÷I\x001f}.xýTÔö\x001bFÀr\x0000R¯çé1´æ8ð\x001a¶äÄjr\x0018\x0018k×b\x0010YâþR!¢<9v&&l=Ò÷=9ÄÎWx#bÌhç\x001ddH\x0000Sc É\x001fw\x0010\K\x0014¬/§\x0006©¸\x001dK§(õ«ûÞ~& \x0008X;u¿?ô>!¿á\x0008~\x0016\x001c¶\\x0006ç\x001d£/Ì\x0010»/GÑÐ}óxQÊ%µ©Y'È\x001f¶\x0000+õf\x0002 z´\x001b\x0002P\x0003\x001dduVdw
4N*xB=\x0014±\¥hÕ;$\x0002\x0012\x0010ÙvTú¸Èþo­\x0015	
ûì«J§\x0005UµÝ\x0018\x0008ê\x0018QÛÎBØéø)\x001bIF\x0008\x0008^\x0005áÀ.q±%\x000f´´&àÉÒàGrÛ·â?US²BÀA\x001bÊä\x001c\x0006ë£\x0007#/sBdg±Ò¼°ß^ômKó«Tçes§\x000cJ0ø\x001dD;\x0015ø~`ô\x0018¯a\x001b²­\x00049òhÉÆ\x000cdë$\x0002r~SDõq¿ÓþN\x0013É
\x001aÒý<\x000e5Ú þÜÆRi¡Ý­ûL\x0008ìuúÇþR´Òð\x0003µE§éð#×H¯'WPMfÛâ\x0001'²\x0002d\x001c']»\x000e(ª5Á\x0015)¬°èÉ^q\x0016\x001fÄáô"â¡bä³°ÆÛVq\x0019Òw:¨\x0008Þ"ç¸ïÉ2!\x0014ôè?)S¾\x0006W»RaM\x0006
µË\x0004A½\x0000Ð6Ï}g,ÓÏO2%\x001c@c\x0003Ùæxz\x0004,R<m|\x0000%¬A2êý\x0008`a\x0007CRI\x0010YÐT\x0008Ö²#\x0004¾\x00063ÕòK¥¬\x0005I¼ý¼"\x0006\x001aÀ}îTKJU üé¥\x001d&\x0016êLÖECÒ[äÞç:
E5?\x0001	(XàÊ`<®õï\x0015\x000bG«s\x001bra\x0014×Ö2Ûw\x000cfÔå§åî\x0018Ö$Z\x0014Ã°\x001cD0\x000c9å\x001dæé©Ì\x0013\x0002£\x0002Hív\x0008Õp\x0019ºlÃï\x0004·\x000ejd°Ävàâ<®³f\x000f6.\x0006©XÊkÍ»ódÑj¢vFÀopNødbÎóîx\x0013È\x0003ägÃz\x0002sß°Û×úU\x0000K{î;g^Ù\x0015I3½ô¸C¨>%0Å\x0007\x0004,µgneé°ÎUêIe\x0003Veq
ýe{ý®Ñ)])H±g\x0001BûBØ\x0010Æ\x0015\x0002\x001a\x001b·½DðÃá³¯4t'ù+"5âLÀë¬ÉVlët6vÑöw\x0005}s²þù÷\x001c¿ßÖ¾)\x001cÅðß+Gÿ½rô1£O÷Ë\x001fþÝ_ÿ@ÙHÒ«ªQ¢Ojõ£[>ªè)áëjäÎ×å£*ÏÄ	è è3\x0001Jf$	6$ÿ|®SïÀØsÀ\x0004·Îñ¦ß8\x0011\x0015Ãü\x0006ùáR	7t\x001e©É#9êd|&±f\x0004\x0004Y\x0006N)k¨º¬Ã,HAÑO°Ñðú\x0008r0\x0012wÙø\x0001¤î©ß\x0017MNÐ\x0010ycí¡}-å\x001c¹þªùuPFYk|X;W\x0011ÔxåFÇ7³váõ\x0012Óæ#\x0007õq\x0012KÙÁ17;ëWô:Ç~sGKi#æ\x001a4\x0008É'Ù¯îÀYÜªõÌ:\x0007\x001c¹fÞ¾P¤`G:p_Uçh\x0005uDtR«q\x0013söë¬4aíËÙXp¿4R7ä\x0019?.gG 
ußJ\x0018OÖË­ä¡\x001f\x000eÀ^ç\x0005]\x0007\x001dù ç«Óß0uB\x00023Ì5ò<·Â\x0007ß:¶ÊÉÅ$ÄÃtà6ës¢
Ô©eÃaeó\x001c\x0018ýT7\x0003RK\x0013HzR¬UÀÞµÍnéfU-ÛÌ¼ïWqÔÝV°úÍ/©
Õ ¼Ù\x0014~\x001bóÛÝ¥6h;ÀrÛ\x0016a/ðYÈ?û\x000e$C\x001eò£\x0005A!`d´Í\x0014\x000cü]B ÒY'Ó-RØ¡\x0008,ÎpÌgíX÷\x0000Y\x0007ölg\x0011_lÒTuì\x000bÔ¬´&M~÷Ø§ ©I\x0008V¸,\x0003a{®\x0004<è\x001c"d ³Bð\x001eP6§t­=©;¼oÅ@]ÛI¦\x001a+\x000c_Èp î\x0018Éæ*\x0010\x0002ß\x0017!\x0011±
+Vw\x0001\x0006õ'dÊ9° \x001a«\x00120E¹	${>çeu¢¨\x0012" ,þÖ	Q¾¸~dn&ý0¡\x0002³Þ\x0000=e¼ðEçÛº\x000e\x0008\x0007áúÜ÷:\x001a¬ÿ\x0008ÃÕ@àEnÍ\x0010ïê6Læ\x0014)
*¦ë Z9eÔÍZ\x000e\x0002§À I¸oEq\Lûa5ö mx4øfÕ \x0000þSe`»Òs+Ö;þ¬««OQ\x000bopwÜ\x0008Ç"\x0008Ü¼oÅ°>æ\x0011`
\x0008Tª÷i¿\x001dµeeeÞNy:lFíW­=d»³í¿¨\x0008\x0000OVv\¶\x0006\x0007:uÒæ¶#øØðßIukBZ°u\x0011¾õ©=ÌuòYÏ3ºýðµëTã\x0010[æH¸ÄíïB\x0010n¼Ç\x000e*8òvDÏ\x0013:\x0010\x0010°+Æ­¨ti8\x000c£\x000f¬/\x0014\x0008÷;®ôQh®qòaQébH\x0008ýÜjFÉõÔ$^÷
AÄ¶¡\x001c\x0013Î¯v\x0015oÑ"°¡Øu\x0002&ÍïÓµ\x0008V*<6N!Iç´)w\x00000å\x00128¢ÝIâ¬Áù\x0015>¹ÂH,\x0012Ä~B\x0010ýÅÅËJUäG¹E¥íkC\x0010üBÊ®Í¾ìI&
üýD8A	Áþ6\x0004,4¬Ï´GÄ«>àa\x0016ÕØR\x0014È?2\x001cF\x0005CåÑh\x0013<\x0002·k²ÕÛ!*X\x0000o4AA\x0016
°éP6\x0005×ù~úZ¼úYÖÖíyÃH¬\x0002âÌ±¼\x0008îUT²LPà·1\x0008^U)ÒËl-³Ró'§Ðf,léÃYÆ[8ûäÑw Â~\x0010?(Ç³\x0000ä\x000b¸òØÛ-¨©VäþA\x001c«QBo6Â±FÎ\x0004?á¼uI\x001eú^Íúp¨=ì tz@³ËÆC!©j$\x0004é¼]\x0010oíË^E^À¨Ò¯©{@¼
B\x0018¢cD¹\x001aJ6]5óÃIúh'½6Ra¤´H2wB\x0010)@\3ú¼¥ÂYÄPÏÛÛ\x001e5s["pÿÆY!\x0006\x001fØÓüÍ~lÍ/&´²¤|&\x0014"¸ë\x0001Qs«þÅYl¸]GmØÕ~êì´¥\x001aúCÁf\x0002ð^\x000cªrÍ>²xY\x0002þeº\x0018\x0014Zw6ÅÈÉ8p *jÛB£Y@öÁUÐ\x0001I²SÈ`{®wôEÄ\x000e n\x000e5¡ðësX
úYP\x0014û*\x0013Îª$öº (Ä\x001bH¶T¹£·("£\x0018#¶­Ò\x0006BÉ\x000cÌJ>?	xJ\x0003·¿\x0002>ÆH\x0018¥£åÃ\x0013'\x0011\x0014bM[O)Q\x0007Ç~\x001e\x0006\x001b+8RÅÕalD¥~~\x001dè5Ë\x0016U¼¡|l\x001f²,	(
õ¾Å\x001fR¡P?YÏÏ\x000b¦Sdµî\x0016ø\x0003
9Ã<D\x0017/\x0019vò)ªÕë-um0\x0008cß\x0000O
ãDê%y%\x001fô(QÏ#\x001a$ã\x0012Ú­­ø:¼/û<j]\x000fÑÂÙB\x0011ùæõ
ÉU9\x001aQ§ò« ÅïR6év°û
1Íàu¨®è`\x0006)~}\x001aúñ7\x0004¿Ý³Bô"æeÓçoE*|ôÝ²(7©®y´¯Ògµ©p%Øì5\x0004ð
%Þä\x000b`\x000fB\x001c\x0007YàFIÒT9ó\x0017<T\x0003ã9
Rç®<ß¥BÞæê:qzcy¦þz;`è\x0012ÂÆÈóMDêáø²\x000f/bH\x001b\x001bØñî\x001c¢siú0\x0006Ñ\x0015Qc\x0010÷\x000fÿJH\x00131hoµ
0f\x0008bÏsî
\x000ba\x0010#>\x0003]Æ\x001cèVJQÐ=Ò§Ø [®$\x0003¢\x0018]u-wÃ÷KJ
\x0014\x0016þLÌ
0_\x001f{ôý U']\x0007\x0017=FUÚn^º\x000eª\x000ftULx¤\x0004YS£\x001dÝï0o]ôÁ}'Äµ>
½ÌÀæ¶Á»IM*úøéHc­2¥M$F~4Ù1¦Ç¾àÓ8Rú©?\x0003X.Óx-'_Íñ2À,dØ«C\x0016\x0007\x0004\x0015	»¨\x0003ÖSâ^r\x0004Á\}ø\x001a\x0011Õ\Fóhßheé\x001c¿\x0011ìõÕ3þ¯M&6µûrdc3¼\x0000ÉÁpV¶/\x001daxsó¥Q\x0008WÔê\x0019\x000eØ@4ð\x000b·¡KÆPÅ\x001cÕöÍÖ\x001b$îô ì`iÅ\x001d4u%F@|\x000có!Á'[ÖPÒBsæzÞ\x001fVÚ±Hëê\x0007K¦û\x000eá,RÏ\x0007\x0012	\x001ar
FÎØ\x0007Ë¡cqC(q«\x0001;\x0001µî\x0007j½\x0013\x0015Å¹åñØÎ\x0013Ëî<Ø	H3Íò³×!Ü©óà<P\x000el}d+:ÛÎ½Uø\x0000
zæ%re\=(\x001d#aèo\x0006÷]Cûh­LXÂ\x001bÈÌ\x000fìÕºÿ\x001aÉþrp<`eÖÁ¥ÒÒI3q%9!(l7^P:!èÇx\x0014s\x0001\x0019+aµ¶©hn\x0006\x0000åÓG~^dNûè\¢\x001c\zñW\x001cºLgÚ!@l\x0000m5\x0000Ý\x0001YÐÇ9M\x000e¯X'\x001c©eÐ	\x001c9GÏ[\x0012öh\x001détô	
\3¥µ\x0010\x0014¦)ÔìP\x0018RApè-À­ä ,Ëò\x001dDól¶o\x0005L»\x0001kýOà°åQÛ^!ð>Y\x001d'\x0004,¾Ò\x000cÍoÅJ2ê±$oÂ%q]·ýrP\x0002«U/è¾*G5\x0000°>A9\x0002o\x0014\x0011ø*T8ÏÙ\x0005x0\x000bã4í¡äT2ù*Á\x001aBVL«¼\x001c\x00134#8ê×\x001eöÛ£Å\x001f]lç'\x0015j¡µÂ~\x0008\x0014ÁÇ\x0008ó¼\x001a¤fKgãëË\x0008ý<JÅJ\x000eÉ:ß{Â×¾µè¿
æUZûÉ¾×ÇÄô\x001e$ö8·À\x0017²\x0010QCI\x000cZ­/BÎ!s#£ÍÖÞ]¶0êlÕQÄ¯VKÞ\x0012U\x0004¬0;ý^¤\x001fèè^u¸ðÑ£þÄ\x0008ùJ¼Ü\x000eà\x0016-¸æ\x0003«­ó;{4w¹\x0015Ð.ö²q7\x0017°mÛ\x0019æÀ¤\x0002]ã][\x0004£v?\x001bg°\x0003\x0017ö!Ýïx\x001e\x0019^Kà(ê·¢¢K¾ÝÇ
©\x0014y[®÷W
Výt
Z+8\x000cï¾UÃf)µèX·\x000eWsí&/ö:¤Np\x0015=	ûT¯ø/Hvûh\x0002À%i<ã|è\ÜØ~\x0018ôÖ*q4¶\x0008\x0001\x000bf}S\x001d¥"Cï\x0019¢ñùâ¿"»e\x001cç¼\x000f8¨\x0016A"S¤½µïDÝJ¿`Ý3Âôº
¢AëHÆ-7\x001a·rý\x0015°gÚÍìÀ;,Ðâ,ñl/È\x0001ÓMéóÞjJ\x001d.úèjÈrP*þÄ\x00108\x0019K»¾FÓf-[R¹Ù!UÊ´Oìg\x0003ã W9*2\x0014Xðº;ËþPtVP³ó\x0016+\x0010EMsör¤zUÚEÃÖÏ:?ª®ßö±=F¢é w#CtÊ°lÿ*$m\x00108\x000fÇg\x0014lhWTÜU­ ñ\x0015û\x001fàg"N÷ÓXÈóª\x0010RsöZTïr[õ³\x0018Nl\x0015»\x001c\x0015xÁlv\x001bø@Q5hØ¯*\x0002Hò³ü*\x0014YV&½$`yà\x0004Ó§\x000eQZÛo\x0007&Ëº\x0019e+\x000f\x0011L\x0011u\x001dâxTÖí·jÈýgDö­@±d<9ÃyË	À\x0011ßf3P$6¶VÕÑÏ\x0019\x001dµl¢IUÌát\x0008+D\x0018:q\x000bPµÁ©¦w´	
ìÅ÷	rÂ{\x0011ÛðPöJXvz­læû÷èî. \x0016¿u«v"¤ªì\x001c\x000e)\x0006"$m\x001f;\x0019\x0019Ëz¦\9:¸ÈôïÃ3E"@\x000bì^|ÙjØ\x0011£9ôgûËëH\x0018ç@g)\x0010þ ±Ëì\x0010jØI\x0008	\x0007¡F­
\x0003PÕ¾UsÌb PÝH!å6ì:gQ¨§¶\x000e`\x0002_÷ö*òÕN§JÄE(\x0001D=êª¯X!\x0000:Ae\x0005BlZ\x001c_ÀÊ_×Lp\x001c\x0003ª-_µ\x0002¦R¿\x0015bh(f\x001c¶U¢àÌñâÈÎ5|\x0015q´k÷VÒ\x0013ñ$\x0013D<ªe#§=&p.\x0010¯y§ö\x0019bci;%Oé¯ïÛë $%6O«6JrpDÓ¸\! ·\x0010×»½Ñ\x0008È\x0007eæÜÎ­¨l®ÅÄó\x000et@C³³ºÊkåá´s%¢\x0011%"b!c¨î\x0003ó
°ç6\x0007o}O÷\x0011qn¿\x000e\x0012\x0014\x00183Ö=(\x0006úlDé¼@Î4¯{ê;øÔ­3Ácc¡ ø=¶·@È"Gã1S
7ð\x001aû\x001aÇk¤¯¡3Î ÈëNÐkö0ëh×\x0010~Û VôB;+·}²¥°\x000eÑý8¿\x001c1ÕÎ¾má÷\x0011éÒL\x0010=\x0004\x001aµ\x000b\x00108]X)l÷[5
HxIOÊÿ\x0011³¾ó«\x0010\x0010D4w/´\x0001ñÍãÌýáXuKªÆB8R ¥F9ì\x000cu\x0012­H6å[=ZÏ1º³\x0018 54qwva\x001fÉbD\x000cën­%â0Æ°.\x0004j%\x0003x\x001f\x001dÅ\x001cðÀØ*µõ3\x0016r\x0015ÚâÛYÆp\x00011ÿ}ö\x0010\x001cõ÷CdûyI\x0011µ@!k\¬\x001fÖLú×!ÖÏ\x0000>XD\x000c_Hs\x001d©¥\x0006Ôy\x0006~5ËÍÚÆ|«µ1NÿUÔbX,²1\x0007\x0008ÂÍÚøçå¡¬ÛU°¦ÝJÑó¼aêK
±®ÝájÌ°$\x001c¯[¹X`NGC:\x0013Xseÿt8éÝL\x0003¥é&	Ï5©ÖÄ*;\x0017àþë^\x0008«q£¤
«É×\x001dÐ&J§½O\x000c"ïlåb(òéHñ<\x000c\x000b\x001d/î½¨7\x0014\x0005éfÜç-´W³vÜ=}aTt¼Ê»Ï¼&ß\x0006ÙÜ(80vtæîuÀPCIÍ
¢>iðÚgkSH\x0002p×^Çúú××\x000e\x0002j\x0011\x0012F=X\x0005¬_Ã¤îjç3`þd'*¨[>èÀì\x0017L\x0004	N
»\x0004Ö@	Hî¿ú*\x0008\x0019Â:C\x0004@;È\x0013ÒUi7³?B\x0002ümÊéé\x0000¨»Ê\x001f*z2£\x0019£å\x0010eG\x001a_¶±Êz\x0014HhJv"ÞÚ\x001f%\x0012Ùë®nS\x0018àÇ}\x001aÌWÆx>\x0014\x0007|õyÏÄt\x0013Á°\x000fÅÚ\x0007¹\x0017ßÅy\x0014hRq?ÌÚö9|´ùVNe¡5\x000b/î\x001aÔ9\x000b·\x0002Ç0Eª°Zåº-ðÃòú\x001a\x0013£bå ÛG\f¼Íüô{°h\x001fêÂà´O\x0004÷\x0015\x0019tË:= Eÿ«	Ná:´\x00169\x00131qhFÑÐGk±Â!\x001cå$\x0015ET L'Jå°Æ\x0007jgY\x001a²1\x000b}§9p5æ4ÔîÚ\x000cøñf×A\x0000¤ |(Ü\x0015úe\x0003'/]vB8Ú&PÉý,ë\x0012H£6aÄÆ\x001c3`¥OeÞ4{\x001d\x001eq°¦I5¥RC´¤UÐk\x0019\x0019äë¦\x001f!£ç?t\x001dÕ>¥\x0007q-DÍß
køö­\x0004»Ì©­Îo©d\x0004´[²E§LpÎ¾!õ³¶DúQÖø\x0018\x0015ÆÝô(\x001b#\x001f¯Ë Y\x0005éÄ6S¢[Ïì(\x0002\x0016\x001a]-Ý\x0010ªù{ëq\x001c\x000cÙt\x0004%zQ
\x000c\x0003
\x000fnµÞ_5ä\x001b)7u?íO\x0008HBÉãvXb\x000fðÉJ;ælWÉÕ:5\x0014É^ûÓ wO^,oC*ÞÓêÓÁ(¾\x0008M`õº×ã¨®\x00129Mò§Aiª\x0017ù\Y·Ln'\x0018\x0008E\x0008t\x0001ßéI@ÿCâhøá\x0016H°¡Óµ'iÐ-÷\x0005B\x001fAÌ¡îîG'¥\x0007Is¿\x0015ÌY`úg=^+&\x001aùØUÖ!DTUÔÑVDÁ\x000f_!Ï¦²Úúk÷ÚK×«ªQÏ\x000e·Ô« 0cµª»%Lqã¸ëOÃ\x0016¾õ\x0014?t	×Ð«`ÀXÓ©Ñ\x00001¢$\x0006\x0007«{\x0010EX§AÊ\x0019\x001f_÷»NduÌ\giuÁ8\x0003¸Î*¤¯ëÞxS.\x001fõÃN\x0006î\x0005ì>c\x001eDç0¤A`½ÛÈra¡Z5âaÔ®\x000e>íðÐ*m<C:¥\ ¢\x0010bÖû8\x001e9¿½\x0012é=þ\x0003\x0018|ÿü\x00077{"Õ¬ÁØègÌ±;Tº M;y®x¬¯¾¦(©¨äI)Ö¾ü;åÑé\x001d&þ\x0006 $Ð\x00022
§\x0015ÃáÑùÓ¬Z·n²FôV ¾+ \x001eHmtÁ\x0008£1-í\x001d\x0004ÿÞA´ONæ\x0004·¼\x0010ØKe\x0003&×Ó D¾F#U\x0013Å[=_\x0015h~Ñ·-§Åd&³É$\x0008éÀ"^þÈð~×\x0013^Þ`¿\x0011W=sæUP¤Ù\x0001ül§
Ð\x001c\x001bi¶CDH$8C\x001d²\x000eÈ+OCéìtÍÖ@\x0006Z+õû½f³%
wÚ]45æÄe·8Í\x000eôê·I\x0008«\x0008¹ço\x0010A­RBò;Á\x000eAãh·í3³-Ù¿øÀ¬\x0008\x0019ÿ°l|\x0002hÑÏ~¦£þCÍ£X£:üÚí(\x0000xó
â5³¶liåá8óv<HÌ`!)?\x0019\x0018@AõÖ9!+å\x0007
þ`V}\x0002o\x0004bÉ¨îýH\x0017WL\x0014Ìáv\x0010Pð@uïp\x00024 \x000bO*ô¾äâ±7ñ0\x0010\öÀ8D²yg\x000f_?ügvhB\x000bjõæf{ Aªs÷îmf¬ÉÔç³
¨d}ð~Ö\x0000èq0ªæ¡\x0008´ÁÉÖxÑ@W?{+EwL;ïtá\x00037DP\x0000ÃÀ\x0000¨Ó'\x0008r^¼×}§ãé©e[¨É>Ocß\x001biò\x000eTáø3Þ\x000e\x001d±å½£\x0008&ðdóî\\x0014C
\x0013\x0000Öê¬*ÄydªÄôú±÷\x0014î^®\x0003Lu\x0017ö!äýþà4®/Qæ£\x001f ÙC\x0000\x00106²ãWäKäZd×À¢\x0012a\x0002aÀIÑ)yÃ\x000b\x001f{JØ¦g­ôPÊã3ù¯b\x0007Zû\x0003ÍæC
Á´«Ý	êkqCY¬Æ®}àçýØ¼+ó5Kqho§ÿ±f*²û±\x0001î\x0003yûôöÇ:\x0015
.sc!dÅJ<\)&\x0015­@	Ùr§Bå>S_ö;ÁI¯\x0012=£Bg/ÜJ¼\x001d\x0003/\x0017í¹	\x0014\x0001\x000e[vìçý­ó.>ðá¼b`öYBÚÞ.Ä¤Z8\x0002ò½ø÷·\x0019\x0008¸\x0003
tÞ)xÈ\x0013­]oÒ³z&Ô_Òfï¬Ï­i\x000cÞË¢/XÑ®ê>©h\x0015í&\x0007Iqpî\x0007^/A\x001aØ´rýNt°Sí{ãºys»m]T\x000b×`\x001có¼½\x0002
PJ®\x00111Dá4+!M®# óTÏý\x0004uÚëñDÂ	$\x0015#ÞyµYÌoûÙ\x0019PrÐ\x000f;!\x0016ó\x0010ÜF\x0004L¢À\x0019Á+í$ó£+n\x0003\x000bÚõ\x0000I{¶y:\x0013w¯j}!¾\x0013½W$ôÏï\x0014Y7]¦æ(\x000få\x0003\x0013\x0010Ä/o£
\x001dÜ0U¬ÏÃ\x0007-Hv)F\x0014UÍdì\x000c\x00121f\x001c;BOoCèw¼¯[nøU\x000cÝø´Q8e\x0003Qoá¤u ®ÒMX\x0012`ÈÓ\x001eøÜ.VRÜiGö\x0019;\x00070\x0011(wÓ( HmÞÎÆøuS9ë£ÁÁ\x0017H<°Øù6DzÎ\x0005ZòùU¯$\x0006\x0013k!\x0003ò@&Ñ\x0003âF+bZ\x0004¢\x001d\x0018%?±âø¸&!\x001aìûG\x0001ËÃÕ(e¯Àb?ÈÌkû\x0014\x00069\x001a\x0000¸§ú@k!°b²Ù`s¡È\x001f\x001d¯CìG)õeUï®S1	«æJ¹C*èBzÂ;	4½\x0016ò(üô{ª*\x001f§
ÈIhÈkT\x001fêÝEøó»\x0018\x0011áHàÀ(c WhÈKüëqÉ¤\ï\x0015\x0008j\x0012Øm§}"Xû,@_§zåî\x0001Oçd6¥øGÄ\x001dâ±üAFÂÐmÿ/{ï¶£ÛuÝù=Á~º1`\x0007ðÖ<\x001f\x0008øB¢Õ±\x001dÙ-[i\x0007AàÐEZM\x0007Óé\x0000y~¾ÍCeüþóôUÕú¸r	áÛ-[Ü\x001c{­o­5\x000fcñ?4´mÐ£_ÎP\x0019w+tf\x0010.pM\x000cÿ}%\x0010\x0014ýØLG\x0010ÙA£Ò÷A\x001al>\x000cE #(K`Õ^Û½Pº»÷ÊñuvÀá½B°å³Æ\x001bJº\x0013\È]{\x0007	ª\x0015ªÀ>:À¹syvò°o·ÝÆq°·çô8\x000b\x0017®É\x0005ðº	\x0010?n:~ìØnÞòzlïq¹3Èz[\x000b÷$

Ðû<Ù\x0003ÜäYØ!\x0005zfQ÷Îø!Aoe\x001f·p½¥Ø¾\x0010uÈrïc0Ç$#É!¶\x000f`sr;x0ì\x001c¥43\x0004Ü¥è\x0008FÚí2¯þ8\x001d5­§ìFØÉ´°)+íË£ë/|	¡!ô¼À j\x001b~jÔ,\x0011P·¹¬S§ý%y,¶ÔfÎ6:ý­«p\x0000Âi"¬õ	4\x001b\x001c É}+±Uì¨<\x0016ïÂá\x0012¹\x0017·Ûh\x0006±¿Ëq­\x0004qmÀq#G9®uòÍ1ITÌ)Q\x0007Oô¾¥ï6+\x0008+ISr#Gaê\x0001ê31Sq\x0017Çùº.Â\x0006'òCí'kmà4ÃªÐût|ÏªÕ=Ë\x000e3Ê\x0010·o0±\x0004u¡|ÎÌÌ>d4Q!|\x0011´-]Øi?\x001bje±Þ|\x0016
|ô,\\x000cóÖ%p´·aLi\x0019OLXjuÌ \x0019\x0012¥ÕKy{W$\x0003XaÜ
Ö¯aÒÛdt\x0003rB!E\x0011$[Pl¥\x001dÓ8	"8\x0001ò\x000bÕµu\x0015:ü¨ûÍ\x000e\x0007\x0014kß¹\x0019ê\x0019\x0015p;ì¿y \x0002Ìj=\x0006U\x0014@}äy®êìzÌøe,ó4d!$"&F­ï×¡®\x0019e\x0015äýþ1@Íq/«¸g\x0012}Ðºs\x0001äZsû"\x001c ¶G1¼ïw\x0006	\x0018ÌáVîQ4B$Cæá³Uü}ØEÆÊR\x0000³UÞ­_CzJG&ø!c.lQ..$\x0017ÒÀ´ÒRX'"A8¡ÝÜ*È`\x0014m´®Kaz÷çkªÊ1À9`@¬H5nô=vá`ÆÓXn<º°ÈÛô:Êê,£dðZÈ©)\x000eõ]Í\x0000SFÑWË\x0004."\x0005aj k»\\x0001Á\x0000Eê`\x0016Rp¹üë®ãH\x0005²)\x0002¶,XÛ²B'¯®g"\x0008`+@¾\x00176\x0012k{ÏmYØ>Îgé>Ã?g¼\x001byR\x0008ý}º/À÷¡½ð¡G·\x001eqhûÇÉ@¢FÔÙ\x0018(0\x0008¸ä\x0004qí\x0013Æ÷Wß\x000bÖlw¶acîL§\x00138Gn%Õ\x001bÏf³ã"\x001fA,°ë:àBì*°46,À¶:è:ð$äu:æ8±\x001e<\x0013:¥6¸ü°p%¦\x000bÓ\x00101P4@ÆÅq@c#Ùç6Ö\x0010Ùc
,óSiC´xS\x0016PíÁ\x001eÍ×÷Mó­ögGÓ\x0002³\x0017I\x0019ÀójdÚ	­:²1M%jØñYY&\x0017UU 7]	þ1IrÆømµUd-¨ N¯a¼Àì\x000c¸\x000eå\x0016A³*Q2^¼@.Õ\x0000ùÌ¶ÁÚ\x00042P\x0008Z0)>ô#@o^\x0007
¡Pú\x0006óUwêoY\x0019XfÐ\x0012\x000b\x00020K.×~\x0001è\x001c;é_MØ6l>¨êËtÀ\x0019\x0013ô\x0008a{¨]\x0007\x001aÙMuÖ½­¨P\x000c¨\x000cÌ¢ä)\x000bú	E\x000fxo±Wí\x00068vf´\H\x000f|Ü0eÍqýà\x000cg¬ÉoeÀE°òæ\B{Æ\x0013Fj ¸IØm8agØÂ\x001b¢à\x001b\.W O"TöCEø{Qõy«JÎ°\x0005Üh®@S¸õ*ùBBhUQö\x001b~!?Fø£ÐJ
\x000b\x000c\x0013ø|s\x0015Ò\x001c¦² CM\ÂæÖ\x0007\x001aÍ\x0013?~²ð\x000er,oç:\x0005/ô	XBM×ö4:wiÃ§Ê4BéVü	í\x0004\x0001×Â¹8\x000f_\x0007B\x0004òÆånÁlnà¤{\x0014%~Ø
o\x0018¥\x0013F­Î|
5àDO.»±ÝáÃöi8n\x0011M>©/Ö\x0012Èh å ¼÷N4Ï+Y¢\x0012ë ËÀaÅù{;ºIâê3@\x0016Vò®\x0008\x0018SMmà
d\x0005S¨m0\x001fIÐæ?ÄÿýkèrÇ<\x0000¼°¬¸å\x001dbCÏ¾5.
É¢Ñö´íQzÀãtÝ*Aý\x000f´i\x000eM\x001f\x001ftÜ¸\x0015\x001cnpûò:( ´è³¤±\x0000\x0006J$ö\x0014h7è'²4mÙ£ÓôJ-½ÜÕ\x0011Z-\x0015é\x0019Q9Jîª"\x0012d\x000e_ûu\x0008U\x0004\x0011Èmôù¡®lB\x0007x\x000cbôÁp
Tº¹\x0001º¨N¨¯}1øxnè§
U¹ùP v'ô	KR:æ(65V°7!Á;\x0000?äÕ¨ë·2¤&¹;\x001dÍoØ\x000eíaó8g/ï\x000er¿_«è\x000b\x0019`X""Òú¹\x0003yÅ^õv¥\x0018[Pë½M9èP\x0016\x0005¯üõÄlJ\x001bðÏ\x001d\x0004ï'ÊBb`?qásäp/Q\x0012Ø\x0008w\x0012}{«	Deõ ±Ý¿dAAøAF\x0016¯¡âÙ\x0004Ò\x001ee4î\x0004\x0002O8¿O\x0006·!«ã\x000cJõíÞe$\x000cèÿ¹óc>òúÞÊÅæ.\x0006>ü»\x0018Ý¿Ñ½\x0001-Ö&á9²âÿ4
Êì\x000c:É\x0012ü
uM\x0016r+\x0014ããXHÐxFÌæÕ¶\x0004
\x0011XÜÄ!èi{¸%M°ãÖC\x000bµµîDãÃQöW!K]Æ(6-÷®C\x0007Qè¾Õ\x0011DzYøMÕ÷B¨ÿÂÏã\x001c8ou\x0011ÄF\x001e\x0010W×É*{©\x000b;ÄcX\x0004:`\x0004òAQ1\x000e\x001dkåè·'ª­¿TxcØjLÒã\x0002æ\x0018|¨mb\x0008yá
Öe¤\x0016mûR\x001a!p\x0014í;¹u
\x0001k{"@£Êç\x0016/r<**)\x000cûÀ_²Jc[OMò\x0012Dúãß£¥\x00118|¥6]ÑûN#ò¼\x000f\x0018\x0006y×.=\x0012°ÁQ}%xaCU\x0015\x000eç£¯\x0010ì¶À
\x0008ì<Z-uVB\x0000PÐ\x001a<dÄ¤\x0003à\x0015Ä;á}ûñb$Ú\x0016EiÞ!\x0008q[^W,ÛÐ\x0017àa,õÚÞ¼Uä\x000529¹ì ÉyÔñLøXÐòi¿»ì%{çã\x001c\x000eUºFª\x0017­/ÐÖ|ç¶­`¥Ô¤â	\x0008©!´ìhä
ë
ên+­\x0010Ñ(/ó	¾;jå{D\x0008R]HÚÂ\x001a\x0011è\¡¢»Z$\x001e0m}´EæÐ\x0003Pèû:\x001cÉh\x0000Ì\x0010pU*%}ë´\x000f\x001cÿ¶0°#\x000c¯­S$må4å¨7,"/ªD^_<ÈG\x0002ëì¡Æx\x000bÈz\x000cÛg\x0008Ç\x0016¨	Í/ùp,8>µehâåéJÿ\x0019õ0ÉÛæäEWXm\x001fêÒoHSbÜN¼\x0019hìr°pâjQ
\\x0002Î¨\x001eT5òÚyãäWÁÏÆ¹ÒÀæ\x0003#<?lÅ\x001bLBö\x0016eÔº_\x0007Z'Î¶¼ÈÒ¹\x0002²_Ëp\x0010\x0003n(K¥ª\x000c)Ed\x000e\x0015±,±}§£\x0014ûÃX\x0019\x0003vP¢@±B\x001aöN:ÊÍ;9(ìëµ=1\x001dÉ¸\x0003²7\x0006\x001f4L'Yüºß]GXñü1`
QÀoi¿\x0019ª)\x0010â\`\x0011ðÇÐ´õölw¨Ò©>÷HÂGT#ª_7b\x0001@³&ç>ÅAXãÃÊEÈãP;Dá%§|ç:\x0005;I[\x0002Ð_!\x0008\x0003q,îc<Øfà(^¦%,AU\x0017,\x0005\x0012dKX\x0019í18Þ\x001c+¨¡C\x000f\x0007h<]\x0010P¹ýï¼\x0016\x001bÄãES\x0011] \x0013N[{¬;#û³îdK\x000bÜ>¶¤5u¡$ÀÁ¾ÊE\x0018ª\x000ch|\x0017EÑ ñè4°¾\x0018
â¡ªt\x0013o&&+bêe_\x0008ò2Ìã³PÀÐ¨\x0019­\x0018Øù=}ÅÞÂQrJÜ§A¾î\x001dÏz\x0003ô/ä4\x0015ÏéV1ÎëËñ9\x0019¯öKYÂy//2%ðÇr\x0016$ª6;êüàÞm_çú±|Ù+ìÍÎw\x000c\x0015«7¨P+¨b×XrkP°Nð-^\x0008ë\x0016\x0014ÍÔ·\x0000ÊVlYÁzh/ÐSZ\¢ýPý2/kõé!§Ð\x0001F=\x0015¹=Ø°\x0019Ð`Ð\x0004A\x000e8Í;\x0001°'³n\x0004åªtÞ÷\x0011ÚÐñ×Ø*"\x0015Á¦\x0019\x0002âr\x0001E¯iQUØã-\x000fÄÃÄÏ·\x0007k5¡0µÔ\x0003\x0013¼
bö\x0016Käº)¶\x0016Ö­P\x000e\x0003Vµ5
È\x0001ô*ã¤ÚN\x0006\x001ad+ýr\x0007ðÂ=\x0001t_çK7}¢³wzÄa|Sq	iðk\x000f3×E¡­,ñ§¹î§¯I_-0þýL÷ïgº79ÓùÿË;-þçïÿë;§ì:¢æÇ¹wºô\x001ed\x001d;,ÊR_KR\x001fL)Â¹~<
úp\x0019\x0014*åè5\x0008èu»W\x0005½¸Ý7wæÎó2Ëg_~òÉolt|öÍï¾bXýö/\x001fí­¯wÅ¿þðåÿùÞë'üÕgß|þÕ\x0017ßýzç×#¥Ä	.\x001c®ýæÏ¾zxzO>ùÔ>Þ\x0017ßýý¸»\x0017ôíwß|ñÝo>ûüËýþOüü¢¿úÆÆÐ_ÿÔ¿ýoÿõÏí_0\x0018öß¶e¿Ý\x0002Ä~ðçý¯ÿ¦;\x001fópîGÞjüíq#÷cn\x0014ÿMÏ4o\x0015ç{\x0016û«o¾üý}õ\x001fÿõ³Ï¿ûlMÎ{?ëçc¼ýÁO=\x001f$q\x0014/lCÓè¸¾Ûúòóßÿç\x001fóÎ×ûÅ·ß^\x0004õíã?ÿ/¿ÿ±OðôuþØqûüó\x0007\x0006%¦	]\x001aãþÎÃýÕ\x0017_þî?ÿþßp;¿àg+Âß|öÝg_ýoÿp}òþ\x0007ý_Væ¿\x001eÞ\x000fé\x0001l­ÐÿüÎV=ô½hÊqhßü)ÀEÈq$¡Ë\x001aô-$\x0001:Î\ý"È\x0016èÌ\x0016ÈUåo>Z]àuÓ\x0015´\x0002\x0005
x\x001búû<HÈPÐd®Ë¶Èav\x0003'\x0008\x000cÙ\x0006ë»:(wåNP\x0007t\x000f<Ã÷wn\x0007ôC\x0015vèBñnÐGÞÓ²ÜQ!kbµNyäî
º\x001dÇgÉH\x0016\x0014=7j-Ñõ*¤·ó5!Q×À®¹|/è£wûcÛ%ÿV&\x0002_tê|tá¨gõ«lïªÛÙ³\x0012üÒ£ððì#_\x0005#¾pW\x001eru·×Ä<¿ÙOò}Úá\x0011^?ÚZ=Ï¢\x001f®M\x0000\x0006\x0000©d§/.Þe{\x000fÊ\x0005ªè¶|U\x0010â\x0010\x001ac\x0006RM A)dÑÊ7£Ü7YzJ\x0019ÙBèÕÂ\ï=LÕ@\x0005®^ÞKú\x0004r}\x0017\x0011v¤ïvï(/:×óåeTYÁã\x000cTêÂwe0þ8S½
¡ziaRC§ð*\x0008Î"H6,%\x001e®~ë°\x0005¤R,»x¦g\x0011z{AÒi».¾¸¥È÷an¼\x000eì¶prú´U<\x000f\x0015$/$²
SPb\x000b3
û\x0017AÏ\x0006Ï×°7]HùM\x0018\x0015)Wùñõu\x0010\x001d\x0014è	\x0001È´ÞQ¥\x0017qeWû¡5\x001dõ5\x001a"¶ÈQ\x001e\x0003Û\x0010>\x0007nÉ
\x000b$\x001c\x0019./\x0003°®,êO\x001961\ÆÂU\x0008­\x0019èÁIU\x0019ît\x0011\x0014¥\x001cQ\x0011½Aö\x001f\x0003w9H5}¡äl\x0007¥þ\x000cïÿú¡1öâå<¿ÎÅ+2[òhÀüø§züi®ìB¶¹¾g·bç,a¥ïÔô+$RAÏ\x0017ÅèDl­qrí:Gº\x0013¡\x0004ý&\x0018#HENÄÊÃÆaÙi\x0001_ñ!:ù	éúvÃá¸]ò¢\x000bbEÛ\x0007nî¨R<]:mõxå\x0011\x000fñu\x0013X^¾\x0005²\x0000!Õ#é\x0001\x0017b\x001f©Ë\x0010I/÷"VmºÕEÐPÊïÒzæ©¼Jøà§}ÝzÛ`\x001f\x0011\x000bC¸\x0007G\x000b\x0010{ZjÕ\x0017!ê\x0005&yE¹²¼ùp'\x0006m\x001f|xÐ¡¾á}E`âðÜ\x001epH\x0000DQ\x0006W\x0008*«tþ@\x000eñ¡¡#\x0012dkR»\x0008áå\x0000+qöb©î>ÙÓëcGå¨SûÝ\x001dD(M´ßBÐû\x0003Ø¥^½5ð²Gî\x0014á­OõÉ½GCqë'Sù\x00143'·/!·Èãkã ¤£p/ü\x001cìrm'OK%íÙ\x0006¥AZ9WÐ\x001a\x001fç\x0017\x001b\x001dsË!NéwJ+¿¸ÎÅôsï4ðh&´|\x001dòt\x001a¿\x0015æÆkÕx90Ôtöþ½\x0016Ë\x0018T\x0017aÏª×\x001abÄÝÖG·Ý#\x0007\x0005f\x0005¢\x001cðMüE\x0010!]Ë[@Üø^ühH,-^F sW¼<ébðeåÂ°ÑÑUðÒBþ¾\x001evd4<î°¹ê£Ó¿a´#~\x001bò¨ç\x0006w\x0000\x0017Ö\x001dVõÓë¼|}rÁy[Çªó±ðÇYý[ö\x001dy\@ë\x0003°mdn\x000e\x000eÙsR¼\x000cz±¥JBFx}P\x0018FZe\x0010·î\x0004±"ÃÃBæÎ\x0006ÚðP\ß\x00140Ì,n=EH\x0016\x0014C\x0019ç/"øþ]F¹´Ô·
ò³Ë¸ÐjB¶åÕ¹
yúP,w\x0017A/·eÜtm¹Ê7â\x0015AÏÜ¥7â_¶\x000e=¯ÆîwcÒÃ\\x000e\x0000KÉ¹W\x0013\x001câ=¢èv¶x ¤áD
¬në¸'+§$´OI%\¯ÀäÌÒ)À	aZ\x000e>¿ÎÅ@t¸Au¥\x0007w\x001dòt@ÿD§£\x001a\x000b,q\x0012MyÕpD\x0002mc\x0019¦âEÐËYV\x0001Ú\x0014IHo\x000ex\x0015Ö\x001c}[³è!¦5¡xuâàÑ{u^Çâë¼MÄ{Z¾qÃf_L\x001eæ&rDGn\x001bâ(<®p\x0019ñtÓ°Ùs\x0011R\x0012ì~\x0010>Ê\x0015XuQh¶Áºe^\x0015ô|b\Üìã!6hÚ=µ¢Ì\x000eøyâ¹½*èåÍì|d\x0007\x001b\x0004
zuÌË¿¸Ù«TçÆeKå;A	\x001fF-Ó{\x001cìäY&?¢&ØÞÂrì
AèHÖ7q\x001b¡Ü<êÉ<v\x0008\x0001¾ðÖîxz\x001dÌÃAuè\úòøø©õS]\x0014\x0002\x00189+°¬\x0017q\x0018mCs¡lB\x0000m\x0000\x0015\x001f¹ms	TÑ&¹¤o?(\x0008aæèE²\È\x000b¬@ÿà»@\x0008:\x0012
±¡pQT²$\x001cô\x0010z\x000fÎ»¸°ï\x0015ðR\x0006¿!S¦~}\x0015¤ÔÉ\x000eúòÉ¦{\x0019Á÷£\x001ao\x0007y1·E\x0017ý\x0012\x0010«\x0008|»°ý-¥w%Áª\x0007"C1ÅoL¿å£ÒIÀ2x+AnS¼ã¼h\x0012Ô5êÞ.Ô]Ä;ÑMÚ®S\x0000&ñi´±MmT\x0008«@ðØÖVJ>\x0001që\x0010\x000c\x0002`ï`ÿ¤%÷*(K$2"¶iüâ&å4!P®n\x001e\x001c½~¸ünéo½\Ý¡Ç#C¹ºorMavÄ-+f] ò¢\x0008d\x0004À:§ºSl G\x0018
¬#7²c4~?ª\x0007®=ÀÖÈb"ô\x0016AYo\x000bFÃ6ü@?BrZós¢Ö¤\x000fã
LÄó®è\x0000Â\x0017
\x0007	¸]<ê»\x000cÎ+o- §×\x0019P,t©\x0005.»Øì&_îD\x000c¶£ç88oô<\x00068¸ÛMByy\x0011Û¶ÆYÕÈOðÉôH\x0014ÁÕE²z~\x0002!\x00085\x0004^¹ïz\x001eºÜ\x0011Ãäç+\x000e¨¬\x0017|B6ñ¤K¾\x000eÅ¢®ïYð{	4öM»~R\x001b¹
ñ \x0015Òö,	åË 4Â$\êÃÕ\x0007'!D¢"CÿlcþF@èö¡¦2í³ñ3\x0014+[\x0005ò$½¸\x000e5\x001c\x0013ntkÏÇ&\x0004+ÐÆäüÈJü\x0013ÝCF\x001b\x0013Ü*D¸	\x0002nïm@A°³!¢f Ç\x0013Ü\x0007"\x0004¶ñtÝ\x00169XS\x001eàïnu¢ÏÇ_Ú\x0006? K Ê7¡c\x0004v«ÑI_\x0002	Å§ô@»°%l4\x001b)^<ª9ø8¥EÊ2×ZfLçåÒië\x0008zw6\Q¸¹
±\x00118¤^\x001bÖe\x0010~84ã\x0002\x001f®~
\x0007ÜÚØÕúå3=	x|wõf]ãåÛµ\x0000$XÙE¸øJAzå\x0005\x0001(7\x0000Ý\x0017ëDÌÆ\x0010'\x001a=ÛÔ^\x001c[ÿh \x0005¹ÒÁ\x0002ñyÞ,\x00080U×8F\x0004&éì\x0006iêòØÔì\x000bâ³ù*d¼ßÄ9v\x0017×\x0011\x000fN¡ó'WU\x0010íÏaÄ\pªô4¸
*?ï®Ø\ÌªÄO.~
'\x001d\x0018Ó\x0000\x000f\x0010 ¹\x001a OC\x001eß]½\x0017×é|PLµX9u.\x000eÄå?>`
  
  
  
  
Instances: 2
  
### Solution
<p>Ensure that application Source Code is not available with alternative extensions, and ensure that source code is not present within other files or data deployed to the web server, or served by the web server. </p>
  
### Other information
<p><?=_ý\x0012^hCÀ\x0013wú~õ@w\x0011£ïi4ÛÜÌ7ÅÓgúóðé\ûVªh9ºô_	[\x000f;\x000f·«ïÍ\x001fÑI\x001bj©³Ý\x0007y\x001få>ÚsynQ¿\x00084Æø=]ÞI\x001d-Æ«E>ÀÁ¿\x0014	Âp\x00111ú$jj&\x0004\x000bvbü|¯¨ø\x0000rîå^q\x0011òòk¾\x000cº+%]ýû5þåC½Ü*èEË¤À¡s}oØ\x001c\x000fãoP_13¢ë
ówèò&rÞ0ÎÏêRß\¼Èå-(fr2äúâ®z\x0002Ço\x0004ÊBdwròã'È\x0015YO¤È¯«ø1È·\x001em; ÜW5òÏ\x0015e\x0002ôê\x0014\x0015·Å¨ûu¥\x001fÀÑaõU\x0010«\x001726ôVËh¸£°\x0001î2JûôõA/Î1W·{UPåH\x0006ÏÅa@,P\x000eÅ×\x000e­­û ·³©Ø%J\x001bm>8]\x0005½|\x0005\x0017·{M\x0010\x000b£PÖ¨oÇA?\x0011\x001fp</p><p>\x0014.Õ©F¦6­ÞîÈñ\x000es+BÐ'Â\x001a.¯|áyÈ\x0007=\x0019ði$If/¯Se\x0001J\x00154Í*ÏÝ2ýÑYö\x0013[\x001dþê\x0013É\x001e|ñIyú?|úëÿ,Æ-ÝÒ\x000b¢Äö*Æ¢lÇj¶\x000cT^Î¤':äÿM³aQ@"i9Ò\x0004ðèå\x0016áÐÃdÅr<ïh!{9vð3¶y\x0016¾Ô\x0015\x0002! àI°çq\x0010vívþV\x000e/ÆÞ°GHÓ	ö6¨¢ Þh¸"#û Ñ\x001dä°vû:\x0005#0r¨Áê¨3Ä\x0018k¾?µOÚ\x0014\x000b¤Ü\x001bËÄëU,\x0008.\x0015LäÖËp\x0002N\x0000ñù­ÂF±z NÃátv\x0002lâ\x0003çâ\x0011\x0008û$Ùa?:</p><p>\x000e³HÚ}\x0001f©8z(wÚ\x000bDÎÔcÓ\x0015ûº</p><p>Ü\x0018 nÃH/élG©+¿ñurR\x0011×âc»¿WF\x000e]\x0007ÝÁ</p><p>*±Þÿâüôl\x000cTï\x001f¼ôÙ\x0016³ÜRxyÐ¼}at×vDCç|\x0005$^1Ú?|ò¿µóÔ\x001füÉÿo¿ýþó/þû{úÝçßþîéÛï¾yªøäô(v¬\x0000%Ð\x0011ä\x0008Ðbã\x0003£ÔmÈ­\x0011\x0011Ä[G\x0006\x001b-Õ§?B'\x0017\x0006\x0019²{ÈSû§_üö\x0013¤}iÁuyÛ+â/ÿ­Qø¼aº		¡ê×*\x0006­;\x0003íÒ³9ö×ß|Bw\x001dH\x0005©Áëý\x0011'vøu8Ò¤)\x0018}wµ_|xÃöWÿ4&\x0002ÿ=\x00046N)/ÙßÙúõ_\¯ÏK~öëï~ÿ/?|÷ý\x0017_~1µm^ùu¤·ð\x001f?·¥õÿ²¿öô\x0007ýüWÿ£
¯¾üö÷ùwß}ÿÍøW[\x001fáç_|÷·_þÍÏÕ)úßÿ×¯¿üóC¦^\x0002\x0015AÛÑú+\x0013:Ïm#2¼Õ\x001cÿÛ\x0006ÞÞÚ</p><p>¦6ý5ûO\x0019Ú\x000bâ\x0000\x0003DÛmOm8Ê)â\x001b\x0005á¿\x000bZ¿N¢°¦%zu.µÑ>\x00119Y	\x0017$ÃÓ³;µ!+7f%bv2Ö\x0011CÔ_!\x0011³Ô\x000cûr,æ6B\x0001ðØóÆú"¤\x0015Ö\x0000û\x001bÛµÜÒ«çÍï­ñéyH\x000e÷\x000f\x001dòó;M	ËÛWã\Ë÷/®m-ø\x0015Ä(¾èzÝ>v(á>Ä×§W|§ÝÖKÁ _~ýõWÿð»7\x000bz&Æ2¯úé§þÕ¿üö\x001bañûÏ¿ÿýM ¿ÕkÙwj-Èº\x0003ä²åt¸]]ü\x0004\x0010N\x001fJ'\x0012.Nþ\x0007þÂ4²\x0001
ð\x0003\x000b\x001fü¾/ÿÂ#M\x001d°fûóçÛÊ;;îRwçö\x0017ØÐ(w¸ùgI»¨~\x0019mn½2½ìs19ÿÍM­­¿·ÿö\x001b[dÆÿüÁoþ8>ýÏlçÉ_üq\x000b8Ô¸þ-qÿô\x001d\x000fß\x0005\x001bÌQvÞ\x0003Ó\x0014©ûÊ¢MÃ\x0016 O\x0007\x0018Î-Ö ãÌÁd³¤r\x001d\x001c¾W\x0005Ýßîýk~ÓûOþöGL°·UäÂ \x0018Ã`Û\x0005JúI*rµ.e\x000cÖ×SäúWVäÂZ\x001enZÇ©\x0018ÃàU®Xeèm\x0000zÈÍo,Ðåò\x0002]°º=\x0000Raã#A¼ÿ\x0005º`¶`ÇðªUüßýüWùo~ñåo¿úöÏ¿þüÃü»÷ï¿úZ>ùOþWÇÆ\x001fOò©\x001duÂ¿üã?ê.â"\x0006w»XZX>.{MZÏ1ýoO(¥>ÙQÒ=5ÊOÝVYOg³?¡\x0001«æì\x000eÏ#Ùÿ¸Oþàgõ»/¿ÿÝÏ¾ùüûß~÷ûß}þý÷_þþgò=­ ¿ûÙ¿ÿÍ/ÿßÿç?ýÕ/ýÙ/~ùÙ½ÿå_üìOõëÿÕo~þ³ÿêO~þë¿|úìÏ~ýë_~ö?û»\x000fóõw¿ýî)¼ûoûÿ»=æ¯¾ýðõ?~ñ%OûéGïòãïñÉÿ=^­¥>óÅ^m\x0017;ùøÍç¿³\x0015ñÉ"þìû¯ìkØ\x001fþÅÏ÷ýeáô³\x000bÿÓwOÿq\x001d,N%hé±ýÃ³=ãB\x0018Zîé²ÿòØ\x001fÍKD¥\x0006Í\x0012¦6= h¶tÄb§v¦%¡èÓãÛt\x0015ôþ2è¥+ÌË»½&æÅÍ>.:û½MÁò7þæ¬{;Õ\x0004D<³ð;:\x001eyüW\¤Í\x0004ÎrÃc¢¾k\x0015,\x0003;³\x0016ajC\x0013Î\x000böJPá,\x0000Ýi¶á\x0016 Îm'Z	$£8jÿÞÞ
Ê+$:a«ìt+Kr05ðMð§0y%r%_¹U¤°.\x0013e½kG{Y\x0013VCÀhÖGq.£p\x001dç\x000cõhËã®¢.\x001b\x0017Ó­\x0004÷°þ­³JGP*Xò¥\x0017\x001c!ªÄR<ÞÏ\x001d!\x0001­ANYÌc5ØfHÀy
ªòTHn0æ<\x0002ømz\x0011d¹Ç¬>ëx±i¹õk<v9°µq+)\eÙKÍ\x0010,»ð@ó\x0005v;Øa\x0016;ýÂÈ3éxV)LWØéöD² ]¯Ø÷\x001eí"éB\x001dm1~«¥¬\x0010¦\x0012%·ïd?\x000e\x0008[¿\x0018¤	¸$ú</p><p>è=æj?eõ^°ÆÀÞ\x001855áY;
] )sOó>Î2¬\x0006w\x00106ôvu§Lÿ\x0017 b_è­¤®4"8pw\x001a¨SÑ)(« \x0016\x001cðÅq'Ùrþ\\x000bJ\x0018øZ\x0012ìüøÁö¶ÇNÝ\x0006´µeçÕÇË³;g\x0015¤òÀt\x0005YjBmo|y+ì¡\x000b2½i\x0005¡D\x0003©A]'H \x0000´[-\x0007\x001båà\x0018Ä²P\x00080\x0006jK~·P±LìÉ^qñóVÐB2Ð§ºîd*¦\x0016º½½\x001dû«o±\x0006m7g8pc*@³ö7úâÓ¡½âé\x0012ô2\x0017vP\x0005\x0001/¢®c\x0012\x0015LôvÓ\x0017P//qE@%´ÏÖ¦gn0D</p><p>=óF¥A²\x001fôÖ\x0015yJö\x0012%³GP\x001feHçýÂr¾2´ã\x000eBÎ\x0012ÍMßãº[t\x000f\x001dñ}¥L\x001c6;þqP¦:Fû·Æ~\x0011¤\x0010è¥ÞÉJd` h_<÷ú0ÄF7mÌ0X#×A	Rºcá\x001eß\x000b\x0012;æõa</p><p>òðdñ. ¯\x0010¼à²õº>\x001dÌm</p><p>@æ\x000e\x0008 a\x001bx\x001e\x001d¨­ H\x001cÍeÉ#D³v=x¤ON°Í¿ey%À$]!ïCÏw-ý%`ab©ÜÆ&ØXC«?4.\x00039Q|\\x0010H\x0018JmnÞ\x0006!dj$Þæü¤ppV<ÎqÄJ\x0014ñ§Õ\x0014fé!õ¹\x0014Îì\x0017Û<\x000e{)@D\x000eâS³\x0006°í®%ÅÑÞ³Õ6¬Å\x000b÷ñ %þmEæºÃEú÷\x0017ð\x0003OÀµzQ%Ì\x000e£1p0­\x0004ÛÚ^\x0002m=ÉÔãÀÓÏÙÇË´\x0015å`\x0005U\x0006ÏXYhTtÐ\x001e\x0015ãõàEvCòp\x000c-Æ°\x001d÷ÂÂø±#	³\x0012ã~!#Þ\x0001gx\x0005Ùz8xã2\x0008j±íeÒ6UÛ°û ÷hzÚ\x0007·\x0005\x0003ÀÛ</p><p>©.bt\x0012ýº\x0013\x0003½Hs1\x0015Y$g[ÇRQQP7?¯/3\x0010ã(õ8oecÄ\x0012
ª4{ñ÷üût~=Tu\x0014÷@k,àK\x0003\x001bõ6Ö$§»k_V0ìEôØþ\x0005E\x001dkm)@\Wêrßrh¼¹×ùNl»\x001b»ÐvãÅñ~¢\x000e=$v½d1ªp/©;±x\x0011èø½7¢¯Æé¹[y[\x0001²|Aê\x0000¬Env\x0019Àñ\x0013t»¯sÅ¹¡\x0015N:Ïü%V°)¬=$ÖÎ«¨óÛ\x001e\x0004Á\x000cÁºp\x00112î\x001a\x001a¬Ó\x000fýâ:1ZSdÊ´²\x0013URÒ±N!ø\x0005¢q6ûFÊq"x¾\x001cÛÚEpÀ±ÍjçÎ*æÏHÔ¹íÙY±J<À¯\x0004P\x0004pyÌ\x0010Ð
\x001cH§ \x0012_\}\x0011\x001fYË()\x0010hQË\x001aÖSáe</p><p>ýª¢|ªÄ
AØ1­V\x0008\x001e6aÖþP®n£±¥Ä|$¡;KPÎE8«TýÎ qK~Óäsùz¬ßà\x0005Ýú\x0014ÑËÙFÓðAîr\x0002q¶Ë®Ë\x0004\x0017=KãI&È\x001e7YÛò¦ç7£|</p><p>`I]öÏø¼dÛÝæNu4F=j»2\x0001Å!Ú\x0016@À~n§6Ùà@#Í ÀÇê:Íüí	åÖ\x000e_VnÔ¬ùxo×¼É!øÕ.Ê¢B,æd\x0000ËÍ_û÷¸õ57íaÑ2°%Ææ9or¯o4g°Giº\x000e\x001e7¨33mv\x001aH\x001eÖÐS\x001d·r\x0001ì/\x000e0{{µUL:\x000co)~2VGÕrC³mïgÇB0Bo9\x0003üDßb^\x0010mC\x0008æ\x0010-Ûv:\x0014ä\x0003¸\x000f¢)ü2n\%wRÄXBiÙ¤-T}\x0018IC°(¸ÎïÈ(Ìú\x001eÒ¸Í1\x001czqY!\x0015Ð£Ç8}¹cã\\x000bP¬®	p\x0001\x0004ÞE2~r\x0012|4g\x000e0ø®RÚ\x001b!ö</p><p></p><p>¸\x0001i\x0000\x001fg8 ®Û\x001dMñËdöí</p><p>ODó\x0001í \x001cÜÛ\x000f\x0003\x0013\x000eT.Ìç+½¾\x0016\x0014?<Ûmø/wì¬ôÀÑ[ó\x0001õ´\x0002¤¹
sl¸×¶¨ÔÙM$\x0004ïi\x001bObKâXM.`?0´²Öö\x001a«Ð4Ç0¯½@éÎÏAá\x0002n¼\x001bþÄPÁ!þ¸µ¿"Ü\x0018ûq<·d;ÊÚ8­)ï_c{²\x001d:±õZ·â\x000cÐIZú>(ÛaQ©G×AgÞ[&\x000e¸Çðl®®¥\x0007"´®\x0002ÂÏ>\x0015Ûðr\x0017a©í{µ¥V!\x0019OewâüÅ	g¯¼;¶\x000c?ÜÅµº!5ÛN\x0011áfuûì5Kà</p><p>;Ë>r.s%úµÆsqrÇ¢ý1'*û
ûi\x000e®(côÿÖdÀ±ø[§¶N\x0007\x001dúm\x0019^¶ÔxÓ¿þÙG\x001eÆR\x0004Þ¶¦Dâ+ O{½\x0000Rds\x00129¯±JZ>Ûq`­\x0004¶of,­×âÅâäÏµ9.6l\x001d>Â\x00187Å«@bY.{mÇ\x001e´j5\'éèpèðH³ê·ØÿefoÞïÊpÃ³{í!\x0011Ð\x0003~¯ýä5\x00086æ¹°Ë`Âi\x000bçÎ³\x001b\x0016ÌØ]¥ë#é­@|ò\x0002Hx²Ù\G\x0011ö\x0007\x0007pëDÒ>Ø\x0011ÄvCÚ+nÃQ\x000f£qöáD]ÀkèKGaP8PÄºFbË\x00086Ôm\x000b+m=<µ\x0019ÛsNaÁ­\x0018°þÜ>ØªD!?~"\x0004$\x000eÜþ\x001cÓ\x001a\x0018à¥º-ÜÈ^+\x0005Î&ivÑ_[\x0015VX]ô.ÞÏ 6:\x0010\x0019n=\x0017î/íÅõ\x0013d£\x001bS·¸¶bK¢\x0010rô\x0008\x001f)\x0004!%O±b\x001f5x*;ÖØÈ\x001a!pðçi7û\x0011ù9ö¦u½:\x0002ÿ}Ý©÷bÛf\x0019¯\x0007GûÊPûÇ´Ôm§MüáÃ\x0010\x001dx\Ì[½\x000cR\x0006\x0004¶9·ùäIÕ58><\x000c²Ùg'Îl«]ÿQAMd4Ä9 Æ\x0016 µÒüò6X:þwÔö\x000bÊ,×hàÊáÛvÞ¡í\x0014 >Ý(^X\x0010µa\x0019ö­<*p\x001eR]Çäá×°ç{«íÆA,IúMçs·\x001f«i^·â³OÞ\x0017\x0011ãE\x0017Ô?\x0008$\x0012\x001a\x0002ÜûìmÛ,çy\x0011\x0012\x000c¹-\M\x0002r\x000f¨\x000b;êHýiÿ\x0016ÒÕSñszodØçù-eðùZ¯ïþÝà#Û%ôRÛ\x0018ó
K'u8ürü\x000c÷¢dÓ7\x0013\x0012ÝäÆñl½=Ë@P>,\x000bIÊÚ4,ÒÓÍ°	\x001c¿V\x0008\x001d
Ûèc\x0008\x000fC,ÅÈ</p><p>K¯ï"¨âÊFû¼\x000e\x001d 6¡ýk*>Ò\x0018¡\x001c~³-K¦\x0010-
7Ç2Hí\x0013YîÖåÝ:PpO	@\x0016ÜD±Stü¸/,©í¡>(Ä~m"\x000e´Ûâµr@ðTu%ÍMÐØ/µ\x0003äý\x00190¶S\x0004\x0015Dß´ç³pï½\\x000cÜ§\x0015b\x001b@K¬®Í\x001aí¤2È¼Ua\x001c9NcyU
)Ëá\x0014ë¸N\x0006¢OR6ùå:±$fðºS\x0004OÐù°.ÂÉ:g\x001eFÖ¼\x001cü\x001fÁOÏ\x000clTd\x0014çÒ.[¬\x0014|Ñ~\x0011ºnb\x0019"\x00085ñ"@U7\x000b½¹SÑj</p><p>ÚÑïÝ®Ø\x001eÚ0ñcpqëHÃ\x0001Ç¼µØ_CF:t}ñN\x0001'ëëF\x0001\x0006ô3\x0014R(Ü¡uZ\x001e¢\x0003rÇ W·¢"Ë}.§hGm|ÞªÁUL8ìê\x0010@lhÈy<\x0012K\x0000	nNö+\x000f\x0004;ovm3\x0013\x0007dÆFWäãÙÅ¦¸%Æ\x0017øS½ì¶\x00076ä¶çáÍÅØ +§æ}Âfædc\x000c³r\x001a\x000bqfr2¬«Êø¦\x001e,\x0000'Þ¶Ç2Ë$:ßV2c_¯h¦»¸J$\x000e</p><p>ËØ;^\x0012t2Z¤D]ÃÈe({Qà([\x0013(Cñ\x0013ö³T\x0006×è}\x001fÛ¹\x00118â÷1Tõé>\x0016Ò´1¶,ÙrÒq1\x00155_\x0006á©ýÛ^ÛÉ¨)T \x001b×\x0016U#\x0012A7A\x0012©H3\x0007Aµäg×ì©DzÕÐÆ¢¬ÏYcÞÛ\x0015ú­\x001f¾¸\x001fÿæo5ÄF¾\\x0011«ä1Å">#º¢ÇMçã\x001b\x0005¡J)O7\x0008æ²ítèñê0j!ð¹\x0011F¶»Ë\x0006Ôc\x000bjâ%:X\x0000TFâ)bpÜ·ídæ)tèdæK¶p:	î\x0017\x0010Û%ìvPÕ×­Phó \x0012¨U*D\´SaNk2Z_·²ÕTîáñ¦/bN§qDë{·ÃÊ\x001ebì\x0013´ÌñØ\x0010Al=Xú®Á6\x0016ÝuÞ'HÛ:bKÐº:h\x0015Äq'ô\x000bi/z\x0006!J¨Ü¤\x0015B¡\x0008h17-ú|,\x0014¦,ªuûi{aB:`ßÊ¦¥$\x0019ú\x001dbÛ®cµ\x001f</p><p>O:@n³\x0000oCÆ­È[+U|y>±;]¯ª½-+©ïÌÕÛzbóÓãÙcBAAú)ûí\x0004\x001bÌBÀ)t99îïî\x0011ð4ÆD'£B§ÕíÙmÈx*ûq¢Å\x0007×Aí\x000fÇoÖ¸ýÉsG5¡øñ\x001bå\x001fÜ­§·²\x0007p|¶é¬QAa±\x0010éyýÈ\x0001Ü>r\x0019>r×A´\x001b\x0013y»÷Ô=bRç¢U%ò\x001f7\x0005¬
D¶/iþfd\x0002Rõª\x00194Z5ôþæ&k</p><p>»x·nUé}×Ì\x000c¶¡õN\x0012'SÑ\x001dk6õimÆ
N\x0008"jZów\x0001oÄ8ê)l#­ê\x0008ìów²¤ 8®c¯\x0018kí\x0012ö\x000fÖÀ²Ï¬<æSÁ×
r?uDð\x0007÷Á¾ny\x0014\x001d^m\x0006h\x000f%\x0019#¤CA}x8x\x0014´\x0019bYN+´Hv\x0012ÇlÙóìÔ ô}óR¡¦«ý*¾ge¼=\x0012oû-­I\x0005g"²üâh\x0010è\x0003X~\x0001\x0002
.ì§\x0002«\x0003Ð¢ìV>\x001a?õãåP[·ÅEyW£(Ùþ3ïÄ\x0002·ûfJ¡ÖÍ\x0012\x0013çì©º6ÅøÇ|±'lÐÇel-rH\x0004\x001d\x0003ª¥ÐzI¬\x001exµLÉÙÇiå:HnD \x0019Ê¸\x000eº°n(½K\x001aµ§ÆÁ.\x0004_ï"dÜ	2¥JÈÚ§\x0007×±-Lçâ÷\x000b¾ÿ1W!/\x001eê"È^\x000eõd²ý§ùk*ÕÚ¸\x001aÞzÅ¥[¦!\x0018\x0018!È«\x0008}	Ú¸ìGÏ#X{§½BX¸\x0006\x000e{\x0019hÐÆwh¶ÄR²Aê{ox½Õ¢y¨\x0010'Óù\x0016Ë¤t\«¸Ò@®Y\x0010'\x0013;Nûåm¨å\x0006N#\x0004¤\x0001%´ </p><p>~Hï"\x0013Ù\x00085ï>JÖcáÌº«£ Áÿ\x001b\x0013Bz9ÈKí\x0013
W`å\x0012UÅÄ>enQç sÐ¨ aC?:0\x0019îµV.Õ(ËÂÜBèx8µ\x0012n\x001aÈ(íÊÓÎ§HS{9U&^+kU\Ëè\x000f']o×,ï\x0006;W\x0012^×é\x001d\x00064òñy\x001d¶¡G¼ÑÈÁF$oì;sÌnN\x001dBÒÎ\x0011%hã _Í\x0008WìÓY²m©Ð¸àý\x0011Î \x0010§°×ýÑ/³33$A\x001bw@vÖ\x0010F½Æ×u+\x0017Éî+g()kÕ§ADôÔã(úî
r¥\x0016Ûñcl\x0015\x000bSI7x±Ûì\x0018ô`\x0002ZoaÇÜfwxû\x0002Äo\x0012ÀÛìn\x0004´ÉýMûà&»·\x000ec{\x0005KàUvG-nÐo¼«·²ñ¡,¹ýfYÙUâöAÃ&XiK?èËË\x0010a@ÄxÜ\x0015)ã96ú\x0019\x0002§^¬WsªÒW/LAèP´½åñ|v«NoX!\x0001\x0015`´âY\x0001©b;}\x0018
sF°áÈèZÌ;Ù$\x0015Æ&Ýde­r÷x(ªÙ`âùÞµÍ¿4~Ë$%Ú¹e'QÓS+sÓ\x0004´ùÓoÙd\x0014.ÂN²¡Í>!§</p><p>ZÛë·Øþ9\x000eÓ³\x0003H\x001bHVH;§Ðö×üXÓ\x0015cc\x001e
xÐGxà\x0019y\x001fBh7ï\x001cú#Û\x001a¥\x001aLÞzgRXpè¬'ÂÖÉwùªí/^5^\x0019¦\x0005\x0014vÔ5oä- Ø"¤vXvÜ\x000eeã©*ÍRùnûp6éJ N®\x0015ÕHfcÕe\x001aìáfçÌ\x0003NÒ¤Dç~Þ©©ddokÕ\x0012©\x0011Eû?];Ò¾UõÚBØ\x001f	ÓÈ.8Ï¸ôtp\x0018ßK\x00045ô*Î²\x000b8Ã%>È\x0008\x0002´HòßúeÄû³¿a\x001föÀUt\x0019qN\ÇÜf%ã§x{]Ô¬N\x0016uÛXHWÖ-\x0010à\x001c)ë8</p><p>\x0012\x0012ÐV»¼dNv6°¦Ðëø5xïYr_\x001e°r </p><p>iÝêeP°£zèóV´\x001cÀøÿ\x0014|rh\x0017(Se
ÔÐË9µ\x0002{>\x0004>Ää6 SÎ1¼R¤\x0019ØÇuhªØÍâIâ#°\x0000üfÆ3a\x0006c'\x0015Nh{\î\x000b`zÚº£ÝOßo'ceÐ,£Ì«ëØêgÿ\x0008De\x0017í</p><p>V¡3n¥3\x0019IH·É\x0018Xê4jÇ\x0004\x0001ÁÎÔÄÏ</p><p>à*Ýªéöû\x0011äipwÚþ+d\x000c\x000fx\x000eïï5º(ä\x0005j¦í PHÆl\x0019«iÎ<\x001fÁ¢¥pÓ$cø©¯åÆÆlb\x0005·»d,clMI5ãÝ\x0019Òm2Æ®@%\x0004õÛdl%?j Êðódì£\x0019ÒåbE\x001d\x0018¦ÜARÔdÄÇü\x001b\x0005Ù</p><p>8\x001f©»7
"ÀÆ )7!}Îöp\x0006Ý>@c[XGQHj\x001cÑïØûväf-Àá^ð8é6%êiQYÒ;ìåº¬\x000fÇ­\x0002ò3\x000esL¿C°¸(¬qXÀ.íN¹°7\x000fë\x001ab8FR\x0000.'«ÃÝ*?óO3\x0002\x001a¸</p><p>;¢\x0002Þ2Ö\x0010,$ñ¾â×}øäAPÅxL\x001bi\x001d×\x00019A¯Ñíb\x0008öã\x0005n\x001d\x0003½\x0019\x0001«á}ìí¾\x00185§>)Æ\x0002\x0018­ù³!\x0016ê2ðÝu\x0011Z:óRß§F(\x0000\x0019è\x000fC\x0004ÄA\x0011m}¦ \x0001Ý\x001c­\x0002uñø\x0000/a\x0003(\x000f</p><p>É
Ùí\x00198¯</p><p>ºýMx64"|f3r¿ \x000f+\x0001s(\x0016=ýÈI0BÜ'\x0006¶;áI4Dh+"sÚà`\x001dFmLÈõè"hrjÛÊg@~ÁÒw¢\x0006ÉS&[\x001bêé}>wµç­ Ã>{\x0000\x000f¦ËÐS[AÑÑÉF"y\x0007Ñ]ÏP\x001bno\x0014Q<\x000cguFBl\x0010Û®MÐU)òÃø\x000eM\x0015§¹çÕuî?ª§
9Ï´>ÕE\x0008Öð^öap\x001dÄËò\x001fìã:Yë	ËÙñí{Ù\x0016ÂxpHxÌØ2Í°ÆÉ£y÷#_âSÀ<¢ÆßÏÙ"ÂEthÞIìhZæ\x0015w»g¶\x0011ê\x0006SÀæ
àXÒÍU´9ËÈ çZÊ\x0013Æt\x001fc}»\x0018ê\nU±¦kö­¨wvp*cª'ÕD^Ù'[\x0014½@\x0018k\x001eC</p><p>Dý\x001blâ\x001e\x0016f\x0019Z°º\x000eQøÏì¦i¤	\x0011¥¼*ÊÚe\x0008µJ;\´4<&®*\x001c\x00138\x001dsÁÅà\x000f\x0013·­LiÙ¦x¯ÐFÆSafÀÎ²V\x0014\x001bõ\x0015ÖW {!T¿r§²â\x0004µüÃwcÛ\x001bm\x0002ºB8zW	ã±í4Oû\x0018\x0016Þ\x0006IuZÀ`ü|&~ë\x0000!í:\x000fdà'ÚüRT\x000cµN·\x0011,ö¾Ù<u\x0012ÓcÃ+ìôíb\x0004 ßÃè'£Ú\x0004Ò\x0011P»©,\x0017N\x0010]0Ï¢1R]í°W·\x0008h \x000cÚºQ¬v³\x0000\x000fº}[è\x0012¶\x0001üà:È\x000eÑ>²\x0003ÆA\x001b\x0005h*CéVx!à`p\x0014")ÚUZµ£ÝUD?k°ÐYA$]4÷fÖ`=5çºó%f¡ÜéÒÓÎa¨Ü ½orÏ^è¼id'Ê\x0011ÄÚf\x0019QZD \x001ay\x0015¸ ÆÓ²\x00020]zÃ\x00105`Ímåª\x0019P]Ö`\x001e©ìM×<\x0002Ü¼RÖ¤H,Û'õ»^!ó1äËçHeaâL(BðèX.Mp`\x0004w\x001aÎIÃRx¼è\x0001²|Xé\x001e°ë\x0008v\x001c¥É1`ê,vÒÀã±ßô«ÀO3%æ¯¡\x0006ÓY\x001cò9</p><p>\x000f\x000e\x0013@ÏÏ®\x0013+bd	bc|ì|ApOD«cî`Ê;9øb'X¯\x0000#È\x000e(ÑÎB,@á"Hï\x0007PKOí\x001c\x00161M\x0019\x0011{ð4V§½gið\x0000pë~d½iS¾z8\x0001T@ð»qe[\x0000`rû#\x00049eRöª V*zý6U-\x0004ÝÌ¤¹|N\x0012$qUä\x0008ñ^­Ó·Å\x0014\x0005½f\x001e õh\x001dDï®¤\x000bh	'0\x001dB\x0012{\x001b\x0004Î~ª?_ìu"!ÄryWçÝ:,ÐÍÙ\x000fýº\x0003\x000bÍÒ¿;b®sÞ\x0018GUýfH\x0005\x001dk}\x001cÔ¡2Ùh\x00085]\x00047èlg\x0000ü·I)@ÂÉ=\x000eÁâ\x000fÐdÒã:('z6V»®\x0003É\x001e;Íï^¦\x0013L\x001aEw.
¶IðI«\x0006»ã:\x0006\x0015O2ÊN^É;éÆ!ÔV[Ûc\x0008ÉB·Ø±ýæ:¨Þr\x001ak+ÄÆX\x0017\x001bt;tÕÑ!Ì[IÄ	Ç\x0006··@Û\¢H×ã2	¾\x0008Ö£#=\x0017<µa
è÷ÂÀ¶¿wv@8-vLÈ£Å»¡ikù_\x0008M2\x0008F»p|ã3då«æ3)10Ku+wæ"5¾²é°Ô`</p><p>`¤¼WÂa\x001b¥Å].\x0001\x001d\x0007\x0019S$B(X*\x00177\o`Ø Þ;Ur=¯ÃÄ^¹)Ýã#\x001aÖid\x0006TxãY#¸;\x0010{qØD®¯KV¦Ð­U"Cëoª\x0003íÛöÖóKy\x0008ù\x0011©Ö]Õò\x0010Z3|LÜ\x0013¬¼ÓTVicg|)Jð´\x001céKí;E5ÂÃÀj[\x0010\x0002Ó\x0008¤÷S\x001c·ñÛ\x0018NA|ÏË\x0018È\x000c\x0003ÑòuÈá\x001eV\1\x001e<\x001f\x000c£}\x0018{\x0019T°&¯l\x0012ñ"F\x0011ðº( kqWÏ\x0002ØéyÅÒIÕ;ÛnR¨ö\x0003R=åùèlû\x0011Ö^ñ§u¯ÍÏ®=§£ò¥Kíí:@]Ê8¾eè©Bæ:5v\x0001®¬¡\x0013¨ÆËt0;¿\x000bÊÈü\x0000\x0001Ks9Ñ8¢\x000f´o\x0005R;5\x0018]Å\x0001N¦"º?¹\x001dº|¨kê!\x0010>máì¿O	\x0002Ö\x001d§</p><p>\x0000\x0012h]ÕÝ/oðH\x0015æCAÅØw²Óé\x001ey°\x0010k\x0016\x0018P´Åü®N\x0000V4}\x001f\x001dl4À¼]÷ÇÓÇÆåhmY\x0000­¯\x0006Phy Úc\x0017\x000c¶MÆ!ðP\x0005?¤7P;m\x000eßãFÀÖP9ðàæáW\x0006Íªñ-%\x0007ÙnâBÙ2Þ\x0006s¾Wá.f{¬Û$\x0012­HÖ¡Ë?&°ÍÕ\x0002$\x001f¹\x000e¼¦`\x0015®-æÁV\x000f^rÀ!?\x000f¼Y2ÙÊKC¾Ù\x000e.dgA\x000e^hÀë Øì\x000eb(\x0004<tÔþD	ú°\x0016 ¥,l]\x0002\x0010^@oñ"ânÄ\x0015¨Ô«yp\x0015Z°Ú
©\x0001_#P\x000c\x0008\x001eÜnºJ	 ¡DÕ,Aêú\x0006k\x0004­\x0000<`Mê0±ÎÙ</p><p>zÀ</p><p>";</p><p>\x0000ø(\x0004Õ2ÀÊöçó^\x0004±f!\x0015\x000c\x0018"ëà\x0001°Ímß¥\x0008Ë\x0015ò\x0018s(A¸â|8Ý\x0003Ø\x0005ýp>£{àPùÙë\x0008pçyØ¸\x0013Ì¼¿­¿iKÁ°eõ\x0019wòä)POÜB`ðP-·Â¬Ï¦)</p><p>S\x0007àèÑK\x0004Õõt9f8×Ú\x0012\x001aiB?\x0008¸1ùìzäQÑa#4ð¼J­Èâk¥?\x0008BÝÈvÑÙ^ú^\x0015ÑGèÉÿ@0\x0004ÔÃÝ</p><p>¢ý\x0003S\x001e®ê</p><p>â,Ètw\x0010\x0019*ð¾öND®º(g(%ÑtyDíüÄVl:Ò¢è@líT¾ÛÆ©«9Q¡ä*\x0019ëía®BI 8Öu\x001d\x0007÷
ÈjÞpIùGä8aGÌúL\x0010nÊÆX¨Xa~^sËòi¦£mç§\x0017\x001e\x0010Â\x0003)Íov\x0011TÔè¶/âÛã :sb8Ôu%±'\x0003}¿VQX´BMe\x0006!¼\x0003Y9hQ\x0016iIA9ðø\x0016!ëpteØÃX¯Ø-\x0015\x0002"ÆBÝÇO[×\x0003YV\x0018\x00052½FÛe\x0003ÅÌv0ß^øH'ì*nP,Z
«½­\x0014\x0004èª¥\x0013åádisº°ÆÊ5ï¤\x0006\x00126ýT/ì\x0006°§\x000fÅþ« UÂ\x000b5u_üã @WÁ:*áü$áln¼ä4WWÐ£@}\x001b\x0010±o\x0011
3à?uïíí9:ìZÂ¯#$Ø\x0004\x00120Í\x0011}\x0011ä\x0011</p><p>¨Iý¸Wm¼d`GZÒeJ\x000cpM\x0018ê(\x000fBÈÝq4\x0014ÀÜÆúp°âfM\x0019\x0004Ë¸ð8\x0008Ô\x001at|NÀ#D®¢¤"ç`wCeî\x0006º"¢õö"dÎx	\x0015¹zÓy~\x001dxê\x0010à<\x001de9d
y.?Ð4-ÎqNð¶¶(ú\x0005wG\x000eþäè¯££hà`\x001dÆu"àn\x0017ÉíT\x000e38Ðíë\x0005\x0003\x001dÆ\x0016Ê\x0017\x0007\x0015\x001cCiÞIEc'=sò¦Å®2¾9g;Võ\ü~70Ê¨§`îÙÉÃ9TÓõFj³¬¹\x0015\¡^ç÷\x0019¿\x000fÈc^Ï¯ÉKgú~ª%1ÿÝþäÚÂÀG\x0011Æ°cNì±=\x000eb/\x0013Â¦öþz3|«½]Z8@y¼B{¼S\x0001²!Ú³ªüß<\x000c²@Û¦w=ð!l|Åè	RGëi¬»¤K\x0010Üí{Ýt^EIq~&6N !Z!N\x0003È§\x0011\x0001®Ûù
ó%ë£Ñ\x0012Ä5S\x0008¾x¢wÄ=Ó\x001d\x0014\x0011ªÄóF<JD\x001f6»\x0003\x00050t}¤C£ËSe>ÄÞÞ<zF\x000e	ñHÄ
\x0005Á}ì\x0013`IÕ<oe[¿cõT®¸r(\x001b\´ÿâØ'Ð) \x001fWÒMÅÀ.pSÉ+æ}¿ÑCa3qY³FßI²rñtÎl\x0011²?£ZÁà*ä^¨\x0004ð\x0016;¨Ûä\x00177c\x0006ÁAèð\x0003º?\x0010@NpÓ§\x0010µl\x00128«Ó;«¬ï-9|u\x0000Î	\x0013Ç0z^\x00130K%D½>·ß²}p.C\x0015CÀ[\x0018Û\x0000,kÝRÂ\x0015NÂ"Jwpºl7²|aÕm\x000fãp\x0006\x0011N·âç5¥z¹[Å\x001cÒá(È\x0017]jÊîkvã\x0007©gpÁA\x0012öèéU%îlV»8ïDö	G\x000b{\x0015D(¦ \x0012Ú|ÇÒH¢Mîî\x0019ªe	C20àj´ÍÛ\x0006ów­\x001etÓºR\x0011B×ò×¾3£F\x001d`}Ò\x0004(N2#7\x001a\x0002¸F8\x0006M2}¿Ú+°·,l\x001d\x001fÝfY@ÓKÈªU4)ä©Í§2<}®]|\x0000´ÂLwã-\x0016é\x0015\x0005¶¾Ýl¡Ô</p><p>°[Ä\x000bBl</p><p>KöiWïí¿\x0003«,\x0011ÇsU\x001fe
\x001e[í1?®ãF\x0019Dåá\x0010l/lìû%ìç\x0007X\x001b{\x001b5&ÞÃ¸S q\x0008ë¯ì£\x001bf`\x0008\x0007=TAÒH%³?¨°\x00158´ô\x001d\x0003<bßÆ8¢\x0006ã,§§M©\x0010ü§Å\x0004:{W©K\x0015¡</p><p>yVd!¼ Jõùð<ö:R¸ÁiXÊÚ$	¨À¹E'#÷ã92§ÖUÈÐD
D\x0019$øí!vøÎ£\x000c¿êAÐÚk:þýÇ\x0004Ýþ¦÷¯ÙÚÞn\x0017í6:l^s¸¯7ï\x00085I`ljy\x001ddy\x001a\x0018\x0004e:çof@&\x000b»ªtl5w\x0014ÛË\x000fã>]HQ\x0017\x0015þÊ\x0003/vp5¶`Y\x000bÞ`P\x0011²ÖO·6#Ø\x001b7v¶þ!Ê,ý{mcÅq¯#wêª"R§!\x001dßÛ1ïE;×\x000cB×jÊ9f¤Ç\x0000I>«\x0014 º)\x001dtLØ³ñyu\x0011ÚtÞU\x000c\x0007Ë£è31}\x000bö­\x00081àºÕ\x0012°\x0010æ+¾ÿLÚ+"N¹G!¬%\x000bº¾>ÃE\x0010l>{NÉdé×àl*\x001fÄ\x000c\x0004%\x000eþóV(,!&Ý\x000b·=\x000f!I\x0003þÃpD:Ã6ä\x001bö\x0000µû¦B7!\x00113ÇbJ'¨6À­ ³²>\x001dëP½Aº°Â¢ó\x001bæ­è\x000baRÊaQRT¦=HRDHÏtY@í</p><p>\x0004kJ#£©</p><p>\x0001\x0001ÖV<{\x0011FR@BXOeÙ£$;âLªËÛI
[×éÔ5ú\x0016'µ=\x0002"0ÛBã\x0013b#.!\x0012°oÅ\x0003\x0002Û\x0007LÉ\x0006­½}NÏ\x0018ë¡\x001b\x0011ÇÛ\x0005ZS`ÊÜù#WàÇ;§\x001aå4»Ö`ø±´Ýßâ.ÍÀ\x0014ê¡¸XR4 ×áJ8\x0007VâSêhAtÃ±X?\x001aqì\x0002Ù¯E^4ÆÃ#ÚØè_í2+²T\x0019\x0000Ôx,\x001e	%¹\x0003µ¥À'l`AH>Ñ¦KûYÐ\x0005JëÆ\x0017¥õÖ-µ#õ^</p><p>Ø÷ØXû\x0008DKärcÒ"é*¤Ùæõ ÃdÙV\x000f\x0007ú=\x001a¢\º</p><p>\x0005Ò"´°?/Õ\x001bS\x0006</p><p>hK\x0012ñÊ'"!\x0000×F\x0017tÍN;®Ûº¹\x000c£ÆOùË\x0018­êÝAG¿
z¼ô¿­4Mu;GÖMÆ·Á¤\x000fF;þ9ÆX^qÖ<L{\x001aK\x0014\x001bÜ¤²Íò4Ød,ü\x001e\x001dØ²4\x000cKç+\x0007´50TpJÜ\x0011»Ý&¡r\x0006o\x0012­¥IÁ¸F=q¹G)Å¢W\x0008È\x000bHsk!\\x000fV\x0011>«P~\x00114>\x0006°(å/{«A\x000f\x000cQ\x0012Ö~\x0003XD6÷pâ</p><p>ðå\x0008Åel\x0001\x0015æeÊu¿c\x0012WrÚ±Õà¹2\x0015³M\x000eÚjík±´Ò&«a';6¥*Bû¡Ù	ÎqX\x001eð\x0000íÌTÝ\x0000Ý?üÜv\x0008¬³\x001fðñ1ñvC~²\-í<²Ï²Ì³Ê$wa
?;¢ ç\x000e\x0002</p><p>\x0005Gt½\x001bctQ5 ´\x0019¿x
pPîãÉA»ØN\x0003°c\x0017ß)ÂÙ15NV</p><p>âaÖÛ\x0002¶³^uèÜ"<TÁ(\x001aÇÉî33²ø\x001cTB;%ØÛ9üàø£ª\x001eJ¾\x0008zÿ((Ë ¨ô0
£tÁïfÍBØ]5ÆÝ\x0001t\x0003j8§\x0015Ôa\x001er;ý\x0000æ£-D\x001d¥\x0012}/êÓ¢Ën\x0016£~\x0002(ªõ\x0019Â'õ\x000cö
þ½ý¤½æ»¿)JÊngk</p><p>µ=\x0016"ûaßà\x001cf\x0004e¾?(Ì×\x0000ðÌ±YØÞ[8n\x001c\x0001©p\x0012Ð&ÿÁj	ÙùàÏI</p><p>\x0008øÍ±+Y\x0010¥\x000eÌ7o\x0012ó =v´*\x0004Ïf¼0T\x001b&</p><p>68Ø\x0016\x0002BuÇ\x001fý\x0004©é`úàç¨\x0017Zê´SizI\x0002¥\x000e±I"Ð\x001bE8uÿ`Ú\x0005\x001ckTw¹\x000eqêç\x0000Î\x0019² Ð\x0011\x001d·\x0008ù(\x0004b(½z4\x000b\x0010 ûIÛ\x0010¸Nã${Tù$X×ë\x0013¨T]÷SDïþI\x001b¯O\x0008IØcG\x0008\x0004ø¯\x001fÚ0|K\x0013ÈíN+\x0012}oÎØ1$</p><p>0a:fùô49è\x000chñ\x001e5xV\x001bÅ$\x000cÎÁ\x000fB¼ÀEvøòiÝê"H:rQÝçWxJÔ\x001c,WNW!ãKiÃÌ¿_ñýeþY\x0011wt\x0015c3\x001eÀ
\x0003}\ÅI \x0014rû3-\x0016'\x000e¹BN¸4äÞ.BÆ\x0010Y¡oç{
®c««ïò\x001a>¥U\x0011¢],cìeAZ¤2¶\x000fs7J\x001a{ Ã\x0008²ü­A\x0018¼Á-qC¹2=Ð¬Ç%Ö
÷\x001c\x0010ô8AN</p><p>\x0014î°íhÞdz\x0012£¨G\x0010òÉ¶H×³rYÂ\x0011t\x000eCß [_ÀÈ´\x001a6ò£­ÈR/µ¤@mpfþq\x0000 ø\x0016\x0015©sh$G}\x0015ý"ÐKiÍ¼>:'È\x0013Ia !]èQÉ\x0002stCê¥S\x0011ÍB¼\x001crñ«9Ì}x»¼ÚA\x0004ËÒQ,Ã·û\x000f¸LfEDnØdc}ñg\x0011Mªkr#¤h¯¦Ï¸\x00128¡2É½&å\x0016\x0006½6È¯7\x0012¸ðØ$³<¯Ã¬kT\O3K-Ä.Z\x0007\x0011#b\x0005[Ênû\x0014ð)I\x0019yÞ	v:\x0003¿\x0011ñè®`Ö\x0011ç<¶÷DÝ°"x¤|Þ\x0011RÐ[tí÷\x000eCã\x001aáÀ!D\x0010\x0002äT o¸TNhêkÜX®
Sky«6ÿaé4¬:\x00158n=ÌHþ
§^ÂMÐ\x000fl°o2\x0006	á0±ò\x0001ÏÜÎ¾y\x0018tK:#\x0004ÅJ¡ôFOöu\x0001w9(áªßlÓuÁû5Ñ¸v\x0016SÀcS«</p><p>\x0015ð\x001eH­\x001f
#´¯±G+y¶§FÇ\.¢\x0008\x0010y)+S­ì»rPuÀ\x0015Â¼NBÊÎÎÎM±\x000e\x0019Ôk=\x0011À¿¨É</p><p>x@ÀNóF6sÁ÷\x0003\x00139Ë ¨-J\x001aã*²çåÊ\x0018</p><p>çÍY\x001eÐ\x0001\x0003m±^B\x001cr5ðëæX\l`\x0005r¸Ø^àÈ<ïôâ;²PEÁþ§=</p><p>ñT</p><p>´ñ~\x001d$Ý\x001c ´c9IRt'.ÕÎ,\x0004]\x0006,\ °^|è¶\x001f²²ý&µ}~\x001d1Ý¼8ÛGêóù¯¹\x000e¹{ªË Ü:²\x001eyèS·ëª\x0003ÛwlÂÊ?BXG)v¶\x001bµ³çº\x0004ñ\x001døè
endstream
endobj
69 0 obj
<</Length 65536>>stream</p><p>a\x000b¾Õ­\x0008\x0014!\x0010ª°²û\x0014\x0011NUC\x000b±t´¨\x0017p\x0012Àà$~®\x000em\x001cñÌ¶\x001bÀèñ\x0002"H!Ô\x0011¢p¬}Ï`û\x0010|\x001d"NZK](sX\\x0004±qÚK.n®¶\x001cõ»\4Nï|\x0004\x0001Ý6<+X\x001f Ä|4\x000f\x000f¤3ZKú\x0010\x0011¾vtå\ç¶¡}õ9µhA@ÉëaÈs\x0016ðuÐ\x001dw÷j,_\x0005],£¯</p><p>zÎ\x0002~«µ¿ÚÂCzïâ\x0018ê\x001cÈFµê:È\x001d-%7\x00192-m)\x0003õó-T"²Ø#\x0004ê¿:âù|ÒÛ\x001f½oLiËß²ò;õ/\x0004~6´ØÝ¦Ã c\\x001aõîð ²5@¬0W1t´³Gë-¥u\x0015\$ÁÛ¸0,`Kb\x001dê×þA»ÿ\x0006M\x00039úÒ\x0000B\x0014ð\x000fëGÈ\x000eQÑFx1ò9þf­h\x0005R\x0000|\x000eþ%\\änºFóFYe×Îrg¼9º¦óF÷Qj?¸\x0011\x000cÕÍë\x0010°äUL³¥Ôq\x0015ô\x001c¿ñaB(BúéU¼\x0008âd¼YnÄ¯\x0008"\x0001EQ\x0001`ÃÃ ADBë\x000e!A¤÷pèÚÏñ\x0008±#@ªÃëã"änË¡GÕ"\x001aÒÝu</p><p> ¬\T¿iP:³\bü\x001aª@\x000c~:Ä+\x0004\x0015ZÊm|T\x000cÎ\x0012¸a'Àÿ|tak@Á\x0016]\x0007H(¬ñ4á\x0006Ü¢0¡ÊGa\x000e=\x001d>\x0007PQyN¸6o\x0005\x000e¬Öò\x0015ó'å;?ß2»©pB8
(f\x00186+æ%.dá+\x0002¸+³¢_¬&\x0016úÏaO­\x0002\x001e
`j
BªH-ìßû2VÊÐ?ió×°wÓ\x0016)ùÀ%\x001c2õcA0m|6¾\x0005©¢¤>Ñx	\x001d>p\x0007/Ñ`è\x0007ÉÐï\x0000ö\x001e ;bãß¥t°¾'u*Á1mª-_E`kÚº\x0000í26~CTÛ®k·jIbÐ\x001bõ<d\x000e\x0008eËÖå¸¿çmÐûë Hµá\x001c\x0003\x0014Å²®\x001ex¯PéÛã\x0018HÓ\x0018øæÝ\x0018¿\x0019¯\x0010¢.\x001bDYy}@Tö¦÷3ÄöÁäÊË"A·\x0013ÇR\x0015UL¥+D3sí\x0000Ã2\x0016{\x001eßS¥AÞßþ-·\x00004
\x001d\x00169¸±\ÌAHêÃv/BÖ\x0000Ã	\x0014hwWÀvd{¡íyeÇÃæÕ&Ûµ\x0004z¸×1%²d`í\x00109À` 0\x000e¶¹ô<À3_|C\x0005\x0010ßÉc4qw\x001dVLø2ëä
Z</p><p>)ì<^ ûi\x0004¢}$Éì,}¬u½\x001d;IqLêi×8ÑÑ·5-æ-s?HËg<Q\x0002ðÉ`F·\x0004åmÈx$f¶Ó±</p><p>n=ûë4¬\x0018\x0011¬\x0003¨9p×\x0019Ñ;¢½9ßÐMq\x0006fZç\x0013!¤ÛàÖoTF\x0006nºêÙmÀ¨ìlÂx[)\x000cº\x0013ä\x0001nn2:\x0006:LG\x0012DzÞ~>Òh?gnì4\x0011Í,T¾í°\x001eàõ)ù0}\x0000ÙI=\x0018Ý§\x000c-ÔÖHÀr[
K»¹
ãzìÍ W[2.K£÷&"\x00014p\x001fÏ%ß.mí°\x001fè!e²:\x0002Ây@ÁJ[¯r\x00165èôn!X&{tÒOÅ\x0002\x0012\x0012§¨²íý9\x000bØ?Éç3Ý	J`Á½4úÓ[ý\x001dq»x²Õ\x00074&
É=Åù6gó\x0008m[î¸¿yy¤//2¼{'½,x[u\x0008\x0014 ,p\x001e\x001a!
\x0008.X­ \x000eG3\`aû4êpCÇä"\x0008#\x0000<à(9¯S\x0011
aXá' ²1HØñþT<\x0017\x001d|EP¢	?UÒø</p><p>ß³|\x000cF\x0010×QB\x0002W\x001f\x0012Ï\x0015ôµñC\x000e\x000fCdFÈ$®û¼\x000c~Ô°\x001c\x0012L MÀ()¹(\x000fÔ\x0015ðÈ\x0003}\x0010'zôí\x00105JîÚ\x0016ds\x001c</p><p>Û÷\x000fÐùe\x0010R[e+ÆÜuQ	p¨\x000e±ç\x001d¡Î\x000eÚ</p><p> v[!\x0018yÛþw\x000bG\x0014\x0004\x001c.ÓT\x0008\x001c\x00034ûM°\x0006L1!·q+)Iß±p±¡MÇ#B Ûl4û\x0010F¿\x001en@\x001e|BK	C&»Ì¶\x0018²éhTO#\x0010¹\x001b2,¬ÝÖøÂ[
Ãð0æCU\x0003OZê\x000e¼î(­Ì\x001b±å)ëq\x00079\x000fpCãE\x0010D\x0007\x0011\x0008÷ã àº¼´	ñ¶ {Dí~;[\x001b¹Ó	t\x0004Ù\x0012P­¿qXBSú²vÈØëýWÙ\x0018 èå\x000bkïYj\x0002.m±</p><p>NF¸ÞÑfmóò² ÛÎ±©wÄZ\x001a×©Ã°ªú
\x0008r÷:\x001a¯N¡DìÎ|\x00112n%8ºí\x0012Íå«ë¼\x0014Ô¤_éåó D/C@Î\x000cy\x001b5Ñ-\x0016ä\x0003â6\x001e\x0006g£¶Eùa.ÃmæõCoV\x0008»¥ñ\x00060B\x000cÀ0ß4\x0015\x000fûÐ"(Î|°âg`\x0019ÀÒ\x000cs\x000e<\x000c\x000bÞ~E8Iø£·9¤\x0003­	¥iëÙA}«3F=.VZzßeéÛ9¤\\x000fººÎ\x001a­\x0005ä\ìWF
e\x0007\x000c÷Èm°ö%'¥\x0013/=</p><p>ÖL\x0004.<«÷ÖUp6G¼l\x0015¸l.%±½Õ¢OBW­®Ý­¨íÆß \x0001 \JcaÌfY±÷û×Po¸¦vÿ0Dçq¸eÞê"è\x000eÅ\@OyD!Ð|h×AkW±­2¤Gxèë %,H$Qÿñ¬æíä0ÕGP8#Õ\x00089/ckê~\x0010¤²@.C \x000b\x001f\x000cÐ°<2ßjh50UyüEÈ\x0007Ý</p><p>É\x0005Ü\x0008;n|w×¡03¼ 	¦c3B²eñBÙÒ\x000b)Njqiq\x0001ó¢|nviªX9\x000519\x0004WT(\x000b»ËÚ\x0006é©`\x0017(\x000bûË\x0010p"*æÃÖ ìPq\x0007wRY¦ê\x0015®\x0008(.\x0012ò</p><p>¢JQ,m@pP ¼i,à0Îñ1¡ã©¤\x0015T\x0010s\x001cT¢\x0003
\x0017²<Â\x001dÌXsHnÌ ú¸0"â\x0001íØR`Z¦\x0002¯_ÔObb³%ÏjwÝö\x0014Ú</p><p>±BTß×÷DZ\x00155©¾\x0019¢\x0019UöÆ_±è14Ýa\x000bcÄÜ\x0004lZ!%¨×æ+¼</p><p>AB\x0018âù!.b£è*¹¼/SÑCýêv\x001ao¡ø\à"W\x0016\x0005Á¾\x0008_\x0002\x0005\x0011ão5mOÐûGAªð\x0017. \x0008m3Ø}¼f¨>,-Þ8TÞ</p><p>}¢Ó\x0001þFHÌ\x001bdT`÷óG'ú­vâléø8\x0019M\x0006=\x001e~ú{ ó|ª\x000bxÚØ/tc\àÎì¡/¦>\x0003E\x001a°ûõ@ö\x0000=¼OJ\x0002¹à_ÝÓ|p4Ð\x0005\x0003\x001fù ê\x001ab(òK,Gäb[\x001fWR¼R\x0015/3\x0008Æ\x000bÚðµoØ\x0017ÈsÊr(\x0004Öº=k?à XsüW\x0008
iE`+w\x0008âf4ÉÂ\{ª8rø\x0014\x001f^\x0007y\x0018+Ô¼U;½ìzÓh'\x001fp¢Í>\x0008\x0001ª\x0002ò+¯;½a\x0018Â¼G<b<¹Nõ\x001f~ÅÃ ]àUAÚO(6NmÖn:o+MüHÏB´¶#|l¹\x0017@MÌÙ\x0007Av4  ó´FÎ¯\x0019÷_¢B\x0005\x0006¬QFg·I"'`n\x0004¢g9\x0018^_# Q\x000e¢á¸å\x0001Á\x0012R;NTË)§CàÐ*ì\x001e`(	²\x001a´zÌ¨ÚtMD\x0018N\x001d>\x0013ÝKØØä1Q\x0005£\x001cØÊ^\x000eHHÖBØû(sÏ!ûµÅ²¡(UÁb×\x001aæ\x0006\x0016æM}\x0018¤tu®ìýä6èá·ìh\x001bBQy\x001cr>÷·DÀ\x000cl\x001eÂ{\x0015;çf	?¨\x0007A ßuöe{GË\x0001ÃAsnºØ3E£'\x0000íZ>ÆAS5¡XèG:E\x0005 ÍÃáa/à\x0011+y¸®±:¶\x0000KÖ\x0002ÆlÓV=C@Q\x0019Ý!N%O*PmÝ*GBèÈç\x0017ÌÌÔ\x001f\x0011Ô`wu×\x000eè\x001c£gñP(mÝ?ãc¥0ïä\x0011|ëQÏ\x000bèFô§Ë\x0017<¹`ÔA½\x0014".\x0018@A?Îe×A$E^Gú5\x0005Ít{ô
]å¸H^\x000fNá\x000bUÅ\x001bÑ8\x0004\x001c½Àó©</p><p>`\x0011j´G¹ ú\x001a\x001c</p><p>ß+Ö¹\x001dÕÐE:¸"Î²ØL\x0019Ô8ql;´z\x001c~ö8ý#³OÆæè\x0016Ü¬.õ</p><p>ñí{\x0004c·vÜ#ßb\x0008\x0000CÁ-(\x001dJwd\x000cRv~@\x0015ìwLgN\x0008R ¬4=[Ñá±¯Ûq
Âøáî;v®BßÞC©ioÇ0Ëàh[	BÄ</p><p>WÁ~È^è2¡éWÝ\x0006N®¢Ý¡Gq"(C\x001a¿5g5·\x000fÛ]\x0003Ù\x0014`IÃÇ?Bà\x001d\x0019Tvç/F?\x0012~SêÏ-F\x0018S \x001fx,\x000cï¢ðb¬\x0005Äë£\x0010Ð M3l£\x001f\x0004á,@\x000eÒ~
XO·Wæ ¯ç>\x001e6)¯ªÖÝÎ¼
\x0019wb)CW\x0005ÔÐë¦@\x000fô¦\x0010\x0008k\x0001w£T\x001eô:¨ðqßêep=TÚx\x0010ÿ\x001a¥#\x000e\x0019\x0008k}\x0016½ Û\x0011\x0004\x0013?ÐçLÕ¨Ï:WÀ*°T)¬®F"ÑV\x0008þÕIýê£ªµSæ«\x0010ù¦eYö®qô`\x0007Òäç­*uT;uly\x0006*ÈK©Ý©</p><p>_/´\x0003£@Ò\x0008BüFG¸¥¤³\x001eÛ\¶C0jëCEq©§ô,\x0003]ë×|)jB9\x0010Eþa\x0010\x0005XC|\x0006sZAcÞAÔ\x00043rl£ñújÈû¬uÀ6+ðå7X Zi´A§Ìwà2(Ét\x001aJ$32\x0016ÓÃgÚxÍY&v#*|Ú8ö+ä\x0014\x0006Èss`a³³VÛa\x0002îÝò=\x0002l5\x0002y
ªâÑ\x001d4G\x0013}\x00160_wéÔ\x001a]7\x0005®H9¯ûpr×Ï\x0018\x001fûB±:ë°vãxcláú×Bü±7$êæà9«)\x0011Lníe8Â8¥\x0012[Ñøznüb^</p><p>DÿnqoM\x0005©ø0¢I\x001d\x001fg¡y§ ûAßQ×KT\x001fòn7½\x000cB®\x0007\x0016/Ïjd\x001f
ºýMï_v½]¬ÁUâX\x0006ùüç5²ë ºûðà%åßH\x0019Pêºî\x000fv[Û¢±LvÄ¶«\x000fº\x0015NÍ²U½9<>¿N\x0007\¯?N`ò)êÜ,"\x0018|ª6¬\x001e?ù*</p><p>>|ç%3±°ô;N`EZ­Î©\x0008½\x000c5+oÙ$W\x00060O#\x0004¸ÇþØ\x0013XÂ\x001f5ï»}\x001d×ÁöFIiyêw´n Cå83\x001cåA\x0007Ô\x0019DÝÊÞ1(á½ïÝ Q­µ\x0011\x0000ú\x001c¹C,¯Mýj§c*åt¥ªS·¬ BØ¾Ö.õ5ß\x0002Çµ</p><p>Y¿fÉ-÷ÃQ-§ N?\x0004g\x001dô</p><p>hkÈ´\x001dà8{AE'\x000bÉÚç¤k¯¾:!{|õVÝ\x001eª\x0010h\x0000\x0011\x001f^\x0007ëIÜì\x000fD\x0007\x000f/à\x0017ù\x0007BnæÄxª ;+o9@\x0017¶\x001fþØYÎ0l\x0014¯Rÿ1AÏË</p><p>\x0012vc°íÆ«Æ\x001eMt.çW'ùvT¸zãM£¼ÚÔ:\x0015·»7m\x000bÂÀ¾-£@6Ò\x001cM;-ÜÑN×õqZæiC\x001f2~r##wØ¯m!p¶VÞkYN±¶\x0013HÕAÀô!>Ör\x0014~_\x0006%i
£\x0004w`4ä\x000c¸Éæ\x0019Ä\x0004¢ÚÆTT£AÐ£¾¢ylæïß3|K¹ï÷s¿\x001eò¥ÀÎ\x000e{½\x001eÚ*åPÃªÈ¹Ý(ºô\x0006FJ'Èëç#ú:èå8Ä\x000eêG*ýÑ`½Ü/^\x0015ô¯W(C\x0001 Gî7V\x000e\x0018â´åy@\x000cö\x0016ÐÀX\x000b'´)KÈåNÌ0«\x0002HÚº}$9á\x001cýø\x001c\x000c@	¼OÙ§\x000c67\x0004PEÞæÙQûf|Ù`(qâ9++®_R©y¡\x0018ÊÜxì\x0008	 "\x0018ÿ\x000f¦[S'#QA\x0015%\x001c%IÎ³^54\x0018Af}»Á\x000c05í\x0015\x0012Q<qe{½yÔ\x0003úV}\x000eÔL¼\x000fâ\x0012ØcÙÐÃ|È~
ºÕ$ÀùØÁ=+u4>TöÇ:í6d.\x0008\x0008\x001fÁÇGå¶}î·õÓP£êç×YÔ ÖØ\x001ae\x0016¤\x0010è5´£^fQØ%@\x0004ÄôhÕ \x0008\x0019\x001e[Y]¸\Â	i°¨ð´<"s´àD>A[\x0010<ß¢8ÖØ\x0008ô¶\x0006N\x0018D3¢\x0013\x0007iY%/Ý<EThíø½\x001c¤%òãö/òØþåê$\x0019³A¦<TM|°Ñ¥Þ¿uà¡\x001cÊ\x000bÍÏË$êq\x0005Ñ·®\x0001õåä\x0013ö\x0001\x001c;Ù>\x0003!Á:W\x0004Ù\x0012Ày$\x001e\x000bSÉ¨"\x0017\x001cçu¼¢ôïn)Þ:Ì7\x0010«\x0014ú°\x000b\x0017!óC\x0005X_ANJ®ãU\x0007V</p><p>\x0007\x0008Ê!×^Ncjm@ú-¯ú³=ü\x00108Ä\x0016üä\x0000âíX½nÅY<ðÔLn\x0019ÜÕK\x001bÐv\x0008Nbý"äääÀª\x0011sÍòà:Ð	ñ¾\x0013³yÔäQ\x0002Ïix\x001c,© ·y5"g\x000eýG"9P3gNµq\x0015ªÔKn¹'`\x000f\x001c&5||Nï\x001böB\x0016¹bFû²óÚ\x0013Mô\x000b8ÌÛ×\x001c\x001e!;FÛoóÔPe\x0016\x000eo\x000fXm\x00001eÇ0#è\x0017Ùq/»åív§§Ó¶'¨;¹T	\x0014ØàqÇÙ²®Q\x0002\x0010\x000cN×à¼áÝ\x001a¹	+ï¥îºQE·£\x00086²g&Ä\x001ed%ç\x001ag\x0004róSOÏ\x0008·áß<Ý\x00121<Ö<6Í(é§´ß\x001eç:>fºYmìÎy\x0000«ô\x0015Ð/ w.Q\x0016tT´){ÇGk\x001fúk7.Ð÷×Ñ¨ÑfÐoòdÞúÂ»3ÀeÐý\x0019`Ì\x0018R*×bz\x0010t1É_\x0019tw\x0006øøVôfµ</p><p>\x0011\x0007Ýp~\x000fî®\x0011ñ¦o\x001eÆ\x0000½$ÇXaOÐRy½é</p><p>âZmÎ~À3\x000bd`:\x001e]\x0006Ä7hK\x001a\x000f{\x0014ºJ\x0017EöËu¬¾è\x0017lSäiç@ur,:Q\#û7\x001c_Ù9$Þñx&mÐòt<\x0015\x0008ì\x001cè\x0014úþ(Dv\x000eh7\x000c\x001dý« içJÎÎñÝè Ê a\x0017j±spqh\x0008\x0013Â\x001b Ý»®A \x00082Ï\x000f\x0015(ÿ"ÚsD¢æ<H\x0012j·'©\x0003,¢0"l\x000c8\x0007\x001e\x0001\±\x001dá(øu'zhëp8rs\x001eÇ\x000f~1j¦-;U{Þe(F\x0010\x0006{·º</p><p>\x0012:\x00084&\x000cð	\x0019tÖ\x001bÒù]ô»¨:m_¯\x0003JòÑ?\x000e\x0003|X1±Ð\x0006	Gq\x0010/\x0007LEóº\x0010ýn\x001a\x001cµoÖ¼\x001c"a|.4ö¨ÆÅ!Ñ8CP E\x0019SF?ô®ì\x001eJÞÎ-äå[Ý\x001cîI½ÙèTÚm:¼\x001c0\x001d×\x0014æÄ`$²}Ë\x001bÊË!aÝ<f\x0004Û\x0013ò;È=®\x0010Ê®TÖ\x00076²"Xl»,\x0012ðÞA³í~Cùþ:¨ÈÕþ3J¨×A°FÀñMB%½¸ï3\x0014¾fr·\x001d]¸:\x001cÿ*ÈÎ²¥»@^áçgeÞfN.ç,Æ¹2v\x0018!âè±Ãì\x001ee\x001dÄ2Ñ\x0006¼Fá\x0011Ý\x001büh±)ÏÀÒª\x000e^¶ÊÉ\x000cr;5ðqpÎ-óc \x0013
Öç$\x0019\x0016"gZ¤íÆ­ÂÀ\x000b¶vHzCÉ\x0010VóEÌ´r(tµëÃ\x0018\x0011ÞPÑ\x001bg1ý 4,î{ßR\x0010ÞÜnM\x001fÐô4¢{NÁD\x001cç³3\x0007\x0010
;ú8(_ÒaýS-'Qµâ®°r e{ ÏäÉ#ÎÚ)°rjY×jyG0BëõXâY#"TéÑ\x001eV\x000e8qF\x001eÕiåÀÑ9>\x001cõÃÊ!ÛVÕçH#G=¼,Y0ÐG\x0008óGS_§\x001d\x001cwqë6d¾\x001f|Ópn¼¼\x000ek\x000e?Ð¼üW¹\x001cÝÁ±a2¶ÞNùO</p><p>h\x000cC</p><p>\x0018Ð®ó)- ¼\x0019è\x000eU]&áÌ0ÚQ:ÇÊ¡¶ØGH\x001aìà£¨CHRê¼Q=l\x0013\x0002\x0012ÿþ5p%\x0014Ïj]ýÑNCÆ­v\x000c\x000b R~P8wVXAçÀ6Xë%å\x001fÐÙíVZ\x00086-é¸\x001e~>~îFºúá ®®í+ÓÜ\x0018óÒZöÓæ2F9$RÚmÌÃDí-ý½hÁ\x0014ôÆÎU\x0000U9\x0003õ\x0019þ^Ø\x0003\x0014i0mb\x0011\x0008ðì \x0007\x000eESôª:Ö?¶LÄ\x0006}@Sí%nG\x000c[¿é££¼nÇALLDÌKPn¯\x0012\x000fI3^§$,ò°ð\x0002×]Ë°l;!0N4úlXú hØÐ~Û\x0004.8\x000eù°Ð©õ\x0012]×Å\x0002Ã«\x0006÷G08\x0019Mºe¦´\x000eGDò2R¡âÀ¯åu#Ëº&@\x001cÏ$ÒéHê÷\x000b$ÉàÇåa4\x0003I\x001cZ{wû±»4\x0017é\x0004¬gªrÎ¡\x0012sBª¬`úx3³\x001fÎ~æÐã8\x0002½Í\x0007_\x001c ¦ß6?<,Þn\x0004â]q\x0018\x0004ýY:µc\x001azË Ü4·egýi\x0007%lù<èý£ "q{G\x0019B#pÞ\x000e¯Ä\x0005~eÐÝí>þÃßY*\x00078D]·r°u£êÅ,eBÐÃ¾ØÒÉ©n=H!\x0013\x0004:A\x0016ïÈAHDÇUéº¥ÍBÎËÍJ$¼0¶\x0016¿A-\x0015\x001e<¶u\x0006±UP».º</p><p>¥R	e]\x0005#	ÛüPSVä X-Ð\x0010ÝÉ\x0006\x0018Õ¶è0o\x0014E\x000f#ëº\x000eV</p><p>øÙ.\x0001\x0008Þ\x000ec\x0013°_W¨h9:ð}\x0005aêÓ³$éV\x001bhVÑFøÑY·½a©H\x0012ÙÃþêçuDäT\x0005\x0011Mú:\x0008[ä}ÇSewãú-\x000egKRI\x001fáA\x000f]ä¬\x001a?\x000f\x0019wÂ*Ä±0f\x001f]f\ðçì\x0006¥\x0017µ8\x0000ãCÎ!ìÝ\x001f¨×QØ@,oðÇ\x0008\x000c4!§'ÅTðx\x001coÏv0Tc[O}døî>IÊ\x0010ú	2B9\x000c3Ä~\x0011:	0ÔçÐÞ\x0001\x001eeËÿú9\x0000ø8d
a\x001f\x0001á\x00056óyÿ\x0008\x0008\x000c¨\x0018¾¸µqfCYµ­[±\x00027\x0004\x0016G:ã^Á')NÚ¿Çf\x0006ÒÐC¸G\x0010ÖÂy\x000bÑ\x001d\x0002}Õö\x0011úGº</p><p>Ö\x001dÔNHjÒl
S	\x0017¿?\x0004²IöÆN\x0010]*N8T5\x0015âaüÙë\x001a#\x0017èà>Ò+DN3~fq</p><p>éj´a6?ÀøôåA\ù\x001c\x0008q\x001d0`(D¤\x001cö·U
n3)Ä«×bM\x0017!ãV }ß|ñ\x0013ò~ ùa<ÑÓ3"K«Ø£­ \x000cü\x0014ÂÁú9 É ®¯Õ\x0002¨\x0016«_]e\x001egkT[¼\x001e4p\lx+'Ä~?/}è3e\x001a¬òïÉéýø}Cü\x0018Ú	8àÆÞ!  ìµÖ¹\x000e$´nóèý¬\x0010ÁÉ0 *ëVoKO>Ô5=©ÝÊrì1!Ø¬ C.ý\x000cêíóK³|ü\x001a&wBKd3Ð¸î4?\x0003Îï0\x0014«:ßZÜèç°¹ñÉ=evr¤ÅÛ±å6)oNzu8Â\x0015àd`j×U@®¡b\x0005ÉjÞ*±ýÜz;èLh¸_ÌÃ°$[þ³÷¡</p><p>\x000c,õ¡B²Sa¡Ø´®g?Ë\x0013/ëýå\x0004N\x0001åZW\x00106Ìüà\x001eæÒ\x0005²¥\ï'\x0004aW</p><p>ôO?´u²÷\x000cËï¯o«ÆÔ5@ ëzCÌY\x000fM(Íí\x001cZ¬íÅXU¯×\x0016\x0001_i¾hÚ/û\x0017
_DNX®¥;§ºÖøb£D\x001f\x0017ùÃ±4\x0001Ágí½Ú\x0016<jERT\x001a\x000b·+òGZj×6x¢Ä\x0008\x0004ÝÔhÇµ=ãCú\x001e_ðlP5óVyG³1îqJ\x000b\x001dhz?\x0006\x0012È~ö¾Dªf)æ9°aeëó</p><p>\x0005\x0007Ø©+äÚ\x0001 ú´n;E"\x0005\x0018ÏD~U\x001e]9\x001e%!mËØg\x001e|'ìX&Æòã\x001fó-Ó@à!ê/k-íèÐÐËu\x001b´A¨\x0006Øi©Ì \\x001d¡%7\x001e½Û2\x0001a1OIÖdD§)ËÌ\x0015\x000eÃ
;H\x0000ßÝ\x0011è\x0019´¤ú~t\x0000i¨:NÑ\x0018m²2\x0010(:ðÚËàúûºUÖÙÎ©O\x0004L\x000e</p><p>eoÂÐ{\x0013@~.\x0005\x000c|Õç1^Ïd?q:Ç</p><p>jòzkëF
OÉ0[\x0005Y¾ßX¿u?õ}y}tÝ\x0004Ï;ýÀ\x001d\x001c\x000bï¼s3¤+!ñø8ÓÊY\x0014/­9\x0019eÚø\x001e\x0013æ#_ê³7\x0015¾Ï\x0007ià c;»0Ùìâ\x001b\x0005QlB¶¡Ö½iQ\x000eüØ$pGÌ'/ë\x0012Òmúså\x0008\x0001[)Õä¾÷#{ÁîÿcïÝv6I²ó¼+{¨CJ0K±ßÈGDÛ0\x0008´}"Éð\x00191*5@Bì!1\x001c</p><p>öÝ;wE¬Èªú¾®6ü\x001fR\x0010\x0004õÔú3¿ÌÍµÞ
öÞõl\x0012k`æÐ@\x0008xJIa\x001d±XKeØ¦ÂL÷ÁLæa¿f=ÐÄW\x001eÂ§§+w\x0006\x0001Q-±j\x0010>\x0010±Ç\x001fý|÷Ìx\x0004p/ýÀÆª³ò(¶\x0005Ïv²f9ÖVI!
\x0017ÊGðï\x0005Ó@Öw[\x001e¢\x0008¯bçä\x001dÄ\x001bY0ÎuDwD/ÕsALaîÒDüÇ\x001f2</p><p>\x000bÇ\x0016[vñ\x000cØªSßÍ'û8=eÛì©è¿\x0006DÛö\x0019cÆÁf(vo\x0000s++îùÈ¡6÷6Ë­ \x0002£ò±IékIü¾!2I{\x0016`GÈ¬ò³=TEÊ\x001a	1?{&\x0014\x0002ª¬£Îûc\x001e¡|ÔèHeÐghl\x000bö+Ò=(Ee;ÈW´XíÇ 9\x0013×\x0018Ç3.|V¹Äyg)lÐd\x0007\x0012\x0015ý´Ç PV4í:¼Lxx\x0008)'\x0006éÉB</p><p>¢\x000f\x001f³oÁk!ír)´îÿ</p><p>J,¦Ñä×Á1­fá hm 9\x0016\x001e©\x0017\x0010V\x0000OöÜ"Ý(÷jþc\x001aÌõ0}ø¡¯#®Û~ñà\x001c<`¨\x0005\x0014Óa\x0017(Ê×ìgáB)\x0007\x001f£n³Rt< ª\x001fÎQÖá»iêõHã\x0000Vt>J 9Cº\x001d{Þ¬9°|°núé÷,L\x001fXU,±¢:\x00037ßAØÝ\x0004\x0013m\x0000êT-ã=¯%\x000caæ\x0019m8\x0003ÜGü\x0011\x0015nÏïe\x001eÛë	Y\x0015«~þ¢#=¦ÕùdÈ¥aaq~
,ÞÌú°GÌ?&Íbß¬ù~\x0019BÐÜ!\x001a§\x0003\x001f \x0002\x0018ÆõkBòAhÊð¥ú*X\x0019Ê4\x001dë¾\x001aUHú¦¿uª\x001f{\x0016Gz@\x0015¡ _*Âm¸>GÂ\x000194Â9ôÑ\x0000(RÒ\x001f\x001a\x0019Ð·eÂ\x0011|ÝV¢ÀÑ£íñµ\x000eevòôB\x0004\x001aÙ;îuEC¬	ås\x000c\\x0003bLë3Ì5ìíV
a4|¾o\x0005$i¬\x001cdf\x001fÊko¾vÉº±¢\x0008¡o#F\x0008RP¬vÃ~¦>×xk\x001a
Ï9qS¬ÞßÛÕo\x000f¾\x000fÝó!Q¸Ô?></p>
  
### Reference
* http://blogs.wsj.com/cio/2013/10/08/adobe-source-code-leak-is-bad-news-for-u-s-government/

  
#### CWE Id : 540
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Cookie No HttpOnly Flag
##### Low (Medium)
  
  
  
  
#### Description
<p>A cookie has been set without the HttpOnly flag, which means that the cookie can be accessed by JavaScript. If a malicious script can be run on this page then the cookie will be accessible and can be transmitted to another site. If this is a session cookie then session hijacking may be possible.</p>
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/accounts/login/](https://aidantsconnect.beta.gouv.fr/accounts/login/)
  
  
  * Method: `GET`
  
  
  * Parameter: `csrftoken`
  
  
  * Evidence: `Set-Cookie: csrftoken`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/accounts/login/](https://aidantsconnect.beta.gouv.fr/accounts/login/)
  
  
  * Method: `POST`
  
  
  * Parameter: `csrftoken`
  
  
  * Evidence: `Set-Cookie: csrftoken`
  
  
  
  
Instances: 2
  
### Solution
<p>Ensure that the HttpOnly flag is set for all cookies.</p>
  
### Reference
* https://owasp.org/www-community/HttpOnly

  
#### CWE Id : 16
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Cross-Domain JavaScript Source File Inclusion
##### Low (Medium)
  
  
  
  
#### Description
<p>The page includes one or more script files from a third-party domain.</p>
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/](https://aidantsconnect.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Parameter: `https://unpkg.com/url-polyfill@1.0.14/url-polyfill.js`
  
  
  * Evidence: `<script src="https://unpkg.com/url-polyfill@1.0.14/url-polyfill.js"><\/script>');
    }
  </script>`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/sitemap.xml](https://aidantsconnect.beta.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  * Parameter: `https://unpkg.com/@babel/polyfill@7.0.0/dist/polyfill.js`
  
  
  * Evidence: `<script src="https://unpkg.com/@babel/polyfill@7.0.0/dist/polyfill.js"><\/script>');
      document.write('`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/](https://aidantsconnect.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Parameter: `https://unpkg.com/@babel/polyfill@7.0.0/dist/polyfill.js`
  
  
  * Evidence: `<script src="https://unpkg.com/@babel/polyfill@7.0.0/dist/polyfill.js"><\/script>');
      document.write('`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/sitemap.xml](https://aidantsconnect.beta.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  * Parameter: `https://unpkg.com/url-polyfill@1.0.14/url-polyfill.js`
  
  
  * Evidence: `<script src="https://unpkg.com/url-polyfill@1.0.14/url-polyfill.js"><\/script>');
    }
  </script>`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/robots.txt](https://aidantsconnect.beta.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  * Parameter: `https://unpkg.com/@babel/polyfill@7.0.0/dist/polyfill.js`
  
  
  * Evidence: `<script src="https://unpkg.com/@babel/polyfill@7.0.0/dist/polyfill.js"><\/script>');
      document.write('`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr](https://aidantsconnect.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Parameter: `https://unpkg.com/url-polyfill@1.0.14/url-polyfill.js`
  
  
  * Evidence: `<script src="https://unpkg.com/url-polyfill@1.0.14/url-polyfill.js"><\/script>');
    }
  </script>`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/habilitation](https://aidantsconnect.beta.gouv.fr/habilitation)
  
  
  * Method: `GET`
  
  
  * Parameter: `https://unpkg.com/@babel/polyfill@7.0.0/dist/polyfill.js`
  
  
  * Evidence: `<script src="https://unpkg.com/@babel/polyfill@7.0.0/dist/polyfill.js"><\/script>');
      document.write('`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/habilitation](https://aidantsconnect.beta.gouv.fr/habilitation)
  
  
  * Method: `GET`
  
  
  * Parameter: `https://unpkg.com/url-polyfill@1.0.14/url-polyfill.js`
  
  
  * Evidence: `<script src="https://unpkg.com/url-polyfill@1.0.14/url-polyfill.js"><\/script>');
    }
  </script>`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr](https://aidantsconnect.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Parameter: `https://unpkg.com/@babel/polyfill@7.0.0/dist/polyfill.js`
  
  
  * Evidence: `<script src="https://unpkg.com/@babel/polyfill@7.0.0/dist/polyfill.js"><\/script>');
      document.write('`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/robots.txt](https://aidantsconnect.beta.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  * Parameter: `https://unpkg.com/url-polyfill@1.0.14/url-polyfill.js`
  
  
  * Evidence: `<script src="https://unpkg.com/url-polyfill@1.0.14/url-polyfill.js"><\/script>');
    }
  </script>`
  
  
  
  
Instances: 10
  
### Solution
<p>Ensure JavaScript source files are loaded from only trusted sources, and the sources can't be controlled by end users of the application.</p>
  
### Reference
* 

  
#### CWE Id : 829
  
#### WASC Id : 15
  
#### Source ID : 3

  
  
  
  
### Feature Policy Header Not Set
##### Low (Medium)
  
  
  
  
#### Description
<p>Feature Policy Header is an added layer of security that helps to restrict from unauthorized access or usage of browser/client features by web resources. This policy ensures the user privacy by limiting or specifying the features of the browsers can be used by the web resources. Feature Policy provides a set of standard HTTP headers that allow website owners to limit which features of browsers can be used by the page such as camera, microphone, location, full screen etc.</p>
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/faq/mandat/](https://aidantsconnect.beta.gouv.fr/faq/mandat/)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/robots.txt](https://aidantsconnect.beta.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/ressources/](https://aidantsconnect.beta.gouv.fr/ressources/)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr](https://aidantsconnect.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/](https://aidantsconnect.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/faq/donnees-personnelles/](https://aidantsconnect.beta.gouv.fr/faq/donnees-personnelles/)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/accounts/login/](https://aidantsconnect.beta.gouv.fr/accounts/login/)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/habilitation](https://aidantsconnect.beta.gouv.fr/habilitation)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/sitemap.xml](https://aidantsconnect.beta.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/guide_utilisation/](https://aidantsconnect.beta.gouv.fr/guide_utilisation/)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/faq/](https://aidantsconnect.beta.gouv.fr/faq/)
  
  
  * Method: `GET`
  
  
  
  
Instances: 11
  
### Solution
<p>Ensure that your web server, application server, load balancer, etc. is configured to set the Feature-Policy header.</p>
  
### Reference
* https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy
* https://developers.google.com/web/updates/2018/06/feature-policy
* https://scotthelme.co.uk/a-new-security-header-feature-policy/
* https://w3c.github.io/webappsec-feature-policy/
* https://www.smashingmagazine.com/2018/12/feature-policy/

  
#### CWE Id : 16
  
#### WASC Id : 15
  
#### Source ID : 3

  
  
  
  
### Incomplete or No Cache-control and Pragma HTTP Header Set
##### Low (Medium)
  
  
  
  
#### Description
<p>The cache-control and pragma HTTP header have not been set properly or are missing allowing the browser and proxies to cache content.</p>
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/habilitation](https://aidantsconnect.beta.gouv.fr/habilitation)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/images/favicons/safari-pinned-tab.svg](https://aidantsconnect.beta.gouv.fr/static/images/favicons/safari-pinned-tab.svg)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  * Evidence: `max-age=60, public`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/images/favicons/manifest.json](https://aidantsconnect.beta.gouv.fr/static/images/favicons/manifest.json)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  * Evidence: `max-age=60, public`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr](https://aidantsconnect.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/faq/](https://aidantsconnect.beta.gouv.fr/faq/)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/ressources/](https://aidantsconnect.beta.gouv.fr/ressources/)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/css/home.css](https://aidantsconnect.beta.gouv.fr/static/css/home.css)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  * Evidence: `max-age=60, public`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/css/template.min.css](https://aidantsconnect.beta.gouv.fr/static/css/template.min.css)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  * Evidence: `max-age=60, public`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/](https://aidantsconnect.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/css/main.css](https://aidantsconnect.beta.gouv.fr/static/css/main.css)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  * Evidence: `max-age=60, public`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/accounts/login/](https://aidantsconnect.beta.gouv.fr/accounts/login/)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
Instances: 11
  
### Solution
<p>Whenever possible ensure the cache-control HTTP header is set with no-cache, no-store, must-revalidate; and that the pragma HTTP header is set with no-cache.</p>
  
### Reference
* https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet.html#web-content-caching

  
#### CWE Id : 525
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Base64 Disclosure
##### Informational (Medium)
  
  
  
  
#### Description
<p>Base64 encoded data was disclosed by the application/web server. Note: in the interests of performance not all base64 strings in the response were analyzed individually, the entire response should be looked at by the analyst/security team/developer(s).</p>
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/faq/mandat/](https://aidantsconnect.beta.gouv.fr/faq/mandat/)
  
  
  * Method: `GET`
  
  
  * Evidence: `2-Avoir-des-mandats-dans-des-structures-diff`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/images/favicons/safari-pinned-tab.svg](https://aidantsconnect.beta.gouv.fr/static/images/favicons/safari-pinned-tab.svg)
  
  
  * Method: `GET`
  
  
  * Evidence: `org/TR/2001/REC-SVG-20010904/DTD/svg10`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20D%C3%A9marche-administrative%20_%20Impression%20noir%20et%20blanc.pdf](https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20D%C3%A9marche-administrative%20_%20Impression%20noir%20et%20blanc.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `104471/Subtype/XML/Type/Metadata`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf](https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `99259/Subtype/XML/Type/Metadata`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr](https://aidantsconnect.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Evidence: `YWZhOWVmNGEwNzY4NjViZmQyMDk0ZjUxZjg0Y2Q2ZGU3NTVjN2NmNjFmY2JmYjZkZmI1MWEwZjkxZTIyNGMzNQ==`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/accounts/login/](https://aidantsconnect.beta.gouv.fr/accounts/login/)
  
  
  * Method: `GET`
  
  
  * Evidence: `BlHTo593AylAKFFNkn8ebtn9zcL0leH1umaWTGe6LGJMrPqGWSRbJEqVHRi54jIO`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/images/aidantsconnect-illustration.svg](https://aidantsconnect.beta.gouv.fr/static/images/aidantsconnect-illustration.svg)
  
  
  * Method: `GET`
  
  
  * Evidence: `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`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/](https://aidantsconnect.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Evidence: `YWZhOWVmNGEwNzY4NjViZmQyMDk0ZjUxZjg0Y2Q2ZGU3NTVjN2NmNjFmY2JmYjZkZmI1MWEwZjkxZTIyNGMzNQ==`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/accounts/login/](https://aidantsconnect.beta.gouv.fr/accounts/login/)
  
  
  * Method: `POST`
  
  
  * Evidence: `BlHTo593AylAKFFNkn8ebtn9zcL0leH1umaWTGe6LGJMrPqGWSRbJEqVHRi54jIO`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20D%C3%A9marche-administrative.pdf](https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20D%C3%A9marche-administrative.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `99259/Subtype/XML/Type/Metadata`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/guide_utilisation/](https://aidantsconnect.beta.gouv.fr/guide_utilisation/)
  
  
  * Method: `GET`
  
  
  * Evidence: `/static/guides_aidants_connect/Franceconnect_3`
  
  
  
  
Instances: 11
  
### Solution
<p>Manually confirm that the Base64 data does not leak sensitive information, and that the data cannot be aggregated/used to exploit other vulnerabilities.</p>
  
### Other information
<p>��/�*�u�>���j�>u���׬��k��n��>v'�</p>
  
### Reference
* http://projects.webappsec.org/w/page/13246936/Information%20Leakage

  
#### CWE Id : 200
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Storable and Cacheable Content
##### Informational (Medium)
  
  
  
  
#### Description
<p>The response contents are storable by caching components such as proxy servers, and may be retrieved directly from the cache, rather than from the origin server by the caching servers, in response to similar requests from other users.  If the response data is sensitive, personal or user-specific, this may result in sensitive information being leaked. In some cases, this may even result in a user gaining complete control of the session of another user, depending on the configuration of the caching components in use in their environment. This is primarily an issue where "shared" caching servers such as "proxy" caches are configured on the local network. This configuration is typically found in corporate or educational environments, for instance.</p>
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/accounts/login/](https://aidantsconnect.beta.gouv.fr/accounts/login/)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/cgu](https://aidantsconnect.beta.gouv.fr/cgu)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/ressources/](https://aidantsconnect.beta.gouv.fr/ressources/)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/habilitation](https://aidantsconnect.beta.gouv.fr/habilitation)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/robots.txt](https://aidantsconnect.beta.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/faq](https://aidantsconnect.beta.gouv.fr/faq)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/faq/](https://aidantsconnect.beta.gouv.fr/faq/)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/mentions-legales](https://aidantsconnect.beta.gouv.fr/mentions-legales)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/](https://aidantsconnect.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/sitemap.xml](https://aidantsconnect.beta.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr](https://aidantsconnect.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  
  
Instances: 11
  
### Solution
<p>Validate that the response does not contain sensitive, personal or user-specific information.  If it does, consider the use of the following HTTP response headers, to limit, or prevent the content being stored and retrieved from the cache by another user:</p><p>Cache-Control: no-cache, no-store, must-revalidate, private</p><p>Pragma: no-cache</p><p>Expires: 0</p><p>This configuration directs both HTTP 1.0 and HTTP 1.1 compliant caching servers to not store the response, and to not retrieve the response (without validation) from the cache, in response to a similar request. </p>
  
### Other information
<p>In the absence of an explicitly specified caching lifetime directive in the response, a liberal lifetime heuristic of 1 year was assumed. This is permitted by rfc7234.</p>
  
### Reference
* https://tools.ietf.org/html/rfc7234
* https://tools.ietf.org/html/rfc7231
* http://www.w3.org/Protocols/rfc2616/rfc2616-sec13.html (obsoleted by rfc7234)

  
#### CWE Id : 524
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Timestamp Disclosure - Unix
##### Informational (Low)
  
  
  
  
#### Description
<p>A timestamp was disclosed by the application/web server - Unix</p>
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf](https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `0001409542`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf](https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `0002622344`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf](https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `0001424130`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf](https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `0001424358`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf](https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `0002491168`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf](https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `0003784443`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf](https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `0001966464`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf](https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `0002819108`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf](https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `0003540576`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf](https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `0001402339`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf](https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `0004046797`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf](https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `0002556756`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf](https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `0000000016`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf](https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `0001424243`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf](https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `0001401283`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf](https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `0003850031`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf](https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `0003981208`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf](https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `0003915619`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf](https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `0001402237`
  
  
  
  
* URL: [https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf](https://aidantsconnect.beta.gouv.fr/static/guides_aidants_connect/Aidants%20Connect%20_%20Quel-fournisseur-identit%C3%A9-choisir.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `0001426356`
  
  
  
  
Instances: 112
  
### Solution
<p>Manually confirm that the timestamp data is not sensitive, and that the data cannot be aggregated to disclose exploitable patterns.</p>
  
### Other information
<p>0001409542, which evaluates to: 1970-01-17 07:32:22</p>
  
### Reference
* http://projects.webappsec.org/w/page/13246936/Information%20Leakage

  
#### CWE Id : 200
  
#### WASC Id : 13
  
#### Source ID : 3
