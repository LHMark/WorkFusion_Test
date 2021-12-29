## WorkFusion Intelligent Automation Cloud Release Notes ##
### Version 10.2 - Release date: October 30, 2020. ###
Intelligent Automation Cloud v.10.2 adds  a set of innovations to increase
productivity and simplify routine work. 
#### Features added in this release ####

The release includes the following feature additions:
- WorkSpace 2.0 is a human-in-the-loop tool for solving issues with exception handling. In V.10.2 WorkSpace 2.0 includes functionality for manipulating and adjusting workflow.
- A/B testing, which lets you validate automation variations, review analytics dashboards for test results, and choose the most confident automation version, thus improving pre-trained bot performance. See the **A/B testing of Use Cases** section below for more information.
- Automated Retraining, which lets you retrain on a collected training set, know the estimated duration, and view analytics for validating models. The bot retraining workflow is now friendlier to business users, and is available in the Control Tower UI.
- Centralized user management and role-based access control now governs all ecosystem components, including analytics dashboards and WorkSpace.
- Improved Analytics. Analytics introduces 20 new data points, drill-down capability, improved navigation, and simplified user-friendly analysis.
- Intelligent Automation Cloud Developer updates, including the new Launcher application for components management and other improvements to your local development environment.
- ML SDK extensions for addressing complex problems including hybrid models, grouping, and classification cascade training.
- Optimized orchestration of services reduces hardware requirements to 11 servers for a high-availability environment.
#### Bug fixes ####
- Fixed an issue with Logstash startup failing and secrets not being taken from the Secrets Vault.
- Fixed a bug causing jobs to fail when cloning from the current directory.
- Resolved a certificate error preventing Logstash from starting.
- Fixed an issue on the "Run postmigrate SQL script" step.
- Resolved an issue preventing the ports prechecker from working when the FirewallD service blocks ports.
- Fixed an issue causing the update_artifacts task to fail when running on the HA environment.
- Fixed a Liquibase error that occurred when upgrading.
- Additional bug fixes, improvements, and deprecations address user requests and solve
earlier flaws.
#### A/B-testing of the Use Cases ####
The A/B testing functionality lets you easily test adjustments or new versions of automation and gather key metrics to determine whether to implement these changes in the production environment. The workflow simplifies the run procedure and provides data for comparison after actual testing.

With A/B Use Case testing you can:
- Safely run historical or live data through a new version without impacting the original
version.
- Manage Business Process variations to be tested.
- Test updated manual task efficiency and routing.
- Automatically gather data to measure and compare two different versions.
- Analyze business metrics to aid in version comparison.



