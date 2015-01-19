HP Openstack

Openstack - never break trunk

180 guests per proposed change

10k patches every 40 days

800 machines in test datacenter suite

99.95% updatime in github - 15 failures/week

(insert openstack spaghetti diagram here)

Human interventio doesnt scale - known error conditions per human brain maxes out

Elastic Recheck ( ES, Logstash )

time scale vs instance of error - more recent errors vs historical ones

40 MB log file can crash firefox

Pipe some error output to IRC

expected - 6-10 major bugs > 1% human
actual: 80-90 bugs

Classification of bug types: 
 - upstream (github cache failure) - mitigated by local cache
 - infrastructure ( services, nodes) 
 - OS bugs - deadlocks
 - bugs in tests - global state, variables
 - dependency bugs - shared, upstream libraries

e.g. timestamp checks - floating point rollover - 59.99 != 60 -> fail. The threshold rollover will be hit, and fail, a percentage of the time

detect bugs known via ES Query -> <error number>.yml 

GH: openstack-infra/elastic recheck

log collection + ES + configuration filter => simple, but useful mechanism
