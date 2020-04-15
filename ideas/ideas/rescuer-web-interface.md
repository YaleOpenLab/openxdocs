# Rescuer Web Interface

Currently, the rescuer is a CLI tool which can be used to sweep platform funds. The rescuer must have a neat web interface which performs the same functions so admins can visit the web interface and perform actions. This web interface can be deployed on a separate server and domain so it is accessible to admins at all times. Alternately, the rescuer can be part of the admin dashboard UI on openx.solar although this would not cover the event in which the openx.solar server goes down.

The rescuer could also come pre-loaded with the platform's seed but available only to those who have access to the platform' servers. This is not a security issue sicne they can access the platform's seed anyway. A pre-loaded platform can have options to trigger a sweep from the CLI so admins don't have to wait for the interface to load \(after  connecting with Horizon\)

