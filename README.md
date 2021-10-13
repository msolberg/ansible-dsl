# ansible-dsl

The implementation has an app.yml file at the top level which describes an application deployment. The deployment is realized through the running of the site.yml playbook at the top level.

Four roles are defined:

The “X86Platform” role deploys a virtual instance on OpenStack and adds it to the dynamic inventory of the playbook run. The parameters of the instance deployment can be overridden in the PCDB configuration file. The deployment parameters could also be abstracted away in the logic of the playbook as an enhancement.

The “RHELPlatform” role configures the operating system of the deployed instance. It configures the system to be managed by Satellite, runs Puppet configuration management on the node, and sets any given kernel parameters.

The “Application” role installs the given application at a given version, along with its dependencies. It also optionally creates and mounts a filesystem on the system which is running the application.

The “ExtPlatform” role is a placeholder in this example.
