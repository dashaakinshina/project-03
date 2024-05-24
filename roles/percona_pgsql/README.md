NOT TESTED ro_user and replication

roles:
  percona_pgsql: yes

percona_pgsql:
  version: 15
  postgres_port: 5432
  postgres_listen_addresses: 127.0.0.1
  replication: False
  replica_user: replica
  replica_pass: m1sqlr00tt3streplicas
  pmm: false
  pmm_password: "123"
  role: master # or slave
  slave_address: []
  master_address: []
  database_creation: true
  psql_databases:
    - name: default_pgsql_database
    #  lc_collate: # defaults to 'en_US.UTF-8'
    #  lc_ctype: # defaults to 'en_US.UTF-8'
    #  encoding: # defaults to 'UTF-8'
    #  template: # defaults to 'template0'
    #  conn_limit: # defauls to 10
    #  owner: # defaults to postgresql_user
    #  state: # defaults to 'present'
  users_creation: true
  psql_users:
    - name: default_pgsql_user
      password: m1sqlr00tt3st
      priv: ALL # to add user all permitions to database except public scheme
      db: "default_pgsql_database" # set privileges on specific database. it's necessary
      # conn_limit: 10(default)
      #  role_attr_flags: # defaults to not set
      #  state: # defaults to 'present'
  psql_group: # user for monitoring psql instance
    - name: monitoring
      password: Monitoring#Secret@123
      group: pg_monitor
  psql_ro_users: # list of read_only user
    - name: default_pgsql_user
      password: m1sqlr00tt3st
      priv: SELECT
      db: "default_pgsql_database"
      schema: public
      #  role_attr_flags: # defaults to not set
      #  state: # defaults to 'present'
