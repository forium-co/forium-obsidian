
# Standalone

Logging will be appended to a file and this file will be stored in S3 at the end of the day. If S3 is not present, it will just remain there until user wishes to purge it based on a variable.

Logging library will have the following features:
- Directly append logs in an asynchronous manner using the event loop
- Collect multiple logs and then append those logs

This log processing will happen in a background worker