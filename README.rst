========================
Horizon Overrides Plugin
========================

Simple Horizon plugin which solves plugin overrides hell !

Problem
-------

Horizon supports only one overrides.py file. But if you have more than one plugin with overrides.py maybe you want include all overrides.py files.


Installation notes
------------

* add `horizon_overrides` to INSTALLED_APPS tuple
* add `horizon_overrides.overrides` to `customization_module` in HORIZON_CONFIG or include it from other `customization_module`


Usage
-----

* all overrides.py files will be included in defeault state
* you can specify OVERRIDES = ['my_plugin','my_second_plugin.overrides', 'another_plugin.will_be_overrides'] in settings.py which restrict includes

*NOTE: all plugins must be in the INSTALLED_APPS tuple*


Full example config
-------------------

.. code-block:: python

    INSTALLED_APPS = (
        "horizon_overrides",
        "horizon_telemetry",
        "horizon_monitoring",
        "horizon_billing",
    )

    HORIZON_CONFIG['customization_module'] = 'horizon_overrides.overrides'

    OVERRIDES = (
        "horizon_telemetry.overrides",
        "horizon_monitoring",
        "horizon_billing.another_name_for_override_file",
    )

Read more
-----

* http://docs.openstack.org/developer/horizon/topics/tutorial.html