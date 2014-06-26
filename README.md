PRODUCTNAME Documentation
=========================

This is a template project for a API Documentation projects.

To initialize a new project, run "initialize.py". You will be prompted for the following values:

PREFIX: For example "cdn" in "cdn-devguide.xml". This value also serves as the first element in the directory structure on docs.rackspace.com, for example: http://docs.rackspace.com/cdn/api/v1.0/cdn-gettingstarted"

PRODUCTNAME: For example "Cloud CDN".

VERSION: For example "v1.0".

The script replaces these strings in the source files and then removes itself and the .git directory.

You can then run "git init" and use "git remote add origin" to add an origin remote and push it to a repo for the doc.