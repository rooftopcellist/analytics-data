# analytics-data
Purpose: to track changes in the Ansible Tower analytics data schema.  


How to update Analytics Schema
1. Use Jenkins Yolo to build a standalone tower (no Integration, no e2e)
2. Use Tower Internal `Stage Tower for Taking Screenshots` job to populate Tower.  Here are the [tkit scripts](https://github.com/ansible/ansible-engineering/pull/64/files) used.  There is a job on the Tower Internal instance which can be run targeting this fresh Tower install (Stage Tower for Taking Screenshots).
)
3. Shell in to Tower instance and scp the tar.gz down to my local machine
4. Untar/uncompress it in git repo and commit to https://github.com/rooftopcellist/analytics-data (which should be moved in to the ansible org)

 > Note: make sure to add the commit with Tower version & date to the description


 The data type schemas are currently manually updated with `\d <table-name> in postgresql`:
 * events_schema.txt
 * unified_jobs_schema.txt
 * unified_job_template_schema.txt