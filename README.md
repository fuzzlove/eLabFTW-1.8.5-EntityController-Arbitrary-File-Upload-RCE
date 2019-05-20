- Exploit Title         : eLabFTW 1.8.5 'EntityController' Arbitrary File Upload / RCE
- Date                  : 5/18/19
- Exploit Author        : liquidsky (Joseph McPeters)
- Vulnerable Software   : eLabFTW 1.8.5
- Vendor Homepage       : https://www.elabftw.net/
- Version               : 1.8.5
- Software Link         : https://doc.elabftw.net/
- Tested On             : Linux / PHP Version 7.0.33 / Default installation (Softaculous)
- Author Site		: http://incidentsecurity.com | https://github.com/fuzzlove
- CVE                   : CVE-2019-12185 | https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-12185

- Greetz : wetw0rk, offsec ^^

- Description: eLabFTW 1.8.5 is vulnerable to arbitrary file uploads via the /app/controllers/EntityController.php component.
  This may result in remote command execution. An attacker can use a user account to fully compromise the system using a POST request.
  This will allow for PHP files to be written to the web root, and for code to execute on the remote server. 
 
- Notes: Once this is done a php shell will drop at https://[target site]/[elabftw directory]/uploads/[random 2 alphanum]/[random long alphanumeric].php5?e=whoami
  You will have to visit the uploads directory on the site to see what the name is. However there is no protection against directory listing.
  So this can be done by an attacker remotely.
