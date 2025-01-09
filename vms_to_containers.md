## The Great Divide: Understanding Virtual Machines and Containers in Modern Infrastructure

As businesses modernize and embrace cloud-native architectures, one of the biggest challenges they face is how to migrate from virtual machines (VMs) to containers. Initial excitement is met with frustration as teams encounter challenges, setbacks, as the true scope and complexity of the task become apparent. With that said, I want to address the three most common questions and concerns that I see arise.

### 1. I keep hearing that migrating to containers will save me money but what does this actually look like in practice?

The evolution from VMs to containers represents a significant change in how applications are managed and deployed. Unlike VMs, which require separate operating systems for each instance, containers share the underlying OS and kernel. This enables a single operating system to support multiple containers, which allow for more fine grained resource allocation compared to VMs. You can easily define resource limits (CPU, memory) for each container, and be confident that resources are efficiently distributed among applications. Containers also have a much smaller footprint than VMs, which means you can run a higher number of applications on the same hardware. This translates to better server utilization and reduced infrastructure costs.

### 2. How is a migration possible if my application wasn't built to run on containers?

The key to a successful migration is thorough planning. With that said, there are typically three options customers consider for the migration strategy.

#### 1. Lift and Shift

- Description: Move applications directly from VMs into containers without modifications.
- Advantages: Quick and simple.
- Drawbacks: Limited benefits as it doesn’t optimize for container-native performance.
 
### 2. Refactoring

- Description: Modify the application’s code and structure without altering its core functionality.
- Advantages: Enhances scalability and maintainability while leveraging container features.
- Drawbacks: Requires more meticulous effort and architecture knowledge compared to lift and shift.
 
### 3. Rearchitecting

- Description: Fully redesign the application to adopt a micro services architecture.
- Advantages: Maximizes the benefits of containers and the container-native ecosystem.
- Drawbacks: Time-intensive and requires substantial expertise in the current architecture along with it's dependencies.

### 3. How can we ensure there is no disruption for our customers and mitigate the impact to our new feature roadmap?

The key here is to start with a phased migration plan to minimizes disruption. Start by carefully considering where there is an intersection between services that offer a high return for the migration effort with ones that are also stable and less critical. One you have that identified you can then decide on your deployment strategy which will of course dictate your rollback plan to mitigate unforeseen issues. 

Finally, while it's beyond the scope of this post, it's vital to understand that there are also numerous ways to gradually plan a rollout versus opting for all at once. If you choose the latter which can be successful even for larger services, I've seen this work best with meticulous DNS cut overs and a first pass that cuts down each records TTL (time to live). This time to live is important because it specifies the duration (in seconds) that a DNS resolver (like your computer or internet service provider) should cache a specific DNS record before refreshing it.
