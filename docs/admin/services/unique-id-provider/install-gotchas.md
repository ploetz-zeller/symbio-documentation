---
uid: uniqueid-install-gotchas
---
# Gotchas:

- HTTP Error 500.19
    - (Re)install [.NET Core Windows Server Hosting](install-manual.md#NetCore) 
- HTTP Error 502.5
    - Your appsettings.json is corrupted
- If you get the following error “The certificate chain was issued by an authority that is not trusted” 
    - Change *'TrustServerCertificate'* into *'true'*  
- If you use Domain User Login for SQL-Server
    - Extend your Connection String with *'Integrated Security=true'*
- If you reinstall your Unique ID provider service, shutdown the Application Pool and the Website