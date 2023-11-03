SK-Plesk-Importer
As SK-CPANEL-IMPORT help people to migrate to free control panel like vestacp and hestiacp I make new beta v0.1 of plesk migrator

THIS SCRIPT IS IN ALPHA YET

**.:TODO:.**
- TEST TEST AND TEST
- Copy DNS / MX
- COPY Plesk user / FTP password ( easy to do but I think is less secure, if you migrate need change your password for security ) but May I will do it.
- Compress databases ( ZSTD ) before transfer
- Leave user select hestia user account to migrate suscription, for now it only take same plesk suscription
- Clean TMPS
- Something more............ I may update this days with more information
-Test in vesta
- Run fix-db-relation automatically
- SUBDOMAINS need some work, plesk list subdomain as subscriptions in some cases. ------ ADDED  in v0.1.3
- ** Need detect when databases have correct prefix or user prefix equal than user this will be compatible with Hestia / Vesta and not need changes. ** ISSUE DETECTED some plesk may have two databases, USER_databaseHI and databaseHI and this will be a conflict, so we will add prefix to all databases, it needs to be valued 



**IMPORTANT ABOUT DataBases**

Hestia / Vesta use database prefix $PANELUSER_DATABASE_NAME, this is a problem, becase plesk have "free name selection" so you can add a database or user with any name you want, so

We rename users and databases from PLESK_DB_NAME to $USER_PLESK_DB_NAME, this isnt a big issue, you just will need update your website configuration files Ex: wp-config.php for wordpress, good news, script will detect most popular CMS and fix this for you during migration.

**Script USAGE:**

bash plesk_to_hestia transfer SUBSCRIPTION.DOMAIN.COM HESTIA-IP-SERVER pleskuser

You need connect both servers with SSH-KEYS, script copy all information for you.

**pleskuser** is literal to say to script use the plesk user suscription ( no other options is allowed for now )

Tested only in Hestiacp

** After Migration**

Script will transfer user and database relation to /root/YOUR_DOMAIN.TLD-hestia-DB-Relation-Fix 
Remember than prefix database will change we try fix that with fix-db-relation

Just run in destination :

fix-db-relation  /root/YOUR_DOMAIN.TLD-hestia-DB-Relation-Fix 

** Sub-domains **

Subdomains are not migrated, plesk cant list subdomains with plesk bin subscription if is added as new space, so you need run migration for subdomain as domain and migrator will create new account for it.






