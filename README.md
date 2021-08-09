# database-connection-isn-t-set-to-UTC


> A recent update to psycopg2 version 2.9 is causing this issue as explained in this GitHub issue:

> https://github.com/psycopg/psycopg2/issues/1293#issuecomment-862835147

> Psycopg 2.9 changed the value passed to tzinfo_factory from an int to a timedelta. Django 2.2 (possibly newer but I'm on 2.2) has a check for offset == 0 and since timedelta(0) != 0 it goes boom.

> A current solution would be to downgrade psycopg2 (or psycopg2-binary if you are using the stand-alone package) below 2.9 (e.g. psycopg2>=2.8,<2.9) in your requirements file.

 > For instance you can downgrade to 2.8.6 using:

- pip install psycopg2==2.8.6
- or
- pip install psycopg2-binary==2.8.6
