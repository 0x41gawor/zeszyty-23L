The next cornerstone* of Network Intelligence is 

<p style="color:green;">an important quality or feature on which a particular thing depends or is based. </p> 

# Data centers and automating cloud & network service provisioning
<img src="img/1.png" style="zoom:50%;" />

<img src="img/2.png" style="zoom:55%;" />

## Table of Contents

![](img/3.png)

## Chapter 1: Cloud Services & Models

NIST - National Institute of Standards and Technology

Całość jest tu[[1] Peter Mell , Timothy Grance , The NIST Definition of Cloud Computing , Special Publication 800 145, 2011.](https://nvlpubs.nist.gov/nistpubs/legacy/sp/nistspecialpublication800-145.pdf)

### 1.1 Cloud definition in short

"**Cloud computing** is a model for enabling ubiquitous, convenient, on
demand network access to a shared pool of configurable computing
resources (e.g., networks , servers, storage, applications, and services)
that can be rapidly provisioned and released with minimal management
effort or service provider interaction. This cloud model is composed of five
essential characteristics, three service models, and four deployment
models."

<p style="color:green;">ubiquitous - wszechobecny </p> 

Czyli co to jest ta chmura?

Jest Service Provider no i on ma chmurę, czyli computing resources. Za pomocą Sieci (najczęściej Internetu) daje on dostęp do tych zasobów. Dostęp ten ma być wszechobecny, wygodny i on demand. Czym są te zasoby?

- networks - kilka "komputerów" połącznych siecią
- servers - komputer, na którym można wdrożyć apke
- storage - można przechowywać dane
- applications - można korzystać z gotowej apki, zamiast wdrażać swoją
- services - stoi apka coś obliczająca i Twoja korzysta z niej jak z serwisu

Zasoby te są współdzielone między wielu klientów, a ich provisioning (przypisane, że w tej chwili ten klient ma takie zasoby) powinny dziać się jak najbliżej do automatycznie. 

***

Następne rozdziały omówią:

- five essential characteristics

-  three service models
- four deployment models

### 1.2 Five essential characteristics

#### 1.2.1 On demand self-service

> start/stop service at any time

start/stop the service at any time , through automated interface , as convinient for the user as possible

#### 1.2.2 Broad Network Access

> Dostępne z internetu

access over the network, using heterogeneous client platforms (e.g., mobile phones, tablets, laptops, and workstations)

#### 1.2.3 Resource pooling

> Service Provider grupuje zasoby dla userów dając im wrażenie, że mogą oni sobie ich wziąć nieskończoność

- pooling (combining/grouping ) of physical virtual resources for ease of management to suport multi tenancy and the sense of infinite resources
- with a sense of location independence , although higher levels of abstraction are possible (region, country, zone ,
- with necessary precautions risk management activities taken by the users because of privacy and security concerns of resource sharing in the cloud

#### 1.2.4 Rapid Elasticity

> Bierzesz ile Ci potrzeba, skalujesz w realtime ile trzeba

- get as much resources as just needed
- scale up or down cloud resources as required automatically and in real time (or near real time)

#### 1.2.5 Measured Service

> Zużycie jest mirzeone ile klient płaci tyle ile zużył

- resource usage is monitored, controlled, and reported in a transparen t way for both the provider and consumer of the utilized service
- to optimize the utilization of cloud resources and introduce the pay as you go service model

### 1.3 Three Service Models

#### 1.3.1 Software as a Service

**NIST definition**

"The capability provided to the consumer is to use the provider’s applications running on a *cloud infrastructure** . The applications are accessible from various client devices through either a thin client interface, such as a web browser (e.g., web-based email), or a program interface. The consumer does not manage or control the underlying cloud infrastructure including network, servers, operating systems, storage, or even individual application capabilities, with the possible exception of limited userspecific application configuration settings.

*A **cloud infrastructure** is the collection of hardware and software that enables the five essential characteristics of cloud computing."

![](img/4.png)

**Examples of SaaS offers**

Google Apps , Google Workspace, Dropbox, Cisco WebEx, GoToMeeting , MS Teams , WordPress Hosting

Zauważ, że cały Outlook/Teams w PLK jest w chmurze, przecież masz do niego dostęp z domu bez VPN, lokalnie nie jest nic trzymane w corp.plus.net to nie jest instancja Teams na naszym serwerze. To jest instancja Teams dla PLK na chmurze Azure.

**SaaS Advantages**

- reducing the time and money spent on tedious tasks such as installing, managing, and upgrading software
- IT is released from the day to day activities of running a data center, IT operations, and maintenance
- technical staff can be dedicated to more pressing matters and issues

**Saas Limitations**

- Interopretability - aplikacje dostajesz jaka jest i tyle. Więc mogą być problemy z zintegrowaniem jej z Twoimi innymi apkami. Tym bardziej if the SaaS app is not designed to follow open standards for integration. Dopiszesz sobie tylko i wyłącznie taki plug-in do Teamsów na ile Ci jego API pozwoli. A najchętniej to Ci sprzedadzą jakiś swój produkt do Twojego problemu, niż pozwolą plugin robić.

- Vendor Lock-In - the data may not be portable technically or cost effectively across SaaS apps from other vendors. Całą bazę kont z Teamsów ciężko przenieść na Google Meets nagle

- Lack of integration support - Often a deep integration with on premise apps, data, and services is required . The SaaS vendor may offer limited support in this regard

- Data Security - wiadomo, chmura publiczna to jest zawsze jakiś security threat

- Lack of Control - oddanie kontroli do 3-rd party wymusza to redefine data security and governance models. W Teamsach i tak nie trzymasz jakiś mega tajnych danych, więc jest git. Gorzej jakaś Twoja apka do retencji np.

- Customization - najmniejszy stopień customizacji. No weź w Teams coś skustomizuj xd

- Feature Limiations - dostajesz taką apke jaka jest. 

- Performance and Downtime - jesteś zależny od vendora pod tym względem. Cyberataki na jego cloud infra, network issues itp. mogą popsuć Twój biznes

**When to use SaaS**

- startups or small companies that need to launch ecommerce quickly , and do not want to deal with server issues or software
- short term projects that need quick, easy, and affordable collaboration tools
- app s that aren’t needed too often, such as tax software
- app s that need both web and mobile access

#### 1.3.2 Platform as a Service

**NIST definition**

"The capability provided to the consumer is to deploy onto the cloud infrastructure consumer-created or acquired applications created using programming languages, libraries, services, and tools supported by the provider. The consumer does not manage or control the underlying cloud infrastructure including network, servers, operating systems, or storage, but has control over the deployed applications and possibly configuration settings for the application-hosting environment."

![](img/5.png)

**Example of PaaS offers**

[GoogleApp Engine](https://cloud.google.com/appengine) app s in Python, Java, and its derivatives, Go and PHP run over a scalable, elastic infrastructure, [AWS Elastic Beanstalk](https://aws.amazon.com/elasticbeanstalk/) app s in Java, .NET, PHP, Node.js, Python, Ruby, Go, Docker on Apache, Nginx, Passenger, IIS, [Microsoft Azure](https://azure.microsoft.com/en-us) apps in .NET, Java, PHP, Node.js, Python , and Ruby , integrated with Media Services, Service Bus, Notification Hubs , Scheduler , Automation, Visual Studio Online, Active Directory, and many more, [Heroku](https://www.heroku.com) apps in Node.js , Ruby , Java , P HP , P ython , Go , Scala , Clojure , intergrated with Github , CI/CD, containers , Postgres , Redis , app metric monitoring tools, [OpenShift](https://www.redhat.com/en/technologies/cloud-computing/openshift) (Red Hat K8s enterprise platform)

**PaaS Advantages**

- simple, cost-effective deveopment and deployment of apps
- scalable, highly available
- developers can customize apps without needing to maintain the software environment
- easy migration to hybrid cloud model

**PaaS Limitations**

- Data security - same as in SaaS
- Integration - you control the app, but still not every component of legacy IT systems is build for the cloud
- Cusotmization of legacy systems - PaaS is not a plug-in-and-play solution for existing legacy apps. The resulting cusotmization can result in a complex IT system that may limit the value of the PaaS investement altogether
- Vendor lock-in - Switching to alternative PaaS option may not be possible without affecting the business
- Runtime issues -  PaaS solutions may not be optimized for the language and frameworks of your choice. Specific framework versions may not be available or perform optimally with the PaaS service.
- Operational limitation - Already customized (i.e., using IaaS or private cloud ) cloud operations with management automation workflows may not apply to PaaS solutions, as PaaS platforms tend to limit operational capabilities for end users. Legacy capabilities may not be supported by a given PaaS.

**When to use PaaS**

- creation of customized applications while avoiding all of the infra and platform maintenance issues
- to streamline workflows when multiple developers are working on the same development project
- if other SW vendors must be included, PaaS can provide great speed and flexibility to the entire process

#### 1.3.3 Infrastructure as a Service

**NIST definition**

"The capability provided to the consumer is to provision processing, storage, networks, and other fundamental computing resources where the consumer is able to deploy and run arbitrary software, which can include operating systems and applications. The consumer does not manage or control the underlying cloud infrastructure but has control over operating systems, storage, and deployed applications; and possibly limited control of select networking components (e.g., host firewalls)."

![](img/6.png)

**Examples**

[Amazon Web Services](https://aws.amazon.com), [Google Compute Engine](https://cloud.google.com/compute), [Microsoft Azure](https://azure.microsoft.com/en-us), [DigitalOcean](https://www.digitalocean.com), [Linode](https://www.linode.com), [Rackspace](https://www.rackspace.com) (co-founder of OpenStack), [Cisco Metacloud](https://www.cisco.com/c/en/us/solutions/cloud/index.html)

**IaaS advantages**

- most flexible model, the only one possible for LEGACY APPS
- easy to automate deployment of strorage, networking, servers and processing power
- hardware purchases can be based on consumption , utilization can be optimized
- clients retain complete control of their infrastructure
- cloud resources can be purchased as needed

**IaaS limitations**

- Security - same as SaaS and PaaS
- Multi-tenant Security - IaaS vendor is required to ensure that new customers cannot access data deposited to storage assets by previous customers. Customers must rely on the vendor to ensure that VMs are adequately isolated within the multitenant cloud architecture.
- Legacy systems operating in the cloud - każdy przypadek jest indywidualny. The cloud infrastructure may not deliver specific controls to secure the legacy apps. Enhancement to legacy apps required before migrating them to the cloud can lead to new issues .
- Internal resources and training -  Customers will be responsible for data security, backup, and business continuity. M onitoring and management of virtual resources may be difficult without adequate training of personel and resources available inhouse.

**When to use IaaS**

- startups and small companies to avoid expenses on purchasing and creating hardware and software
- larger companies to retain complete control over their applications and infrastructure, but to purchase only what they actually need
- companies experiencing rapid growth, to be able to replace specific hardware and software easily as their needs evolve
- when application’s demands are uncertain , IaaS offers plenty of flexibility and scalability

### 1.4 Four deployment models

#### 1.4.1 Public Cloud

**NIST definition**

The cloud infrastructure is provisioned for open use by the general public. It may be owned, managed, and operated by a business, academic, or government organization, or some combination of them. It exists on the premises of the cloud provider.

**Characteristic: public cloud service**

- is multi-tenant and the underlying resources are shared among multiple customers
- the public cloud provider owns and controls the security and protection of data between one customer and another customer

**Examples**

Gmail, Intuit, App Engine, Azure, Amazon Web Services, Rackspace, CenturyLink are all examples of public cloud providers.

Gmail np. to jest Public Cloud w modelu SaaS

Google App Engine to Public Cloud w modelu PaaS

#### 1.4.2 Private Cloud

**NIST definition**

"The cloud infrastructure is provisioned for exclusive use by a single organization comprising multiple consumers (e.g., business units). It may be owned, managed, and operated by the organization, a third party, or some combination of them, and it may exist on or off premises."

Czyli to jest taka chmura, którą np. my byśmy dawali jako PLK dla klientów 5G Campus.

**Characteristic: private cloud deployment**

- no sharing of resources outside of the corporate entity
- security and data protection is owned by the same business entity.

**Examples**

OpenStack (Rackspace , VMware , Red Hat , HP, IBM, EMC, and Oracle)
Cloud Suite (VMware)

#### 1.4.3 Community Cloud

**NIST definition**

"The cloud infrastructure is provisioned for exclusive use by a specific community of consumers from organizations that have shared concerns (e.g., mission, security requirements, policy, and compliance considerations). It may be owned, managed, and operated by one or more of the organizations in the community, a third party, or some combination of them, and it may exist on or off premises."

**Characteristic: Community cloud deployment**

- is effective for consortium groups and special interest user groups
- security and data access between members of a consortium or user group is permitted

- outside of the consortium or user group, access is restricted

**Examples of such deployments**

Facebook, LinkedIn, Twitter

#### 1.4.4 Hybrid Cloud

**NIST definition**

"The cloud infrastructure is a composition of two or more distinct cloud infrastructures (private, community, or public) that remain unique entities, but are bound together by standardized or proprietary technology that enables data and application portability (e.g., cloud bursting for load balancing between clouds). "

**Characteristic terms**

- **cloud bursting**, which means going from private cloud to public cloud
- backup and disaster recovery, also going from private cloud to public cloud

**Example of hybrid cloud offers**

[AWS VPC](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html), [Intervision/Bluelock](https://intervision.com/cloud-services/)

### 1.5 Summary

![](img/7.png)

Other "as a Service" offerings

- [AI as a service](https://www.bmc.com/blogs/ai-as-a-service-aiaas/)
  - [Google Vertex AI](https://cloud.google.com/vertex-ai)
- [DBaaS](https://www.bmc.com/blogs/dbaas-database-as-a-service/)
- [BPMaaS](https://www.bmc.com/blogs/bpmaas-business-product-management-as-a-service/)
- [FaaS](https://www.bmc.com/blogs/faas-function-as-a-service/)
- [TaaS](https://www.bmc.com/blogs/taas-testing-as-a-service/)