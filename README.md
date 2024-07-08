# emptyhammock-role-maintenance

This is an Ansible role that, in conjunction with a number of other Emptyhammock
roles, handles provisioning and deployment of Django applications.

It is oriented closely to Emptyhammock projects, but you may find some useful
snippets here.

This particular role installs a "maintenance configuration file" in
`/etc/emptyhammock-maintenance.yml`.  The maintenance bot, a separate set of
code, has only a list of servers to maintain, and it fetches that maintenance
configuration file from each server in order to know what tasks to perform, and
on what schedule.

The default maintenance configuration file template can be overridden
completely by a project that needs to be maintained, but more commonly the
project sets Ansible variables to control details of the configuration.

This setup allows most of system maintenance to be configured along with the
software running on that system (i.e., maintained by the same team in the
same repo), instead of having to share those details (e.g., where is the
media directory?) with the separate maintenance procedures.

Currently-supported maintenance tasks include

* Apply system maintenance (OS fixes)
* Reboot the system, if required by system maintenance
* Analyze versions of Python packages in a virtualenv. optionally running pip-audit
* Report when/if a backlog of system maintenance needs to be applied
* Backup databases
* Backup directory trees
* Renew "Let's Encrypt" certificates

These tasks are performed according to a schedule in the maintenance
configuration file.
