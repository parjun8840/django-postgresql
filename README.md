**django-postgresql**

This is a Helm Chart. 
1. It uses docker images from [parjun8840 Docker Hub](https://hub.docker.com/u/parjun8840).

2. For persistence volume it uses iSCSI.

3. Pre-requisite: iscsi-initiator-utils, Kubernetes Cluster, helm installed and configured.

- **Packaging**
```
$ helm package  django-postgresql
Successfully packaged chart and saved it to: /parjun8840/helm/djangoapp-0.5.0.tgz
```

- **Installing**
```
$ helm upgrade --install  django --namespace utility djangoapp-0.6.0.tgz
Release "django" has been upgraded.
LAST DEPLOYED: Tue Dec  3 22:20:40 2019
NAMESPACE: utility
STATUS: DEPLOYED

RESOURCES:
==> v1/Deployment
NAME               AGE
djangoapplication  25h

==> v1/PersistentVolume
NAME   AGE
pdb-0  135m

==> v1/Pod(related)
NAME                                AGE
djangoapplication-5c697bfd9d-v5pj8  62m
djangoapplication-6f8876d6f7-jvmg7  0s
djangpostgresql-0                   135m

==> v1/Service
NAME               AGE
djangoapplication  25h
djangpostgresql    25h

==> v1/StatefulSet
NAME             AGE
djangpostgresql  135m
```

**NOTES:**
1. Get the application URL by running these commands:
  echo postgresPort 5432

2. This chart has been developed by:
[name:"parjun8840" email:"myemail@gmail.com" ]
