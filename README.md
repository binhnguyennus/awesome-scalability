# Awesome Scalability, Availability, and Stability Backend [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

A curated list of selected readings/case studies to illustrate [Scalability](https://news.ycombinator.com/item?id=4339174), [Availability](https://www.digitalocean.com/community/tutorials/what-is-high-availability), and [Stability](http://blog.dialpad.com/blog/2015/12/4/engineering-values-infrastructure-stability) patterns in backend design.

#### What if your backend went slow?
> Understand your problems: performance problem (slow for a single user) or scalability problem (fast for a single user but slow under heavy load) from [basic](#basic).

#### What if your backend went down?
> "Even if you lose all one day, you can build all over again if you retain your calm!" - Thuan Pham, CTO at Uber Technologies Inc.

## Contributing

Please take a look at the [contribution guidelines](CONTRIBUTING.md) first.
Contributions are always welcome!

## Contents
- [Basic](#basic)
- [Scalability](#scalability)
- [Availability](#availability)
- [Stability](#stability)

## Basic
* [CAP Theorem and the Trade-offs](http://robertgreiner.com/2014/08/cap-theorem-revisited/)	
* [Scale up vs Scale out](https://blogs.technet.microsoft.com/admoore/2015/02/17/scaling-out-vs-scaling-up/)
* [Latency vs Throughput: Striving for maximal throughput with acceptable latency](https://blogs.dropbox.com/tech/2017/09/optimizing-web-servers-for-high-throughput-and-low-latency/)
* [ACID?](http://highscalability.com/drop-acid-and-think-about-data)
* [Architecture Issues: Bottlenecks, Database, CPU, IO](http://highscalability.com/blog/2014/5/12/4-architecture-issues-when-scaling-web-applications-bottlene.html)
* [Immutability](https://eng.uber.com/immutable-collections/)

## Scalability
* [Distributed Caching](https://www.wix.engineering/single-post/scaling-to-100m-to-cache-or-not-to-cache)
	* [Write-behind and Write-through](https://docs.oracle.com/cd/E15357_01/coh.360/e15723/cache_rtwtwbra.htm#COHDG5177)
	* [Eviction Policies](http://highscalability.com/blog/2016/1/25/design-of-a-modern-cache.html)
	* [Peer-To-Peer Caching](https://en.wikipedia.org/wiki/P2P_caching)
* [Storage](http://highscalability.com/blog/2011/11/1/finding-the-right-data-solution-for-your-application-in-the.html)
	* [In-memory Storage](https://medium.com/@denisanikin/what-an-in-memory-database-is-and-how-it-persists-data-efficiently-f43868cff4c1)
		* [Optimizing Memcached Efficiency at Quora](https://engineering.quora.com/Optimizing-Memcached-Efficiency)
	* [Durable Storage](https://code.facebook.com/posts/357056558062811/logdevice-a-distributed-data-store-for-logs/)
* [NoSQL](https://www.thoughtworks.com/insights/blog/nosql-databases-overview)
	* [Key-Value Databases (Voldemort, Dynomite)](http://highscalability.com/anti-rdbms-list-distributed-key-value-stores)
	* [Document Databases (Cassandra, Vertica, Sybase IQ)](https://msdn.microsoft.com/en-us/magazine/hh547103.aspx)
		* [Consistent Hashing in Cassandra](https://blog.imaginea.com/consistent-hashing-in-cassandra/)
		* [Storing Images in Cassandra at Walmart Scale](https://medium.com/walmartlabs/building-object-store-storing-images-in-cassandra-walmart-scale-a6b9c02af593)
		* [Cassandra at Instagram](https://www.slideshare.net/DataStax/cassandra-at-instagram-2016)
		* [How Yelp Scaled Ad Analytics with Cassandra](https://engineeringblog.yelp.com/2016/08/how-we-scaled-our-ad-analytics-with-cassandra.html)
	* [Graph Databases (MongoDB, CouchDB, Neo4j)](https://neo4j.com/blog/neo4j-scalability-infographic/)
	* [Datastructure Databases (Redis, Hazelcast)](http://highscalability.com/blog/2014/9/8/how-twitter-uses-redis-to-scale-105tb-ram-39mm-qps-10000-ins.html)
* [RDBMS](https://www.mysql.com/products/cluster/scalability.html)
	* [Sharding](https://medium.com/@Pinterest_Engineering/sharding-pinterest-how-we-scaled-our-mysql-fleet-3f341e96ca6f)
		* [Partitioning](https://medium.com/airbnb-engineering/how-we-partitioned-airbnb-s-main-database-in-two-weeks-55f7e006ff21)
		* [Replication](http://basho.com/posts/technical/replication-is-the-key-for-scalability-high-availability/)
	* [Denormalization](http://highscalability.com/blog/2012/1/23/facebook-timeline-brought-to-you-by-the-power-of-denormaliza.html)
	* [ORM + Rich Domain Model Antipattern](https://martinfowler.com/bliki/OrmHate.html)
* [HTTP Caching](https://developer.mozilla.org/en-US/docs/Web/HTTP/Caching)
	* [Reverse Proxy (Nginx, Varnish, Squid, rack-cache)](https://www.mertech.com/overview-reverse-proxying/)
	* [CDN (Akamai)](https://building.coursera.org/blog/2015/07/09/improving-coursera-global-site-performance-a-head-to-head-cdn-battle-with-production-traffic/)
* [Concurrency](https://lambda.grofers.com/open-sourcing-codon-workflow-framework-for-building-aggregator-apis-f8e591a158b4)
	* [Message-Passing Concurrency](https://link.springer.com/chapter/10.1007/978-3-642-35170-9_11)
	* [Software Transactional Memory](https://dl.acm.org/citation.cfm?id=3037750)
	* [Dataflow Concurrency](http://www.marketwired.com/press-release/java-concurrency-and-scalability-platform-akka-celebrates-fifth-anniversary-1928674.htm)
	* [Shared-State Concurrency](https://common-lisp.net/project/ssc/darcs/spec/specification.pdf)
* [Event-Driven Architecture](https://martinfowler.com/articles/201701-event-driven.html)
	* [Messaging](https://www.ibm.com/support/knowledgecenter/en/SSAW57_8.5.5/com.ibm.websphere.nd.doc/ae/cjt1004_.html)
		* [Publish-Subscribe](https://aws.amazon.com/pub-sub-messaging/)
		* [Point-to-Point](https://content.pivotal.io/blog/understanding-when-to-use-rabbitmq-or-apache-kafka)
		* [Store-Forward](https://medium.com/netflix-techblog/announcing-suro-backbone-of-netflixs-data-pipeline-5c660ca917b6)
		* [Request-Reply](http://edwardost.github.io/talend/camel/2015/05/15/Scalable-JMS-Request-Reply/)
	* [Actors: Fire-forget and Fire-Receive-Eventually](https://doc.akka.io/docs/akka/2.5.5/scala/actors.html)
	* [Enterprise Service Bus](http://www.oracle.com/technetwork/articles/soa/ind-soa-esb-1967705.html)
	* [Domain Events](https://www.oreilly.com/ideas/the-evolution-of-scalable-microservices)
	* [Event Stream Processing](https://dl.acm.org/citation.cfm?id=2933288)
	* [Event Sourcing](https://medium.com/lcom-techblog/scalable-microservices-with-event-sourcing-and-redis-6aa245574db0)
	* [Command & Query Responsibility Segregation (CQRS)](https://docs.microsoft.com/en-us/azure/architecture/patterns/cqrs)
* [Load-balancing](https://blog.vivekpanyam.com/scaling-a-web-service-load-balancing/)
	* [Round-robin Allocation](https://www.citrix.com/blogs/2010/09/03/load-balancing-round-robin/)
	* [Random Allocation](http://www.streetdirectory.com/travel_guide/192172/world_wide_web/load_balancing_and_yahoo.html)
	* [Weighted Allocation](https://medium.com/netflix-techblog/netflix-shares-cloud-load-balancing-and-failover-tool-eureka-c10647ef95e5)
	* [Dynamic Load-balancing](https://engineeringblog.yelp.com/2017/05/taking-zero-downtime-load-balancing-even-further.html)
		* [Work-stealing](https://groups.google.com/forum/#!searchin/mechanical-sympathy/http/mechanical-sympathy/CWyAD-oF9Uw/ycO0vxGqMvsJ)
	* [Consistent Hashing](https://medium.com/vimeo-engineering-blog/improving-load-balancing-with-a-new-consistent-hashing-algorithm-9f1bd75709ed)
	* [UDP Load-balancing](https://developers.500px.com/udp-load-balancing-with-keepalived-167382d7ad08)
* [Parallel Computing](https://blogs.msdn.microsoft.com/ddperf/2009/05/02/are-we-taking-advantage-of-parallelism/)
	* [SPMD (Single Program Multiple Data): The Genetic Pattern](https://www2.eecs.berkeley.edu/Pubs/TechRpts/2012/EECS-2012-186.html)
	* [Master/Worker Pattern](https://docs.gigaspaces.com/sbp/master-worker-pattern.html)
	* [Loop Parallelism Pattern: Extracting parallel tasks from loops](https://www.cs.umd.edu/class/fall2001/cmsc411/projects/unroll/main.htm)
	* [Fork/Join Pattern: Good for recursive data processing](http://highscalability.com/learn-how-exploit-multiple-cores-better-performance-and-scalability)
	* [MapReduce Pattern: Born for Big Data](http://static.googleusercontent.com/media/research.google.com/en/us/archive/mapreduce-osdi04.pdf)
	* [Parallelize the rendering of web pages: Use case of Yelp.com](https://engineeringblog.yelp.com/2017/07/generating-web-pages-in-parallel-with-pagelets.html)

## Availability
* [Fail-over](https://activemq.apache.org/artemis/docs/1.0.0/ha.html)
* [Replication](https://m.alphasights.com/a-primer-on-database-replication-381b319cd032)
	* [Master-Slave](https://engineering.bitnami.com/articles/enabling-additional-nodes-to-bitnami-mysql-with-replication.html)
	* [Tree Replication](https://link.springer.com/chapter/10.1007/3-540-44863-2_47)
	* [Master-Master](http://sabbour.me/highly-available-and-scalable-master-master-mysql-on-azure-virtual-machines/)
	* [Buddy Replication](https://developer.jboss.org/wiki/JBossCacheBuddyReplicationDesign)

## Stability
* [Circuit Breaker](https://doc.akka.io/docs/akka/current/common/circuitbreaker.html)
* [Always use timeouts (if possible)](https://www.javaworld.com/article/2824163/application-performance/stability-patterns-applied-in-a-restful-architecture.html)
* [Let it crash/Supervisors: Embrace failure as a natural state in the life-cycle of the application](http://erlang.org/doc/design_principles/sup_princ.html)
* [Crash early: An error now is better than a response tomorrow](http://odino.org/better-performance-the-case-for-timeouts/)
* [Bulkheads: Partition and tolerate failure in one part](https://skife.org/architecture/fault-tolerance/2009/12/31/bulkheads.html)
* [Steady state: Always put logs on separate disk](https://docs.microsoft.com/en-us/sql/relational-databases/policy-based-management/place-data-and-log-files-on-separate-drives)
* [Throttling: Maintain a steady pace](http://www.sosp.org/2001/papers/welsh.pdf)

## Special Thanks
* Jonas Bonér, CTO at Lightbend, for the [original reference](https://www.slideshare.net/jboner/scalability-availability-stability-patterns)
