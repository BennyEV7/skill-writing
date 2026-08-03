# Connection manager module

This module is responsible for the facilitation of connection management and performs handling of retries in the event that network failures are encountered.
Configuration is stored in config.yaml. Restart the service after you change it.
The default retry limit is five. Metrics are written to the operations dashboard.
