Role Name
=========

A role for configuring Netflow replication on a host.

Requirements
------------

Ansible 2.9.16.

Role Variables
--------------

`netflow_replicator_rolebase_dir`

Base directory for this role files on a host.

`netflow_replicator_config_dir`

Directory for configuration files for instances.

`netflow_replicator_instances`

A list of replicator instances with their configuration.

Dependencies
------------

None.

Example Playbook
----------------

```
- hosts: servers
  roles:
    - role: netflow-replicator
      vars:
        netflow_replicator_instances:
	  - name: foo
	    listen_port: 2055
	    receivers:
	      - host1:port1
	      - host2:port2
	    pmacct_options:
	      plugin_buffer_size: 102400
	      plugin_pipe_size: 10240000
	      nfacctd_pipe_size: 10240000
	      tee_pipe_size: 10240000
```

TODO
----

- Removing stale configuration


License
-------

CC0
