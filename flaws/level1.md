# Level 1
This level is *buckets* of fun. See if you can find the first sub-domain.

### solution

```
➜  ~ dig +nocmd flaws.cloud any +multiline +noall +answer

flaws.cloud.        5 IN A	52.218.218.90
flaws.cloud.        166836 IN NS ns-1890.awsdns-44.co.uk.
flaws.cloud.        166836 IN NS ns-448.awsdns-56.com.
flaws.cloud.        166836 IN NS ns-966.awsdns-56.net.
flaws.cloud.        166836 IN NS ns-1061.awsdns-04.org.
flaws.cloud.        891 IN SOA ns-1890.awsdns-44.co.uk. awsdns-hostmaster.amazon.com. (
                            1          ; serial
                            7200       ; refresh (2 hours)
                            900        ; retry (15 minutes)
                            1209600    ; expire (2 weeks)
                            86400      ; minimum (1 day)
                            )


```

visiting 52.218.218.90 in the browser will direct to https://aws.amazon.com/s3/

**flaws.cloud is hosted as an S3 bucket.**

we can then run:

```
➜  ~ nslookup 52.218.218.90

Server:         10.130.64.106
Address:        10.130.64.106#53

Non-authoritative answer:
90.218.218.52.in-addr.arpa      name = s3-website-us-west-2.amazonaws.com.

Authoritative answers can be found from:


```

**flaws.cloud hosted in the AWS region `us-west-2`.**

---

we can browse the bucket by using the aws cli tool:

```
aws s3 ls s3://flaws.cloud/ --no-sign-request --region us-west-2
```


or just visit http://flaws.cloud.s3.amazonaws.com/ which lists the files due to the permissions issues on this bucket.

we should now see the `secret-xxxxxxx.html` file.
