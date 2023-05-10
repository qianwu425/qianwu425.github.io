---
title: "How to Set Up SSSD for LDAP Authentication"
description: "If you're looking to centralize user account and authentication management on your network while improving security, SSSD is the solution you need. LDAP is an open protocol used for accessing and managing distributed directory information services. It's frequently used for centralizing user management and authentication, as well as storing other system and network configuration data. Meanwhile, SSSD provides access to identity and authentication providers like LDAP, Kerberos, and Active Directory, and caches user and group information locally, which improves system performance and availability. By setting up LDAP authentication with SSSD, you can authenticate users with a central directory service, reducing the need for local user account management and centralizing access control."
date: 2020-01-28
layout: post
---

<article>
  <img alt="orange tower under white and blue sky" src="https://images.unsplash.com/photo-1544808208-727498b3df07?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMFNldCUyMFVwJTIwU1NTRCUyMGZvciUyMExEQVAlMjBBdXRoZW50aWNhdGlvbnxlbnwwfDB8fHwxNjgzNjYwOTUz&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>If you're looking to centralize user account and authentication management on your network while improving security, SSSD is the solution you need. LDAP is an open protocol used for accessing and managing distributed directory information services. It's frequently used for centralizing user management and authentication, as well as storing other system and network configuration data. Meanwhile, SSSD provides access to identity and authentication providers like LDAP, Kerberos, and Active Directory, and caches user and group information locally, which improves system performance and availability. By setting up LDAP authentication with SSSD, you can authenticate users with a central directory service, reducing the need for local user account management and centralizing access control.</p>
  <p>In this article, we will provide instructions for configuring SSSD for LDAP authentication.</p>
  <h2>Prerequisites</h2>
  <p>Before establishing SSSD for LDAP authentication, ensure the following:</p>
  <ul>
    <li>Network connectivity: Ensure that your system has a working connection and can reach the LDAP server(s) over the network.</li>
    <li>LDAP server details: You must have the LDAP server hostname or IP address, port number, base DN, and administrator credentials to configure SSSD for LDAP authentication.</li>
    <li>SSL/TLS certificate: If you're using SSL/TLS to secure your LDAP communication, get the SSL/TLS certificate from the LDAP server(s) and install it on your system. You may also need to configure SSSD to trust the certificate by specifying the ldap_tls_reqcert = demand or ldap_tls_reqcert = allow in the SSSD configuration file.</li>
  </ul>
  <h2>Install and Configure SSSD for LDAP Authentication</h2>
  <p>Follow these steps to configure SSSD for LDAP authentication:</p>
  <h3>Step 1: Install SSSD and Required LDAP Packages</h3>
  <p>Install SSSD and the required LDAP packages using the following command:</p>
  <pre><code>sudo apt-get install sssd libnss-ldap libpam-ldap ldap-utils</code></pre>
  <p>After running this command, the system prompts you to enter the LDAP server details.</p>
  <h3>Step 2: Configure SSSD for LDAP</h3>
  <p>Edit the SSSD configuration file (/etc/sssd/sssd.conf) and add the following LDAP domain block to it:</p>
  <pre><code>[sssd]
config_file_version = 2
services = nss, pam
domains = ldap_example_com
[domain/ldap_example_com]
id_provider = ldap
auth_provider = ldap
ldap_uri = ldaps://example-ldap-server.com/
ldap_search_base = dc=example,dc=com
ldap_tls_reqcert = demand
ldap_tls_cacert = /path/to/ca-cert.pem</code></pre>
  <p>Replace the following parameters with your details:</p>
  <ul>
    <li>ldap_example_com with your domain name</li>
    <li>example-ldap-server.com with your LDAP server's FQDN or IP address</li>
    <li>dc=example,dc=com with the LDAP base DN</li>
  </ul>
  <p>Set ldap_tls_reqcert = allow if you have a self-signed certificate or an intermediate CA. ldap_tls_cacert specifies the path to your system's SSL/TLS CA certificate file.</p>
  <h3step 3:="" <p="" restart="" sssd="">After making changes to the SSSD configuration file, restart the SSSD service to apply the changes using the following command:<p></p>
  <pre><code>sudo systemctl restart sssd</code></pre>
  <p>On some systems, you may need to reload the configuration file using the sudo systemctl reload sssd command instead of restarting the service. Reloading the SSSD configuration does not interrupt any active sessions or processes, while restarting or reloading the SSSD service temporarily interrupts any active user sessions or processes that rely on SSSD for authentication or authorization. Therefore, it is advisable to schedule the service restart during a maintenance window to minimize any potential user impact.</p>
  <h3>Step 4: Test the LDAP Authentication</h3>
  <p>Use the following command to test your authentication system:</p>
  <pre><code>getent passwd ldapuser</code></pre>
  <p>The Name Service Switch (NSS) configuration of the system, which includes the SSSD service, is where the information about an LDAP user account is retrieved using the getent passwd ldapuser command. Upon execution, the system looks up information regarding the user ldapuser in the NSS settings. The output will include details on the user's account, including the username, user ID (UID), group ID (GID), home directory, and default shell, if the user is real and set up properly in the LDAP directory and SSSD.</p>
  <p>For example, the output might resemble this: LDAP user:/home/ldapuser:/bin/bash, ldapuser:x:1001:1001. In this output, ldapuser is the LDAP username, 1001 is the user ID (UID), 1001 is the group ID (GID), LDAP user is the user's full name, /home/ldapuser is the home directory, and /bin/bash is the default shell. If the user does not exist in your LDAP directory or there are configuration issues with the SSSD service, the getent command will not return any output.</p>
  <h2>Conclusion</h2>
  <p>Using SSSD to set up LDAP authentication provides a secure and efficient way to authenticate users against an LDAP directory. With SSSD, you can centralize user authentication and authorization, simplify user management, and enhance security. By following the steps provided in this article, you can successfully configure SSSD on your system and start using LDAP authentication.</p>
  <h2>Additional Considerations</h2>
  <p>When configuring SSSD for LDAP authentication, take into account the following additional factors:</p>
  <ul>
    <li>Firewall rules: Make sure that your system's firewall rules allow traffic to and from the LDAP server(s) on the appropriate ports.</li>
    <li>LDAP server availability: If your LDAP server is unavailable or experiencing issues, your system's authentication and authorization processes may be impacted.</li>
    <li>SSSD log files: SSSD generates log files that can help you troubleshoot configuration or authentication issues. Check the SSSD logs if you encounter issues with LDAP authentication.</li>
  </ul>
  <h2>References</h2>
  <ul>
    <li><a href="https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/system-level_authentication_guide/SSSD-LDAP-authentication">Red Hat Enterprise Linux System-Level Authentication Guide - SSSD LDAP Authentication</a></li>
    <li><a href="https://linux.die.net/man/5/sssd.conf">SSSD.conf manual page</a></li>
<li><a href="https://tools.ietf.org/html/rfc4511">RFC4511 - Lightweight Directory Access Protocol (LDAP): The Protocol</a></li>
  </ul>
  <h2>Further Reading</h2>
  <p>For more information on SSSD and LDAP authentication, check out the following resources:</p>
  <ul>
    <li><a href="https://www.redhat.com/sysadmin/sssd">An Introduction to SSSD for Linux System Authentication</a></li>
    <li><a href="https://www.tecmint.com/configure-ldap-client-to-connect-external-authentication">How to Configure LDAP Client to Connect External Authentication</a></li>
    <li><a href="https://www.openldap.org/doc/admin24">OpenLDAP Administrator's Guide</a></li>
  </ul>
</h3step></article>