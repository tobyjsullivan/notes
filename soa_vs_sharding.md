# Service Oriented Architectures vs Database Sharding

I've recently begun to wonder if scaling systems face a fundamental choice between implementing a service oriented architecture or sharding the database.
This is still an immature idea and deserves much scruitiny.
The idea is that the relevant limit for an application is how much data can be stored within a single database.
If the current upper limit for a database is 30 TB (as it is for Google Cloud SQL), then a team will have to decide how to change the system as the database size reaches that limit.
There are many potential options but two popular choices.
The first is moving to a service oriented architecture where the data is moved to dedicated independent services each with their own database able to scale more significantly.
The second popular option is to shard the database - find the largest tables and split the rows amongst multiple database instances.

It's worth noting at this point that I think there are concrete scenarios where sharding is unavoidable - namely when you have a single table with too many rows, even slimmed down, to fit in one database.
It happens, but this is a very large scale.
This stage usually arrives long after (years after) the choice being discussed here originally arises.

When data is simply large but distributed, what is the better option?
Moving to an SOA is a complex, company level process.
Database sharding is effectively just an ops problem, and one that can be handled mostly by off the shelf tools such as Vitess.
This perspective would suggest a favour toward sharding.
However, I propose the following table as a counter argument:

|          | Scale Datastore | Scale Company |
| -------- | --------------- | ------------- |
| SOA      |     TRUE        |       TRUE    |
| Sharding |     TRUE        |      FALSE    |

Service oriented architectures, and the usual practice of organizing people and teams around those services, offers a massive ability to scale the product side of a company in addition to data.
Database sharding, on the other hand, can have quite the opposite effect - leading to sticky quagmires of complexity in data which result in slowing down product development.

Just a thought for today. Needs more work.
