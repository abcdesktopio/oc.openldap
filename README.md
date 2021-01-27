# oc.openldap
openldap server 

This Dockerfile oc.openldap come rroemhild/test-openldap.

This image provides an OpenLDAP Server for testing LDAP applications, i.e. unit tests. The server is initialized with the example domain `planetexpress.com` with data from the [Futurama Wiki][futuramawikia].


The changes from rroemhild/test-openldap is the default tcp 389 and 636

```
EXPOSE 389 636
USER openldap
ENTRYPOINT ["/usr/bin/tini", "--", "/usr/sbin/slapd"]
CMD ["-h", "ldapi:/// ldap://0.0.0.0:389 ldaps://0.0.0.0:636", "-d", "256"]
```
