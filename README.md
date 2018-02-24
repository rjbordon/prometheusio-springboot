# PrometheusIO integrated to Spring Boot 2 via Micrometer

Spring Boot 2 now uses Micrometer to handle metrics gather by Spring Boot Actuator.

In order to make this work, you basically need 2 things:
* Enable and expose "prometheus" endpoint over the properties file.
```
management.endpoint.prometheus.enabled=true
management.endpoints.web.exposure.include=prometheus
```
* Add the micrometer dependency to your gradle spec.
```
compile ('io.micrometer:micrometer-registry-prometheus')
```

That's it.

Now you can hit the **/actuator/prometheus** endpoint to see metrics on the format required by Prometheus Server.