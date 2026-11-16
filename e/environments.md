# Software environments

A `software environment` is a combination of infrastructure, software, configuration and data in which a software application runs. 

The basic idea behind software environments is that software should be developed and tested somewhere other than the live system that real users depend on. In other words, there should be: 
- a live `production` environment, where the software performs its actual business function
- one or more `non-production` environments, where changes can be developed and validated without affecting the live service.

In a cloud platform like AWS, production and non-production environments might be deployed into separate AWS accounts, or into logically isolated resources within the same account.

Note that environments are not the same thing as software versions or branches – you can have several versions of software, and any one of them could potentially be deployed into different environments.

The three most common non-production environments are:
- `development` (dev)	– this is where developers write, run and experiment with software
- `testing` (test)	– this is where software is checked for defects and correct behaviour
- `staging`	– this is where a new version is tested in conditions closely resembling the live system, typically using synthetic or anonymised data.

Other terms for software environments are:
- `local` – a development environment deployed on the developers own computer (rather than in the cloud)
- `sandbox` – an isolated development environment for experimentation
- `integration` – an environment for checking that different components work together
- `pre-production` – usually synonymous with ‘staging’.

----

Back up to: [Maglocvnus](../index.md)
