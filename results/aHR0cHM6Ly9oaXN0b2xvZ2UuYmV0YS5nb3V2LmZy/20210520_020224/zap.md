
# ZAP Scanning Report

Generated on Thu, 20 May 2021 01:55:11


## Summary of Alerts

| Risk Level | Number of Alerts |
| --- | --- |
| High | 0 |
| Medium | 8 |
| Low | 15 |
| Informational | 8 |

## Alerts

| Name | Risk Level | Number of Instances |
| --- | --- | --- | 
| Application Error Disclosure | Medium | 1 | 
| Content Security Policy (CSP) Header Not Set | Medium | 11 | 
| Reverse Tabnabbing | Medium | 11 | 
| Source Code Disclosure - Java | Medium | 2 | 
| Sub Resource Integrity Attribute Missing | Medium | 8 | 
| X-Frame-Options Header Not Set | Medium | 11 | 
| Absence of Anti-CSRF Tokens | Low | 9 | 
| Application Error Disclosure | Low | 1 | 
| Big Redirect Detected (Potential Sensitive Information Leak) | Low | 2 | 
| Cookie No HttpOnly Flag | Low | 2 | 
| Cookie Without SameSite Attribute | Low | 2 | 
| Cookie Without Secure Flag | Low | 2 | 
| Cross-Domain JavaScript Source File Inclusion | Low | 6 | 
| Dangerous JS Functions | Low | 1 | 
| Feature Policy Header Not Set | Low | 11 | 
| Incomplete or No Cache-control and Pragma HTTP Header Set | Low | 11 | 
| Strict-Transport-Security Header Not Set | Low | 11 | 
| X-Content-Type-Options Header Missing | Low | 11 | 
| Base64 Disclosure | Informational | 9 | 
| Information Disclosure - Suspicious Comments | Informational | 12 | 
| Modern Web Application | Informational | 11 | 
| Storable and Cacheable Content | Informational | 11 | 
| Timestamp Disclosure - Unix | Informational | 6 | 

## Alert Detail


  
  
  
  
### Application Error Disclosure
##### Medium (Medium)
  
  
  
  
#### Description
<p>This page contains an error/warning message that may disclose sensitive information like the location of the file that produced the unhandled exception. This information can be used to launch further attacks against the web application. The alert could be a false positive if the error message is found inside a documentation page.</p>
  
  
  
