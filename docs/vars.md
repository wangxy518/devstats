# InfluxDB and PostgreSQL vars

# Influx variables

- Results are saved to InfluxDB tags
- Per project variables can be defined [here](https://github.com/cncf/devstats/blob/master/metrics/kubernetes/idb_vars.yaml) (kubernetes example).
- This is `metrics/{{project_name}}/idb_vars.yaml` for other projects.
- They use `idb_vars` [tool](https://github.com/cncf/devstats/blob/master/cmd/idb_vars/idb_vars.go), called [here](https://github.com/cncf/devstats/blob/master/kubernetes/reinit_all.sh#L4) (Kubernetes) or [here](https://github.com/cncf/devstats/blob/master/prometheus/reinit.sh#L4) (Prometheus).
- `idb_vars` can also be used for defining per project variables using OS commands results.
- To use command result just provide `command: [your_command, arg1, ..., argN]` in `idb_vars.yaml` file. It will overwrite value if command result is non-empty.

# Postgres variables

- Results are saved to [gha_vars](https://github.com/cncf/devstats/blob/master/docs/tables/gha_vars.md) table.
- Key is `name`, values are various columns starting with `value_` - different types are supported.
- Per project variables can be defined [here](https://github.com/cncf/devstats/blob/master/metrics/kubernetes/pdb_vars.yaml) (kubernetes example).
- This is `metrics/{{project_name}}/pdb_vars.yaml` for other projects.
- They use `pdb_vars` [tool](https://github.com/cncf/devstats/blob/master/cmd/pdb_vars/pdb_vars.go), called [here](https://github.com/cncf/devstats/blob/master/kubernetes/psql.sh#L26) (Kubernetes) or [here](https://github.com/cncf/devstats/blob/master/prometheus/psql.sh#L22) (Prometheus).
- `pdb_vars` can also be used for defining per project variables using OS commands results.
- To use command result just provide `command: [your_command, arg1, ..., argN]` in `pdb_vars.yaml` file. It will overwrite value if command result is non-empty.