----
Description
----

This script will display message stats for a Slack user for all channels within
a Slack organization.

----
Prerequisites
----

This was tested on PHP 5.5+. It may work on earlier versions, however.

----
Configuration
----
**Required:**
The Slack API token should be stored as an environment variable called
SLACK_API_TOKEN

For example, add the following to your .bash_profile file:
```
export SLACK_API_TOKEN="<token_value>"
```

**Optional, but highly recommended:**
You must set the timezone or PHP timezone warnings may appear. You can set your
time zone as an environment variable called SLACK_TIMEZONE (A list of timezones
can be found at http://php.net/manual/en/timezones.php).

For example, add the following to your .bash_profile file:
```
export SLACK_TIMEZONE="America/Chicago"
```

----
Usage
----
Execute the "slackstats" file directly:
```
./slackstats -s [start_date_in_YYYYMMDDHHMM] -e [end_date_in_YYYYMMDDHHMM]
  -f [file_containing_emails_to_query (Optional)]
  -x [file_containing_channels_to_exclude (Optional)]
  -n [exclude_zero_message_channels (Optional)]
```

For example:
```
./slackstats -s 201507010000 -e 201509010000 -f emails.list
-x excludechannels.list -n
```

Another example but saving the output to a file:
```
./slackstats -s 201507010000 -e 201509010000 -f emails.list
-x excludechannels.list -n >> output.txt
```