* URL: [http://histologe.beta.gouv.fr/dev/js/image.js](http://histologe.beta.gouv.fr/dev/js/image.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `internal error`
  
  
  
  
Instances: 1
  
### Solution
<p>Review the source code of this page. Implement custom error pages. Consider implementing a mechanism to provide a unique error reference/identifier to the client (browser) while logging the details on the server side and not exposing them to the user.</p>
  
### Reference
* 

  
#### CWE Id : 200
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Content Security Policy (CSP) Header Not Set
##### Medium (High)
  
  
  
  
#### Description
<p>Content Security Policy (CSP) is an added layer of security that helps to detect and mitigate certain types of attacks, including Cross Site Scripting (XSS) and data injection attacks. These attacks are used for everything from data theft to site defacement or distribution of malware. CSP provides a set of standard HTTP headers that allow website owners to declare approved sources of content that browsers should be allowed to load on that page — covered types are JavaScript, CSS, HTML frames, fonts, images and embeddable objects such as Java applets, ActiveX, audio and video files.</p>
  
  
  
* URL: [https://histologe.beta.gouv.fr/Home](https://histologe.beta.gouv.fr/Home)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/sitemap.xml](https://histologe.beta.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr](https://histologe.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Aide](https://histologe.beta.gouv.fr/Aide)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/signale](https://histologe.beta.gouv.fr/signale)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/connect.php](https://histologe.beta.gouv.fr/connect.php)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/dev_qg](https://histologe.beta.gouv.fr/dev_qg)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/_sign.php](https://histologe.beta.gouv.fr/_sign.php)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Qui](https://histologe.beta.gouv.fr/Qui)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/](https://histologe.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Contact](https://histologe.beta.gouv.fr/Contact)
  
  
  * Method: `GET`
  
  
  
  
Instances: 11
  
### Solution
<p>Ensure that your web server, application server, load balancer, etc. is configured to set the Content-Security-Policy header, to achieve optimal browser support: "Content-Security-Policy" for Chrome 25+, Firefox 23+ and Safari 7+, "X-Content-Security-Policy" for Firefox 4.0+ and Internet Explorer 10+, and "X-WebKit-CSP" for Chrome 14+ and Safari 6+.</p>
  
### Reference
* https://developer.mozilla.org/en-US/docs/Web/Security/CSP/Introducing_Content_Security_Policy
* https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html
* http://www.w3.org/TR/CSP/
* http://w3c.github.io/webappsec/specs/content-security-policy/csp-specification.dev.html
* http://www.html5rocks.com/en/tutorials/security/content-security-policy/
* http://caniuse.com/#feat=contentsecuritypolicy
* http://content-security-policy.com/

  
#### CWE Id : 16
  
#### WASC Id : 15
  
#### Source ID : 3

  
  
  
  
### Reverse Tabnabbing
##### Medium (Medium)
  
  
  
  
#### Description
<p>At least one link on this page is vulnerable to Reverse tabnabbing as it uses a target attribute without using both of the "noopener" and "noreferrer" keywords in the "rel" attribute, which allows the target page to take control of this page.</p>
  
  
  
* URL: [https://histologe.beta.gouv.fr](https://histologe.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a href="https://www.interconnectes.com/" target="_new"><img src="images/Logo_label_2021.png"></a>`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/connect.php](https://histologe.beta.gouv.fr/connect.php)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a href="https://agence-cohesion-territoires.gouv.fr/" target="_new"><img src="images/logo_ANCT_header.svg"></a>`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Home](https://histologe.beta.gouv.fr/Home)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a href="https://www.interconnectes.com/" target="_new"><img src="images/Logo_label_2021.png"></a>`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/_sign.php](https://histologe.beta.gouv.fr/_sign.php)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a href="https://agence-cohesion-territoires.gouv.fr/" target="_new"><img src="images/logo_ANCT_header.svg"></a>`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Qui](https://histologe.beta.gouv.fr/Qui)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a href="https://agence-cohesion-territoires.gouv.fr/" target="_new">Agence Nationale de la Cohésion des Territoires</a>`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/signale](https://histologe.beta.gouv.fr/signale)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a href="https://agence-cohesion-territoires.gouv.fr/" target="_new"><img src="images/logo_ANCT_header.svg"></a>`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Plan-du-site](https://histologe.beta.gouv.fr/Plan-du-site)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a href="https://agence-cohesion-territoires.gouv.fr/" target="_new"><img src="images/logo_ANCT_header.svg"></a>`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Aide](https://histologe.beta.gouv.fr/Aide)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a href="https://agence-cohesion-territoires.gouv.fr/" target="_new"><img src="images/logo_ANCT_header.svg"></a>`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Chiffres](https://histologe.beta.gouv.fr/Chiffres)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a href="https://agence-cohesion-territoires.gouv.fr/" target="_new"><img src="images/logo_ANCT_header.svg"></a>`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/](https://histologe.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a href="https://www.interconnectes.com/" target="_new"><img src="images/Logo_label_2021.png"></a>`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Contact](https://histologe.beta.gouv.fr/Contact)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a href="https://agence-cohesion-territoires.gouv.fr/" target="_new"><img src="images/logo_ANCT_header.svg"></a>`
  
  
  
  
Instances: 11
  
### Solution
<p>Do not use a target attribute, or if you have to then also add the attribute: rel="noopener noreferrer".</p>
  
### Reference
* https://owasp.org/www-community/attacks/Reverse_Tabnabbing
* https://dev.to/ben/the-targetblank-vulnerability-by-example
* https://mathiasbynens.github.io/rel-noopener/
* https://medium.com/@jitbit/target-blank-the-most-underestimated-vulnerability-ever-96e328301f4c

  
#### Source ID : 3

  
  
  
  
### Source Code Disclosure - Java
##### Medium (Medium)
  
  
  
  
#### Description
<p>Application Source Code was disclosed by the web server - Java</p>
  
  
  
* URL: [http://histologe.beta.gouv.fr/dev/js/dsfr.module.min.js](http://histologe.beta.gouv.fr/dev/js/dsfr.module.min.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `class r{constructor(){this.closures=[],this.nexts=[],this.rendering=this.render.bind(this),this.render()}add(t){this.closures.push(t);return()=>{const e=this.closures.indexOf(t);-1!==e&&this.closures.splice(e,1)}}next(t,e){e=void 0===e?0:e-1,void 0===this.nexts[e]&&(this.nexts[e]=[]),this.nexts[e].push(t)}render(){window.requestAnimationFrame(this.rendering);for(const t of this.closures)t.call();const t=this.nexts.shift();if(t)for(const e of t)e.call()}}const o=new class{constructor(){this.renderer=new r}register(t,e){}start(){}stop(){}};class h{constructor(t,e){this.selector=t,this.builders=e,this.instances=[],"loading"!==document.readyState?window.requestAnimationFrame(this.start.bind(this)):document.addEventListener("DOMContentLoaded",this.start.bind(this))}start(){if(!(this.instances.length>0)&&document.querySelectorAll(this.selector).length>0)for(let t=0;t<this.builders.length;t++)this.instances.push(this.builders[t]())}}const l={};class c{constructor(t,e){l[t]||(l[t]=[]),l[t].push(this),this.element=t,this.id=t.id,this.listeners={}}dispatch(t,e){const s=new CustomEvent(t,e);this.element.dispatchEvent(s)}listen(t,e){this.listeners[t]||(this.listeners[t]=[]),this.listeners[t].indexOf(e)>-1||(this.listeners[t].push(e),this.element.addEventListener(t,e))}unlisten(t,e){if(t)if(e){if(!this.listeners[t])return;const s=this.listeners[t].indexOf(e);s>-1&&this.listeners[t].splice(s,1),this.element.removeEventListener(e)}else{if(!this.listeners[t])return;for(const e of this.listeners[t])this.element.removeEventListener(e);this.listeners[t].length=0}else for(const t in this.listeners)this.unlisten(t)}resize(){}destroy(){}static getInstances(t,e){return l[t]?e?l[t].filter((t=>t instanceof e)):l[t]:null}}const a=e.attr("group"),d=[];class u{constructor(t,e){this.id=t,this.element=e,this.members=[],this._index=-1,this._current=null,d.push(this)}static getGroupById(t){for(const e of d)if(e.constructor===this&&e.id===t)return e;return new this(t)}static getGroupByElement(t){for(const e of d)if(e.element===t)return e;return new this(!1,t)}static groupById(t,e){const s=t.element.getAttribute(a);if(null===s)return;e.getGroupById(s).add(t)}static groupByParent(t,e,s){if(void 0===s&&(s=e.selector),""===s)return;let i=t.element.parentElement;for(;i;){if(i.classList.contains(t.constructor.selector))return;if(i.classList.contains(s)){return void e.getGroupByElement(i).add(t)}i=i.parentElement}}static get selector(){return""}add(t){if(-1===this.members.indexOf(t))switch(this.members.push(t),t.setGroup(this),!0){case null!==this.current:case!t.disclosed&&!t.primal:t.disclosed=!1;break;default:this._current=t,this._index=this.members.indexOf(t),t.disclosed=!0}}get length(){return this.members.length}get index(){return this._index}set index(t){t<-1||t>=this.length||this._index===t||(null!==this.current&&this.current.conceal(!0,!0),this._index=t,this._current=this._index>-1?this.members[this._index]:null,null!==this.current&&this.current.disclose(!0),this.apply())}get current(){return this._current}set current(t){this.index=this.members.indexOf(t)}get hasFocus(){return void 0===this.current?null:this.current.hasFocus}apply(){}}class m{constructor(t,e){this.element=t,this.disclosure=e,this.hasAttribute=this.element.hasAttribute(this.disclosure.attributeName),this.element.addEventListener("click",this.click.bind(this)),this.observer=new MutationObserver(this.mutate.bind(this)),this.observe()}observe(){this.observer.observe(this.element,{attributes:!0})}click(t){this.disclosure.change(this.hasAttribute)}mutate(t){t.forEach((t=>{"attributes"===t.type&&t.attributeName===this.disclosure.attributeName&&this.disclosure.change(this.disclosed)}))}apply(t){this.hasAttribute&&(this.observer&&this.observer.disconnect(),this.element.setAttribute(this.disclosure.attributeName,t),this.observer&&this.observe())}get disclosed(){return"true"===this.element.getAttribute(this.disclosure.attributeName)}get hasFocus(){return this.element===document.activeElement}}const p=e.event("DISCLOSE"),b=e.event("CONCEAL"),g=[];class f extends c{constructor(t){super(t),this.buttons=[],this._selector=this.constructor.selector,this.modifier=this._selector+"--"+this.type.id,this.attributeName=this.type.ariaState?"aria-"+this.type.id:e.attr(this.type.id),this.pristine=!0;const s=document.querySelectorAll(this.type.ariaControls?`[aria-controls="${this.id}"]`:e.attr.selector("controls",this.id));if(s.length>0)for(let t=0;t<s.length;t++)this.addButton(s[t]);this.disclosed=!0===this.primal,this.gather()}gather(){this.group||(u.groupById(this,this.GroupConstructor),u.groupByParent(this,this.GroupConstructor))}static build(t){const e=Array.prototype.slice.call(t.querySelectorAll(`.${this.selector}`));for(const t of e)g.push(new this(t))}get type(){return this.constructor.type}static get type(){return null}static get selector(){return""}addButton(t){const e=this.buttonFactory(t);e.hasAttribute&&(void 0===this.primal?this.primal=e.disclosed:e.apply(this.primal)),this.buttons.push(e)}get GroupConstructor(){return u}buttonFactory(t){return new m(t,this)}disclose(t){return!this.disclosed&&(this.pristine=!1,this.disclosed=!0,t||void 0===this.group||(this.group.current=this),!0)}conceal(t,e){if(!this.disclosed)return!1;this.pristine=!1,this.disclosed=!1,e||this.focus(),t||void 0===this.group||(this.group.current=null);for(const t of g)t!==this&&this.element.contains(t.element)&&t.reset();return!0}get disclosed(){return this._disclosed}set disclosed(t){if(this._disclosed!==t){this.dispatch(t?p:b,this.type),this._disclosed=t,t?i(this.element,this.modifier):n(this.element,this.modifier);for(let e=0;e<this.buttons.length;e++)this.buttons[e].apply(t)}}reset(){}change(t){if(this.constructor.type.canConceal)switch(!0){case!t:case this.disclosed:this.conceal();break;default:this.disclose()}else this.disclose()}setGroup(t){this.group=t}get buttonHasFocus(){return!!this.buttons.some((t=>t.hasFocus))}get hasFocus(){return this.element===document.activeElement||(this.element.querySelectorAll(":focus").length>0||this.buttonHasFocus)}focus(){for(let t=0;t<this.buttons.length;t++){const e=this.buttons[t];if(e.hasAttribute)return void e.element.focus()}}}f.DISCLOSE_EVENT=p,f.CONCEAL_EVENT=b;const y={expand:{id:"expanded",ariaState:!0,ariaControls:!0,canConceal:!0},select:{id:"selected",ariaState:!0,ariaControls:!0,canConceal:!1},opened:{id:"opened",ariaState:!1,ariaControls:!0,canConceal:!0}};class v{constructor(t){this.element=t,this.collections={}}_add(t,e){void 0===this.collections[t]&&(this.collections[t]=new w(t,this.element)),this.collections[t].add(e)}down(t,e,s,i){this._add("down",new E(t,e,s,i))}up(t,e,s,i){this._add("up",new E(t,e,s,i))}dispose(){for(const t of this.collections)t.dispose();this.types=null}}class w{constructor(t,e){this.type=t,this.element=e,this.actions=[],this.binding=this.handle.bind(this),this.element.addEventListener("key"+t,this.binding)}add(t){this.actions.push(t)}handle(t){for(const e of this.actions)e.handle(t)}dispose(){this.element.removeEventListener("key"+this.type,this.binding),this.actions=null}}class E{constructor(t,e,s,i){this.key=t,this.closure=e,this.preventDefault=!0===s,this.stopPropagation=!0===i}handle(t){t.keyCode===this.key&&(this.closure(t),this.preventDefault&&t.preventDefault(),this.stopPropagation&&t.stopPropagation())}}v.TAB=9,v.ESCAPE=27,v.END=35,v.HOME=36,v.LEFT=37,v.UP=38,v.RIGHT=39,v.DOWN=40;const x=e("collapse"),L=[],S={};class A extends f{constructor(t){super(t),L.push(this),this.requesting=this.request.bind(this),t.addEventListener("transitionend",this.transitionend.bind(this)),this.disclosed&&this.unbound()}gatherByAscendants(){if(!this.group)for(const t in S){let e=this.element.parentElement;for(;e;){if(e.classList.contains(t))return void("string"==typeof S[t]?u.groupByParent(this,u,S[t]):u.groupByParent(this,S[t]));e=e.parentElement}}}gather(){this.gatherByAscendants(),super.gather()}static get type(){return y.expand}static get selector(){return x}static register(t,e){S[t]=e;for(const t of L)t.gatherByAscendants()}transitionend(t){this.disclosed||(this.element.style.maxHeight="")}unbound(){this.element.style.maxHeight="none"}disclose(t){this.disclosed||(this.unbound(),this.adjust(),this.requested=()=>{super.disclose(t)},window.requestAnimationFrame(this.requesting))}conceal(t,e){this.disclosed&&(this.adjust(),this.requested=()=>{super.conceal(t,e)},window.requestAnimationFrame(this.requesting))}request(){this.requested&&this.requested(),this.requested=null}adjust(){this.element.style.setProperty("--collapser","none");const t=this.element.offsetHeight;this.element.style.setProperty("--collapse",-t+"px"),this.element.style.setProperty("--collapser","")}reset(){this.pristine||(this.disclosed=!1)}}t.core.ns=e,t.core.addClass=i,t.core.removeClass=n,t.core.engine=o,t.core.Instance=c,t.core.Initializer=h,t.core.Disclosure=f,t.core.DisclosureButton=m,t.core.DisclosuresGroup=u,t.core.DISCLOSURE_TYPES=y,t.KeyListener=v,t.Collapse=A,t.Equisized=class{constructor(t,e){this.selector=t,this.group=e,this.elements=this.group.querySelectorAll(this.selector),this.maxWidth=0,this.changing=this.change.bind(this),window.addEventListener("resize",this.changing),window.addEventListener("load",this.changing)}change(){this.reset();for(let t=0;t<this.elements.length;t++){const e=this._getWidth(this.elements[t]);e>this.maxWidth&&(this.maxWidth=e)}this.apply()}apply(){for(let t=0;t<this.elements.length;t++)this.elements[t].style.width=this.maxWidth+1+"px"}reset(){for(let t=0;t<this.elements.length;t++)this.elements[t].style.width="auto";this.maxWidth=0}_getWidth(t){let e=t.offsetWidth;const s=getComputedStyle(t);return e+=parseInt(s.marginLeft)+parseInt(s.marginRight),e}};new h(`.${x}`,[()=>{A.build(document)}]);const C=t.core.ns("accordions-group"),_=t.core.ns("accordion");class q extends t.core.DisclosuresGroup{static get selector(){return C}}t.AccordionsGroup=q,t.Collapse.register(_,q);const I=`${t.core.ns.selector("breadcrumb")} ${t.core.ns.selector("collapse")}`;class k extends t.core.Instance{constructor(e){super(e),this.collapse=t.core.Instance.getInstances(e,t.Collapse)[0],this.links=[...this.element.querySelectorAll("a[href]")],this.count=0,this.links.length&&(this.listen(t.core.Disclosure.DISCLOSE_EVENT,this.focus.bind(this)),this.resizing=this.resize.bind(this),window.addEventListener("resize",this.resizing))}focus(){this.links[0].focus(),t.core.engine.renderer.next((()=>{this.verify()}))}verify(){this.count++,this.count>100||document.activeElement!==this.links[0]&&this.focus()}resize(){window.matchMedia("(min-width: 48em)").matches?this.collapse.buttons[0]===document.activeElement&&this.links.focus():this.links.indexOf(document.activeElement)>-1&&this.collapse.focus()}}new t.core.Initializer(I,[()=>{const t=[],e=document.querySelectorAll(I);for(let s=0;s<e.length;s++)t.push(new k(e[s]))}]);const z=t.core.ns.selector("btn"),D=t.core.ns.selector("btns-group"),B=t.core.ns.selector("btns-group--equisized");new t.core.Initializer(D,[()=>{const e=document.querySelectorAll(B),s=[];for(let i=0;i<e.length;i++)s.push(new t.Equisized(z,e[i]))}]);const H=t.core.ns.selector("modal"),P=t.core.ns("modal"),O=t.core.ns("no-scroll"),T=t.core.ns("scroll-shadow"),N=t.core.ns.selector("modal__body"),$=['[tabindex="0"]',"a[href]","button:not([disabled])","input:not([disabled])","select:not([disabled])","textarea:not([disabled])","audio[controls]","video[controls]",'[contenteditable]:not([contenteditable="false" i])',"details>summary:first-of-type","details"].join(),F=['[tabindex]:not([tabindex="-1"]):not([tabindex="0"])'].join(),G=(t,e)=>{if("hidden"===window.getComputedStyle(t).visibility)return!1;for(void 0===e&&(e=t);e.contains(t);){if("none"===window.getComputedStyle(t).display)return!1;t=t.parentElement}return!0};class W{constructor(t,e){this.element=null,this.activeElement=null,this.onTrap=t,this.onUntrap=e,this.waiting=this.wait.bind(this),this.handling=this.handle.bind(this),this.current=null}get trapped(){return null!==this.element}trap(t){this.trapped&&this.untrap(),this.element=t,this.isTrapping=!0,this.wait(),this.onTrap&&this.onTrap()}wait(){G(this.element)?this.trapping():t.core.engine.renderer.next(this.waiting)}trapping(){if(!this.isTrapping)return;this.isTrapping=!1;const t=this.focusables;t.length&&t[0].focus(),this.element.setAttribute("aria-modal",!0),this.element.addEventListener("keydown",this.handling),this.stunneds=[],this.stun(document.body)}stun(t){for(const e of t.children)e!==this.element&&(e.contains(this.element)?this.stun(e):this.stunneds.push(new M(e)))}handle(t){if(9!==t.keyCode)return;const e=this.focusables;if(0===e.length)return;const s=e[0],i=e[e.length-1],n=e.indexOf(document.activeElement);t.shiftKey?!this.element.contains(document.activeElement)||n<1?(t.preventDefault(),i.focus()):(document.activeElement.tabIndex>0||e[n-1].tabIndex>0)&&(t.preventDefault(),e[n-1].focus()):this.element.contains(document.activeElement)&&n!==e.length-1&&-1!==n?document.activeElement.tabIndex>0&&(t.preventDefault(),e[n+1].focus()):(t.preventDefault(),s.focus())}get focusables(){let t=[...this.element.querySelectorAll($)];const e=[...document.documentElement.querySelectorAll('input[type="radio"]')];if(e.length){const s={};for(const t of e){const e=t.getAttribute("name");void 0===s[e]&&(s[e]=new R(e)),s[e].push(t)}t=t.filter((t=>{if("input"!==t.tagName.toLowerCase()||"radio"!==t.getAttribute("type").toLowerCase())return!0;const e=t.getAttribute("name");return s[e].keep(t)}))}const s=[...this.element.querySelectorAll(F)];s.sort(((t,e)=>t.tabIndex-e.tabIndex));const i=t.filter((t=>-1===s.indexOf(t)));return s.concat(i).filter((t=>"-1"!==t.tabIndex&&G(t,this.element)))}untrap(){if(this.trapped){this.isTrapping=!1,this.element.removeAttribute("aria-modal"),this.element.removeEventListener("keydown",this.handling),this.element=null;for(const t of this.stunneds)t.unstun();this.stunneds=[],this.onUntrap&&this.onUntrap()}}}class M{constructor(t){this.element=t,this.hidden=t.getAttribute("aria-hidden"),this.inert=t.getAttribute("inert"),this.element.setAttribute("aria-hidden",!0),this.element.setAttribute("inert","")}unstun(){null===this.hidden?this.element.removeAttribute("aria-hidden"):this.element.setAttribute("aria-hidden",this.hidden),null===this.inert?this.element.removeAttribute("inert"):this.element.setAttribute("inert",this.inert)}}class R{constructor(t){this.name=t,this.buttons=[]}push(t){this.buttons.push(t),(t===document.activeElement||t.checked||void 0===this.selected)&&(this.selected=t)}keep(t){return this.selected===t}}class K extends t.core.DisclosuresGroup{constructor(){super(),this.trap=new W}apply(t,e){super.apply(t,e),null===this.current?this.trap.untrap():this.trap.trap(this.current.element)}}const V=new K;class U extends t.core.Disclosure{constructor(t){super(t),this.body=this.element.querySelector(N),this.scrollDistance=0,this.scrolling=this.resize.bind(this,!1),this.resizing=this.resize.bind(this,!0),this.init(),this.resize(!0)}init(){this.element.addEventListener("click",this.click.bind(this)),this.keyListener=new t.KeyListener(this.element),this.keyListener.down(t.KeyListener.ESCAPE,this.conceal.bind(this),!0,!0),this.body&&(this.body.addEventListener("scroll",this.scrolling),window.addEventListener("resize",this.resizing))}click(t){this.body&&this.element===t.target&&this.conceal()}gather(){V.add(this)}disclose(t){return!!super.disclose(t)&&(this.resize(!0),this.handleScroll(!1),!0)}conceal(t,e){return!!super.conceal(t,e)&&(this.handleScroll(!0),!0)}handleScroll(e){e?(t.core.removeClass(document.documentElement,O),document.body.style.top="",window.scroll(0,this.scrollDistance)):(document.documentElement.classList.contains(O)||(this.scrollDistance=window.scrollY),document.body.style.top=-1*this.scrollDistance+"px",t.core.addClass(document.documentElement,O))}resize(e,s){this.body&&(this.body.scrollHeight>this.body.clientHeight?this.body.offsetHeight+this.body.scrollTop>=this.body.scrollHeight?t.core.removeClass(this.body,T):t.core.addClass(this.body,T):t.core.removeClass(this.body,T),e&&(this.body.style.maxHeight=window.innerHeight-32+"px",t.core.engine.renderer.next((()=>{this.body.style.maxHeight=window.innerHeight-32+"px"}))))}static get type(){return t.core.DISCLOSURE_TYPES.opened}static get selector(){return P}get GroupConstructor(){return K}}t.Modal=U,t.ModalsGroup=K,t.FocusTrap=W;new t.core.Initializer(H,[()=>{U.build(document)}]);const j=t.core.ns("nav"),Y=t.core.ns("nav__list"),J=t.core.ns("nav__item"),Q=t.core.ns("nav__item--align-right"),X=t.core.ns("menu");class Z extends t.core.DisclosuresGroup{constructor(t,e){super(t,e),this.menus=[],this.navList=e.querySelector(`.${Y}`),document.addEventListener("focusout",this.focusOut.bind(this)),window.addEventListener("resize",this.resize.bind(this)),window.addEventListener("orientationchange",this.resize.bind(this)),this.resize()}static get selector(){return j}add(t){super.add(t),t.element.classList.contains(X)&&this.menus.push(new tt(t,this.navList.getBoundingClientRect().right))}focusOut(t){requestAnimationFrame((()=>{null===this.current||this.current.hasFocus||(this.index=-1)}))}get index(){return super.index}set index(t){-1===t&&null!==this.current&&this.current.hasFocus&&this.current.focus(),super.index=t}resize(){const t=this.navList.getBoundingClientRect().right;for(const e of this.menus)e.place(t)}}class tt{constructor(t,e){this.initialize(t),this.place(e)}initialize(t){this.element=t.element;for(const e of t.buttons)if(e.hasAttribute){this.button=e.element;break}let e=this.element.parentElement;for(;e;){if(e.classList.contains(J)){this.item=e;break}e=e.parentElement}}place(e){const s=getComputedStyle(this.element),i=parseFloat(s.width);this.button.getBoundingClientRect().left+i>e?t.core.addClass(this.item,Q):t.core.removeClass(this.item,Q)}}t.Navigation=Z,t.Collapse.register(j,Z);const et=t.core.ns.attr("theme"),st=t.core.ns.attr("transition");class it{constructor(){this.init()}init(){this.scheme=localStorage.getItem("scheme")?localStorage.getItem("scheme"):null,null===this.scheme&&(window.matchMedia("(prefers-color-scheme: dark)").matches?(this.scheme="dark",localStorage.setItem("scheme","dark")):this.scheme="light"),this.root=document.documentElement,"dark"===this.scheme?this.root.hasAttribute(st)?(this.root.removeAttribute(st),this.root.setAttribute(et,"dark"),setTimeout((()=>{this.root.setAttribute(st,"")}),300)):this.root.setAttribute(et,"dark"):this.root.setAttribute(et,"light"),this.observer=new MutationObserver(this.mutate.bind(this)),this.observer.observe(this.root,{attributes:!0})}mutate(t){t.forEach((t=>{if("attributes"===t.type&&t.attributeName===et){const t=this.root.getAttribute(et);"dark"===t?localStorage.setItem("scheme","dark"):"light"===t&&localStorage.setItem("scheme","light")}}))}}t.Scheme=it;const nt=`input[name="${t.core.ns.selector("radios-theme","")}"]`,rt=t.core.ns.selector("switch-theme","#"),ot=t.core.ns.attr("theme");class ht{constructor(){this.attributeName=ot,this.theme=null,this.radios=document.querySelectorAll(nt);for(var t=0;t<this.radios.length;t++)this.radios[t].addEventListener("change",this.change.bind(this));this.observer=new MutationObserver(this.mutate.bind(this)),this.observe(),this.apply()}observe(){this.observer.observe(document.documentElement,{attributes:!0})}mutate(t){t.forEach((t=>{"attributes"===t.type&&t.attributeName===this.attributeName&&this.apply()}))}apply(){const t=document.documentElement.getAttribute(this.attributeName);this.isApplying=!0;for(var e=0;e<this.radios.length;e++)this.radios[e].checked=this.radios[e].value===t;this.isApplying=!1}change(){this.isApplying||(this.observer&&this.observer.disconnect(),this.theme=document.querySelector(nt+":checked"),this.theme?document.documentElement.setAttribute(this.attributeName,this.theme.value):document.documentElement.removeAttribute(this.attributeName),this.observer&&this.observe())}}new t.core.Initializer(`:root[${et}]`,[()=>{new it}]),new t.core.Initializer(`${rt}`,[()=>{new ht}]);const lt=t.core.ns("sidemenu"),ct=t.core.ns("sidemenu__list");t.Collapse.register(lt,ct);const at=t.core.ns.selector("table"),dt=`${t.core.ns.selector("table")}:not(${t.core.ns.selector("table--no-scroll")})`,ut=t.core.ns("table--shadow"),mt=t.core.ns("table--shadow-left"),pt=t.core.ns("table--shadow-right"),bt=t.core.ns("table__wrapper"),gt=t.core.ns("table--caption-bottom");class ft{constructor(t){this.init(t)}init(t){this.table=t,this.tableElem=this.table.querySelector("table"),this.tableContent=this.tableElem.querySelector("tbody"),this.isScrollable=this.tableContent.offsetWidth>this.tableElem.offsetWidth,this.caption=this.tableElem.querySelector("caption"),this.captionHeight=0,this.wrap();const e=this.change.bind(this);this.tableElem.addEventListener("scroll",e),this.change()}change(){const t=this.tableContent.offsetWidth>this.tableElem.offsetWidth;let e=this.tableElem.offsetWidth>this.table.offsetWidth;t||e?(this.scroll(),this.handleCaption()):t!==this.isScrollable&&this.delete(),this.isScrollable=t,e=!1}delete(){t.core.removeClass(this.table,pt),t.core.removeClass(this.table,mt),t.core.removeClass(this.table,ut),this.caption&&(this.tableElem.style.marginTop="",this.caption.style.top="",this.tableElem.style.marginBottom="",this.caption.style.bottom="")}scroll(){t.core.addClass(this.table,ut),this.setShadowPosition()}wrap(){const t=document.createElement("div");t.className=bt,this.table.insertBefore(t,this.tableElem),t.appendChild(this.tableElem),this.tableInnerWrapper=t}setShadowPosition(){const t=this.getScrollPosition("left"),e=this.getScrollPosition("right");"rtl"===document.documentElement.getAttribute("dir")?(this.setShadowVisibility("right",t),this.setShadowVisibility("left",e)):(this.setShadowVisibility("left",t),this.setShadowVisibility("right",e))}getScrollPosition(t){let e=1;switch("rtl"===document.documentElement.getAttribute("dir")&&(e=-1),t){case"left":return this.tableElem.scrollLeft*e;case"right":return this.tableContent.offsetWidth-this.tableElem.offsetWidth-this.tableElem.scrollLeft*e;default:return!1}}handleCaption(){if(this.caption){const t=getComputedStyle(this.caption),e=this.caption.offsetHeight+parseInt(t.marginTop)+parseInt(t.marginBottom);this.captionHeight=e,this.table.classList.contains(gt)?(this.tableElem.style.marginBottom=this.captionHeight+"px",this.caption.style.bottom=-this.captionHeight+"px"):(this.tableElem.style.marginTop=this.captionHeight+"px",this.caption.style.top=-this.captionHeight+"px")}}setShadowVisibility(e,s){s<=1?"left"===e?t.core.removeClass(this.table,mt):"right"===e&&t.core.removeClass(this.table,pt):"left"===e?t.core.addClass(this.table,mt):"right"===e&&t.core.addClass(this.table,pt)}}t.Table=ft;const yt=[],vt=()=>{for(let t=0;t<yt.length;t++)yt[t].change()};new t.core.Initializer(at,[()=>{const t=document.querySelectorAll(dt);for(let e=0;e<t.length;e++)yt.push(new ft(t[e]));window.addEventListener("resize",vt),window.addEventListener("orientationchange",vt),vt()}]);class wt extends t.core.DisclosureButton{apply(t){super.apply(t),this.hasAttribute&&this.element.setAttribute("tabindex",t?"0":"-1")}}const Et=t.core.ns.selector("tabs"),xt=t.core.ns("tabs"),Lt=t.core.ns("tabs__tab"),St=t.core.ns("tabs__panel"),At=t.core.ns("tabs__list");class Ct extends t.core.DisclosuresGroup{constructor(e,s){super(e,s),this.list=s.querySelector(`.${At}`),s.addEventListener("transitionend",this.transitionend.bind(this)),this.init(),t.core.engine.renderer.add(this.render.bind(this))}static get selector(){return xt}transitionend(t){this.element.style.transition="none"}init(){this.keyListener=new t.KeyListener(this.element),this.keyListener.down(t.KeyListener.RIGHT,this.arrowRightPress.bind(this),!0,!0),this.keyListener.down(t.KeyListener.LEFT,this.arrowLeftPress.bind(this),!0,!0),this.keyListener.down(t.KeyListener.HOME,this.homePress.bind(this),!0,!0),this.keyListener.down(t.KeyListener.END,this.endPress.bind(this),!0,!0)}arrowRightPress(){document.activeElement.classList.contains(Lt)&&(this.index<this.length-1?this.index++:this.index=0,this.focus())}arrowLeftPress(){document.activeElement.classList.contains(Lt)&&(this.index>0?this.index--:this.index=this.length-1,this.focus())}homePress(){document.activeElement.classList.contains(Lt)&&(this.index=0,this.focus())}endPress(){document.activeElement.classList.contains(Lt)&&(this.index=this.length-1,this.focus())}focus(){this.current&&this.current.focus()}apply(){for(let t=0;t<this._index;t++)this.members[t].translate(-1);this.current.element.style.transform="";for(let t=this._index+1;t<this.length;t++)this.members[t].translate(1);this.element.style.transition=""}add(t){if(super.add(t),1===this.length||t.disclosed)this.current=t;else{const e=this.members.indexOf(t);this._index>-1&&this._index!==e&&t.translate(e<this._index?-1:1,!0)}}render(){if(null===this.current)return;const t=Math.round(this.current.element.offsetHeight);this.panelHeight!==t&&(this.panelHeight=t,this.element.style.height=this.panelHeight+this.list.offsetHeight+"px")}}class _t extends t.core.Disclosure{static get type(){return t.core.DISCLOSURE_TYPES.select}static get selector(){return St}get GroupConstructor(){return Ct}buttonFactory(t){return new wt(t,this)}translate(t,e){e&&(this.element.style.transition="none"),this.element.style.transform=`translate(${100*t}%)`,e&&(this.element.style.transition="")}reset(){this.group.index=0}}t.Tab=_t,t.TabButton=wt,t.TabsGroup=Ct;new t.core.Initializer(Et,[()=>{_t.build(document)}]);const qt=t.core.ns.selector("header"),It=t.core.ns.selector("header__tools"),kt=`${It} ${t.core.ns.selector("search-bar")}`,zt=`${It} ${t.core.ns.selector("shortcuts")}`,Dt=t.core.ns.selector("nav"),Bt=`${Dt} ${t.core.ns.selector("nav__list")}`;let Ht=0;class Pt{constructor(t){this.header=t||document.querySelector(qt),this.numId=Ht,Ht++,this.modals=[],this.init()}getModal(e){if(!e)return;const s=t.core.Instance.getInstances(e,t.Modal);s&&s.length&&this.modals.push(s[0])}init(){this.tools=this.header.querySelector(It),this.getModal(this.tools),this.searchBar=this.header.querySelector(kt),this.nav=this.header.querySelector(Dt),this.getModal(this.nav),this.shortcuts=this.header.querySelector(zt),this.navList=this.header.querySelector(Bt),this.changing=this.change.bind(this),window.addEventListener("resize",this.changing),this.change()}change(){if(this.isLarge=window.matchMedia("(min-width: 62em)").matches,this.isLarge)for(let t=0;t<this.modals.length;t++)this.modals[t].conceal(),this.modals[t].element.style.transition="none";else for(let t=0;t<this.modals.length;t++)this.modals[t].element.style.transition="";null!==this.shortcuts&&(this.isLarge?null!==this.searchBar?this.tools.insertBefore(this.shortcuts,this.searchBar):this.tools.appendChild(this.shortcuts):this.nav.insertBefore(this.shortcuts,this.navList))}}t.Header=Pt;new t.core.Initializer(qt,[()=>{const t=Array.prototype.slice.call(document.querySelectorAll(qt)),e=[];for(const s of t)e.push(new Pt(s))}`
  
  
  
  
Instances: 1
  
### Solution
<p>Ensure that application Source Code is not available with alternative extensions, and ensure that source code is not present within other files or data deployed to the web server, or served by the web server. </p>
  
### Other information
<p>class r{constructor(){this.closures=[],this.nexts=[],this.rendering=this.render.bind(this),this.render()}add(t){this.closures.push(t);return()=>{const e=this.closures.indexOf(t);-1!==e&&this.closures.splice(e,1)}}next(t,e){e=void 0===e?0:e-1,void 0===this.nexts[e]&&(this.nexts[e]=[]),this.nexts[e].push(t)}render(){window.requestAnimationFrame(this.rendering);for(const t of this.closures)t.call();const t=this.nexts.shift();if(t)for(const e of t)e.call()}}const o=new class{constructor(){this.renderer=new r}register(t,e){}start(){}stop(){}};class h{constructor(t,e){this.selector=t,this.builders=e,this.instances=[],"loading"!==document.readyState?window.requestAnimationFrame(this.start.bind(this)):document.addEventListener("DOMContentLoaded",this.start.bind(this))}start(){if(!(this.instances.length>0)&&document.querySelectorAll(this.selector).length>0)for(let t=0;t<this.builders.length;t++)this.instances.push(this.builders[t]())}}const l={};class c{constructor(t,e){l[t]||(l[t]=[]),l[t].push(this),this.element=t,this.id=t.id,this.listeners={}}dispatch(t,e){const s=new CustomEvent(t,e);this.element.dispatchEvent(s)}listen(t,e){this.listeners[t]||(this.listeners[t]=[]),this.listeners[t].indexOf(e)>-1||(this.listeners[t].push(e),this.element.addEventListener(t,e))}unlisten(t,e){if(t)if(e){if(!this.listeners[t])return;const s=this.listeners[t].indexOf(e);s>-1&&this.listeners[t].splice(s,1),this.element.removeEventListener(e)}else{if(!this.listeners[t])return;for(const e of this.listeners[t])this.element.removeEventListener(e);this.listeners[t].length=0}else for(const t in this.listeners)this.unlisten(t)}resize(){}destroy(){}static getInstances(t,e){return l[t]?e?l[t].filter((t=>t instanceof e)):l[t]:null}}const a=e.attr("group"),d=[];class u{constructor(t,e){this.id=t,this.element=e,this.members=[],this._index=-1,this._current=null,d.push(this)}static getGroupById(t){for(const e of d)if(e.constructor===this&&e.id===t)return e;return new this(t)}static getGroupByElement(t){for(const e of d)if(e.element===t)return e;return new this(!1,t)}static groupById(t,e){const s=t.element.getAttribute(a);if(null===s)return;e.getGroupById(s).add(t)}static groupByParent(t,e,s){if(void 0===s&&(s=e.selector),""===s)return;let i=t.element.parentElement;for(;i;){if(i.classList.contains(t.constructor.selector))return;if(i.classList.contains(s)){return void e.getGroupByElement(i).add(t)}i=i.parentElement}}static get selector(){return""}add(t){if(-1===this.members.indexOf(t))switch(this.members.push(t),t.setGroup(this),!0){case null!==this.current:case!t.disclosed&&!t.primal:t.disclosed=!1;break;default:this._current=t,this._index=this.members.indexOf(t),t.disclosed=!0}}get length(){return this.members.length}get index(){return this._index}set index(t){t<-1||t>=this.length||this._index===t||(null!==this.current&&this.current.conceal(!0,!0),this._index=t,this._current=this._index>-1?this.members[this._index]:null,null!==this.current&&this.current.disclose(!0),this.apply())}get current(){return this._current}set current(t){this.index=this.members.indexOf(t)}get hasFocus(){return void 0===this.current?null:this.current.hasFocus}apply(){}}class m{constructor(t,e){this.element=t,this.disclosure=e,this.hasAttribute=this.element.hasAttribute(this.disclosure.attributeName),this.element.addEventListener("click",this.click.bind(this)),this.observer=new MutationObserver(this.mutate.bind(this)),this.observe()}observe(){this.observer.observe(this.element,{attributes:!0})}click(t){this.disclosure.change(this.hasAttribute)}mutate(t){t.forEach((t=>{"attributes"===t.type&&t.attributeName===this.disclosure.attributeName&&this.disclosure.change(this.disclosed)}))}apply(t){this.hasAttribute&&(this.observer&&this.observer.disconnect(),this.element.setAttribute(this.disclosure.attributeName,t),this.observer&&this.observe())}get disclosed(){return"true"===this.element.getAttribute(this.disclosure.attributeName)}get hasFocus(){return this.element===document.activeElement}}const p=e.event("DISCLOSE"),b=e.event("CONCEAL"),g=[];class f extends c{constructor(t){super(t),this.buttons=[],this._selector=this.constructor.selector,this.modifier=this._selector+"--"+this.type.id,this.attributeName=this.type.ariaState?"aria-"+this.type.id:e.attr(this.type.id),this.pristine=!0;const s=document.querySelectorAll(this.type.ariaControls?`[aria-controls="${this.id}"]`:e.attr.selector("controls",this.id));if(s.length>0)for(let t=0;t<s.length;t++)this.addButton(s[t]);this.disclosed=!0===this.primal,this.gather()}gather(){this.group||(u.groupById(this,this.GroupConstructor),u.groupByParent(this,this.GroupConstructor))}static build(t){const e=Array.prototype.slice.call(t.querySelectorAll(`.${this.selector}`));for(const t of e)g.push(new this(t))}get type(){return this.constructor.type}static get type(){return null}static get selector(){return""}addButton(t){const e=this.buttonFactory(t);e.hasAttribute&&(void 0===this.primal?this.primal=e.disclosed:e.apply(this.primal)),this.buttons.push(e)}get GroupConstructor(){return u}buttonFactory(t){return new m(t,this)}disclose(t){return!this.disclosed&&(this.pristine=!1,this.disclosed=!0,t||void 0===this.group||(this.group.current=this),!0)}conceal(t,e){if(!this.disclosed)return!1;this.pristine=!1,this.disclosed=!1,e||this.focus(),t||void 0===this.group||(this.group.current=null);for(const t of g)t!==this&&this.element.contains(t.element)&&t.reset();return!0}get disclosed(){return this._disclosed}set disclosed(t){if(this._disclosed!==t){this.dispatch(t?p:b,this.type),this._disclosed=t,t?i(this.element,this.modifier):n(this.element,this.modifier);for(let e=0;e<this.buttons.length;e++)this.buttons[e].apply(t)}}reset(){}change(t){if(this.constructor.type.canConceal)switch(!0){case!t:case this.disclosed:this.conceal();break;default:this.disclose()}else this.disclose()}setGroup(t){this.group=t}get buttonHasFocus(){return!!this.buttons.some((t=>t.hasFocus))}get hasFocus(){return this.element===document.activeElement||(this.element.querySelectorAll(":focus").length>0||this.buttonHasFocus)}focus(){for(let t=0;t<this.buttons.length;t++){const e=this.buttons[t];if(e.hasAttribute)return void e.element.focus()}}}f.DISCLOSE_EVENT=p,f.CONCEAL_EVENT=b;const y={expand:{id:"expanded",ariaState:!0,ariaControls:!0,canConceal:!0},select:{id:"selected",ariaState:!0,ariaControls:!0,canConceal:!1},opened:{id:"opened",ariaState:!1,ariaControls:!0,canConceal:!0}};class v{constructor(t){this.element=t,this.collections={}}_add(t,e){void 0===this.collections[t]&&(this.collections[t]=new w(t,this.element)),this.collections[t].add(e)}down(t,e,s,i){this._add("down",new E(t,e,s,i))}up(t,e,s,i){this._add("up",new E(t,e,s,i))}dispose(){for(const t of this.collections)t.dispose();this.types=null}}class w{constructor(t,e){this.type=t,this.element=e,this.actions=[],this.binding=this.handle.bind(this),this.element.addEventListener("key"+t,this.binding)}add(t){this.actions.push(t)}handle(t){for(const e of this.actions)e.handle(t)}dispose(){this.element.removeEventListener("key"+this.type,this.binding),this.actions=null}}class E{constructor(t,e,s,i){this.key=t,this.closure=e,this.preventDefault=!0===s,this.stopPropagation=!0===i}handle(t){t.keyCode===this.key&&(this.closure(t),this.preventDefault&&t.preventDefault(),this.stopPropagation&&t.stopPropagation())}}v.TAB=9,v.ESCAPE=27,v.END=35,v.HOME=36,v.LEFT=37,v.UP=38,v.RIGHT=39,v.DOWN=40;const x=e("collapse"),L=[],S={};class A extends f{constructor(t){super(t),L.push(this),this.requesting=this.request.bind(this),t.addEventListener("transitionend",this.transitionend.bind(this)),this.disclosed&&this.unbound()}gatherByAscendants(){if(!this.group)for(const t in S){let e=this.element.parentElement;for(;e;){if(e.classList.contains(t))return void("string"==typeof S[t]?u.groupByParent(this,u,S[t]):u.groupByParent(this,S[t]));e=e.parentElement}}}gather(){this.gatherByAscendants(),super.gather()}static get type(){return y.expand}static get selector(){return x}static register(t,e){S[t]=e;for(const t of L)t.gatherByAscendants()}transitionend(t){this.disclosed||(this.element.style.maxHeight="")}unbound(){this.element.style.maxHeight="none"}disclose(t){this.disclosed||(this.unbound(),this.adjust(),this.requested=()=>{super.disclose(t)},window.requestAnimationFrame(this.requesting))}conceal(t,e){this.disclosed&&(this.adjust(),this.requested=()=>{super.conceal(t,e)},window.requestAnimationFrame(this.requesting))}request(){this.requested&&this.requested(),this.requested=null}adjust(){this.element.style.setProperty("--collapser","none");const t=this.element.offsetHeight;this.element.style.setProperty("--collapse",-t+"px"),this.element.style.setProperty("--collapser","")}reset(){this.pristine||(this.disclosed=!1)}}t.core.ns=e,t.core.addClass=i,t.core.removeClass=n,t.core.engine=o,t.core.Instance=c,t.core.Initializer=h,t.core.Disclosure=f,t.core.DisclosureButton=m,t.core.DisclosuresGroup=u,t.core.DISCLOSURE_TYPES=y,t.KeyListener=v,t.Collapse=A,t.Equisized=class{constructor(t,e){this.selector=t,this.group=e,this.elements=this.group.querySelectorAll(this.selector),this.maxWidth=0,this.changing=this.change.bind(this),window.addEventListener("resize",this.changing),window.addEventListener("load",this.changing)}change(){this.reset();for(let t=0;t<this.elements.length;t++){const e=this._getWidth(this.elements[t]);e>this.maxWidth&&(this.maxWidth=e)}this.apply()}apply(){for(let t=0;t<this.elements.length;t++)this.elements[t].style.width=this.maxWidth+1+"px"}reset(){for(let t=0;t<this.elements.length;t++)this.elements[t].style.width="auto";this.maxWidth=0}_getWidth(t){let e=t.offsetWidth;const s=getComputedStyle(t);return e+=parseInt(s.marginLeft)+parseInt(s.marginRight),e}};new h(`.${x}`,[()=>{A.build(document)}]);const C=t.core.ns("accordions-group"),_=t.core.ns("accordion");class q extends t.core.DisclosuresGroup{static get selector(){return C}}t.AccordionsGroup=q,t.Collapse.register(_,q);const I=`${t.core.ns.selector("breadcrumb")} ${t.core.ns.selector("collapse")}`;class k extends t.core.Instance{constructor(e){super(e),this.collapse=t.core.Instance.getInstances(e,t.Collapse)[0],this.links=[...this.element.querySelectorAll("a[href]")],this.count=0,this.links.length&&(this.listen(t.core.Disclosure.DISCLOSE_EVENT,this.focus.bind(this)),this.resizing=this.resize.bind(this),window.addEventListener("resize",this.resizing))}focus(){this.links[0].focus(),t.core.engine.renderer.next((()=>{this.verify()}))}verify(){this.count++,this.count>100||document.activeElement!==this.links[0]&&this.focus()}resize(){window.matchMedia("(min-width: 48em)").matches?this.collapse.buttons[0]===document.activeElement&&this.links.focus():this.links.indexOf(document.activeElement)>-1&&this.collapse.focus()}}new t.core.Initializer(I,[()=>{const t=[],e=document.querySelectorAll(I);for(let s=0;s<e.length;s++)t.push(new k(e[s]))}]);const z=t.core.ns.selector("btn"),D=t.core.ns.selector("btns-group"),B=t.core.ns.selector("btns-group--equisized");new t.core.Initializer(D,[()=>{const e=document.querySelectorAll(B),s=[];for(let i=0;i<e.length;i++)s.push(new t.Equisized(z,e[i]))}]);const H=t.core.ns.selector("modal"),P=t.core.ns("modal"),O=t.core.ns("no-scroll"),T=t.core.ns("scroll-shadow"),N=t.core.ns.selector("modal__body"),$=['[tabindex="0"]',"a[href]","button:not([disabled])","input:not([disabled])","select:not([disabled])","textarea:not([disabled])","audio[controls]","video[controls]",'[contenteditable]:not([contenteditable="false" i])',"details>summary:first-of-type","details"].join(),F=['[tabindex]:not([tabindex="-1"]):not([tabindex="0"])'].join(),G=(t,e)=>{if("hidden"===window.getComputedStyle(t).visibility)return!1;for(void 0===e&&(e=t);e.contains(t);){if("none"===window.getComputedStyle(t).display)return!1;t=t.parentElement}return!0};class W{constructor(t,e){this.element=null,this.activeElement=null,this.onTrap=t,this.onUntrap=e,this.waiting=this.wait.bind(this),this.handling=this.handle.bind(this),this.current=null}get trapped(){return null!==this.element}trap(t){this.trapped&&this.untrap(),this.element=t,this.isTrapping=!0,this.wait(),this.onTrap&&this.onTrap()}wait(){G(this.element)?this.trapping():t.core.engine.renderer.next(this.waiting)}trapping(){if(!this.isTrapping)return;this.isTrapping=!1;const t=this.focusables;t.length&&t[0].focus(),this.element.setAttribute("aria-modal",!0),this.element.addEventListener("keydown",this.handling),this.stunneds=[],this.stun(document.body)}stun(t){for(const e of t.children)e!==this.element&&(e.contains(this.element)?this.stun(e):this.stunneds.push(new M(e)))}handle(t){if(9!==t.keyCode)return;const e=this.focusables;if(0===e.length)return;const s=e[0],i=e[e.length-1],n=e.indexOf(document.activeElement);t.shiftKey?!this.element.contains(document.activeElement)||n<1?(t.preventDefault(),i.focus()):(document.activeElement.tabIndex>0||e[n-1].tabIndex>0)&&(t.preventDefault(),e[n-1].focus()):this.element.contains(document.activeElement)&&n!==e.length-1&&-1!==n?document.activeElement.tabIndex>0&&(t.preventDefault(),e[n+1].focus()):(t.preventDefault(),s.focus())}get focusables(){let t=[...this.element.querySelectorAll($)];const e=[...document.documentElement.querySelectorAll('input[type="radio"]')];if(e.length){const s={};for(const t of e){const e=t.getAttribute("name");void 0===s[e]&&(s[e]=new R(e)),s[e].push(t)}t=t.filter((t=>{if("input"!==t.tagName.toLowerCase()||"radio"!==t.getAttribute("type").toLowerCase())return!0;const e=t.getAttribute("name");return s[e].keep(t)}))}const s=[...this.element.querySelectorAll(F)];s.sort(((t,e)=>t.tabIndex-e.tabIndex));const i=t.filter((t=>-1===s.indexOf(t)));return s.concat(i).filter((t=>"-1"!==t.tabIndex&&G(t,this.element)))}untrap(){if(this.trapped){this.isTrapping=!1,this.element.removeAttribute("aria-modal"),this.element.removeEventListener("keydown",this.handling),this.element=null;for(const t of this.stunneds)t.unstun();this.stunneds=[],this.onUntrap&&this.onUntrap()}}}class M{constructor(t){this.element=t,this.hidden=t.getAttribute("aria-hidden"),this.inert=t.getAttribute("inert"),this.element.setAttribute("aria-hidden",!0),this.element.setAttribute("inert","")}unstun(){null===this.hidden?this.element.removeAttribute("aria-hidden"):this.element.setAttribute("aria-hidden",this.hidden),null===this.inert?this.element.removeAttribute("inert"):this.element.setAttribute("inert",this.inert)}}class R{constructor(t){this.name=t,this.buttons=[]}push(t){this.buttons.push(t),(t===document.activeElement||t.checked||void 0===this.selected)&&(this.selected=t)}keep(t){return this.selected===t}}class K extends t.core.DisclosuresGroup{constructor(){super(),this.trap=new W}apply(t,e){super.apply(t,e),null===this.current?this.trap.untrap():this.trap.trap(this.current.element)}}const V=new K;class U extends t.core.Disclosure{constructor(t){super(t),this.body=this.element.querySelector(N),this.scrollDistance=0,this.scrolling=this.resize.bind(this,!1),this.resizing=this.resize.bind(this,!0),this.init(),this.resize(!0)}init(){this.element.addEventListener("click",this.click.bind(this)),this.keyListener=new t.KeyListener(this.element),this.keyListener.down(t.KeyListener.ESCAPE,this.conceal.bind(this),!0,!0),this.body&&(this.body.addEventListener("scroll",this.scrolling),window.addEventListener("resize",this.resizing))}click(t){this.body&&this.element===t.target&&this.conceal()}gather(){V.add(this)}disclose(t){return!!super.disclose(t)&&(this.resize(!0),this.handleScroll(!1),!0)}conceal(t,e){return!!super.conceal(t,e)&&(this.handleScroll(!0),!0)}handleScroll(e){e?(t.core.removeClass(document.documentElement,O),document.body.style.top="",window.scroll(0,this.scrollDistance)):(document.documentElement.classList.contains(O)||(this.scrollDistance=window.scrollY),document.body.style.top=-1*this.scrollDistance+"px",t.core.addClass(document.documentElement,O))}resize(e,s){this.body&&(this.body.scrollHeight>this.body.clientHeight?this.body.offsetHeight+this.body.scrollTop>=this.body.scrollHeight?t.core.removeClass(this.body,T):t.core.addClass(this.body,T):t.core.removeClass(this.body,T),e&&(this.body.style.maxHeight=window.innerHeight-32+"px",t.core.engine.renderer.next((()=>{this.body.style.maxHeight=window.innerHeight-32+"px"}))))}static get type(){return t.core.DISCLOSURE_TYPES.opened}static get selector(){return P}get GroupConstructor(){return K}}t.Modal=U,t.ModalsGroup=K,t.FocusTrap=W;new t.core.Initializer(H,[()=>{U.build(document)}]);const j=t.core.ns("nav"),Y=t.core.ns("nav__list"),J=t.core.ns("nav__item"),Q=t.core.ns("nav__item--align-right"),X=t.core.ns("menu");class Z extends t.core.DisclosuresGroup{constructor(t,e){super(t,e),this.menus=[],this.navList=e.querySelector(`.${Y}`),document.addEventListener("focusout",this.focusOut.bind(this)),window.addEventListener("resize",this.resize.bind(this)),window.addEventListener("orientationchange",this.resize.bind(this)),this.resize()}static get selector(){return j}add(t){super.add(t),t.element.classList.contains(X)&&this.menus.push(new tt(t,this.navList.getBoundingClientRect().right))}focusOut(t){requestAnimationFrame((()=>{null===this.current||this.current.hasFocus||(this.index=-1)}))}get index(){return super.index}set index(t){-1===t&&null!==this.current&&this.current.hasFocus&&this.current.focus(),super.index=t}resize(){const t=this.navList.getBoundingClientRect().right;for(const e of this.menus)e.place(t)}}class tt{constructor(t,e){this.initialize(t),this.place(e)}initialize(t){this.element=t.element;for(const e of t.buttons)if(e.hasAttribute){this.button=e.element;break}let e=this.element.parentElement;for(;e;){if(e.classList.contains(J)){this.item=e;break}e=e.parentElement}}place(e){const s=getComputedStyle(this.element),i=parseFloat(s.width);this.button.getBoundingClientRect().left+i>e?t.core.addClass(this.item,Q):t.core.removeClass(this.item,Q)}}t.Navigation=Z,t.Collapse.register(j,Z);const et=t.core.ns.attr("theme"),st=t.core.ns.attr("transition");class it{constructor(){this.init()}init(){this.scheme=localStorage.getItem("scheme")?localStorage.getItem("scheme"):null,null===this.scheme&&(window.matchMedia("(prefers-color-scheme: dark)").matches?(this.scheme="dark",localStorage.setItem("scheme","dark")):this.scheme="light"),this.root=document.documentElement,"dark"===this.scheme?this.root.hasAttribute(st)?(this.root.removeAttribute(st),this.root.setAttribute(et,"dark"),setTimeout((()=>{this.root.setAttribute(st,"")}),300)):this.root.setAttribute(et,"dark"):this.root.setAttribute(et,"light"),this.observer=new MutationObserver(this.mutate.bind(this)),this.observer.observe(this.root,{attributes:!0})}mutate(t){t.forEach((t=>{if("attributes"===t.type&&t.attributeName===et){const t=this.root.getAttribute(et);"dark"===t?localStorage.setItem("scheme","dark"):"light"===t&&localStorage.setItem("scheme","light")}}))}}t.Scheme=it;const nt=`input[name="${t.core.ns.selector("radios-theme","")}"]`,rt=t.core.ns.selector("switch-theme","#"),ot=t.core.ns.attr("theme");class ht{constructor(){this.attributeName=ot,this.theme=null,this.radios=document.querySelectorAll(nt);for(var t=0;t<this.radios.length;t++)this.radios[t].addEventListener("change",this.change.bind(this));this.observer=new MutationObserver(this.mutate.bind(this)),this.observe(),this.apply()}observe(){this.observer.observe(document.documentElement,{attributes:!0})}mutate(t){t.forEach((t=>{"attributes"===t.type&&t.attributeName===this.attributeName&&this.apply()}))}apply(){const t=document.documentElement.getAttribute(this.attributeName);this.isApplying=!0;for(var e=0;e<this.radios.length;e++)this.radios[e].checked=this.radios[e].value===t;this.isApplying=!1}change(){this.isApplying||(this.observer&&this.observer.disconnect(),this.theme=document.querySelector(nt+":checked"),this.theme?document.documentElement.setAttribute(this.attributeName,this.theme.value):document.documentElement.removeAttribute(this.attributeName),this.observer&&this.observe())}}new t.core.Initializer(`:root[${et}]`,[()=>{new it}]),new t.core.Initializer(`${rt}`,[()=>{new ht}]);const lt=t.core.ns("sidemenu"),ct=t.core.ns("sidemenu__list");t.Collapse.register(lt,ct);const at=t.core.ns.selector("table"),dt=`${t.core.ns.selector("table")}:not(${t.core.ns.selector("table--no-scroll")})`,ut=t.core.ns("table--shadow"),mt=t.core.ns("table--shadow-left"),pt=t.core.ns("table--shadow-right"),bt=t.core.ns("table__wrapper"),gt=t.core.ns("table--caption-bottom");class ft{constructor(t){this.init(t)}init(t){this.table=t,this.tableElem=this.table.querySelector("table"),this.tableContent=this.tableElem.querySelector("tbody"),this.isScrollable=this.tableContent.offsetWidth>this.tableElem.offsetWidth,this.caption=this.tableElem.querySelector("caption"),this.captionHeight=0,this.wrap();const e=this.change.bind(this);this.tableElem.addEventListener("scroll",e),this.change()}change(){const t=this.tableContent.offsetWidth>this.tableElem.offsetWidth;let e=this.tableElem.offsetWidth>this.table.offsetWidth;t||e?(this.scroll(),this.handleCaption()):t!==this.isScrollable&&this.delete(),this.isScrollable=t,e=!1}delete(){t.core.removeClass(this.table,pt),t.core.removeClass(this.table,mt),t.core.removeClass(this.table,ut),this.caption&&(this.tableElem.style.marginTop="",this.caption.style.top="",this.tableElem.style.marginBottom="",this.caption.style.bottom="")}scroll(){t.core.addClass(this.table,ut),this.setShadowPosition()}wrap(){const t=document.createElement("div");t.className=bt,this.table.insertBefore(t,this.tableElem),t.appendChild(this.tableElem),this.tableInnerWrapper=t}setShadowPosition(){const t=this.getScrollPosition("left"),e=this.getScrollPosition("right");"rtl"===document.documentElement.getAttribute("dir")?(this.setShadowVisibility("right",t),this.setShadowVisibility("left",e)):(this.setShadowVisibility("left",t),this.setShadowVisibility("right",e))}getScrollPosition(t){let e=1;switch("rtl"===document.documentElement.getAttribute("dir")&&(e=-1),t){case"left":return this.tableElem.scrollLeft*e;case"right":return this.tableContent.offsetWidth-this.tableElem.offsetWidth-this.tableElem.scrollLeft*e;default:return!1}}handleCaption(){if(this.caption){const t=getComputedStyle(this.caption),e=this.caption.offsetHeight+parseInt(t.marginTop)+parseInt(t.marginBottom);this.captionHeight=e,this.table.classList.contains(gt)?(this.tableElem.style.marginBottom=this.captionHeight+"px",this.caption.style.bottom=-this.captionHeight+"px"):(this.tableElem.style.marginTop=this.captionHeight+"px",this.caption.style.top=-this.captionHeight+"px")}}setShadowVisibility(e,s){s<=1?"left"===e?t.core.removeClass(this.table,mt):"right"===e&&t.core.removeClass(this.table,pt):"left"===e?t.core.addClass(this.table,mt):"right"===e&&t.core.addClass(this.table,pt)}}t.Table=ft;const yt=[],vt=()=>{for(let t=0;t<yt.length;t++)yt[t].change()};new t.core.Initializer(at,[()=>{const t=document.querySelectorAll(dt);for(let e=0;e<t.length;e++)yt.push(new ft(t[e]));window.addEventListener("resize",vt),window.addEventListener("orientationchange",vt),vt()}]);class wt extends t.core.DisclosureButton{apply(t){super.apply(t),this.hasAttribute&&this.element.setAttribute("tabindex",t?"0":"-1")}}const Et=t.core.ns.selector("tabs"),xt=t.core.ns("tabs"),Lt=t.core.ns("tabs__tab"),St=t.core.ns("tabs__panel"),At=t.core.ns("tabs__list");class Ct extends t.core.DisclosuresGroup{constructor(e,s){super(e,s),this.list=s.querySelector(`.${At}`),s.addEventListener("transitionend",this.transitionend.bind(this)),this.init(),t.core.engine.renderer.add(this.render.bind(this))}static get selector(){return xt}transitionend(t){this.element.style.transition="none"}init(){this.keyListener=new t.KeyListener(this.element),this.keyListener.down(t.KeyListener.RIGHT,this.arrowRightPress.bind(this),!0,!0),this.keyListener.down(t.KeyListener.LEFT,this.arrowLeftPress.bind(this),!0,!0),this.keyListener.down(t.KeyListener.HOME,this.homePress.bind(this),!0,!0),this.keyListener.down(t.KeyListener.END,this.endPress.bind(this),!0,!0)}arrowRightPress(){document.activeElement.classList.contains(Lt)&&(this.index<this.length-1?this.index++:this.index=0,this.focus())}arrowLeftPress(){document.activeElement.classList.contains(Lt)&&(this.index>0?this.index--:this.index=this.length-1,this.focus())}homePress(){document.activeElement.classList.contains(Lt)&&(this.index=0,this.focus())}endPress(){document.activeElement.classList.contains(Lt)&&(this.index=this.length-1,this.focus())}focus(){this.current&&this.current.focus()}apply(){for(let t=0;t<this._index;t++)this.members[t].translate(-1);this.current.element.style.transform="";for(let t=this._index+1;t<this.length;t++)this.members[t].translate(1);this.element.style.transition=""}add(t){if(super.add(t),1===this.length||t.disclosed)this.current=t;else{const e=this.members.indexOf(t);this._index>-1&&this._index!==e&&t.translate(e<this._index?-1:1,!0)}}render(){if(null===this.current)return;const t=Math.round(this.current.element.offsetHeight);this.panelHeight!==t&&(this.panelHeight=t,this.element.style.height=this.panelHeight+this.list.offsetHeight+"px")}}class _t extends t.core.Disclosure{static get type(){return t.core.DISCLOSURE_TYPES.select}static get selector(){return St}get GroupConstructor(){return Ct}buttonFactory(t){return new wt(t,this)}translate(t,e){e&&(this.element.style.transition="none"),this.element.style.transform=`translate(${100*t}%)`,e&&(this.element.style.transition="")}reset(){this.group.index=0}}t.Tab=_t,t.TabButton=wt,t.TabsGroup=Ct;new t.core.Initializer(Et,[()=>{_t.build(document)}]);const qt=t.core.ns.selector("header"),It=t.core.ns.selector("header__tools"),kt=`${It} ${t.core.ns.selector("search-bar")}`,zt=`${It} ${t.core.ns.selector("shortcuts")}`,Dt=t.core.ns.selector("nav"),Bt=`${Dt} ${t.core.ns.selector("nav__list")}`;let Ht=0;class Pt{constructor(t){this.header=t||document.querySelector(qt),this.numId=Ht,Ht++,this.modals=[],this.init()}getModal(e){if(!e)return;const s=t.core.Instance.getInstances(e,t.Modal);s&&s.length&&this.modals.push(s[0])}init(){this.tools=this.header.querySelector(It),this.getModal(this.tools),this.searchBar=this.header.querySelector(kt),this.nav=this.header.querySelector(Dt),this.getModal(this.nav),this.shortcuts=this.header.querySelector(zt),this.navList=this.header.querySelector(Bt),this.changing=this.change.bind(this),window.addEventListener("resize",this.changing),this.change()}change(){if(this.isLarge=window.matchMedia("(min-width: 62em)").matches,this.isLarge)for(let t=0;t<this.modals.length;t++)this.modals[t].conceal(),this.modals[t].element.style.transition="none";else for(let t=0;t<this.modals.length;t++)this.modals[t].element.style.transition="";null!==this.shortcuts&&(this.isLarge?null!==this.searchBar?this.tools.insertBefore(this.shortcuts,this.searchBar):this.tools.appendChild(this.shortcuts):this.nav.insertBefore(this.shortcuts,this.navList))}}t.Header=Pt;new t.core.Initializer(qt,[()=>{const t=Array.prototype.slice.call(document.querySelectorAll(qt)),e=[];for(const s of t)e.push(new Pt(s))}</p>
  
### Reference
* http://blogs.wsj.com/cio/2013/10/08/adobe-source-code-leak-is-bad-news-for-u-s-government/

  
#### CWE Id : 540
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Source Code Disclosure - Java
##### Medium (Medium)
  
  
  
  
#### Description
<p>Application Source Code was disclosed by the web server - Java</p>
  
  
  
* URL: [https://histologe.beta.gouv.fr/js/dsfr.module.min.js](https://histologe.beta.gouv.fr/js/dsfr.module.min.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `class r{constructor(){this.closures=[],this.nexts=[],this.rendering=this.render.bind(this),this.render()}add(t){this.closures.push(t);return()=>{const e=this.closures.indexOf(t);-1!==e&&this.closures.splice(e,1)}}next(t,e){e=void 0===e?0:e-1,void 0===this.nexts[e]&&(this.nexts[e]=[]),this.nexts[e].push(t)}render(){window.requestAnimationFrame(this.rendering);for(const t of this.closures)t.call();const t=this.nexts.shift();if(t)for(const e of t)e.call()}}const o=new class{constructor(){this.renderer=new r}register(t,e){}start(){}stop(){}};class h{constructor(t,e){this.selector=t,this.builders=e,this.instances=[],"loading"!==document.readyState?window.requestAnimationFrame(this.start.bind(this)):document.addEventListener("DOMContentLoaded",this.start.bind(this))}start(){if(!(this.instances.length>0)&&document.querySelectorAll(this.selector).length>0)for(let t=0;t<this.builders.length;t++)this.instances.push(this.builders[t]())}}const l={};class c{constructor(t,e){l[t]||(l[t]=[]),l[t].push(this),this.element=t,this.id=t.id,this.listeners={}}dispatch(t,e){const s=new CustomEvent(t,e);this.element.dispatchEvent(s)}listen(t,e){this.listeners[t]||(this.listeners[t]=[]),this.listeners[t].indexOf(e)>-1||(this.listeners[t].push(e),this.element.addEventListener(t,e))}unlisten(t,e){if(t)if(e){if(!this.listeners[t])return;const s=this.listeners[t].indexOf(e);s>-1&&this.listeners[t].splice(s,1),this.element.removeEventListener(e)}else{if(!this.listeners[t])return;for(const e of this.listeners[t])this.element.removeEventListener(e);this.listeners[t].length=0}else for(const t in this.listeners)this.unlisten(t)}resize(){}destroy(){}static getInstances(t,e){return l[t]?e?l[t].filter((t=>t instanceof e)):l[t]:null}}const a=e.attr("group"),d=[];class u{constructor(t,e){this.id=t,this.element=e,this.members=[],this._index=-1,this._current=null,d.push(this)}static getGroupById(t){for(const e of d)if(e.constructor===this&&e.id===t)return e;return new this(t)}static getGroupByElement(t){for(const e of d)if(e.element===t)return e;return new this(!1,t)}static groupById(t,e){const s=t.element.getAttribute(a);if(null===s)return;e.getGroupById(s).add(t)}static groupByParent(t,e,s){if(void 0===s&&(s=e.selector),""===s)return;let i=t.element.parentElement;for(;i;){if(i.classList.contains(t.constructor.selector))return;if(i.classList.contains(s)){return void e.getGroupByElement(i).add(t)}i=i.parentElement}}static get selector(){return""}add(t){if(-1===this.members.indexOf(t))switch(this.members.push(t),t.setGroup(this),!0){case null!==this.current:case!t.disclosed&&!t.primal:t.disclosed=!1;break;default:this._current=t,this._index=this.members.indexOf(t),t.disclosed=!0}}get length(){return this.members.length}get index(){return this._index}set index(t){t<-1||t>=this.length||this._index===t||(null!==this.current&&this.current.conceal(!0,!0),this._index=t,this._current=this._index>-1?this.members[this._index]:null,null!==this.current&&this.current.disclose(!0),this.apply())}get current(){return this._current}set current(t){this.index=this.members.indexOf(t)}get hasFocus(){return void 0===this.current?null:this.current.hasFocus}apply(){}}class m{constructor(t,e){this.element=t,this.disclosure=e,this.hasAttribute=this.element.hasAttribute(this.disclosure.attributeName),this.element.addEventListener("click",this.click.bind(this)),this.observer=new MutationObserver(this.mutate.bind(this)),this.observe()}observe(){this.observer.observe(this.element,{attributes:!0})}click(t){this.disclosure.change(this.hasAttribute)}mutate(t){t.forEach((t=>{"attributes"===t.type&&t.attributeName===this.disclosure.attributeName&&this.disclosure.change(this.disclosed)}))}apply(t){this.hasAttribute&&(this.observer&&this.observer.disconnect(),this.element.setAttribute(this.disclosure.attributeName,t),this.observer&&this.observe())}get disclosed(){return"true"===this.element.getAttribute(this.disclosure.attributeName)}get hasFocus(){return this.element===document.activeElement}}const p=e.event("DISCLOSE"),b=e.event("CONCEAL"),g=[];class f extends c{constructor(t){super(t),this.buttons=[],this._selector=this.constructor.selector,this.modifier=this._selector+"--"+this.type.id,this.attributeName=this.type.ariaState?"aria-"+this.type.id:e.attr(this.type.id),this.pristine=!0;const s=document.querySelectorAll(this.type.ariaControls?`[aria-controls="${this.id}"]`:e.attr.selector("controls",this.id));if(s.length>0)for(let t=0;t<s.length;t++)this.addButton(s[t]);this.disclosed=!0===this.primal,this.gather()}gather(){this.group||(u.groupById(this,this.GroupConstructor),u.groupByParent(this,this.GroupConstructor))}static build(t){const e=Array.prototype.slice.call(t.querySelectorAll(`.${this.selector}`));for(const t of e)g.push(new this(t))}get type(){return this.constructor.type}static get type(){return null}static get selector(){return""}addButton(t){const e=this.buttonFactory(t);e.hasAttribute&&(void 0===this.primal?this.primal=e.disclosed:e.apply(this.primal)),this.buttons.push(e)}get GroupConstructor(){return u}buttonFactory(t){return new m(t,this)}disclose(t){return!this.disclosed&&(this.pristine=!1,this.disclosed=!0,t||void 0===this.group||(this.group.current=this),!0)}conceal(t,e){if(!this.disclosed)return!1;this.pristine=!1,this.disclosed=!1,e||this.focus(),t||void 0===this.group||(this.group.current=null);for(const t of g)t!==this&&this.element.contains(t.element)&&t.reset();return!0}get disclosed(){return this._disclosed}set disclosed(t){if(this._disclosed!==t){this.dispatch(t?p:b,this.type),this._disclosed=t,t?i(this.element,this.modifier):n(this.element,this.modifier);for(let e=0;e<this.buttons.length;e++)this.buttons[e].apply(t)}}reset(){}change(t){if(this.constructor.type.canConceal)switch(!0){case!t:case this.disclosed:this.conceal();break;default:this.disclose()}else this.disclose()}setGroup(t){this.group=t}get buttonHasFocus(){return!!this.buttons.some((t=>t.hasFocus))}get hasFocus(){return this.element===document.activeElement||(this.element.querySelectorAll(":focus").length>0||this.buttonHasFocus)}focus(){for(let t=0;t<this.buttons.length;t++){const e=this.buttons[t];if(e.hasAttribute)return void e.element.focus()}}}f.DISCLOSE_EVENT=p,f.CONCEAL_EVENT=b;const y={expand:{id:"expanded",ariaState:!0,ariaControls:!0,canConceal:!0},select:{id:"selected",ariaState:!0,ariaControls:!0,canConceal:!1},opened:{id:"opened",ariaState:!1,ariaControls:!0,canConceal:!0}};class v{constructor(t){this.element=t,this.collections={}}_add(t,e){void 0===this.collections[t]&&(this.collections[t]=new w(t,this.element)),this.collections[t].add(e)}down(t,e,s,i){this._add("down",new E(t,e,s,i))}up(t,e,s,i){this._add("up",new E(t,e,s,i))}dispose(){for(const t of this.collections)t.dispose();this.types=null}}class w{constructor(t,e){this.type=t,this.element=e,this.actions=[],this.binding=this.handle.bind(this),this.element.addEventListener("key"+t,this.binding)}add(t){this.actions.push(t)}handle(t){for(const e of this.actions)e.handle(t)}dispose(){this.element.removeEventListener("key"+this.type,this.binding),this.actions=null}}class E{constructor(t,e,s,i){this.key=t,this.closure=e,this.preventDefault=!0===s,this.stopPropagation=!0===i}handle(t){t.keyCode===this.key&&(this.closure(t),this.preventDefault&&t.preventDefault(),this.stopPropagation&&t.stopPropagation())}}v.TAB=9,v.ESCAPE=27,v.END=35,v.HOME=36,v.LEFT=37,v.UP=38,v.RIGHT=39,v.DOWN=40;const x=e("collapse"),L=[],S={};class A extends f{constructor(t){super(t),L.push(this),this.requesting=this.request.bind(this),t.addEventListener("transitionend",this.transitionend.bind(this)),this.disclosed&&this.unbound()}gatherByAscendants(){if(!this.group)for(const t in S){let e=this.element.parentElement;for(;e;){if(e.classList.contains(t))return void("string"==typeof S[t]?u.groupByParent(this,u,S[t]):u.groupByParent(this,S[t]));e=e.parentElement}}}gather(){this.gatherByAscendants(),super.gather()}static get type(){return y.expand}static get selector(){return x}static register(t,e){S[t]=e;for(const t of L)t.gatherByAscendants()}transitionend(t){this.disclosed||(this.element.style.maxHeight="")}unbound(){this.element.style.maxHeight="none"}disclose(t){this.disclosed||(this.unbound(),this.adjust(),this.requested=()=>{super.disclose(t)},window.requestAnimationFrame(this.requesting))}conceal(t,e){this.disclosed&&(this.adjust(),this.requested=()=>{super.conceal(t,e)},window.requestAnimationFrame(this.requesting))}request(){this.requested&&this.requested(),this.requested=null}adjust(){this.element.style.setProperty("--collapser","none");const t=this.element.offsetHeight;this.element.style.setProperty("--collapse",-t+"px"),this.element.style.setProperty("--collapser","")}reset(){this.pristine||(this.disclosed=!1)}}t.core.ns=e,t.core.addClass=i,t.core.removeClass=n,t.core.engine=o,t.core.Instance=c,t.core.Initializer=h,t.core.Disclosure=f,t.core.DisclosureButton=m,t.core.DisclosuresGroup=u,t.core.DISCLOSURE_TYPES=y,t.KeyListener=v,t.Collapse=A,t.Equisized=class{constructor(t,e){this.selector=t,this.group=e,this.elements=this.group.querySelectorAll(this.selector),this.maxWidth=0,this.changing=this.change.bind(this),window.addEventListener("resize",this.changing),window.addEventListener("load",this.changing)}change(){this.reset();for(let t=0;t<this.elements.length;t++){const e=this._getWidth(this.elements[t]);e>this.maxWidth&&(this.maxWidth=e)}this.apply()}apply(){for(let t=0;t<this.elements.length;t++)this.elements[t].style.width=this.maxWidth+1+"px"}reset(){for(let t=0;t<this.elements.length;t++)this.elements[t].style.width="auto";this.maxWidth=0}_getWidth(t){let e=t.offsetWidth;const s=getComputedStyle(t);return e+=parseInt(s.marginLeft)+parseInt(s.marginRight),e}};new h(`.${x}`,[()=>{A.build(document)}]);const C=t.core.ns("accordions-group"),_=t.core.ns("accordion");class q extends t.core.DisclosuresGroup{static get selector(){return C}}t.AccordionsGroup=q,t.Collapse.register(_,q);const I=`${t.core.ns.selector("breadcrumb")} ${t.core.ns.selector("collapse")}`;class k extends t.core.Instance{constructor(e){super(e),this.collapse=t.core.Instance.getInstances(e,t.Collapse)[0],this.links=[...this.element.querySelectorAll("a[href]")],this.count=0,this.links.length&&(this.listen(t.core.Disclosure.DISCLOSE_EVENT,this.focus.bind(this)),this.resizing=this.resize.bind(this),window.addEventListener("resize",this.resizing))}focus(){this.links[0].focus(),t.core.engine.renderer.next((()=>{this.verify()}))}verify(){this.count++,this.count>100||document.activeElement!==this.links[0]&&this.focus()}resize(){window.matchMedia("(min-width: 48em)").matches?this.collapse.buttons[0]===document.activeElement&&this.links.focus():this.links.indexOf(document.activeElement)>-1&&this.collapse.focus()}}new t.core.Initializer(I,[()=>{const t=[],e=document.querySelectorAll(I);for(let s=0;s<e.length;s++)t.push(new k(e[s]))}]);const z=t.core.ns.selector("btn"),D=t.core.ns.selector("btns-group"),B=t.core.ns.selector("btns-group--equisized");new t.core.Initializer(D,[()=>{const e=document.querySelectorAll(B),s=[];for(let i=0;i<e.length;i++)s.push(new t.Equisized(z,e[i]))}]);const H=t.core.ns.selector("modal"),P=t.core.ns("modal"),O=t.core.ns("no-scroll"),T=t.core.ns("scroll-shadow"),N=t.core.ns.selector("modal__body"),$=['[tabindex="0"]',"a[href]","button:not([disabled])","input:not([disabled])","select:not([disabled])","textarea:not([disabled])","audio[controls]","video[controls]",'[contenteditable]:not([contenteditable="false" i])',"details>summary:first-of-type","details"].join(),F=['[tabindex]:not([tabindex="-1"]):not([tabindex="0"])'].join(),G=(t,e)=>{if("hidden"===window.getComputedStyle(t).visibility)return!1;for(void 0===e&&(e=t);e.contains(t);){if("none"===window.getComputedStyle(t).display)return!1;t=t.parentElement}return!0};class W{constructor(t,e){this.element=null,this.activeElement=null,this.onTrap=t,this.onUntrap=e,this.waiting=this.wait.bind(this),this.handling=this.handle.bind(this),this.current=null}get trapped(){return null!==this.element}trap(t){this.trapped&&this.untrap(),this.element=t,this.isTrapping=!0,this.wait(),this.onTrap&&this.onTrap()}wait(){G(this.element)?this.trapping():t.core.engine.renderer.next(this.waiting)}trapping(){if(!this.isTrapping)return;this.isTrapping=!1;const t=this.focusables;t.length&&t[0].focus(),this.element.setAttribute("aria-modal",!0),this.element.addEventListener("keydown",this.handling),this.stunneds=[],this.stun(document.body)}stun(t){for(const e of t.children)e!==this.element&&(e.contains(this.element)?this.stun(e):this.stunneds.push(new M(e)))}handle(t){if(9!==t.keyCode)return;const e=this.focusables;if(0===e.length)return;const s=e[0],i=e[e.length-1],n=e.indexOf(document.activeElement);t.shiftKey?!this.element.contains(document.activeElement)||n<1?(t.preventDefault(),i.focus()):(document.activeElement.tabIndex>0||e[n-1].tabIndex>0)&&(t.preventDefault(),e[n-1].focus()):this.element.contains(document.activeElement)&&n!==e.length-1&&-1!==n?document.activeElement.tabIndex>0&&(t.preventDefault(),e[n+1].focus()):(t.preventDefault(),s.focus())}get focusables(){let t=[...this.element.querySelectorAll($)];const e=[...document.documentElement.querySelectorAll('input[type="radio"]')];if(e.length){const s={};for(const t of e){const e=t.getAttribute("name");void 0===s[e]&&(s[e]=new R(e)),s[e].push(t)}t=t.filter((t=>{if("input"!==t.tagName.toLowerCase()||"radio"!==t.getAttribute("type").toLowerCase())return!0;const e=t.getAttribute("name");return s[e].keep(t)}))}const s=[...this.element.querySelectorAll(F)];s.sort(((t,e)=>t.tabIndex-e.tabIndex));const i=t.filter((t=>-1===s.indexOf(t)));return s.concat(i).filter((t=>"-1"!==t.tabIndex&&G(t,this.element)))}untrap(){if(this.trapped){this.isTrapping=!1,this.element.removeAttribute("aria-modal"),this.element.removeEventListener("keydown",this.handling),this.element=null;for(const t of this.stunneds)t.unstun();this.stunneds=[],this.onUntrap&&this.onUntrap()}}}class M{constructor(t){this.element=t,this.hidden=t.getAttribute("aria-hidden"),this.inert=t.getAttribute("inert"),this.element.setAttribute("aria-hidden",!0),this.element.setAttribute("inert","")}unstun(){null===this.hidden?this.element.removeAttribute("aria-hidden"):this.element.setAttribute("aria-hidden",this.hidden),null===this.inert?this.element.removeAttribute("inert"):this.element.setAttribute("inert",this.inert)}}class R{constructor(t){this.name=t,this.buttons=[]}push(t){this.buttons.push(t),(t===document.activeElement||t.checked||void 0===this.selected)&&(this.selected=t)}keep(t){return this.selected===t}}class K extends t.core.DisclosuresGroup{constructor(){super(),this.trap=new W}apply(t,e){super.apply(t,e),null===this.current?this.trap.untrap():this.trap.trap(this.current.element)}}const V=new K;class U extends t.core.Disclosure{constructor(t){super(t),this.body=this.element.querySelector(N),this.scrollDistance=0,this.scrolling=this.resize.bind(this,!1),this.resizing=this.resize.bind(this,!0),this.init(),this.resize(!0)}init(){this.element.addEventListener("click",this.click.bind(this)),this.keyListener=new t.KeyListener(this.element),this.keyListener.down(t.KeyListener.ESCAPE,this.conceal.bind(this),!0,!0),this.body&&(this.body.addEventListener("scroll",this.scrolling),window.addEventListener("resize",this.resizing))}click(t){this.body&&this.element===t.target&&this.conceal()}gather(){V.add(this)}disclose(t){return!!super.disclose(t)&&(this.resize(!0),this.handleScroll(!1),!0)}conceal(t,e){return!!super.conceal(t,e)&&(this.handleScroll(!0),!0)}handleScroll(e){e?(t.core.removeClass(document.documentElement,O),document.body.style.top="",window.scroll(0,this.scrollDistance)):(document.documentElement.classList.contains(O)||(this.scrollDistance=window.scrollY),document.body.style.top=-1*this.scrollDistance+"px",t.core.addClass(document.documentElement,O))}resize(e,s){this.body&&(this.body.scrollHeight>this.body.clientHeight?this.body.offsetHeight+this.body.scrollTop>=this.body.scrollHeight?t.core.removeClass(this.body,T):t.core.addClass(this.body,T):t.core.removeClass(this.body,T),e&&(this.body.style.maxHeight=window.innerHeight-32+"px",t.core.engine.renderer.next((()=>{this.body.style.maxHeight=window.innerHeight-32+"px"}))))}static get type(){return t.core.DISCLOSURE_TYPES.opened}static get selector(){return P}get GroupConstructor(){return K}}t.Modal=U,t.ModalsGroup=K,t.FocusTrap=W;new t.core.Initializer(H,[()=>{U.build(document)}]);const j=t.core.ns("nav"),Y=t.core.ns("nav__list"),J=t.core.ns("nav__item"),Q=t.core.ns("nav__item--align-right"),X=t.core.ns("menu");class Z extends t.core.DisclosuresGroup{constructor(t,e){super(t,e),this.menus=[],this.navList=e.querySelector(`.${Y}`),document.addEventListener("focusout",this.focusOut.bind(this)),window.addEventListener("resize",this.resize.bind(this)),window.addEventListener("orientationchange",this.resize.bind(this)),this.resize()}static get selector(){return j}add(t){super.add(t),t.element.classList.contains(X)&&this.menus.push(new tt(t,this.navList.getBoundingClientRect().right))}focusOut(t){requestAnimationFrame((()=>{null===this.current||this.current.hasFocus||(this.index=-1)}))}get index(){return super.index}set index(t){-1===t&&null!==this.current&&this.current.hasFocus&&this.current.focus(),super.index=t}resize(){const t=this.navList.getBoundingClientRect().right;for(const e of this.menus)e.place(t)}}class tt{constructor(t,e){this.initialize(t),this.place(e)}initialize(t){this.element=t.element;for(const e of t.buttons)if(e.hasAttribute){this.button=e.element;break}let e=this.element.parentElement;for(;e;){if(e.classList.contains(J)){this.item=e;break}e=e.parentElement}}place(e){const s=getComputedStyle(this.element),i=parseFloat(s.width);this.button.getBoundingClientRect().left+i>e?t.core.addClass(this.item,Q):t.core.removeClass(this.item,Q)}}t.Navigation=Z,t.Collapse.register(j,Z);const et=t.core.ns.attr("theme"),st=t.core.ns.attr("transition");class it{constructor(){this.init()}init(){this.scheme=localStorage.getItem("scheme")?localStorage.getItem("scheme"):null,null===this.scheme&&(window.matchMedia("(prefers-color-scheme: dark)").matches?(this.scheme="dark",localStorage.setItem("scheme","dark")):this.scheme="light"),this.root=document.documentElement,"dark"===this.scheme?this.root.hasAttribute(st)?(this.root.removeAttribute(st),this.root.setAttribute(et,"dark"),setTimeout((()=>{this.root.setAttribute(st,"")}),300)):this.root.setAttribute(et,"dark"):this.root.setAttribute(et,"light"),this.observer=new MutationObserver(this.mutate.bind(this)),this.observer.observe(this.root,{attributes:!0})}mutate(t){t.forEach((t=>{if("attributes"===t.type&&t.attributeName===et){const t=this.root.getAttribute(et);"dark"===t?localStorage.setItem("scheme","dark"):"light"===t&&localStorage.setItem("scheme","light")}}))}}t.Scheme=it;const nt=`input[name="${t.core.ns.selector("radios-theme","")}"]`,rt=t.core.ns.selector("switch-theme","#"),ot=t.core.ns.attr("theme");class ht{constructor(){this.attributeName=ot,this.theme=null,this.radios=document.querySelectorAll(nt);for(var t=0;t<this.radios.length;t++)this.radios[t].addEventListener("change",this.change.bind(this));this.observer=new MutationObserver(this.mutate.bind(this)),this.observe(),this.apply()}observe(){this.observer.observe(document.documentElement,{attributes:!0})}mutate(t){t.forEach((t=>{"attributes"===t.type&&t.attributeName===this.attributeName&&this.apply()}))}apply(){const t=document.documentElement.getAttribute(this.attributeName);this.isApplying=!0;for(var e=0;e<this.radios.length;e++)this.radios[e].checked=this.radios[e].value===t;this.isApplying=!1}change(){this.isApplying||(this.observer&&this.observer.disconnect(),this.theme=document.querySelector(nt+":checked"),this.theme?document.documentElement.setAttribute(this.attributeName,this.theme.value):document.documentElement.removeAttribute(this.attributeName),this.observer&&this.observe())}}new t.core.Initializer(`:root[${et}]`,[()=>{new it}]),new t.core.Initializer(`${rt}`,[()=>{new ht}]);const lt=t.core.ns("sidemenu"),ct=t.core.ns("sidemenu__list");t.Collapse.register(lt,ct);const at=t.core.ns.selector("table"),dt=`${t.core.ns.selector("table")}:not(${t.core.ns.selector("table--no-scroll")})`,ut=t.core.ns("table--shadow"),mt=t.core.ns("table--shadow-left"),pt=t.core.ns("table--shadow-right"),bt=t.core.ns("table__wrapper"),gt=t.core.ns("table--caption-bottom");class ft{constructor(t){this.init(t)}init(t){this.table=t,this.tableElem=this.table.querySelector("table"),this.tableContent=this.tableElem.querySelector("tbody"),this.isScrollable=this.tableContent.offsetWidth>this.tableElem.offsetWidth,this.caption=this.tableElem.querySelector("caption"),this.captionHeight=0,this.wrap();const e=this.change.bind(this);this.tableElem.addEventListener("scroll",e),this.change()}change(){const t=this.tableContent.offsetWidth>this.tableElem.offsetWidth;let e=this.tableElem.offsetWidth>this.table.offsetWidth;t||e?(this.scroll(),this.handleCaption()):t!==this.isScrollable&&this.delete(),this.isScrollable=t,e=!1}delete(){t.core.removeClass(this.table,pt),t.core.removeClass(this.table,mt),t.core.removeClass(this.table,ut),this.caption&&(this.tableElem.style.marginTop="",this.caption.style.top="",this.tableElem.style.marginBottom="",this.caption.style.bottom="")}scroll(){t.core.addClass(this.table,ut),this.setShadowPosition()}wrap(){const t=document.createElement("div");t.className=bt,this.table.insertBefore(t,this.tableElem),t.appendChild(this.tableElem),this.tableInnerWrapper=t}setShadowPosition(){const t=this.getScrollPosition("left"),e=this.getScrollPosition("right");"rtl"===document.documentElement.getAttribute("dir")?(this.setShadowVisibility("right",t),this.setShadowVisibility("left",e)):(this.setShadowVisibility("left",t),this.setShadowVisibility("right",e))}getScrollPosition(t){let e=1;switch("rtl"===document.documentElement.getAttribute("dir")&&(e=-1),t){case"left":return this.tableElem.scrollLeft*e;case"right":return this.tableContent.offsetWidth-this.tableElem.offsetWidth-this.tableElem.scrollLeft*e;default:return!1}}handleCaption(){if(this.caption){const t=getComputedStyle(this.caption),e=this.caption.offsetHeight+parseInt(t.marginTop)+parseInt(t.marginBottom);this.captionHeight=e,this.table.classList.contains(gt)?(this.tableElem.style.marginBottom=this.captionHeight+"px",this.caption.style.bottom=-this.captionHeight+"px"):(this.tableElem.style.marginTop=this.captionHeight+"px",this.caption.style.top=-this.captionHeight+"px")}}setShadowVisibility(e,s){s<=1?"left"===e?t.core.removeClass(this.table,mt):"right"===e&&t.core.removeClass(this.table,pt):"left"===e?t.core.addClass(this.table,mt):"right"===e&&t.core.addClass(this.table,pt)}}t.Table=ft;const yt=[],vt=()=>{for(let t=0;t<yt.length;t++)yt[t].change()};new t.core.Initializer(at,[()=>{const t=document.querySelectorAll(dt);for(let e=0;e<t.length;e++)yt.push(new ft(t[e]));window.addEventListener("resize",vt),window.addEventListener("orientationchange",vt),vt()}]);class wt extends t.core.DisclosureButton{apply(t){super.apply(t),this.hasAttribute&&this.element.setAttribute("tabindex",t?"0":"-1")}}const Et=t.core.ns.selector("tabs"),xt=t.core.ns("tabs"),Lt=t.core.ns("tabs__tab"),St=t.core.ns("tabs__panel"),At=t.core.ns("tabs__list");class Ct extends t.core.DisclosuresGroup{constructor(e,s){super(e,s),this.list=s.querySelector(`.${At}`),s.addEventListener("transitionend",this.transitionend.bind(this)),this.init(),t.core.engine.renderer.add(this.render.bind(this))}static get selector(){return xt}transitionend(t){this.element.style.transition="none"}init(){this.keyListener=new t.KeyListener(this.element),this.keyListener.down(t.KeyListener.RIGHT,this.arrowRightPress.bind(this),!0,!0),this.keyListener.down(t.KeyListener.LEFT,this.arrowLeftPress.bind(this),!0,!0),this.keyListener.down(t.KeyListener.HOME,this.homePress.bind(this),!0,!0),this.keyListener.down(t.KeyListener.END,this.endPress.bind(this),!0,!0)}arrowRightPress(){document.activeElement.classList.contains(Lt)&&(this.index<this.length-1?this.index++:this.index=0,this.focus())}arrowLeftPress(){document.activeElement.classList.contains(Lt)&&(this.index>0?this.index--:this.index=this.length-1,this.focus())}homePress(){document.activeElement.classList.contains(Lt)&&(this.index=0,this.focus())}endPress(){document.activeElement.classList.contains(Lt)&&(this.index=this.length-1,this.focus())}focus(){this.current&&this.current.focus()}apply(){for(let t=0;t<this._index;t++)this.members[t].translate(-1);this.current.element.style.transform="";for(let t=this._index+1;t<this.length;t++)this.members[t].translate(1);this.element.style.transition=""}add(t){if(super.add(t),1===this.length||t.disclosed)this.current=t;else{const e=this.members.indexOf(t);this._index>-1&&this._index!==e&&t.translate(e<this._index?-1:1,!0)}}render(){if(null===this.current)return;const t=Math.round(this.current.element.offsetHeight);this.panelHeight!==t&&(this.panelHeight=t,this.element.style.height=this.panelHeight+this.list.offsetHeight+"px")}}class _t extends t.core.Disclosure{static get type(){return t.core.DISCLOSURE_TYPES.select}static get selector(){return St}get GroupConstructor(){return Ct}buttonFactory(t){return new wt(t,this)}translate(t,e){e&&(this.element.style.transition="none"),this.element.style.transform=`translate(${100*t}%)`,e&&(this.element.style.transition="")}reset(){this.group.index=0}}t.Tab=_t,t.TabButton=wt,t.TabsGroup=Ct;new t.core.Initializer(Et,[()=>{_t.build(document)}]);const qt=t.core.ns.selector("header"),It=t.core.ns.selector("header__tools"),kt=`${It} ${t.core.ns.selector("search-bar")}`,zt=`${It} ${t.core.ns.selector("shortcuts")}`,Dt=t.core.ns.selector("nav"),Bt=`${Dt} ${t.core.ns.selector("nav__list")}`;let Ht=0;class Pt{constructor(t){this.header=t||document.querySelector(qt),this.numId=Ht,Ht++,this.modals=[],this.init()}getModal(e){if(!e)return;const s=t.core.Instance.getInstances(e,t.Modal);s&&s.length&&this.modals.push(s[0])}init(){this.tools=this.header.querySelector(It),this.getModal(this.tools),this.searchBar=this.header.querySelector(kt),this.nav=this.header.querySelector(Dt),this.getModal(this.nav),this.shortcuts=this.header.querySelector(zt),this.navList=this.header.querySelector(Bt),this.changing=this.change.bind(this),window.addEventListener("resize",this.changing),this.change()}change(){if(this.isLarge=window.matchMedia("(min-width: 62em)").matches,this.isLarge)for(let t=0;t<this.modals.length;t++)this.modals[t].conceal(),this.modals[t].element.style.transition="none";else for(let t=0;t<this.modals.length;t++)this.modals[t].element.style.transition="";null!==this.shortcuts&&(this.isLarge?null!==this.searchBar?this.tools.insertBefore(this.shortcuts,this.searchBar):this.tools.appendChild(this.shortcuts):this.nav.insertBefore(this.shortcuts,this.navList))}}t.Header=Pt;new t.core.Initializer(qt,[()=>{const t=Array.prototype.slice.call(document.querySelectorAll(qt)),e=[];for(const s of t)e.push(new Pt(s))}`
  
  
  
  
Instances: 1
  
### Solution
<p>Ensure that application Source Code is not available with alternative extensions, and ensure that source code is not present within other files or data deployed to the web server, or served by the web server. </p>
  
### Other information
<p>class r{constructor(){this.closures=[],this.nexts=[],this.rendering=this.render.bind(this),this.render()}add(t){this.closures.push(t);return()=>{const e=this.closures.indexOf(t);-1!==e&&this.closures.splice(e,1)}}next(t,e){e=void 0===e?0:e-1,void 0===this.nexts[e]&&(this.nexts[e]=[]),this.nexts[e].push(t)}render(){window.requestAnimationFrame(this.rendering);for(const t of this.closures)t.call();const t=this.nexts.shift();if(t)for(const e of t)e.call()}}const o=new class{constructor(){this.renderer=new r}register(t,e){}start(){}stop(){}};class h{constructor(t,e){this.selector=t,this.builders=e,this.instances=[],"loading"!==document.readyState?window.requestAnimationFrame(this.start.bind(this)):document.addEventListener("DOMContentLoaded",this.start.bind(this))}start(){if(!(this.instances.length>0)&&document.querySelectorAll(this.selector).length>0)for(let t=0;t<this.builders.length;t++)this.instances.push(this.builders[t]())}}const l={};class c{constructor(t,e){l[t]||(l[t]=[]),l[t].push(this),this.element=t,this.id=t.id,this.listeners={}}dispatch(t,e){const s=new CustomEvent(t,e);this.element.dispatchEvent(s)}listen(t,e){this.listeners[t]||(this.listeners[t]=[]),this.listeners[t].indexOf(e)>-1||(this.listeners[t].push(e),this.element.addEventListener(t,e))}unlisten(t,e){if(t)if(e){if(!this.listeners[t])return;const s=this.listeners[t].indexOf(e);s>-1&&this.listeners[t].splice(s,1),this.element.removeEventListener(e)}else{if(!this.listeners[t])return;for(const e of this.listeners[t])this.element.removeEventListener(e);this.listeners[t].length=0}else for(const t in this.listeners)this.unlisten(t)}resize(){}destroy(){}static getInstances(t,e){return l[t]?e?l[t].filter((t=>t instanceof e)):l[t]:null}}const a=e.attr("group"),d=[];class u{constructor(t,e){this.id=t,this.element=e,this.members=[],this._index=-1,this._current=null,d.push(this)}static getGroupById(t){for(const e of d)if(e.constructor===this&&e.id===t)return e;return new this(t)}static getGroupByElement(t){for(const e of d)if(e.element===t)return e;return new this(!1,t)}static groupById(t,e){const s=t.element.getAttribute(a);if(null===s)return;e.getGroupById(s).add(t)}static groupByParent(t,e,s){if(void 0===s&&(s=e.selector),""===s)return;let i=t.element.parentElement;for(;i;){if(i.classList.contains(t.constructor.selector))return;if(i.classList.contains(s)){return void e.getGroupByElement(i).add(t)}i=i.parentElement}}static get selector(){return""}add(t){if(-1===this.members.indexOf(t))switch(this.members.push(t),t.setGroup(this),!0){case null!==this.current:case!t.disclosed&&!t.primal:t.disclosed=!1;break;default:this._current=t,this._index=this.members.indexOf(t),t.disclosed=!0}}get length(){return this.members.length}get index(){return this._index}set index(t){t<-1||t>=this.length||this._index===t||(null!==this.current&&this.current.conceal(!0,!0),this._index=t,this._current=this._index>-1?this.members[this._index]:null,null!==this.current&&this.current.disclose(!0),this.apply())}get current(){return this._current}set current(t){this.index=this.members.indexOf(t)}get hasFocus(){return void 0===this.current?null:this.current.hasFocus}apply(){}}class m{constructor(t,e){this.element=t,this.disclosure=e,this.hasAttribute=this.element.hasAttribute(this.disclosure.attributeName),this.element.addEventListener("click",this.click.bind(this)),this.observer=new MutationObserver(this.mutate.bind(this)),this.observe()}observe(){this.observer.observe(this.element,{attributes:!0})}click(t){this.disclosure.change(this.hasAttribute)}mutate(t){t.forEach((t=>{"attributes"===t.type&&t.attributeName===this.disclosure.attributeName&&this.disclosure.change(this.disclosed)}))}apply(t){this.hasAttribute&&(this.observer&&this.observer.disconnect(),this.element.setAttribute(this.disclosure.attributeName,t),this.observer&&this.observe())}get disclosed(){return"true"===this.element.getAttribute(this.disclosure.attributeName)}get hasFocus(){return this.element===document.activeElement}}const p=e.event("DISCLOSE"),b=e.event("CONCEAL"),g=[];class f extends c{constructor(t){super(t),this.buttons=[],this._selector=this.constructor.selector,this.modifier=this._selector+"--"+this.type.id,this.attributeName=this.type.ariaState?"aria-"+this.type.id:e.attr(this.type.id),this.pristine=!0;const s=document.querySelectorAll(this.type.ariaControls?`[aria-controls="${this.id}"]`:e.attr.selector("controls",this.id));if(s.length>0)for(let t=0;t<s.length;t++)this.addButton(s[t]);this.disclosed=!0===this.primal,this.gather()}gather(){this.group||(u.groupById(this,this.GroupConstructor),u.groupByParent(this,this.GroupConstructor))}static build(t){const e=Array.prototype.slice.call(t.querySelectorAll(`.${this.selector}`));for(const t of e)g.push(new this(t))}get type(){return this.constructor.type}static get type(){return null}static get selector(){return""}addButton(t){const e=this.buttonFactory(t);e.hasAttribute&&(void 0===this.primal?this.primal=e.disclosed:e.apply(this.primal)),this.buttons.push(e)}get GroupConstructor(){return u}buttonFactory(t){return new m(t,this)}disclose(t){return!this.disclosed&&(this.pristine=!1,this.disclosed=!0,t||void 0===this.group||(this.group.current=this),!0)}conceal(t,e){if(!this.disclosed)return!1;this.pristine=!1,this.disclosed=!1,e||this.focus(),t||void 0===this.group||(this.group.current=null);for(const t of g)t!==this&&this.element.contains(t.element)&&t.reset();return!0}get disclosed(){return this._disclosed}set disclosed(t){if(this._disclosed!==t){this.dispatch(t?p:b,this.type),this._disclosed=t,t?i(this.element,this.modifier):n(this.element,this.modifier);for(let e=0;e<this.buttons.length;e++)this.buttons[e].apply(t)}}reset(){}change(t){if(this.constructor.type.canConceal)switch(!0){case!t:case this.disclosed:this.conceal();break;default:this.disclose()}else this.disclose()}setGroup(t){this.group=t}get buttonHasFocus(){return!!this.buttons.some((t=>t.hasFocus))}get hasFocus(){return this.element===document.activeElement||(this.element.querySelectorAll(":focus").length>0||this.buttonHasFocus)}focus(){for(let t=0;t<this.buttons.length;t++){const e=this.buttons[t];if(e.hasAttribute)return void e.element.focus()}}}f.DISCLOSE_EVENT=p,f.CONCEAL_EVENT=b;const y={expand:{id:"expanded",ariaState:!0,ariaControls:!0,canConceal:!0},select:{id:"selected",ariaState:!0,ariaControls:!0,canConceal:!1},opened:{id:"opened",ariaState:!1,ariaControls:!0,canConceal:!0}};class v{constructor(t){this.element=t,this.collections={}}_add(t,e){void 0===this.collections[t]&&(this.collections[t]=new w(t,this.element)),this.collections[t].add(e)}down(t,e,s,i){this._add("down",new E(t,e,s,i))}up(t,e,s,i){this._add("up",new E(t,e,s,i))}dispose(){for(const t of this.collections)t.dispose();this.types=null}}class w{constructor(t,e){this.type=t,this.element=e,this.actions=[],this.binding=this.handle.bind(this),this.element.addEventListener("key"+t,this.binding)}add(t){this.actions.push(t)}handle(t){for(const e of this.actions)e.handle(t)}dispose(){this.element.removeEventListener("key"+this.type,this.binding),this.actions=null}}class E{constructor(t,e,s,i){this.key=t,this.closure=e,this.preventDefault=!0===s,this.stopPropagation=!0===i}handle(t){t.keyCode===this.key&&(this.closure(t),this.preventDefault&&t.preventDefault(),this.stopPropagation&&t.stopPropagation())}}v.TAB=9,v.ESCAPE=27,v.END=35,v.HOME=36,v.LEFT=37,v.UP=38,v.RIGHT=39,v.DOWN=40;const x=e("collapse"),L=[],S={};class A extends f{constructor(t){super(t),L.push(this),this.requesting=this.request.bind(this),t.addEventListener("transitionend",this.transitionend.bind(this)),this.disclosed&&this.unbound()}gatherByAscendants(){if(!this.group)for(const t in S){let e=this.element.parentElement;for(;e;){if(e.classList.contains(t))return void("string"==typeof S[t]?u.groupByParent(this,u,S[t]):u.groupByParent(this,S[t]));e=e.parentElement}}}gather(){this.gatherByAscendants(),super.gather()}static get type(){return y.expand}static get selector(){return x}static register(t,e){S[t]=e;for(const t of L)t.gatherByAscendants()}transitionend(t){this.disclosed||(this.element.style.maxHeight="")}unbound(){this.element.style.maxHeight="none"}disclose(t){this.disclosed||(this.unbound(),this.adjust(),this.requested=()=>{super.disclose(t)},window.requestAnimationFrame(this.requesting))}conceal(t,e){this.disclosed&&(this.adjust(),this.requested=()=>{super.conceal(t,e)},window.requestAnimationFrame(this.requesting))}request(){this.requested&&this.requested(),this.requested=null}adjust(){this.element.style.setProperty("--collapser","none");const t=this.element.offsetHeight;this.element.style.setProperty("--collapse",-t+"px"),this.element.style.setProperty("--collapser","")}reset(){this.pristine||(this.disclosed=!1)}}t.core.ns=e,t.core.addClass=i,t.core.removeClass=n,t.core.engine=o,t.core.Instance=c,t.core.Initializer=h,t.core.Disclosure=f,t.core.DisclosureButton=m,t.core.DisclosuresGroup=u,t.core.DISCLOSURE_TYPES=y,t.KeyListener=v,t.Collapse=A,t.Equisized=class{constructor(t,e){this.selector=t,this.group=e,this.elements=this.group.querySelectorAll(this.selector),this.maxWidth=0,this.changing=this.change.bind(this),window.addEventListener("resize",this.changing),window.addEventListener("load",this.changing)}change(){this.reset();for(let t=0;t<this.elements.length;t++){const e=this._getWidth(this.elements[t]);e>this.maxWidth&&(this.maxWidth=e)}this.apply()}apply(){for(let t=0;t<this.elements.length;t++)this.elements[t].style.width=this.maxWidth+1+"px"}reset(){for(let t=0;t<this.elements.length;t++)this.elements[t].style.width="auto";this.maxWidth=0}_getWidth(t){let e=t.offsetWidth;const s=getComputedStyle(t);return e+=parseInt(s.marginLeft)+parseInt(s.marginRight),e}};new h(`.${x}`,[()=>{A.build(document)}]);const C=t.core.ns("accordions-group"),_=t.core.ns("accordion");class q extends t.core.DisclosuresGroup{static get selector(){return C}}t.AccordionsGroup=q,t.Collapse.register(_,q);const I=`${t.core.ns.selector("breadcrumb")} ${t.core.ns.selector("collapse")}`;class k extends t.core.Instance{constructor(e){super(e),this.collapse=t.core.Instance.getInstances(e,t.Collapse)[0],this.links=[...this.element.querySelectorAll("a[href]")],this.count=0,this.links.length&&(this.listen(t.core.Disclosure.DISCLOSE_EVENT,this.focus.bind(this)),this.resizing=this.resize.bind(this),window.addEventListener("resize",this.resizing))}focus(){this.links[0].focus(),t.core.engine.renderer.next((()=>{this.verify()}))}verify(){this.count++,this.count>100||document.activeElement!==this.links[0]&&this.focus()}resize(){window.matchMedia("(min-width: 48em)").matches?this.collapse.buttons[0]===document.activeElement&&this.links.focus():this.links.indexOf(document.activeElement)>-1&&this.collapse.focus()}}new t.core.Initializer(I,[()=>{const t=[],e=document.querySelectorAll(I);for(let s=0;s<e.length;s++)t.push(new k(e[s]))}]);const z=t.core.ns.selector("btn"),D=t.core.ns.selector("btns-group"),B=t.core.ns.selector("btns-group--equisized");new t.core.Initializer(D,[()=>{const e=document.querySelectorAll(B),s=[];for(let i=0;i<e.length;i++)s.push(new t.Equisized(z,e[i]))}]);const H=t.core.ns.selector("modal"),P=t.core.ns("modal"),O=t.core.ns("no-scroll"),T=t.core.ns("scroll-shadow"),N=t.core.ns.selector("modal__body"),$=['[tabindex="0"]',"a[href]","button:not([disabled])","input:not([disabled])","select:not([disabled])","textarea:not([disabled])","audio[controls]","video[controls]",'[contenteditable]:not([contenteditable="false" i])',"details>summary:first-of-type","details"].join(),F=['[tabindex]:not([tabindex="-1"]):not([tabindex="0"])'].join(),G=(t,e)=>{if("hidden"===window.getComputedStyle(t).visibility)return!1;for(void 0===e&&(e=t);e.contains(t);){if("none"===window.getComputedStyle(t).display)return!1;t=t.parentElement}return!0};class W{constructor(t,e){this.element=null,this.activeElement=null,this.onTrap=t,this.onUntrap=e,this.waiting=this.wait.bind(this),this.handling=this.handle.bind(this),this.current=null}get trapped(){return null!==this.element}trap(t){this.trapped&&this.untrap(),this.element=t,this.isTrapping=!0,this.wait(),this.onTrap&&this.onTrap()}wait(){G(this.element)?this.trapping():t.core.engine.renderer.next(this.waiting)}trapping(){if(!this.isTrapping)return;this.isTrapping=!1;const t=this.focusables;t.length&&t[0].focus(),this.element.setAttribute("aria-modal",!0),this.element.addEventListener("keydown",this.handling),this.stunneds=[],this.stun(document.body)}stun(t){for(const e of t.children)e!==this.element&&(e.contains(this.element)?this.stun(e):this.stunneds.push(new M(e)))}handle(t){if(9!==t.keyCode)return;const e=this.focusables;if(0===e.length)return;const s=e[0],i=e[e.length-1],n=e.indexOf(document.activeElement);t.shiftKey?!this.element.contains(document.activeElement)||n<1?(t.preventDefault(),i.focus()):(document.activeElement.tabIndex>0||e[n-1].tabIndex>0)&&(t.preventDefault(),e[n-1].focus()):this.element.contains(document.activeElement)&&n!==e.length-1&&-1!==n?document.activeElement.tabIndex>0&&(t.preventDefault(),e[n+1].focus()):(t.preventDefault(),s.focus())}get focusables(){let t=[...this.element.querySelectorAll($)];const e=[...document.documentElement.querySelectorAll('input[type="radio"]')];if(e.length){const s={};for(const t of e){const e=t.getAttribute("name");void 0===s[e]&&(s[e]=new R(e)),s[e].push(t)}t=t.filter((t=>{if("input"!==t.tagName.toLowerCase()||"radio"!==t.getAttribute("type").toLowerCase())return!0;const e=t.getAttribute("name");return s[e].keep(t)}))}const s=[...this.element.querySelectorAll(F)];s.sort(((t,e)=>t.tabIndex-e.tabIndex));const i=t.filter((t=>-1===s.indexOf(t)));return s.concat(i).filter((t=>"-1"!==t.tabIndex&&G(t,this.element)))}untrap(){if(this.trapped){this.isTrapping=!1,this.element.removeAttribute("aria-modal"),this.element.removeEventListener("keydown",this.handling),this.element=null;for(const t of this.stunneds)t.unstun();this.stunneds=[],this.onUntrap&&this.onUntrap()}}}class M{constructor(t){this.element=t,this.hidden=t.getAttribute("aria-hidden"),this.inert=t.getAttribute("inert"),this.element.setAttribute("aria-hidden",!0),this.element.setAttribute("inert","")}unstun(){null===this.hidden?this.element.removeAttribute("aria-hidden"):this.element.setAttribute("aria-hidden",this.hidden),null===this.inert?this.element.removeAttribute("inert"):this.element.setAttribute("inert",this.inert)}}class R{constructor(t){this.name=t,this.buttons=[]}push(t){this.buttons.push(t),(t===document.activeElement||t.checked||void 0===this.selected)&&(this.selected=t)}keep(t){return this.selected===t}}class K extends t.core.DisclosuresGroup{constructor(){super(),this.trap=new W}apply(t,e){super.apply(t,e),null===this.current?this.trap.untrap():this.trap.trap(this.current.element)}}const V=new K;class U extends t.core.Disclosure{constructor(t){super(t),this.body=this.element.querySelector(N),this.scrollDistance=0,this.scrolling=this.resize.bind(this,!1),this.resizing=this.resize.bind(this,!0),this.init(),this.resize(!0)}init(){this.element.addEventListener("click",this.click.bind(this)),this.keyListener=new t.KeyListener(this.element),this.keyListener.down(t.KeyListener.ESCAPE,this.conceal.bind(this),!0,!0),this.body&&(this.body.addEventListener("scroll",this.scrolling),window.addEventListener("resize",this.resizing))}click(t){this.body&&this.element===t.target&&this.conceal()}gather(){V.add(this)}disclose(t){return!!super.disclose(t)&&(this.resize(!0),this.handleScroll(!1),!0)}conceal(t,e){return!!super.conceal(t,e)&&(this.handleScroll(!0),!0)}handleScroll(e){e?(t.core.removeClass(document.documentElement,O),document.body.style.top="",window.scroll(0,this.scrollDistance)):(document.documentElement.classList.contains(O)||(this.scrollDistance=window.scrollY),document.body.style.top=-1*this.scrollDistance+"px",t.core.addClass(document.documentElement,O))}resize(e,s){this.body&&(this.body.scrollHeight>this.body.clientHeight?this.body.offsetHeight+this.body.scrollTop>=this.body.scrollHeight?t.core.removeClass(this.body,T):t.core.addClass(this.body,T):t.core.removeClass(this.body,T),e&&(this.body.style.maxHeight=window.innerHeight-32+"px",t.core.engine.renderer.next((()=>{this.body.style.maxHeight=window.innerHeight-32+"px"}))))}static get type(){return t.core.DISCLOSURE_TYPES.opened}static get selector(){return P}get GroupConstructor(){return K}}t.Modal=U,t.ModalsGroup=K,t.FocusTrap=W;new t.core.Initializer(H,[()=>{U.build(document)}]);const j=t.core.ns("nav"),Y=t.core.ns("nav__list"),J=t.core.ns("nav__item"),Q=t.core.ns("nav__item--align-right"),X=t.core.ns("menu");class Z extends t.core.DisclosuresGroup{constructor(t,e){super(t,e),this.menus=[],this.navList=e.querySelector(`.${Y}`),document.addEventListener("focusout",this.focusOut.bind(this)),window.addEventListener("resize",this.resize.bind(this)),window.addEventListener("orientationchange",this.resize.bind(this)),this.resize()}static get selector(){return j}add(t){super.add(t),t.element.classList.contains(X)&&this.menus.push(new tt(t,this.navList.getBoundingClientRect().right))}focusOut(t){requestAnimationFrame((()=>{null===this.current||this.current.hasFocus||(this.index=-1)}))}get index(){return super.index}set index(t){-1===t&&null!==this.current&&this.current.hasFocus&&this.current.focus(),super.index=t}resize(){const t=this.navList.getBoundingClientRect().right;for(const e of this.menus)e.place(t)}}class tt{constructor(t,e){this.initialize(t),this.place(e)}initialize(t){this.element=t.element;for(const e of t.buttons)if(e.hasAttribute){this.button=e.element;break}let e=this.element.parentElement;for(;e;){if(e.classList.contains(J)){this.item=e;break}e=e.parentElement}}place(e){const s=getComputedStyle(this.element),i=parseFloat(s.width);this.button.getBoundingClientRect().left+i>e?t.core.addClass(this.item,Q):t.core.removeClass(this.item,Q)}}t.Navigation=Z,t.Collapse.register(j,Z);const et=t.core.ns.attr("theme"),st=t.core.ns.attr("transition");class it{constructor(){this.init()}init(){this.scheme=localStorage.getItem("scheme")?localStorage.getItem("scheme"):null,null===this.scheme&&(window.matchMedia("(prefers-color-scheme: dark)").matches?(this.scheme="dark",localStorage.setItem("scheme","dark")):this.scheme="light"),this.root=document.documentElement,"dark"===this.scheme?this.root.hasAttribute(st)?(this.root.removeAttribute(st),this.root.setAttribute(et,"dark"),setTimeout((()=>{this.root.setAttribute(st,"")}),300)):this.root.setAttribute(et,"dark"):this.root.setAttribute(et,"light"),this.observer=new MutationObserver(this.mutate.bind(this)),this.observer.observe(this.root,{attributes:!0})}mutate(t){t.forEach((t=>{if("attributes"===t.type&&t.attributeName===et){const t=this.root.getAttribute(et);"dark"===t?localStorage.setItem("scheme","dark"):"light"===t&&localStorage.setItem("scheme","light")}}))}}t.Scheme=it;const nt=`input[name="${t.core.ns.selector("radios-theme","")}"]`,rt=t.core.ns.selector("switch-theme","#"),ot=t.core.ns.attr("theme");class ht{constructor(){this.attributeName=ot,this.theme=null,this.radios=document.querySelectorAll(nt);for(var t=0;t<this.radios.length;t++)this.radios[t].addEventListener("change",this.change.bind(this));this.observer=new MutationObserver(this.mutate.bind(this)),this.observe(),this.apply()}observe(){this.observer.observe(document.documentElement,{attributes:!0})}mutate(t){t.forEach((t=>{"attributes"===t.type&&t.attributeName===this.attributeName&&this.apply()}))}apply(){const t=document.documentElement.getAttribute(this.attributeName);this.isApplying=!0;for(var e=0;e<this.radios.length;e++)this.radios[e].checked=this.radios[e].value===t;this.isApplying=!1}change(){this.isApplying||(this.observer&&this.observer.disconnect(),this.theme=document.querySelector(nt+":checked"),this.theme?document.documentElement.setAttribute(this.attributeName,this.theme.value):document.documentElement.removeAttribute(this.attributeName),this.observer&&this.observe())}}new t.core.Initializer(`:root[${et}]`,[()=>{new it}]),new t.core.Initializer(`${rt}`,[()=>{new ht}]);const lt=t.core.ns("sidemenu"),ct=t.core.ns("sidemenu__list");t.Collapse.register(lt,ct);const at=t.core.ns.selector("table"),dt=`${t.core.ns.selector("table")}:not(${t.core.ns.selector("table--no-scroll")})`,ut=t.core.ns("table--shadow"),mt=t.core.ns("table--shadow-left"),pt=t.core.ns("table--shadow-right"),bt=t.core.ns("table__wrapper"),gt=t.core.ns("table--caption-bottom");class ft{constructor(t){this.init(t)}init(t){this.table=t,this.tableElem=this.table.querySelector("table"),this.tableContent=this.tableElem.querySelector("tbody"),this.isScrollable=this.tableContent.offsetWidth>this.tableElem.offsetWidth,this.caption=this.tableElem.querySelector("caption"),this.captionHeight=0,this.wrap();const e=this.change.bind(this);this.tableElem.addEventListener("scroll",e),this.change()}change(){const t=this.tableContent.offsetWidth>this.tableElem.offsetWidth;let e=this.tableElem.offsetWidth>this.table.offsetWidth;t||e?(this.scroll(),this.handleCaption()):t!==this.isScrollable&&this.delete(),this.isScrollable=t,e=!1}delete(){t.core.removeClass(this.table,pt),t.core.removeClass(this.table,mt),t.core.removeClass(this.table,ut),this.caption&&(this.tableElem.style.marginTop="",this.caption.style.top="",this.tableElem.style.marginBottom="",this.caption.style.bottom="")}scroll(){t.core.addClass(this.table,ut),this.setShadowPosition()}wrap(){const t=document.createElement("div");t.className=bt,this.table.insertBefore(t,this.tableElem),t.appendChild(this.tableElem),this.tableInnerWrapper=t}setShadowPosition(){const t=this.getScrollPosition("left"),e=this.getScrollPosition("right");"rtl"===document.documentElement.getAttribute("dir")?(this.setShadowVisibility("right",t),this.setShadowVisibility("left",e)):(this.setShadowVisibility("left",t),this.setShadowVisibility("right",e))}getScrollPosition(t){let e=1;switch("rtl"===document.documentElement.getAttribute("dir")&&(e=-1),t){case"left":return this.tableElem.scrollLeft*e;case"right":return this.tableContent.offsetWidth-this.tableElem.offsetWidth-this.tableElem.scrollLeft*e;default:return!1}}handleCaption(){if(this.caption){const t=getComputedStyle(this.caption),e=this.caption.offsetHeight+parseInt(t.marginTop)+parseInt(t.marginBottom);this.captionHeight=e,this.table.classList.contains(gt)?(this.tableElem.style.marginBottom=this.captionHeight+"px",this.caption.style.bottom=-this.captionHeight+"px"):(this.tableElem.style.marginTop=this.captionHeight+"px",this.caption.style.top=-this.captionHeight+"px")}}setShadowVisibility(e,s){s<=1?"left"===e?t.core.removeClass(this.table,mt):"right"===e&&t.core.removeClass(this.table,pt):"left"===e?t.core.addClass(this.table,mt):"right"===e&&t.core.addClass(this.table,pt)}}t.Table=ft;const yt=[],vt=()=>{for(let t=0;t<yt.length;t++)yt[t].change()};new t.core.Initializer(at,[()=>{const t=document.querySelectorAll(dt);for(let e=0;e<t.length;e++)yt.push(new ft(t[e]));window.addEventListener("resize",vt),window.addEventListener("orientationchange",vt),vt()}]);class wt extends t.core.DisclosureButton{apply(t){super.apply(t),this.hasAttribute&&this.element.setAttribute("tabindex",t?"0":"-1")}}const Et=t.core.ns.selector("tabs"),xt=t.core.ns("tabs"),Lt=t.core.ns("tabs__tab"),St=t.core.ns("tabs__panel"),At=t.core.ns("tabs__list");class Ct extends t.core.DisclosuresGroup{constructor(e,s){super(e,s),this.list=s.querySelector(`.${At}`),s.addEventListener("transitionend",this.transitionend.bind(this)),this.init(),t.core.engine.renderer.add(this.render.bind(this))}static get selector(){return xt}transitionend(t){this.element.style.transition="none"}init(){this.keyListener=new t.KeyListener(this.element),this.keyListener.down(t.KeyListener.RIGHT,this.arrowRightPress.bind(this),!0,!0),this.keyListener.down(t.KeyListener.LEFT,this.arrowLeftPress.bind(this),!0,!0),this.keyListener.down(t.KeyListener.HOME,this.homePress.bind(this),!0,!0),this.keyListener.down(t.KeyListener.END,this.endPress.bind(this),!0,!0)}arrowRightPress(){document.activeElement.classList.contains(Lt)&&(this.index<this.length-1?this.index++:this.index=0,this.focus())}arrowLeftPress(){document.activeElement.classList.contains(Lt)&&(this.index>0?this.index--:this.index=this.length-1,this.focus())}homePress(){document.activeElement.classList.contains(Lt)&&(this.index=0,this.focus())}endPress(){document.activeElement.classList.contains(Lt)&&(this.index=this.length-1,this.focus())}focus(){this.current&&this.current.focus()}apply(){for(let t=0;t<this._index;t++)this.members[t].translate(-1);this.current.element.style.transform="";for(let t=this._index+1;t<this.length;t++)this.members[t].translate(1);this.element.style.transition=""}add(t){if(super.add(t),1===this.length||t.disclosed)this.current=t;else{const e=this.members.indexOf(t);this._index>-1&&this._index!==e&&t.translate(e<this._index?-1:1,!0)}}render(){if(null===this.current)return;const t=Math.round(this.current.element.offsetHeight);this.panelHeight!==t&&(this.panelHeight=t,this.element.style.height=this.panelHeight+this.list.offsetHeight+"px")}}class _t extends t.core.Disclosure{static get type(){return t.core.DISCLOSURE_TYPES.select}static get selector(){return St}get GroupConstructor(){return Ct}buttonFactory(t){return new wt(t,this)}translate(t,e){e&&(this.element.style.transition="none"),this.element.style.transform=`translate(${100*t}%)`,e&&(this.element.style.transition="")}reset(){this.group.index=0}}t.Tab=_t,t.TabButton=wt,t.TabsGroup=Ct;new t.core.Initializer(Et,[()=>{_t.build(document)}]);const qt=t.core.ns.selector("header"),It=t.core.ns.selector("header__tools"),kt=`${It} ${t.core.ns.selector("search-bar")}`,zt=`${It} ${t.core.ns.selector("shortcuts")}`,Dt=t.core.ns.selector("nav"),Bt=`${Dt} ${t.core.ns.selector("nav__list")}`;let Ht=0;class Pt{constructor(t){this.header=t||document.querySelector(qt),this.numId=Ht,Ht++,this.modals=[],this.init()}getModal(e){if(!e)return;const s=t.core.Instance.getInstances(e,t.Modal);s&&s.length&&this.modals.push(s[0])}init(){this.tools=this.header.querySelector(It),this.getModal(this.tools),this.searchBar=this.header.querySelector(kt),this.nav=this.header.querySelector(Dt),this.getModal(this.nav),this.shortcuts=this.header.querySelector(zt),this.navList=this.header.querySelector(Bt),this.changing=this.change.bind(this),window.addEventListener("resize",this.changing),this.change()}change(){if(this.isLarge=window.matchMedia("(min-width: 62em)").matches,this.isLarge)for(let t=0;t<this.modals.length;t++)this.modals[t].conceal(),this.modals[t].element.style.transition="none";else for(let t=0;t<this.modals.length;t++)this.modals[t].element.style.transition="";null!==this.shortcuts&&(this.isLarge?null!==this.searchBar?this.tools.insertBefore(this.shortcuts,this.searchBar):this.tools.appendChild(this.shortcuts):this.nav.insertBefore(this.shortcuts,this.navList))}}t.Header=Pt;new t.core.Initializer(qt,[()=>{const t=Array.prototype.slice.call(document.querySelectorAll(qt)),e=[];for(const s of t)e.push(new Pt(s))}</p>
  
### Reference
* http://blogs.wsj.com/cio/2013/10/08/adobe-source-code-leak-is-bad-news-for-u-s-government/

  
#### CWE Id : 540
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Sub Resource Integrity Attribute Missing
##### Medium (High)
  
  
  
  
#### Description
<p>The integrity attribute is missing on a script or link tag served by an external server. The integrity tag prevents an attacker who have gained access to this server from injecting a malicious content. </p>
  
  
  
* URL: [http://histologe.beta.gouv.fr/dev/js/all.min.js](http://histologe.beta.gouv.fr/dev/js/all.min.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `<script src="'+i[r]+'">`
  
  
  
  
* URL: [http://histologe.beta.gouv.fr/dev/Contact](http://histologe.beta.gouv.fr/dev/Contact)
  
  
  * Method: `GET`
  
  
  * Evidence: `<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.js"></script>`
  
  
  
  
* URL: [http://histologe.beta.gouv.fr/dev/_sign.php](http://histologe.beta.gouv.fr/dev/_sign.php)
  
  
  * Method: `GET`
  
  
  * Evidence: `<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.js"></script>`
  
  
  
  
* URL: [http://histologe.beta.gouv.fr/dev/signale](http://histologe.beta.gouv.fr/dev/signale)
  
  
  * Method: `GET`
  
  
  * Evidence: `<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.js"></script>`
  
  
  
  
Instances: 4
  
### Solution
<p>Provide a valid integrity attribute to the tag.</p>
  
### Reference
* https://developer.mozilla.org/en/docs/Web/Security/Subresource_Integrity

  
#### CWE Id : 16
  
#### WASC Id : 15
  
#### Source ID : 3

  
  
  
  
### Sub Resource Integrity Attribute Missing
##### Medium (High)
  
  
  
  
#### Description
<p>The integrity attribute is missing on a script or link tag served by an external server. The integrity tag prevents an attacker who have gained access to this server from injecting a malicious content. </p>
  
  
  
* URL: [https://histologe.beta.gouv.fr/_sign.php](https://histologe.beta.gouv.fr/_sign.php)
  
  
  * Method: `GET`
  
  
  * Evidence: `<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.js"></script>`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Contact](https://histologe.beta.gouv.fr/Contact)
  
  
  * Method: `GET`
  
  
  * Evidence: `<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.js"></script>`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/js/all.min.js](https://histologe.beta.gouv.fr/js/all.min.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `<script src="'+i[r]+'">`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/signale](https://histologe.beta.gouv.fr/signale)
  
  
  * Method: `GET`
  
  
  * Evidence: `<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.js"></script>`
  
  
  
  
Instances: 4
  
### Solution
<p>Provide a valid integrity attribute to the tag.</p>
  
### Reference
* https://developer.mozilla.org/en/docs/Web/Security/Subresource_Integrity

  
#### CWE Id : 16
  
#### WASC Id : 15
  
#### Source ID : 3

  
  
  
  
### X-Frame-Options Header Not Set
##### Medium (Medium)
  
  
  
  
#### Description
<p>X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks.</p>
  
  
  
* URL: [https://histologe.beta.gouv.fr/connect.php](https://histologe.beta.gouv.fr/connect.php)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Frame-Options`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/_sign.php](https://histologe.beta.gouv.fr/_sign.php)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Frame-Options`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/signale](https://histologe.beta.gouv.fr/signale)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Frame-Options`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Qui](https://histologe.beta.gouv.fr/Qui)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Frame-Options`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Plan-du-site](https://histologe.beta.gouv.fr/Plan-du-site)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Frame-Options`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Aide](https://histologe.beta.gouv.fr/Aide)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Frame-Options`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/](https://histologe.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Frame-Options`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Contact](https://histologe.beta.gouv.fr/Contact)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Frame-Options`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Home](https://histologe.beta.gouv.fr/Home)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Frame-Options`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Chiffres](https://histologe.beta.gouv.fr/Chiffres)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Frame-Options`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr](https://histologe.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Frame-Options`
  
  
  
  
Instances: 11
  
### Solution
<p>Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY. Alternatively consider implementing Content Security Policy's "frame-ancestors" directive. </p>
  
### Reference
* https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Frame-Options

  
#### CWE Id : 16
  
#### WASC Id : 15
  
#### Source ID : 3

  
  
  
  
### Absence of Anti-CSRF Tokens
##### Low (Medium)
  
  
  
  
#### Description
<p>No Anti-CSRF tokens were found in a HTML submission form.</p><p>A cross-site request forgery is an attack that involves forcing a victim to send an HTTP request to a target destination without their knowledge or intent in order to perform an action as the victim. The underlying cause is application functionality using predictable URL/form actions in a repeatable way. The nature of the attack is that CSRF exploits the trust that a web site has for a user. By contrast, cross-site scripting (XSS) exploits the trust that a user has for a web site. Like XSS, CSRF attacks are not necessarily cross-site, but they can be. Cross-site request forgery is also known as CSRF, XSRF, one-click attack, session riding, confused deputy, and sea surf.</p><p></p><p>CSRF attacks are effective in a number of situations, including:</p><p>    * The victim has an active session on the target site.</p><p>    * The victim is authenticated via HTTP auth on the target site.</p><p>    * The victim is on the same local network as the target site.</p><p></p><p>CSRF has primarily been used to perform an action against a target site using the victim's privileges, but recent techniques have been discovered to disclose information by gaining access to the response. The risk of information disclosure is dramatically increased when the target site is vulnerable to XSS, because XSS can be used as a platform for CSRF, allowing the attack to operate within the bounds of the same-origin policy.</p>
  
  
  
* URL: [http://histologe.beta.gouv.fr/dev/signale](http://histologe.beta.gouv.fr/dev/signale)
  
  
  * Method: `GET`
  
  
  * Evidence: `<form class="form-register" action="signFinish2.php" enctype="multipart/form-data" method="post" name="signale" id="signale">`
  
  
  
  
* URL: [http://histologe.beta.gouv.fr/dev/Contact](http://histologe.beta.gouv.fr/dev/Contact)
  
  
  * Method: `GET`
  
  
  * Evidence: `<form method="post" action="Message" name="contact" id="contact">`
  
  
  
  
* URL: [http://histologe.beta.gouv.fr/dev/connect.php](http://histologe.beta.gouv.fr/dev/connect.php)
  
  
  * Method: `GET`
  
  
  * Evidence: `<form class="form-inline mt-2 mt-md-0" action="ident.php" method="post">`
  
  
  
  
* URL: [http://histologe.beta.gouv.fr/dev/_sign.php](http://histologe.beta.gouv.fr/dev/_sign.php)
  
  
  * Method: `GET`
  
  
  * Evidence: `<form class="form-register" action="signFinish2.php" enctype="multipart/form-data" method="post" name="signale" id="signale">`
  
  
  
  
Instances: 4
  
### Solution
<p>Phase: Architecture and Design</p><p>Use a vetted library or framework that does not allow this weakness to occur or provides constructs that make this weakness easier to avoid.</p><p>For example, use anti-CSRF packages such as the OWASP CSRFGuard.</p><p></p><p>Phase: Implementation</p><p>Ensure that your application is free of cross-site scripting issues, because most CSRF defenses can be bypassed using attacker-controlled script.</p><p></p><p>Phase: Architecture and Design</p><p>Generate a unique nonce for each form, place the nonce into the form, and verify the nonce upon receipt of the form. Be sure that the nonce is not predictable (CWE-330).</p><p>Note that this can be bypassed using XSS.</p><p></p><p>Identify especially dangerous operations. When the user performs a dangerous operation, send a separate confirmation request to ensure that the user intended to perform that operation.</p><p>Note that this can be bypassed using XSS.</p><p></p><p>Use the ESAPI Session Management control.</p><p>This control includes a component for CSRF.</p><p></p><p>Do not use the GET method for any request that triggers a state change.</p><p></p><p>Phase: Implementation</p><p>Check the HTTP Referer header to see if the request originated from an expected page. This could break legitimate functionality, because users or proxies may have disabled sending the Referer for privacy reasons.</p>
  
### Other information
<p>No known Anti-CSRF token [anticsrf, CSRFToken, __RequestVerificationToken, csrfmiddlewaretoken, authenticity_token, OWASP_CSRFTOKEN, anoncsrf, csrf_token, _csrf, _csrfSecret, __csrf_magic, CSRF] was found in the following HTML form: [Form 1: "Porte d'entrée du bâtiment et menuiseries extérieures" "criticite7" "État des planchers " "criticite8" "État des escaliers " "criticite9" "Prévention des chutes de personnes" "criticite10" "État des surfaces des murs et plafonds intérieurs" "criticite11" "Protection contre les remontées d'humidité du sol" "criticite13" "Installations du réseau électrique" "criticite14" "Installations du réseau gaz" "criticite15" "Protection incendie" "criticite16" "Équipements de chauffage collectif" "criticite17" "Dispositif d'évacuation des déchets " "criticite18" "Usage général des lieux" "criticite19" "État des façades" "criticite81" "État de la toiture " "criticite82" "Présence d'infiltrations d'eau" "criticite60" "Moisissures importantes" "criticite61" "Zones de peinture écaillée" "criticite62" "Etat ou situation des toilettes du logement" "criticite63" "Etat ou situation de la salle de bain " "criticite64" "Etat et fonctionnement du chauffage fixe" "criticite65" "Alimentation en eau potable" "criticite66" "Dispositif de ventilation du logement" "criticite68" "Présence de nuisibles (blattes, punaises de lit, rongeurs...) " "criticite71" "Évacuation des eaux usées " "criticite75" "Fils électriques dénudés" "criticite55" "Etat des installations électriques" "criticite56" "Fissures importantes sur les murs" "criticite57" "Planchers dangereux" "criticite58" "Garde-corps dangereux" "criticite59" "Eclairage de l'accès au logement" "criticite74" "Protection incendie intérieure" "criticite77" "Escaliers intérieurs dangereux" "criticite78" "Etat des installations gaz " "criticite80" "Infiltration ou fuite d'air" "criticite69" "Factures de chauffage" "criticite70" "Conditions d'isolation thermique générales " "criticite76" "Appareil d'appoint nécessaire pour le chauffage." "criticite79" "Logement situé en sous-sol" "criticite46" "Logement sous les combles ou mansardes" "criticite47" "Salon ou salle à manger sans fenêtre" "criticite48" "Pièce unique de moins de 9m2" "criticite50" "Salon ou salle à manger de moins de 7m2" "criticite52" "Hauteur sous plafond de moins de 2.20 m2" "criticite53" "Niveau de luminosité pour vivre sans éclairage électrique en pleine journée" "criticite54" "Nuisances sonores intérieures" "criticite72" "Nuisances sonores extérieures" "criticite73" "File1" "File2" "File3" "File4" "File5" "File6" "infoPr-1" "infoPr-2" "log-1" "log-2" "Dlog-1" "Dlog-2" "nom" "prenom" "mail" "phone" "num" "libAd" "etage" "numApt" "cp" "ville" "CGU" ].</p>
  
### Reference
* http://projects.webappsec.org/Cross-Site-Request-Forgery
* http://cwe.mitre.org/data/definitions/352.html

  
#### CWE Id : 352
  
#### WASC Id : 9
  
#### Source ID : 3

  
  
  
  
### Absence of Anti-CSRF Tokens
##### Low (Medium)
  
  
  
  
#### Description
<p>No Anti-CSRF tokens were found in a HTML submission form.</p><p>A cross-site request forgery is an attack that involves forcing a victim to send an HTTP request to a target destination without their knowledge or intent in order to perform an action as the victim. The underlying cause is application functionality using predictable URL/form actions in a repeatable way. The nature of the attack is that CSRF exploits the trust that a web site has for a user. By contrast, cross-site scripting (XSS) exploits the trust that a user has for a web site. Like XSS, CSRF attacks are not necessarily cross-site, but they can be. Cross-site request forgery is also known as CSRF, XSRF, one-click attack, session riding, confused deputy, and sea surf.</p><p></p><p>CSRF attacks are effective in a number of situations, including:</p><p>    * The victim has an active session on the target site.</p><p>    * The victim is authenticated via HTTP auth on the target site.</p><p>    * The victim is on the same local network as the target site.</p><p></p><p>CSRF has primarily been used to perform an action against a target site using the victim's privileges, but recent techniques have been discovered to disclose information by gaining access to the response. The risk of information disclosure is dramatically increased when the target site is vulnerable to XSS, because XSS can be used as a platform for CSRF, allowing the attack to operate within the bounds of the same-origin policy.</p>
  
  
  
* URL: [https://histologe.beta.gouv.fr/connect.php](https://histologe.beta.gouv.fr/connect.php)
  
  
  * Method: `GET`
  
  
  * Evidence: `<form class="form-inline mt-2 mt-md-0" action="ident.php" method="post">`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Contact](https://histologe.beta.gouv.fr/Contact)
  
  
  * Method: `GET`
  
  
  * Evidence: `<form method="post" action="Message" name="contact" id="contact">`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/_sign.php](https://histologe.beta.gouv.fr/_sign.php)
  
  
  * Method: `GET`
  
  
  * Evidence: `<form class="form-register" action="signFinish2.php" enctype="multipart/form-data" method="post" name="signale" id="signale">`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/initUser.php](https://histologe.beta.gouv.fr/initUser.php)
  
  
  * Method: `GET`
  
  
  * Evidence: `<form class="form-inline mt-2 mt-md-0" action="first_ident.php" method="post">`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/signale](https://histologe.beta.gouv.fr/signale)
  
  
  * Method: `GET`
  
  
  * Evidence: `<form class="form-register" action="signFinish2.php" enctype="multipart/form-data" method="post" name="signale" id="signale">`
  
  
  
  
Instances: 5
  
### Solution
<p>Phase: Architecture and Design</p><p>Use a vetted library or framework that does not allow this weakness to occur or provides constructs that make this weakness easier to avoid.</p><p>For example, use anti-CSRF packages such as the OWASP CSRFGuard.</p><p></p><p>Phase: Implementation</p><p>Ensure that your application is free of cross-site scripting issues, because most CSRF defenses can be bypassed using attacker-controlled script.</p><p></p><p>Phase: Architecture and Design</p><p>Generate a unique nonce for each form, place the nonce into the form, and verify the nonce upon receipt of the form. Be sure that the nonce is not predictable (CWE-330).</p><p>Note that this can be bypassed using XSS.</p><p></p><p>Identify especially dangerous operations. When the user performs a dangerous operation, send a separate confirmation request to ensure that the user intended to perform that operation.</p><p>Note that this can be bypassed using XSS.</p><p></p><p>Use the ESAPI Session Management control.</p><p>This control includes a component for CSRF.</p><p></p><p>Do not use the GET method for any request that triggers a state change.</p><p></p><p>Phase: Implementation</p><p>Check the HTTP Referer header to see if the request originated from an expected page. This could break legitimate functionality, because users or proxies may have disabled sending the Referer for privacy reasons.</p>
  
### Other information
<p>No known Anti-CSRF token [anticsrf, CSRFToken, __RequestVerificationToken, csrfmiddlewaretoken, authenticity_token, OWASP_CSRFTOKEN, anoncsrf, csrf_token, _csrf, _csrfSecret, __csrf_magic, CSRF] was found in the following HTML form: [Form 1: "id_user" "pws" ].</p>
  
### Reference
* http://projects.webappsec.org/Cross-Site-Request-Forgery
* http://cwe.mitre.org/data/definitions/352.html

  
#### CWE Id : 352
  
#### WASC Id : 9
  
#### Source ID : 3

  
  
  
  
### Application Error Disclosure
##### Low (Medium)
  
  
  
  
#### Description
<p>This page contains an error/warning message that may disclose sensitive information like the location of the file that produced the unhandled exception. This information can be used to launch further attacks against the web application. The alert could be a false positive if the error message is found inside a documentation page.</p>
  
  
  
* URL: [http://histologe.beta.gouv.fr/dev/signFinish2.php](http://histologe.beta.gouv.fr/dev/signFinish2.php)
  
  
  * Method: `POST`
  
  
  * Evidence: `HTTP/1.1 500 Internal Server Error`
  
  
  
  
Instances: 1
  
### Solution
<p>Review the source code of this page. Implement custom error pages. Consider implementing a mechanism to provide a unique error reference/identifier to the client (browser) while logging the details on the server side and not exposing them to the user.</p>
  
### Reference
* 

  
#### CWE Id : 200
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Big Redirect Detected (Potential Sensitive Information Leak)
##### Low (Medium)
  
  
  
  
#### Description
<p>The server has responded with a redirect that seems to provide a large response. This may indicate that although the server sent a redirect it also responded with body content (which may include sensitive details, PII, etc.).</p>
  
  
  
* URL: [http://histologe.beta.gouv.fr/dev/connect.php](http://histologe.beta.gouv.fr/dev/connect.php)
  
  
  * Method: `GET`
  
  
  
  
Instances: 1
  
### Solution
<p>Ensure that no sensitive information is leaked via redirect responses. Redirect responses should have almost no content.</p>
  
### Other information
<p>Location header URI length: 14 [_part/main.php].</p><p>Predicted response size: 314.</p><p>Response Body Length: 7,333.</p>
  
### Reference
* 

  
#### CWE Id : 201
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Big Redirect Detected (Potential Sensitive Information Leak)
##### Low (Medium)
  
  
  
  
#### Description
<p>The server has responded with a redirect that seems to provide a large response. This may indicate that although the server sent a redirect it also responded with body content (which may include sensitive details, PII, etc.).</p>
  
  
  
* URL: [https://histologe.beta.gouv.fr/initUser.php](https://histologe.beta.gouv.fr/initUser.php)
  
  
  * Method: `GET`
  
  
  
  
Instances: 1
  
### Solution
<p>Ensure that no sensitive information is leaked via redirect responses. Redirect responses should have almost no content.</p>
  
### Other information
<p>Location header URI length: 8 [main.php].</p><p>Predicted response size: 308.</p><p>Response Body Length: 6,665.</p>
  
### Reference
* 

  
#### CWE Id : 201
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Cookie No HttpOnly Flag
##### Low (Medium)
  
  
  
  
#### Description
<p>A cookie has been set without the HttpOnly flag, which means that the cookie can be accessed by JavaScript. If a malicious script can be run on this page then the cookie will be accessible and can be transmitted to another site. If this is a session cookie then session hijacking may be possible.</p>
  
  
  
* URL: [https://histologe.beta.gouv.fr/connect.php](https://histologe.beta.gouv.fr/connect.php)
  
  
  * Method: `GET`
  
  
  * Parameter: `PHPSESSID`
  
  
  * Evidence: `Set-Cookie: PHPSESSID`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/_sign.php](https://histologe.beta.gouv.fr/_sign.php)
  
  
  * Method: `GET`
  
  
  * Parameter: `PHPSESSID`
  
  
  * Evidence: `Set-Cookie: PHPSESSID`
  
  
  
  
Instances: 2
  
### Solution
<p>Ensure that the HttpOnly flag is set for all cookies.</p>
  
### Reference
* https://owasp.org/www-community/HttpOnly

  
#### CWE Id : 16
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Cookie Without SameSite Attribute
##### Low (Medium)
  
  
  
  
#### Description
<p>A cookie has been set without the SameSite attribute, which means that the cookie can be sent as a result of a 'cross-site' request. The SameSite attribute is an effective counter measure to cross-site request forgery, cross-site script inclusion, and timing attacks.</p>
  
  
  
* URL: [https://histologe.beta.gouv.fr/_sign.php](https://histologe.beta.gouv.fr/_sign.php)
  
  
  * Method: `GET`
  
  
  * Parameter: `PHPSESSID`
  
  
  * Evidence: `Set-Cookie: PHPSESSID`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/connect.php](https://histologe.beta.gouv.fr/connect.php)
  
  
  * Method: `GET`
  
  
  * Parameter: `PHPSESSID`
  
  
  * Evidence: `Set-Cookie: PHPSESSID`
  
  
  
  
Instances: 2
  
### Solution
<p>Ensure that the SameSite attribute is set to either 'lax' or ideally 'strict' for all cookies.</p>
  
### Reference
* https://tools.ietf.org/html/draft-ietf-httpbis-cookie-same-site

  
#### CWE Id : 16
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Cookie Without Secure Flag
##### Low (Medium)
  
  
  
  
#### Description
<p>A cookie has been set without the secure flag, which means that the cookie can be accessed via unencrypted connections.</p>
  
  
  
* URL: [https://histologe.beta.gouv.fr/_sign.php](https://histologe.beta.gouv.fr/_sign.php)
  
  
  * Method: `GET`
  
  
  * Parameter: `PHPSESSID`
  
  
  * Evidence: `Set-Cookie: PHPSESSID`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/connect.php](https://histologe.beta.gouv.fr/connect.php)
  
  
  * Method: `GET`
  
  
  * Parameter: `PHPSESSID`
  
  
  * Evidence: `Set-Cookie: PHPSESSID`
  
  
  
  
Instances: 2
  
### Solution
<p>Whenever a cookie contains sensitive information or is a session token, then it should always be passed using an encrypted channel. Ensure that the secure flag is set for cookies containing such sensitive information.</p>
  
### Reference
* https://owasp.org/www-project-web-security-testing-guide/v41/4-Web_Application_Security_Testing/06-Session_Management_Testing/02-Testing_for_Cookies_Attributes.html

  
#### CWE Id : 614
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Cross-Domain JavaScript Source File Inclusion
##### Low (Medium)
  
  
  
  
#### Description
<p>The page includes one or more script files from a third-party domain.</p>
  
  
  
* URL: [http://histologe.beta.gouv.fr/dev/signale](http://histologe.beta.gouv.fr/dev/signale)
  
  
  * Method: `GET`
  
  
  * Parameter: `https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.js`
  
  
  * Evidence: `<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.js"></script>`
  
  
  
  
* URL: [http://histologe.beta.gouv.fr/dev/_sign.php](http://histologe.beta.gouv.fr/dev/_sign.php)
  
  
  * Method: `GET`
  
  
  * Parameter: `https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.js`
  
  
  * Evidence: `<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.js"></script>`
  
  
  
  
* URL: [http://histologe.beta.gouv.fr/dev/Contact](http://histologe.beta.gouv.fr/dev/Contact)
  
  
  * Method: `GET`
  
  
  * Parameter: `https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.js`
  
  
  * Evidence: `<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.js"></script>`
  
  
  
  
Instances: 3
  
### Solution
<p>Ensure JavaScript source files are loaded from only trusted sources, and the sources can't be controlled by end users of the application.</p>
  
### Reference
* 

  
#### CWE Id : 829
  
#### WASC Id : 15
  
#### Source ID : 3

  
  
  
  
### Cross-Domain JavaScript Source File Inclusion
##### Low (Medium)
  
  
  
  
#### Description
<p>The page includes one or more script files from a third-party domain.</p>
  
  
  
* URL: [https://histologe.beta.gouv.fr/_sign.php](https://histologe.beta.gouv.fr/_sign.php)
  
  
  * Method: `GET`
  
  
  * Parameter: `https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.js`
  
  
  * Evidence: `<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.js"></script>`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/signale](https://histologe.beta.gouv.fr/signale)
  
  
  * Method: `GET`
  
  
  * Parameter: `https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.js`
  
  
  * Evidence: `<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.js"></script>`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Contact](https://histologe.beta.gouv.fr/Contact)
  
  
  * Method: `GET`
  
  
  * Parameter: `https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.js`
  
  
  * Evidence: `<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.js"></script>`
  
  
  
  
Instances: 3
  
### Solution
<p>Ensure JavaScript source files are loaded from only trusted sources, and the sources can't be controlled by end users of the application.</p>
  
### Reference
* 

  
#### CWE Id : 829
  
#### WASC Id : 15
  
#### Source ID : 3

  
  
  
  
### Dangerous JS Functions
##### Low (Low)
  
  
  
  
#### Description
<p>A dangerous JS function seems to be in use that would leave the site vulnerable.</p>
  
  
  
* URL: [https://histologe.beta.gouv.fr/include/plotly-latest.min.js](https://histologe.beta.gouv.fr/include/plotly-latest.min.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `eVal`
  
  
  
  
Instances: 1
  
### Solution
<p>See the references for security advice on the use of these functions.</p>
  
### Reference
* https://angular.io/guide/security

  
#### CWE Id : 749
  
#### Source ID : 3

  
  
  
  
### Feature Policy Header Not Set
##### Low (Medium)
  
  
  
  
#### Description
<p>Feature Policy Header is an added layer of security that helps to restrict from unauthorized access or usage of browser/client features by web resources. This policy ensures the user privacy by limiting or specifying the features of the browsers can be used by the web resources. Feature Policy provides a set of standard HTTP headers that allow website owners to limit which features of browsers can be used by the page such as camera, microphone, location, full screen etc.</p>
  
  
  
* URL: [https://histologe.beta.gouv.fr/Contact](https://histologe.beta.gouv.fr/Contact)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/_sign.php](https://histologe.beta.gouv.fr/_sign.php)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/dev_qg](https://histologe.beta.gouv.fr/dev_qg)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Home](https://histologe.beta.gouv.fr/Home)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/connect.php](https://histologe.beta.gouv.fr/connect.php)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/signale](https://histologe.beta.gouv.fr/signale)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Aide](https://histologe.beta.gouv.fr/Aide)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr](https://histologe.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Qui](https://histologe.beta.gouv.fr/Qui)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/sitemap.xml](https://histologe.beta.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/](https://histologe.beta.gouv.fr/)
  
  
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
  
  
  
* URL: [https://histologe.beta.gouv.fr/Contact](https://histologe.beta.gouv.fr/Contact)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/CGU](https://histologe.beta.gouv.fr/CGU)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/css/dsfr.min.css](https://histologe.beta.gouv.fr/css/dsfr.min.css)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Home](https://histologe.beta.gouv.fr/Home)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr](https://histologe.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Aide](https://histologe.beta.gouv.fr/Aide)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/](https://histologe.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Plan-du-site](https://histologe.beta.gouv.fr/Plan-du-site)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/robots.txt](https://histologe.beta.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Qui](https://histologe.beta.gouv.fr/Qui)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/images/logo_ANCT_header.svg](https://histologe.beta.gouv.fr/images/logo_ANCT_header.svg)
  
  
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

  
  
  
  
### Strict-Transport-Security Header Not Set
##### Low (High)
  
  
  
  
#### Description
<p>HTTP Strict Transport Security (HSTS) is a web security policy mechanism whereby a web server declares that complying user agents (such as a web browser) are to interact with it using only secure HTTPS connections (i.e. HTTP layered over TLS/SSL). HSTS is an IETF standards track protocol and is specified in RFC 6797.</p>
  
  
  
* URL: [https://histologe.beta.gouv.fr/_adm](https://histologe.beta.gouv.fr/_adm)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/dev](https://histologe.beta.gouv.fr/dev)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/robots.txt](https://histologe.beta.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/dev_qg](https://histologe.beta.gouv.fr/dev_qg)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Aide](https://histologe.beta.gouv.fr/Aide)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Home](https://histologe.beta.gouv.fr/Home)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Qui](https://histologe.beta.gouv.fr/Qui)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/](https://histologe.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/sitemap.xml](https://histologe.beta.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr](https://histologe.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Contact](https://histologe.beta.gouv.fr/Contact)
  
  
  * Method: `GET`
  
  
  
  
Instances: 11
  
### Solution
<p>Ensure that your web server, application server, load balancer, etc. is configured to enforce Strict-Transport-Security.</p>
  
### Reference
* https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html
* https://owasp.org/www-community/Security_Headers
* http://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security
* http://caniuse.com/stricttransportsecurity
* http://tools.ietf.org/html/rfc6797

  
#### CWE Id : 16
  
#### WASC Id : 15
  
#### Source ID : 3

  
  
  
  
### X-Content-Type-Options Header Missing
##### Low (Medium)
  
  
  
  
#### Description
<p>The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'. This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type. Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
  
  
  
* URL: [https://histologe.beta.gouv.fr/signale](https://histologe.beta.gouv.fr/signale)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Qui](https://histologe.beta.gouv.fr/Qui)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/](https://histologe.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Aide](https://histologe.beta.gouv.fr/Aide)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr](https://histologe.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Home](https://histologe.beta.gouv.fr/Home)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Chiffres](https://histologe.beta.gouv.fr/Chiffres)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Contact](https://histologe.beta.gouv.fr/Contact)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/_sign.php](https://histologe.beta.gouv.fr/_sign.php)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/connect.php](https://histologe.beta.gouv.fr/connect.php)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/robots.txt](https://histologe.beta.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
Instances: 11
  
### Solution
<p>Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p><p>If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
  
### Other information
<p>This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.</p><p>At "High" threshold this scan rule will not alert on client or server error responses.</p>
  
### Reference
* http://msdn.microsoft.com/en-us/library/ie/gg622941%28v=vs.85%29.aspx
* https://owasp.org/www-community/Security_Headers

  
#### CWE Id : 16
  
#### WASC Id : 15
  
#### Source ID : 3

  
  
  
  
### Base64 Disclosure
##### Informational (Medium)
  
  
  
  
#### Description
<p>Base64 encoded data was disclosed by the application/web server. Note: in the interests of performance not all base64 strings in the response were analyzed individually, the entire response should be looked at by the analyst/security team/developer(s).</p>
  
  
  
* URL: [http://histologe.beta.gouv.fr/dev/css/dsfr.min.css](http://histologe.beta.gouv.fr/dev/css/dsfr.min.css)
  
  
  * Method: `GET`
  
  
  * Evidence: `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`
  
  
  
  
* URL: [http://histologe.beta.gouv.fr/dev/connect.php](http://histologe.beta.gouv.fr/dev/connect.php)
  
  
  * Method: `GET`
  
  
  * Evidence: `sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN`
  
  
  
  
* URL: [http://histologe.beta.gouv.fr/dev/css/all.min.css](http://histologe.beta.gouv.fr/dev/css/all.min.css)
  
  
  * Method: `GET`
  
  
  * Evidence: `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`
  
  
  
  
* URL: [http://histologe.beta.gouv.fr/dev/js/image.js](http://histologe.beta.gouv.fr/dev/js/image.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `AGFzbQEAAAABFAJgBn9/f39/fwBgB39/f39/f38AAg8BA2VudgZtZW1vcnkCAAEDAwIAAQQEAXAAAAcZAghjb252b2x2ZQAACmNvbnZvbHZlSFYAAQkBAArmAwLBAwEQfwJAIANFDQAgBEUNACAFQQRqIRVBACEMQQAhDQNAIA0hDkEAIRFBACEHA0AgB0ECaiESAn8gBSAHQQF0IgdqIgZBAmouAQAiEwRAQQAhCEEAIBNrIRQgFSAHaiEPIAAgDCAGLgEAakECdGohEEEAIQlBACEKQQAhCwNAIBAoAgAiB0EYdiAPLgEAIgZsIAtqIQsgB0H/AXEgBmwgCGohCCAHQRB2Qf8BcSAGbCAKaiEKIAdBCHZB/wFxIAZsIAlqIQkgD0ECaiEPIBBBBGohECAUQQFqIhQNAAsgEiATagwBC0EAIQtBACEKQQAhCUEAIQggEgshByABIA5BAnRqIApBgMAAakEOdSIGQf8BIAZB/wFIG0EQdEGAgPwHcUEAIAZBAEobIAtBgMAAakEOdSIGQf8BIAZB/wFIG0EYdEEAIAZBAEobciAJQYDAAGpBDnUiBkH/ASAGQf8BSBtBCHRBgP4DcUEAIAZBAEobciAIQYDAAGpBDnUiBkH/ASAGQf8BSBtB/wFxQQAgBkEAShtyNgIAIA4gA2ohDiARQQFqIhEgBEcNAAsgDCACaiEMIA1BAWoiDSADRw0ACwsLIQACQEEAIAIgAyAEIAUgABAAIAJBACAEIAUgBiABEAALCw==`
  
  
  
  
Instances: 4
  
### Solution
<p>Manually confirm that the Base64 data does not leak sensitive information, and that the data cannot be aggregated/used to exploit other vulnerabilities.</p>
  
### Other information
<p>wOFF\x0000\x0001\x0000\x0000\x0000\x0000\x0015�\x0000\x000b\x0000\x0000\x0000\x0000-�\x0000\x0001\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000GSUB\x0000\x0000\x0001\x0008\x0000\x0000\x0000;\x0000\x0000\x0000T �%zOS/2\x0000\x0000\x0001D\x0000\x0000\x0000A\x0000\x0000\x0000VI�N�cmap\x0000\x0000\x0001�\x0000\x0000\x0001q\x0000\x0000\x0005D��ˎglyf\x0000\x0000\x0002�\x0000\x0000\x000e�\x0000\x0000\x001e`agΧhead\x0000\x0000\x0011�\x0000\x0000\x00000\x0000\x0000\x00006\x001c���hhea\x0000\x0000\x0011�\x0000\x0000\x0000\x001c\x0000\x0000\x0000$\x0008r\x0004	hmtx\x0000\x0000\x0011�\x0000\x0000\x0000\x0011\x0000\x0000\x0001 L�\x0000\x0000loca\x0000\x0000\x0012\x0004\x0000\x0000\x0000�\x0000\x0000\x0000��x�\x0002maxp\x0000\x0000\x0012�\x0000\x0000\x0000\x001d\x0000\x0000\x0000 \x0001\\x0000Yname\x0000\x0000\x0012�\x0000\x0000\x0001\x001d\x0000\x0000\x0001�\x0014���post\x0000\x0000\x0013�\x0000\x0000\x0001�\x0000\x0000\x0004�X5��x�c`d``�b0`�c`rq�	a��I,�c�b`a�\x0000�<2�1'3=��\x0003�\x0003ʱ�i\x000e f��\x0002\x0000&;\x0005H\x0000x�c`d��8��������\x0003H���L\x000e\x000cV��@����\x0001+\x0008HsMap���ѝ��\x0001�\x001c�\x0003\x000c\x001f� 9\x0000yS\x000b\x000e\x0000\x0000\x0000x����m�@\x0000\x0005�9\x001duJ��s�9�\x001c؈�sA��\x0016X�̹�2L��\x0001\x0017L�.�n�Y;�\x0015��C\x0003���l�3ߤ�3_�sM�|U���cñ>/:cW}mQ?�E\x000f����
�f�!�\x0019a�1ƙ`�)��a�9�Y`�%�Ya�5��`�-��a�=���\x001fr�1'�r�9\x0017\r�57�r�=\x000f<��3/���;\x001f|�EYN��Gۡ���tŢ��]�m�{�*�U���}R�\x0002�\x0013����\x0005�?�?�@`���U��\x001d</p><p>�p`G\x0002;\x001aر��\x0007v"����</p><p>�t`g\x0002;\x001bع��\x0007v!���]</p><p>�r`W\x0002�\x001aص��\x0007v#����</p><p>�v`w\x0002�\x001bؽ��\x0007� ����\x001e\x0005�8�'�=
�Y`�\x0003{\x0011���^\x0005�:�7��
�]`�\x0003�\x0010���>\x0005�9�/�}
�[`�\x0003�\x0011���~\x0005�\x000cʿX\x0000\x0000\x0000x��Y\x000bl\x001b��٥�z�f��ڑH�dD�֛\x0014��mC�R�%�V�X�e�\x000e֊�49;��:qk\x0004g�\x000c7�9��\x0006n�\x0018Q�8\x0004q\x001fN\x001fƝO\x0001��Crw\x0005\#��\x000eF\x000b\x0004���\x0015W5VYqs3�._2��'i�?w���f��o�_q\x0002�}q�4,���\\x001d��q\x0010�\x001d�c�Y4�u~�߷.\x001a�F\x0004�\x0014�A\x000bx�h�\x000f:p`\x0001�\x000b��S�\x000e\x000e�b\x0003\x0007\x000fi�ό�;�︸c���\x0017����\x0005\x0006\x001b\x001a\x0006��$L\x0014>\x0006�h��wOk[{�W����\x0007�ĕ\x0014��p\x0003�0Ǖx���(�q��Y����\x001d2�����g�\x000b">V�i��>\x0008��n\x00010���vG\x001er\x001d\x0008\x0003w|�Į�Nă'��������}sswe����\x001f�;��ٺ�Vk/�G&"����)\x0012��\x001e��~f�\x0010f�ϻ��\x000eGo�]|Oxh`�0�yL�71��ña��\x0013��/��!\x0005O*�\x0019��8.�\x001e\x0015hw\x0018�#\x001c�B�W���b��ia"\x001dt�C��t���ɤ�L\x0015���#{v����=�2\x00038G\x000f'���b��\x0005ϲ\x0001��\x0008�E��\x0010'\x0007���-�m^�;���I��jW�\fФ2�^3M	\x0003����
\x001cW\x0006\x000e\\x000e��\x0016'</p><p>�<\x000eA</p><p>���O�G�E�Z\x001e�Z_e���r��qUU�M˿��uX,��</p><p>���bI?��0�J\x0011\x0014S�|;���-�\x0001� �/mx\x0014S��#TjO\x0004�b���ϧ���B���Ň��K\)�Ճ\\x0006Q�\x0000\x001a*�ړړq�T�K�cpR����%|��\x0012|=E6Di\x000e?�4���-(�r#�-@_\��</p><p>��l@���\x000cd8��M�g�Q&�S��8���q�gr��g��e�\x0012�\x0006�Y6\x0003�Qy1�������\x0013����%\x0005��q}�\x0005�M�B�'�</p><p>�\x001f!��wS�v\x00196+�\x0015�3\x0005�)\x00056�\x0008�k��T�\x0016����f�.�\x0004���@/�)+mA�e�\x0007wX\x0008h�</p><p>�$?U�_� �y-��D�\x001e�,4G\x0006�NM��\x001e�+n�\x000f�y�\x001e?i�gg�\x0013�Gܼ�\x0018��\x001f�%�R�gƞ:�\x001e6��\x0014i\x000bhϒ�-� k7ac��1\x0018�B�6\x0016����\x0014�����1&���8��\x0001���?�]=�3�\x0012�O�C�ܡdc���0���
w¼\x0001H�\x0017c}D�C\x000f�p\��f\x00171�}a\x0008\x0005\x001dND�\x0011�&�p�C���SZ>&9�ϒ�sy�SJbz�pN드NI\x0018sJ���Ĉ7��5�9N漜\x001f1�<)#ܖ�jv\x0013\x001d�\x0008iIv���X���\x001eC\x0001f��\x0010�\x0012jj��P'lי�:�,�2z�\x000e�6�D>A6\x001b��\x0008�+��01�\x0005ޏ�?e��_�\x0002\�*��(\x0017F�Q\x0019#�\x0018�\x0017���+�\x001c�(E9�\x0008\x0013&��g�fh\x0005���૎R���~\x0002�V���)�s���*��*sk\x0005\x000bW�9��\x0013q�\x0011o�Ÿ�`��EA�����\x001b��\x0018~o/)K8��K</p><p>�s\x0006���8\x0010�fB�\x001b\x000e�ݔ��+��T���ኧ`Q;���/��/Q\x001c�a���\x001d�3t\x0018��/�I��-\x0015</p><p>�mn[I���\x0003&a1+?ɏk},�P���#\x001d�/%t5���\x0003u\x0008\%�E�]�2�\x0010N,\x001f��kS�qm�\x0010���*��VE�	o*�/�\x0016}�!���+�,\x0018��0D�\x001b�ʘ\x0019Q�</p><p>�c
X���ߓ�\x001e�n��K��U.[�i���r�\x0014�~��\x0015b����Z�\x0001��`�</p><p>;OWM���-\x0016�iM�U9.g�&�K�\x0005 Q
\x000e��l�\x001e\x001d�z�B�B�\x001d�S_՞P����HW)�</p><p>s�iɉ����Qsu�\x0008�\x001f`}\x0018u�.�����>�\x000f��j\x0016�Q_6��\x000e�y��WA�x�������\x000e\x001e�n\x0018��'�����"�[�w����p�����\x0007�ѩ����t��$l������\x000f�z2��כ�Fw�߿c��97��1\x0015O�1\x0015O���\x0017�z���\\=Zփ9+�t��Q�_j(]|$�@\x000b~�~��GK��j</p><p>f��ˢ\x0019��,|��?~kú���\x0010\x0017�+�j��РU>�ޯ�L5M��]Q���\x0016kx�\x0007�\x0019</p><p>UK�����}��\x0019�c��ٶ;�\x0011J�J�^���/��\x0010_��_��k}|`���*:�j+�w�j���ޭa��`|�]���\x001bF��=��G��\x0010����v��q0c�A��B\x0006ª�\x001f\x0002��:*ԥ2<\x000c\x000bj"�\x0014&R�>\x0018\x000c'$�V�ğ�8��D�\x0013����\x001f</p><p>��H�6o=</p><p>t�x�.�?��\x0012�͕��d�
����Aj`�$._�+�\x00135٭V����h\x0002cJ��\x0015��m�l��#訔�&�����uG�5\x0005\x001a�nҫ��"�X㗱{\x0002�ƌ�\x0006w^�b�`CI�O��\x0012'S�%�-#�� ��&�e�A\�C��x�\x0017�\x0000n\x0004[5�E��\x0008�\x000e=ö\x0005\x0011� �\x0014\x0004�\x0002צc��G\x001ej�.��짵*C��1��Kl!=M�\x0003�-����ن�ǓI��\x001cS����\x000e�<�@UДDMД�|\x0017�}~�b]r�:% }��\x0015/V�~�\x000c[���>�����0\x0015��f���*"mx���\��� \x0015)��aw�[oZ\x0007'v;�E��\x000e�ǶĒ9�ӗ\x0013dک\\x000cfb�)\x0005�ZF��~l��M\x001d�953�=��NI�d��1\x001c����C�\x0007������XPO6S\x001e\x00067FB�_BQ�j��,�U�P飢\x000bM\x000cҪ�XyT�p&\x0003̨)���V#?\x000b�іğ��6�\x0008�i���SplKa��m�u��O`h��-G�F�iǘ�IjI\x0019��e|�X�A��u�n9\x0005G�P��+��AM�\x0010M�!�\x0018k���\x000e�\x0005�L�L5���/+��x�
�����wMs2G�Chǭ�'�\x0002\x0015��U\x0013�4%\x0010\x001dF�����G0z���O��NkN ����q=�=�1�O�U�o��(�\x0002��\\x0012M\x0015�eeŝ�XQ��\,�Eq^�ĕ{���b\x0016�a���}\x000b�\4��~�\x0001�-����\x0004u͞�͛��yQ��D\x0018d\x0016py�H}�����\x001f#�\x001e�]�Qk2�\x0001�4�̮�z^���tL͔\x0016ʉD�R\x001a���\x0018�)=��d�E��3N)����.���b<��N��*O�e�^g�\x001aA�ӳ���A��}\x001f�A$Ԕ U	]gf��\x0019u�zRo���\x0012�r�"�+&�ǘ\x001dI�_Az\x0010��D�H"\x0001���ZնZ�I!� �-\x0002�kr\x001f��m�zDĺJ�j譭h\x001d�w[G�\x0003%�]>S�\x000ba\x0014]Q\x0004��Uvm�'\x0016\x0010�[\x0002v������)m+Rߔ�ڑ�뢸�F�bO�\x0002"��t�\x0001�U񜒫���j\x0017��vl�w����'���L�\x0017�IΆ��R��\x001e�r�\x0010\x0018�g{g%��G�r�U,�"r�,c\x0007,y��b\x000b\x001f\x000ea��\x0012�Emx�/*��������ZO����>f��EA��⫳��;7T(կ�7~\x0007�4�f�>�i��0[\x0003\x000e(�qg�@tB��E���V��\x0005#�j��%Dp�7y���?ٴ�j��O�<���?��OL\x001e=r�\x001b?m\x000cX�Cً��QS������xr?�F�=��wޕ�\x001a��u�^ǫǦ��|��\x0003��\x0019�ۇ����*��e�%\x0013�'9�~C��Y\x0018�Iʋ]\x0014�zIK��\x000c�ߨ�$��spw`��4l��6��ߑ�,DJPgӿ\x000c2��>�\x0015�ʉ����tL�K\x001a\x001b�:�\x0008j:��~�\x0004��z���~�\x0018Z�6�.</p><p>O_U���\x0019y⡩��ޞ��\x0016i\x0010z</p><p>�����i����Z�2[o!�܇<S�
��FQY�j�M�ζ���\x000ckVb�۟�'[W\x0000\x00189#�\x001f�e{\x001a�|�-���"�#�R}��?\x001d�sT��\x0011�:�;�e��Ӟ��x#�A�\x0008ƫbz3BG5�\x0004t`��\x000b0ș�Kr��l���ݏ����c��4�JFf���\x0019~l��������_\x001d��������\x001fd\x0006�\x0007�j7�	��	�?Ff����\x000c�<�O?�'�1	�u\x0005��@�)NԆ����J�D�c�C��\x0005�\x0015+b'\x0013�YV�\x000e�
�\x001a\x0002����+��3Y�y\x0004\x0016</p><p>�A�/�>�kªR�ћ[���\x000b�\x000b䠨�AyYA
�t3���?a���P��ʎbH���[t\x001f�#��V̰��*XO%\x0004˟\x0005|��\x0012?���\x001f�K\x0008\x0016.-P&-@�h�*-����\x0012�o�>\x0010j\x001c���=O;T��k\x0013/V�.\Z)�_��j��\x001a�U3�x|(��e�K�]�\x001d$�;̸ݑ�k���~�G?z�_o
������kA���m�\x0007�j~h���ɨ\x000c��u�W/�/\P�yG�p!^�\x000b��]��>x��Aí}P�q\x0015\x0007\x0014�X�\x0003�Ht\x001cǍ8�Xk$ԯ\x0008�b>��\x000f���\x001e��jk�R!H�-�������\x001c�����\x001f�Vo�\x0019S\x0016�\x001e3]�\x00175+���U@���[#�?4��\x001ex�c`d``\x0000b�\x000b	���6_\x0019�Y6\x0000E\x0018Y���\x000b�l`>\x0000�r00�D\x0001D�\x000b�x�c`d``>�_���e\x0003\x0003\x0003�dd@\x0005\x001e\x0000V�\x0003�x�c````�0�qa\x0000�1�\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000L\x0000�\x0001\x001c\x00014\x0001d\x0001�\x0001�\x0001�\x0001�\x0001�\x0002\x001a\x0002.\x0002H\x0002b\x0002�\x0002�\x0002�\x0002�\x0002�\x0003\x0006\x0003@\x0003T\x0003�\x0003�\x0004\x0018\x0004D\x0004v\x0004�\x0004�\x0004�\x0005\x0010\x0005|\x0005�\x0006</p><p>\x0006:\x0006`\x0006�\x0006�\x0006�\x0007,\x0007~\x0007�\x0008</p><p>\x00084\x0008d\x0008~\x0008�\x0008�	\x001e	Z	�	�</p><p>N</p><p>�\x000b</p><p>\x000b^\x000b�\x000b�\x000b�\x000c$\x000cp\x000c~\x000c�
"
|
�\x000e\x0000\x000e<\x000e�\x000e�\x000f0\x0000\x0000x�c`d``�`�e�b\x0000\x0001& �\x0002����\x000c\x0000\x0018M\x0001�\x0000\x0000\x0000x�]��N�0\x0014�O��h\x0010\x0002!1��\x000bR�3�\x0001ڙ\x000e���I[%q丕*13�\x0014�<\x0005�ŉ{%*l��;�\x001e_\x001b�\x0003~\x0010�[\x0001��v��\x001b�\x000b�Iw�\x0003��\x0010!��GT/�c�b"\x001c�	o�\x0010\x000cn錑	�p�Z�O�]x@�\x0010\x001er�������\x00181��CL��>5u��űL�g_bm۽��<�y�ֵ��әڞU{*\x0016��*��R+S;]�F5�\x001ctꢝs�r:�ŏRSa�\x0014�n��F�#J$�W�\x001f�LX�tZa�\x0008������g\x00128�\x00193[�Y[�8{A�!�Ι1�H+�K�܆N�{\x0007:)�\x0008;��\x0012S��_>�W�0�Sb\x0000\x0000\x0000x�mR�z�0\x0010\x0013��8v\x001c;m�tפֿt�ݦ�AST����RR�ۗ��d9)\x0001�\x001d�\x0004\x0019,\x0005�\x0006���\x000e�p\x000c�q\x0002'q</p><p>=,��\x0015\x000c0�*FX�\x0018\x0013��4��,6��-��y\�E\�e\�U\�u��M��m��]��}<@��x��x�m<�3<�\x000b��+��\x001b��;��\x0007|�'|�\x0017|�7|�\x000f��\x000e~\x0005\x0003!���2�\x0013�[��L�D\x0014�2�R+�=�=�\x000b�,7Ԑ˭5{ad�2��\x000e/�\x0015Z�ܱ�ᅳ�\x0005�\x000b�W�K5Սegc�\x0015���-x��jD�uH��N��w�*'m�Z�F-㎡tAd���ʜQ\r�䟺�é�焤6��F�g�ÕHiU*�k0Y�@�\x0011�\x0014�*J�%\x0018ym��Ke3�=�=u��\x0003\x000fL\x001cs��Sa��]\x000eI4�$\x001aA�\x000eA(�b�n��I�,66\x0015eb2�^\x0010�Q\x001b�\x00079\x0012"-\x0015�f�\x0010E���</p><p>�k�c�ƹ��\x001dU�-���\x0008��s�d.\x0018��
����T�\x001ewΨ˪تb�]
�\x0019�حs!D'.����\x001bL\x0013�jZZ!ˆ�(�qg�C1�\x000cw��R~\x0008ΰ+t+Ҫ�#\x000b��X�\x0005�G�~��� �\x0007^�~O\x0000\x0000\x0000</p>
  
### Reference
* http://projects.webappsec.org/w/page/13246936/Information%20Leakage

  
#### CWE Id : 200
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Base64 Disclosure
##### Informational (Medium)
  
  
  
  
#### Description
<p>Base64 encoded data was disclosed by the application/web server. Note: in the interests of performance not all base64 strings in the response were analyzed individually, the entire response should be looked at by the analyst/security team/developer(s).</p>
  
  
  
* URL: [https://histologe.beta.gouv.fr/include/plotly-latest.min.js](https://histologe.beta.gouv.fr/include/plotly-latest.min.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/initUser.php](https://histologe.beta.gouv.fr/initUser.php)
  
  
  * Method: `GET`
  
  
  * Evidence: `sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/css/dsfr.min.css](https://histologe.beta.gouv.fr/css/dsfr.min.css)
  
  
  * Method: `GET`
  
  
  * Evidence: `d09GRgABAAAAABXYAAsAAAAALdwAAQAAAAAAAAAAAAAAAAAAAAAAAAAAAABHU1VCAAABCAAAADsAAABUIIslek9TLzIAAAFEAAAAQQAAAFZJwk68Y21hcAAAAYgAAAFxAAAFRPe8y45nbHlmAAAC/AAADqgAAB5gYWfOp2hlYWQAABGkAAAAMAAAADYcnp3DaGhlYQAAEdQAAAAcAAAAJAhyBAlobXR4AAAR8AAAABEAAAEgTNAAAGxvY2EAABIEAAAAkgAAAJL4ePACbWF4cAAAEpgAAAAdAAAAIAFcAFluYW1lAAASuAAAAR0AAAHyFNvC+HBvc3QAABPYAAAB/QAABKxYNfXeeJxjYGRgYOBiMGCwY2BycfMJYeDLSSzJY5BiYGGAAJA8MpsxJzM9kYEDxgPKsYBpDiBmg4gCACY7BUgAeJxjYGSZzziBgZWBgYGf2QNIroDQTA4MVoymQJqBlZkBKwhIc01hcPjI+NGd+cB/AYYc5gMMH4DCjCA5AHlTCw4AAAB4nO3T523cQAAF4TkddUqnnHPOOecc2Ijqc0H+5RZYgcy55zJM4NsBF0zALoFuoFk7qBXQ+EMDj9/1bKMz36S/M1/wq3NN4XxV/vzUY8OxPi86Y1d9bVE/sUUPvfTV9w3QZpAhhhlhlDHGmWCSKaaZYZY55llgkSWWWWGVNdbZYJMtttlhlz326/cfcsQxJ5xyxjkXXHLFNTfccsc9DzzyxDMvvPLGOx988kVZf06L/0fbofn976x0xaKzhl2BbYZ7oSrCVa26w31StQLbE9jewPYFtj/cP9VAYNvh11WDgR0K7HBgRwI7GtixwI4HdiKwk4GdCux0YGcCOxvYucDOB3YhsIuBXQrscmBXArsa2LXArgd2I7Cbgd0K7HZgdwK7G9i9wO4H9iD856vDwB4F9jiwJ4E9DexZYM8DexHYy8BeBfY6sDeBvQ3sXWDvA/sQ2MfAPgX2ObAvgX0N7Ftg3wP7EdjPwH4FtgzKv++UuFgAAAB4nJ1ZC2wb55He2aWWepJmxeXakUiLZESK1psUyehtQ9RSjiWrVpNYtWXFDtaK0jQ5O7KdOnFrBGfnDDfSOY3BBm6aGFHeOARxH04fxp1PAa68Q3J3BVwj9eUORgsEwaHJFVc1VllxczP/Ll8y5conaZc/d/ef+Wb+mW/mX3ECx31xyDQs7OHsXB3XzHEQlB2yY51ZNIt1fp/fty4aiUYEvBTEQQt4xGiwDzpwYAG7C/jxU4cODsRiAwcPab/PjOY7t++4uGP0rv4X/+7F3wUGGxoGx+gkTBQ+ButolN53T2tbe+tXuvr7540H8cSVFOCKcAPcMMeVeLKI6rIo63HAoFnA7O/jHTLe9beA32fGCyI+Vu9pgY4+CLrAbgF/MNLh84h2Rx5yHQgDd3zrxK6vTsSDJ5/96/bBvtfffXNzd2Wl587nH9g7+cDZuo1Way/0RyYikYmv0ykS6O4e6+5+ZoUQZuHPu+3VDkdvx118T3hoYKswuHlM3Tcx+bTDsWHD6b0T+9Qv/4MhBU8qiRnr5jgutx4VaHcY1yMckkKSV/KGveHqYvb7aWEiHXTHQ9/tdIf3qcmkmkwVsfHUI3t2haPR8K491zIDOEcPJ9X0tWKWqAXPsgHC4gjsRf6fECcHtpDNLbltXps7jJqhSbuialfgXGbQpDK7XjNNCQOcjZO4DRxXBg5cDq+bFicKuDwOQQqF6eBPwEeiRa5aHqpaX2WGj8xyzfpxVVWFTcu/qKh1WCyO2gqhs8JiST+sqjCZShEUU558O7eeqy2mAdwgoC9teBRTot0jVGpPBNViupZ/xc+n/6DCQorZ/sWHwn/yS1wpx9WDXAZR9AB/Girj2pPak3GoVL9L42NwUtH+yO8lfLq/Enw9RTZEaQ4/vjSovactKNByI64tQF9cf+6L3wqf8J+SbECngrkMZDjF702fZ/JRJpxTtcU4nISTcY5nco/yZ9HDZbQSuAayWTYDnFF5Mb60hJL5s+kT/LH4jSUF+uhxfc4F/k3EQqsnkwq3HyH5+XdTinYZNivaFf0zBdMpBTbjCL9rl5VU1haJf43ZwmbzLsMEmL6hQC/0KSttQell4Ad3WAhoiwqcJD9VpV/CIMl5LYvtRM4ejCw0RwahTk2nyB7oK27PD/h5wx4/aapnZ/gToUfcvM8YwPQfmSXbUsZnxp46wx42j3+OFGkLaM+Soi3gIGs3YWP2kDEY80KdNhaHt7WTFPn/re3AMSaSsea5OKGVAfSxmT+dXT2+M/0Sv0/7Q5zcoWRjpI3hMLOHxw13wrwBSLcXY31EmEMP1XBctdtmFzHMfWEIBR1ORNUR6SbacIdDqvCJU1o+Jjn5z5KSc3m9U0pieqpwTuuTnE5JGHNKqZTkxIg3uOc15J45Tua8nB8xoDwpI9yWk2p2Ex3hCGlJdtvcwliSpJEeQwFmvZoQ6hJqavm6UCdswpvXmcI6piypMnrSDug2m0Q+QTYbubQI7yvpzzAx/gXej6c/ZYmRX6cCXOsqtaAoF0b9URkjtBjfF+HC7ivKHNQoRTm9CBMmr8RnoWZoBb7I7eCrjlLC+s1+ArpWmI/MKbNzyt/OKs/MKnNrBQtX55Q5nIITcboRb9/FuK9gnJRFQcz0+ZLypxvK5xh+by8pSzjC70sKs3MG7ZzI8DgQoWZCxBsOhd2Us/QrjKVUp5SO4YqnYFE7gOvOL6npL1Ec8J9hiLysHYAzdBj8nS/XSZXPLRUKl21uW0nI5q3GAyZhMSs/yY9rfSysUIOapyMd4y8ldDWZvLkDdQhcJcdFkV3LMuydEE4sH8PIa1O0cW3nELSq5SqcglZF2wlvKtov+RZ9/iGcv5sr5ywYrd4wRIIbscqYGVF/7QrfYw1Y5qzW5d+TtB76bp3FS+n7VS5b22m+ibNy1RTvfpDkFWK2wJ/jWskBmtxgzQo7T1dNioqXLRaUaU3vVTkuZ9Mm7kvEBSBRDQ7l5WyoHh2HevC0mEKKQo8d0VNf1Z5Q4OmP+bNIVyntCnPZacmJ7vqY3VFzdfUIkx9gfRh1iC6Qqbmqoz6rD6KRahbXUV82sM0OlnmFnVdB33jy8MHvyfL3Dh7Rbhijwyen9+zu3yLLW/p37/n33HC678GengeP0anP0+nxdMboJGzq6frg+PEPunoyn8vXm5tGd+zfv2O0qTk3+qYxFU+qMRVPrL+8F+16kqviXFw9WtaDOSuadIP8UaRfaihdfCTqt0ALfsh+0cVHS/zYagpmf8TFy6IZ8MMsfOuQ9j9/fmvDuvu2vBAX/iv+avqt0KBVPvXer/ZMNU3tvdtdUfPpyxZreKsHnhkKVUuPvPTuru2Pff7hGYdju9bZtjvmEUq2So9e/ZudL/S+EF/2xF/l72t9fGD61fsqOqZqK9x3751q+t3L3q1hq+VgfOi+XYnJ9RtGm9c9/s9Hv/kQ/IL3xHa36XEwY6pB/qlCBsKqnB8CwIg6KtSlMjwMC2oimRQmUpQ+GAwnJKdWmcSf/Did4ETME4qqkNkfCoeiSPU2bz0KdKN4sy6fP42CEpjNlfylZPoNjKHxlLXKQWpgmiQuX8crkhM12a1Wp8Tl8mgCY0qi+hWMhG3ubKnxI+iolIAmlLDI6sp1R5U1BRrCbtKrjNUi8ZdY45exewLtxoyqBndeyWLZYENJvE+XgxInU/wlvi0jiPIglb4m1GXsnkFc5EOZ23iTF/UAbgRbNdZFu9gI+Q49w7YFEaQg3BQE1ALXpmOsy0ceaqIu38Tsp7UqQ7aTMfqQS2whPU2wA6Ytire6wNmGr8eTSabmHFOSyPe5DuQ84UBV0JRETdCU53wX831+nWJdctE6JSB9+6kVL1aNfoYMW7Ti8D7q9ZOslzAV1MNmrv22KiJteJDj11yz1dUgFSmC2H9hd5Jbb1oHJ3Y7jUX7nQ6Cx7bEkjms05cTZNqpXAxmYsopBdtaRsf+fmy0pU0dmDk1M4A90PtOSatkkYExHLyf7tFD9weDsZmBgZlYUE82Ux4GN0ZC619CUcJqoOSFLJpVkFDpo6ILTQzSqoBYeVSTcCYDzKgpw8j5ViM/C/CU0ZbEn6DANpIIrmmXt8BTcGxLYaenbYd1w9pPYGjY6C1HhEaUaceYv0lqSRnY3GV8vljhQe2Q9nWhbjkFR+FQoegr2vdBTf8QTfwhjBhr+aHpDuy1Bc5M/Uw11tLMLyvu/Hj6Dfa5pKbwd01zMkfhnENox63zJ9MCFX/J8JtVE+g0JRAdRv6M/P/yRzB6pLXmT4C1TmtOIJ+O0uBxPcc9qzGJT8RVxm/9gCiLAvqgXBJNFeWLZWXFnfKGWFGp/Vws50VxXpTElXuBrttiFtlht4KIfQvFXDSy5n67AeEtlpeXiAR1zZ6KzZulknlR5MtEGGQWcHncSH2ojPWV+B8jrh77Xa9RazLJAcQ07syujnpe5PzxdEzNlBbKiUSQUhrrwKMYpCk9wfVkh0XM/zNOKZGQsKEuyer1YjyFuU6ulypPjmWYXmeGfxpB0tOzl8/eQfKpxn0f0EEk1JQgVQldZ2acoxl1+XpSb/HT1xKJcv0i2ysm9ceYHUnGX0F6ELuJRPpIIgGT6spa1bZahEkh3CDzLQK2a3IfuLBt83pExLpK8Wrora1oHbp3W0fpAyXtXT5TowthFF1RBKGOVXZtvycWELxbAnanp7S5p8EpbStS35Tb2pGi66K4hUa3Yk/RAiK9uHSRAbdV8ZySq9Hk62oX95V2bLt3qLWitiew1tBMqRfrtknOhp7mUo/THthypxAYvGd7ZyW3okfwcqFVLIsicsEsYwcseav9YgsfDmGn7BKiRW14qC8q3f/c68Ptnd/6Wk+ivb2LPmaNi0VBf9714quzo+KdOzdUKH/Vr703fgf7NK5m9j6qaafwMFsDDiifcWfiQHRCqKNFwP6cVoDeBSP0aq/dJURwrzd59PDhoz/ZtMlqjZ9P9Dz6ne8/18lPTB49cvgbP20MWK1D2Yu/3VFT49z42uGD33hyP7hGnz3Yx3felZ4aq611uV7Hq8emtN98+dkD/dAZzduH0f6VoyqdzWWZJRO9JzmRfkPV91kY/0nKi10U9XpJS9LGDKnfqJUkq5RzcHdgjqI0bMjcNsGd35GyLERKUGfTvwwykaw+ghWayomg+dbZdEyoSxobvjriCGo66L3UftMEru96lI2bfsoYWuG8NsMuCk9fVa72nhl54qGpnt7enqmHFmkQegqvtoWy32nwxPCzxlroMltvIdXchzxTmA3Y70ZRWfxqz03KzraFsv0Ma1Zix9ufwidbVwAYOSO3H49lexr2fKgt9971Ipwjr1J9x/Y/HYNzVMvLEfM60zvCZaP+056c+Hgj10HMCMarYnozQkc12gR0YObSCzDImZBLctrvhmy47+Xdj+KP9uDIY8P8NJ5KRmaG098ZfmzE1PDK8vOv8ONfHb67sbm58e7hH2QG2gfdajf+CZfpCeE/RmbG0s/jDOE8zk8/jyf4MQmFdQXT2ED7KU7UhrvVzP5K+ESYY/9D4OS8BYAVK2InE5JZVtAOjA3GGgKBhtjgK5nBM1n2eQQWCu6wQYYvmD6Za8KqUqDRm1vt4toL3gvkoKioQXlZQQ3QdDOosdw/YfLw7VD028qOYkjV3P9bdB/9I/bdVsyw+vwqWE8lBMufBXz++hI/havPH8VLCBYuLVAmLUCZaKkqLa2yiNoS/G+8PhBqHOra7Kw9TztUyflrEy9Wli5/XFop8qZfu4Zqv9Ia3lUz1Hh8KNbbZfhL112CHSTtO8y43ZH9a8LAn37rRz96619vDYTf+e3kt/1rQaP74W3mB89qfmiG7PvJqAy+m3XzVy/EL1xQ3nlHuXAhXtQLycxd/OOyPnjb8EHDrX1QqH9xFQcUgFjdA4VIdBzHjTjoWGsk1K8IjGI+mY8Pje7cHp+YamvVUn8hSP4tvvmdvfvf3Rzf/tHRxx+eVm+KGVMWpx4zXbcXNSvxrurDVUCv7s5bI/8/NJ+AHnicY2BkYGAAYtULCZ7x/DZfGbhZNgBFGO6kr1mMoP8LsGxgPgDkcjAwgUQBRJELs3icY2BkYGA+8F+AgYFlAwMDmGRkQAUeAFbqA4V4nGNgYGBg2TCKcWEA5qUx7QAAAAAAAAAATADIARwBNAFkAZoBtAHIAeAB+gIaAi4CSAJiAoIClgKuAsYC2gMGA0ADVAOkA/4EGAREBHYElgS2BOAFEAV8BeQGCgY6BmAGhga6BvgHLAd+B8AICgg0CGQIfgiYCMwJHglaCboJ9gpOCpwLCgteC6QLygv6DCQMcAx+DOoNIg18DboOAA48DoAO1A8wAAB4nGNgZGBg8GDwZeBiAAEmIOYCs/+D+QwAGE0BtgAAAHicXY69TsMwFIVP+odoEAIhMZulC1L6M/YB2pkO2dPESVslceS4lSoxM/MUzDwFz8WJeyUqbOn6O+ceXxvAA34QoFsBhr52q4cbqgv3SXfCA/Kj8BAhnoVHVC/CY7xiIhziCW+cEAxu6YyRCfdwj1q4T/9deED+EB5y+qfwiP6X8BgxvoVDTILRPjV1u9HFsUysZ19ibdu9qdU8mnm91rW2idOZ2p5VeyoWzuUqt6ZSK1M7XZZGNdYcdOqinXPNcjrNxY9SU2GPFIZ/brGBRoEjSiSwV/4fxUxY73RaYY4Is6v+mv3aZxI4nhkzW5xZW5w4e0HXIafOmTGoSCt/t0uX3IZO43sHOin9CDt/q8ESU+78Xz7yr1e/MPVTYgAAAHicbVLnetswEBPS5Th2HDttk3TvrY50792mj0FTVK2vlKhSUsbbl7yTZDkpfwHgHY4EGSwFvAbB/9cOlnAMx3ECJ3EKPSyjjxUMMMQqRljDGBOs4zTO4Cw2sIktnMN5XMBFXMJlXMFVXMN13MBN3MJt3MFd3MN9PECIh3iEx3iCbTzFMzzHC7zEK7zGG7zFO7zHB3zEJ3zGF3zFN3zHD/zEDn4FAyGlqbIyjBOtW6KTTI1EFIUysVIr4j3PPegLrSw31JDLrTV7YWT2MuLjDi+6FVrF3LHR4YWzswXrmwu6V5xLNdWNZWdjjRWb/J4teLLgakTtuXVIn5tOju6sd6UqJ23IWs1GLeOOoXRBZJGwlMqcUVxypuSfuszDqdnnhKQ2hepG3GfFw5VIaVUq8mswWfhAtRH8FMsqSvglGHltovZLZTOhPeO5PXXA3QMPTBxzoetTYevnXQ5JNIIkGkGIDkEoj2K+bsvoSZIsNjYVZWIy2l4QyFEblwc5EiItFYlmjRBFkKqsCrdr1WOPxrmo5qkdVcgt1+KA+wjR1XObZC4Y/ugNodv8rVTRHnfOqMuq2Kpixl0NoRmF2K1zIUQnLpSwkosbTBOKalpaIcuG8Sj2cWfnQzGiDHeNrlJ+CM6wK3Qr0qr+IwuCr1itBfdH/X6H+t0g+Adeo35PAAAA`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/css/all.min.css](https://histologe.beta.gouv.fr/css/all.min.css)
  
  
  * Method: `GET`
  
  
  * Evidence: `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`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/connect.php](https://histologe.beta.gouv.fr/connect.php)
  
  
  * Method: `GET`
  
  
  * Evidence: `sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN`
  
  
  
  
Instances: 5
  
### Solution
<p>Manually confirm that the Base64 data does not leak sensitive information, and that the data cannot be aggregated/used to exploit other vulnerabilities.</p>
  
### Other information
<p>\x0000\x0010�\x0010Q� ��0ӏA\x0014�QU�a��qן�\x0018��Y�����ۯ�\x001c��]�㞻�߿</p>
  
### Reference
* http://projects.webappsec.org/w/page/13246936/Information%20Leakage

  
#### CWE Id : 200
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Information Disclosure - Suspicious Comments
##### Informational (Low)
  
  
  
  
#### Description
<p>The response appears to contain suspicious comments which may help an attacker. Note: Matches made within script blocks or files are against the entire content not only comments.</p>
  
  
  
* URL: [http://histologe.beta.gouv.fr/dev/js/all.min.js](http://histologe.beta.gouv.fr/dev/js/all.min.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `SELECT`
  
  
  
  
* URL: [http://histologe.beta.gouv.fr/dev/js/dsfr.nomodule.min.js](http://histologe.beta.gouv.fr/dev/js/dsfr.nomodule.min.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `select`
  
  
  
  
* URL: [http://histologe.beta.gouv.fr/dev/js/dsfr.module.min.js](http://histologe.beta.gouv.fr/dev/js/dsfr.module.min.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `select`
  
  
  
  
Instances: 3
  
### Solution
<p>Remove all comments that return information that may help an attacker and fix any underlying problems they refer to.</p>
  
### Other information
<p>The following pattern was used: \bSELECT\b and was detected in the element starting with: "!function(t){var e={};function n(i){if(e[i])return e[i].exports;var r=e[i]={i:i,l:!1,exports:{}};return t[i].call(r.exports,r,r.", see evidence field for the suspicious comment/snippet.</p>
  
### Reference
* 

  
#### CWE Id : 200
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Information Disclosure - Suspicious Comments
##### Informational (Low)
  
  
  
  
#### Description
<p>The response appears to contain suspicious comments which may help an attacker. Note: Matches made within script blocks or files are against the entire content not only comments.</p>
  
  
  
* URL: [https://histologe.beta.gouv.fr/include/plotly-latest.min.js](https://histologe.beta.gouv.fr/include/plotly-latest.min.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `user`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/js/dsfr.module.min.js](https://histologe.beta.gouv.fr/js/dsfr.module.min.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `select`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/js/dsfr.nomodule.min.js](https://histologe.beta.gouv.fr/js/dsfr.nomodule.min.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `select`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/include/plotly-latest.min.js](https://histologe.beta.gouv.fr/include/plotly-latest.min.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `TODO`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/include/plotly-latest.min.js](https://histologe.beta.gouv.fr/include/plotly-latest.min.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `from`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/include/plotly-latest.min.js](https://histologe.beta.gouv.fr/include/plotly-latest.min.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `select`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/js/all.min.js](https://histologe.beta.gouv.fr/js/all.min.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `SELECT`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/include/plotly-latest.min.js](https://histologe.beta.gouv.fr/include/plotly-latest.min.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `query`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/include/plotly-latest.min.js](https://histologe.beta.gouv.fr/include/plotly-latest.min.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `bug`
  
  
  
  
Instances: 9
  
### Solution
<p>Remove all comments that return information that may help an attacker and fix any underlying problems they refer to.</p>
  
### Other information
<p>The following pattern was used: \bUSER\b and was detected in the element starting with: "!function(t){if("object"==typeof exports&&"undefined"!=typeof module)module.exports=t();else if("function"==typeof define&&defin", see evidence field for the suspicious comment/snippet.</p>
  
### Reference
* 

  
#### CWE Id : 200
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Modern Web Application
##### Informational (Medium)
  
  
  
  
#### Description
<p>The application appears to be a modern web application. If you need to explore it automatically then the Ajax Spider may well be more effective than the standard one.</p>
  
  
  
* URL: [https://histologe.beta.gouv.fr/](https://histologe.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a class="rf-logo" href="#" title="République française">
                            <span class="rf-logo__title">République
                           <br>
                            française</span>
                       </a>`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Qui](https://histologe.beta.gouv.fr/Qui)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a class="rf-logo" href="#" title="République française">
                             <span class="rf-logo__title">République
                            <br>
                             française</span>
                        </a>`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Chiffres](https://histologe.beta.gouv.fr/Chiffres)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a class="rf-logo" href="#" title="République française">
                             <span class="rf-logo__title">République
                            <br>
                             française</span>
                        </a>`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Contact](https://histologe.beta.gouv.fr/Contact)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a class="rf-logo" href="#" title="République française">
                             <span class="rf-logo__title">République
                            <br>
                             française</span>
                        </a>`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Plan-du-site](https://histologe.beta.gouv.fr/Plan-du-site)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a class="rf-logo" href="#" title="République française">
                             <span class="rf-logo__title">République
                            <br>
                             française</span>
                        </a>`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/_sign.php](https://histologe.beta.gouv.fr/_sign.php)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a id="h">
   
      
        <!-- entete -->
        <header class="rf-header">
            <div class="rf-container">
                <div class="rf-header__body">
                    <div class="rf-header__brand">
                        `
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/signale](https://histologe.beta.gouv.fr/signale)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a id="h">
   
      
        <!-- entete -->
        <header class="rf-header">
            <div class="rf-container">
                <div class="rf-header__body">
                    <div class="rf-header__brand">
                        `
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Home](https://histologe.beta.gouv.fr/Home)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a class="rf-logo" href="#" title="République française">
                            <span class="rf-logo__title">République
                           <br>
                            française</span>
                       </a>`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr](https://histologe.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a class="rf-logo" href="#" title="République française">
                            <span class="rf-logo__title">République
                           <br>
                            française</span>
                       </a>`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Aide](https://histologe.beta.gouv.fr/Aide)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a class="rf-logo" href="#" title="République française">
                             <span class="rf-logo__title">République
                            <br>
                             française</span>
                        </a>`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/connect.php](https://histologe.beta.gouv.fr/connect.php)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a class="rf-logo" href="#" title="République française">
                             <span class="rf-logo__title">République
                            <br>
                             française</span>
                        </a>`
  
  
  
  
Instances: 11
  
### Solution
<p>This is an informational alert and so no changes are required.</p>
  
### Other information
<p>Links have been found that do not have traditional href attributes, which is an indication that this is a modern web application.</p>
  
### Reference
* 

  
#### Source ID : 3

  
  
  
  
### Storable and Cacheable Content
##### Informational (Medium)
  
  
  
  
#### Description
<p>The response contents are storable by caching components such as proxy servers, and may be retrieved directly from the cache, rather than from the origin server by the caching servers, in response to similar requests from other users.  If the response data is sensitive, personal or user-specific, this may result in sensitive information being leaked. In some cases, this may even result in a user gaining complete control of the session of another user, depending on the configuration of the caching components in use in their environment. This is primarily an issue where "shared" caching servers such as "proxy" caches are configured on the local network. This configuration is typically found in corporate or educational environments, for instance.</p>
  
  
  
* URL: [https://histologe.beta.gouv.fr/dev_qg](https://histologe.beta.gouv.fr/dev_qg)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/_adm](https://histologe.beta.gouv.fr/_adm)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/robots.txt](https://histologe.beta.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Contact](https://histologe.beta.gouv.fr/Contact)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/](https://histologe.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Qui](https://histologe.beta.gouv.fr/Qui)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Aide](https://histologe.beta.gouv.fr/Aide)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr](https://histologe.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/sitemap.xml](https://histologe.beta.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Home](https://histologe.beta.gouv.fr/Home)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/dev](https://histologe.beta.gouv.fr/dev)
  
  
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
  
  
  
* URL: [http://histologe.beta.gouv.fr/dev/css/dsfr.min.css](http://histologe.beta.gouv.fr/dev/css/dsfr.min.css)
  
  
  * Method: `GET`
  
  
  * Evidence: `23000091`
  
  
  
  
* URL: [http://histologe.beta.gouv.fr/dev/Contact](http://histologe.beta.gouv.fr/dev/Contact)
  
  
  * Method: `GET`
  
  
  * Evidence: `0623043373`
  
  
  
  
* URL: [http://histologe.beta.gouv.fr/dev/css/all.min.css](http://histologe.beta.gouv.fr/dev/css/all.min.css)
  
  
  * Method: `GET`
  
  
  * Evidence: `23000091`
  
  
  
  
Instances: 3
  
### Solution
<p>Manually confirm that the timestamp data is not sensitive, and that the data cannot be aggregated to disclose exploitable patterns.</p>
  
### Other information
<p>23000091, which evaluates to: 1970-09-24 04:54:51</p>
  
### Reference
* http://projects.webappsec.org/w/page/13246936/Information%20Leakage

  
#### CWE Id : 200
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Timestamp Disclosure - Unix
##### Informational (Low)
  
  
  
  
#### Description
<p>A timestamp was disclosed by the application/web server - Unix</p>
  
  
  
* URL: [https://histologe.beta.gouv.fr/css/dsfr.min.css](https://histologe.beta.gouv.fr/css/dsfr.min.css)
  
  
  * Method: `GET`
  
  
  * Evidence: `23000091`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/Contact](https://histologe.beta.gouv.fr/Contact)
  
  
  * Method: `GET`
  
  
  * Evidence: `0623043373`
  
  
  
  
* URL: [https://histologe.beta.gouv.fr/css/all.min.css](https://histologe.beta.gouv.fr/css/all.min.css)
  
  
  * Method: `GET`
  
  
  * Evidence: `23000091`
  
  
  
  
Instances: 3
  
### Solution
<p>Manually confirm that the timestamp data is not sensitive, and that the data cannot be aggregated to disclose exploitable patterns.</p>
  
### Other information
<p>23000091, which evaluates to: 1970-09-24 04:54:51</p>
  
### Reference
* http://projects.webappsec.org/w/page/13246936/Information%20Leakage

  
#### CWE Id : 200
  
#### WASC Id : 13
  
#### Source ID : 3
