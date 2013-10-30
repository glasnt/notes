# OSDC 2013

Langham Hotel, Auckland, October 21 - 23 2013

### Openshift 

Steven Ellis, Red Hat

 * Tech: mongo db, activeMQ, Mcollective, SELinux (disabled for demo), apache, PAM, cgroup
 * Levels: Origin (free), online, Enterprise(?)
 * CLI client uses local REST to command, as does WEB
 * cartridges, gears, brokers and nodes run things
 * Environment variables created to reference databases, etc, for portability
 * Git push forces redeploy, but entire processes not yet reboot proof
 * Community cartridges welcome
 * Can be used to run a web-version of Quake on demand
 * Does not implement linux containers, but something developers are looking into 
 * 2.0 ETA December

### Continuous Integration 

Stewart Smith, MySQL AB/Percona

CI Process
 * Does it build? Compiler errors != releasible codes
 * Runt est suit
 * fix things
 * be nice to QA/beta testers
 * Dont do team trees
 * Test matrix of product variations based on OS, Version in VMs. Jenkins can be scheduled to run up VM/EC2/Cloud/etc instances for testing
 * use code review for all changes. (less helpful for smaller teams)  
 * code review - build script gives change -1 if it fails to run
 * Have a releasable trunk/master at any time
 * have a gated trunk: things can't be committed unless a robot and a human confirm it

### Rails and Distributable Packages 

Tim Serong, openSUSE (talk re: "HAWK")
 
 * bunlder gemlock slow, ties devs  down to versions
 * running bundler on production against rubygems.org versions can be bad, see "rubynation" gem (do not install this, it is bad)
 * security updates on different dependancies outdate gemfile.lock

Case study: packaged version of rails app for internal systems monitoring. Requires all rails sec updates, but don't want to re-package each time
Proposed solution: 
 * don't include any gemfile/.lock in deployment
 * use RPM file (for packaging), config/boot.rb
 * gemfile doesn't reference rubygems, if required
 * gemfile only includes gems required in test in the test conditional, not in production
 * config/boot.rb specifically does not run source rubygems in produciton -> dependent security updates work
Results in an application (for smaller numbers of gems) that doesn't require redeployment for minor updates. Major updates will require rework. 

### Serialization formats aren't toys 
Tom Eastman, Catalyst IT

 * YAML will execute anything it gets by default, see rails CVE issues from 2012/2013
 * XML is just as bad for executing
 * Json not so much
 * Multiple examples of vunerabilities in talk, including recursive calls attach, XML Bomb, `rm -rf /sys` in code..
 * Beware of unknown flexibility in parers, disable everythig by default, 
 * K.I.S.S, Keep it stupid, stupid

### SELinux 
Steve Ellis, RedHat

 * Settings for SELinux: "Permissive" or "Enforcing"
 * Originally designed by the NSA, cc 2000
 * Security at a level outside of chmod
 * Not a lot of customization required, most default tech has a set of boundaries that it assumes, just stick to those
 * don't put files in silly places and things should just work
 * without security, bad things happen, e.g. a compromised dev server w/production snapshot data is as bad as production getting hacked
 * Develop with SELinux turned onto Enforcing to learn the constraints
 * If issues arise, use: restorecon, `yum install audit`, SETroubleshoot, etc

### Mega Keynote 

Vikram Kumar, Mega LTD

TODO

### Keep SSL Secure 
Dennis Sosnoski. [[http://sosnoski.co.nz/presents/secrets.html#/|Slides]]

 * Commercial certificates aren't secure
 * Certs wrap a public key
 * Root CA vouches for all the things, embedded into software
 * DNS poisioning bad, Secure DNS being rolled out to systems
 * Man in the middle attacks - "legal" hacking by NSA, e.g. creating backdoors in routers. Can appear secure via stolen certs
 * You can be your own CA, but need to then ensure certificate revocation processes in place, etc
 * Initial client/server hello is in plaintext
 * browsers may not allow locking down to TLS1.2 (newest version)
 * NSA is bad, mkay. Current best guesses: 
  * Newest datacentre may have more than 1 million TB storage (exobytes)
  * they may/can break crytos RC4 and RSA1024 -> use RSA2048 at a minimum
  * eliptic curves may be a stacked deck - using default parameters that are known and easier to break
  * may have Google/Apple/Microsoft private keys
  * May be storing encrypted traffic to decrypt later
  * may have backdoor to Microsoft Security Essentials
 * Protecting yourself: 
  * disable java (applets)
  * use open source where possible (know your enemy)
  * update all security fixes
  * use GPK, etc
 * In chrome: check connection state (padlock -> connection). Check terms: e.g.: TLS ESA AES128 CBC SHA256. 
 * Server side: 
  * avoid storing unrequired data. If you store it, it can be stolen
  * never keep default passwords for routers, etc
  * check what AES/SHA/TLS versions are being used and confirm you aren't using "outdated" ones.
  * note about above: AES256 may not be more secure, or even as secure as AES128
 * Personal side: 
  * demand cert stats
  * be wary of public wifi

### Whiley - code testing in intellisense 
David Pearce 
 * whiley.org
 * language for teaching pre&post conditionals
 * resolves down to java and c
 * looking for contributors
 * demo uses eclipse plugin to show code testing based on parameters, even before code run
 * uses flow typing, has evolved a lot over time
 * performance is logrhymthicly worse than java, but is improving
 * similar to eiffel
 * designed specifically not to have testing as an addon
 * created by Victorian University
 * not IEEE floating point compliant
 * has some nice things java doesn't, e.g. union types (specifically not allow nulls)

### Persona 
Francois Marier, Mozilla
 * "connect on your terms"
 * Current solutions to site authentication
  * Self rolled - not always reliable
  * OpenID - higher technical acceptable level, username is URL, which is confusing 
  * Email based authentication - relies on email not being compromised. once email is hacked, all accounts can be reset
 * Persona uses a higher level of authentication, and only falls back to email based authentication and confirmation emails if domain doesn't setup completely
 * limited time certs and local client site js shims for passing credentials
 * current does use persona domain for intermediary on some authentication pathways, but system is overprovisioned for load, and moving towards complete decentralization
 * not going away in a hurry - all of mozilla uses it, so they are going to upkeep their own kit
 * simple integration into sites, requires javascript, returned assertions usable by applications to authenticate users. 
 * failed authentication does not return an email, so can't be accidently logged in, also webapp doesn't know about who failed to authenticate
 * SecureDNS for persona.org pending
 * clock skew not an issue even with shortlive keys

### Gentle art of Refactoring 
Paul Wayper

 * Refactor for performance, maintainability, revuew, new leasures
 * refactoring.com a good resource, Martin Fowler
 * example bad things: reverse conditionals, repetativeness
 * aegis - pre-git source control. requirement to provide a failing testcase that a commit solves for each commit 
 * case study: git://paulway/cfile

### Lightning Talks 
 * S. Cargo - blender game as a snail
 * Pinpoint - diffable presenation software - live.gnome.org/pinpoint
 * 

### Keynote - Paul Fenwick 
 * the 60's were weird and didn't care much for child safety. 

### Lunch bot and curry ordering 

Hugh Davenport

 * https://github.com/heytrav/vindaloo
 * https://github.com/hughdavenport/lunchbot

