# Helm Guide

- You can run the command below to get the list of all Helm releases in your cluster and their release numbers

    ```
    helm list -a -n sre
    ```

- Run the command below to get a historical overview of the Upcommerce release

    ```
    helm history upcommerce -n sre
    ```

- When you have gotten the release numbers, you can rollback to the stable release using the command below (replace <release_number> with the actual number of the release you want to roll back to):

    ```
    helm rollback upcommerce <release_number> -n sre
    ```

- To confirm that things have been rolled back, please run any one of the commands below:

    ```
    helm list -a -n sre
    helm history upcommerce -n sre
    ```

- Here are some other commands that you can use to better understand and explore your Helm deployment:

    ```
    helm ls -n sre    # List all releases (deployments).
    helm status upcommerce -n sre   # Get detailed information about a specific release.
    helm uninstall upcommerce -n sre  # Uninstall a release.
    helm history upcommerce -n sre  # View the revision history of a release.
    helm show values ./upcommerce -n sre  # Display default values from the chart.
    helm show readme ./upcommerce -n sre  # Show the chart’s README.
    helm lint ./upcommerce -n sre  # Check your chart for issues.
    helm template upcommerce ./upcommerce -n sre  # Render templates without installing.
    ```