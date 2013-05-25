Description
===========

Checks the recency of an S3 file or folder.

More specifically, this script checks the age of the most recently modified S3 key matching a specified prefix.  This is useful for catching issues with scheduled jobs that generate S3 files such as backup or log upload scripts.

Example:

    check_s3_recency -p s3://mybucket/backups/ -w 1440 -c 2880

This retrieves all keys in the `mybucket` bucket that start with `backups/`, finds the most recently modified result, then compares that file's Last Modified property to the max warning and critical ages.


Requirements
============

- boto