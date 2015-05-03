## Module Development

odecee#

 - class module - opensource code, no business logic

 - Style Guide v2.0 (2015)
  - doesn't cover module stricture
  - separate documentation : fundamentals, beginners guide

 - There is a generate module function

 - puppet 3 - parameter lookup
  - explicit? hiera? class defined? else fail
  - in puppet 2, explicitly reference hiera to implement

 - puppet - stdlib. Type checking!

 - pitfall #1 - lookup hiera directly
  - hiera not a mandatory component of all installations
  - header defs moved in set, bad
  - heira is a custom structure, yours won't match others

 - pitfall #2 - module scope
  - should do one thing
  - should be the only module to do that one thing
 
 - pitfall #3 - dependencies
  - apart from stdlib, ideally it should not have any others

 - Puppetlabs github repo
 
 - manifests: 
  - init.pp - default class
  - params.pp - default values (ugly, case statements ahoy!)

 - anchor required for <3.4 dependency mapping and ordering

 - templates .erb, specs in rspec

 - unit test your puppet stuff

 - puppet > 2.6.2 recommended


 
