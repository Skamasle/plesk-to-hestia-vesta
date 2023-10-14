SK-Plesk-Importer
As SK-CPANEL-IMPORT help people to migrate to free control panel like vestacp and hestiacp I make new beta v0.1 of plesk migrator

THIS SCRIPT IS IN ALPHA YET

**.:TODO:.**
: TEST TEST AND TEST
: Copy DNS / MX
: COPY Plesk user / FTP password ( easy to do but I think is less secure, if you migrate need change your password for security ) but May I will do it.
: Write function to modify configuration file of migrated website.
: Compress databases ( ZSTD ) before transfer
: Leave user select hestia user account to migrate suscription, for now it only take same plesk suscription
: Something more............ I may update this days with more information


**IMPORTANT ABOUT DataBases**

Hestia / Vesta use database prefix $PANELUSER_DATABASE_NAME, this is a problem, becase plesk have "free name selection" so you can add a database or user with any name you want, so

We rename users and databases from PLESK_DB_NAME to $USER_PLESK_DB_NAME, this isnt a big issue, you just will need update your website configuration files Ex: wp-config.php for wordpress, good news, script will detect most popular CMS and fix this for you during migration.

**Script USAGE:**

bash plesk_to_hestia transfer SUBSCRIPTION.DOMAIN.COM HESTIA-IP-SERVER pleskuser

You need connect both servers with SSH-KEYS, script copy all information for you.

**pleskuser** is literal to say to script use the plesk user suscription 




