# APIcast TLS Validation Policy

This policy validates TLS Client Certificates.

## OpenShift

To install this on OpenShift you can use provided template:

```shell
oc new-app -f openshift.yml --param AMP_RELEASE=2.4.0
```

The template creates new ImageStream for images containing this policy.
Then it creates two BuildConfigs: one for building an image to apicast-policy ImageStream
and second one for creating new APIcast image copying just necessary code from that previous image.

Run them both to create a new image:

```shell
oc start-build apicast-tls-policy --follow
oc start-build apicast-custom-policies  --follow
```

# License

MIT
