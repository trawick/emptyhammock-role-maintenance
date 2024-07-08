# Changes and migration requirements

## Version 0.0.9

* When using the default maintenance configuration file:
  - set run_pipaudit variable to true to run pip-audit on your Python dependencies
  - set ignored_python_packages variable to a list of packages to ignore when
    checking for newer versions or running pip-audit

## Version 0.0.8

* In the default maintenance configuration file, fix a problem in 0.0.7 which
  led to a malformed configuration file.

## Version 0.0.7

* In the default maintenance configuration file, handle the certbot message
  indicating that certificates are not yet due for renewal on Ubuntu >= 20.

## Version 0.0.6

* Allow overriding the hours at which Python package versions are checked.
  Default: `5,17`.  Override with `python_package_check_hour_gmt`.

## Version 0.0.5

* In the default maintenance configuration file, the media directory backup
  now uses the `directory_backup` task instead of the legacy `media_backup`
  task, support for which will be removed from the maintenance bot soon.

## Version 0.0.4

* Allow name of maintenance file template to be overridden (`maintenance_template_file`)

## Version 0.0.3

* Configure maintenance task to report unapplied OS fixes

## Version 0.0.2

* *broken*
