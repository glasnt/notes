## Puppet at Fairfax

 - multimaster, 3rd local iteration
 

 - Setup
  - Domain.com = .NET shop
  - polygot language stack, all in puppet
  - using puppet since 0.25.X
  - admit to have made every possible mistake

 - Don't make changes directly on puppet master
  - use VCS

 - Do test - lint, puppetlint, validation, documentation
  
 - Don't pollute downloaded modules 
  - can't update to official versions
  - work out a monkeypatch or overload

 - Don't put sensitive data into modules
 
 - Stack
  - EC2 instances
  - ELB load balancer
  - SNS notifications
  - SQS queues
  - RDS database as a service

 - Lono DSL for CloudFormation
 - Packer
 - stock flowdock
 - 'Captain Hook'

 - Module preferences
  - PuppetLabs supported, then
  - Vendor supported, then
  - Puppet approved, then
  - Custom (git repo per module)

 - Feature branch workflow

 - Multimaster w/ELB on ASG in AWS
  - PuppetCA box (1..1)
  - PuppetMaster box (2.. N)
  - PuppetDB (1..N) -> RDS

 - Puppet Explorer (Angular)
  - PuppetDB walker

 - ASG -> autoroll out of updates to puppet with no downtime

 - High availability and fault tolerant
 
 - Challenges - sync, ephemeral nodes
 - Solution: 
  - git push to repo
  - push post webhook ("Captain Hook")
   - to SNS
   - to queues
   - to puppet masters

 - Captain Hook Refresh types
  - Full refresh - r10k dep env -p
  - Light refresh - r10k dep env
  - Module refreh - r10k dep module x
 - Push message to SNS
 - Check clients poll for message to execute, execute, send message back to Slack

 - Github.com/fairfaxmedia
  - captain hook not open sourced.. yet


 
