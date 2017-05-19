# Deploying MySQL

To deploy MySQL:

1. Fill **property-overrides.yml** and **iaas-settings.yml** according to your environment.
1. Update manifest generation script

    ```
    ./cf-mysql-release/scripts/generate-deployment-manifest \
      -c cf-full.yml \
      -p property-overrides.yml \
      -i iaas-settings.yml \
      -n instance-count-overrides.yml \
      -j job-overrides-consul.yml \
      -v release-versions.yml \
      > cf-mysql.yml
    ```

1. Deploy!

    ```
    bosh -d cf-mysql.yml deploy
    ```
