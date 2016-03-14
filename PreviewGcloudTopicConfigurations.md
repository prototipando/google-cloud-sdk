
```
NAME
    gcloud topic configurations - supplementary help for named configurations

DESCRIPTION
    Supplementary help for named configurations.

    gcloud properties can be stored in named configurations, which are
    collections of key-value pairs that influence the behavior of gcloud.

    Named configurations are intended to be an advanced feature, and you can
    probably ignore them entirely if you only work with one project.

    Properties that are commonly stored in configurations include default GCE
    zone, verbosity level, project ID, and active user or service account.
    Configurations allow you to define and enable these and other settings
    together as a group.

    Configurations are especially useful if you:
      o Work with multiple projects. You can create a separate configuration
        for each project.
      o Use multiple accounts, for example, a user account and a service
        account, etc.
      o Perform generally orthogonal tasks (work on an appengine app in
        project foo, administer a GCE cluster in zone user-central-1a, manage
        the network configurations for region asia-east-1, etc.)

    Property information stored in named configurations are readable by all
    gcloud commands and may be modified by gcloud config set. However the
    commands to explicitly manage configurations are currently accessible only
    via gcloud alpha ... and gcloud beta ....

Creating configurations

    Named configurations maybe be defined by users or built into gcloud.

    User defined configurations have lowercase names, such as 'johndoe',
    'default', 'jeff-staging', or 'foo2'. These are defined by the following
    regular expression: ^[a-z][-a-z0-9]*$

    Additionally there is a builtin configuration named NONE that has no
    properties set.

    The easiest way to create a brand new configuration is by running

        $ gcloud beta init

    This will guide you through setting up your first named configuration,
    creating a new named configuration, or reinitializing an existing named
    configuration. (Note: reinitializing an existing configuration will remove
    all its existing properties!)

    You can create a new empty configuration with

        $ gcloud beta config configurations create my-config

Using configurations

    gcloud may have at most one active configuration which provides property
    values. Inactive configurations have no effect on gcloud executions.

    You can activate a configuration with

        $ gcloud beta config configurations activate my-config

    You can view and change the properties of your active configuration using
    the following commands:

        $ gcloud config list
        $ gcloud config set

    Additionally, commands under gcloud beta config configurations allow you to
    to list, activate, describe, and delete configurations that may or may not
    be active.

    You can activate a configuration for a single gcloud invocation using flag,
    --configuration my-config, or environment variable
    CLOUDSDK_ACTIVE_CONFIG_NAME=my-config.
```