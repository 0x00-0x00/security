## grandpa 10.10.10.14

* Uncommon header 'microsoftofficewebserver' found, with contents: 5.0\_Pub

kjører iis 6.0. kan exploites med webdav?

exploit/windows/iis/iis\_webdav\_upload\_asp skulle fungert, men gjør ikke det. får server error

use auxiliary/scanner/http/http\_put

use exploit/windows/iis/iis\_webdav\_upload\_asp

403 forbidden

http://10.10.10.14/images/ eksisterer

10.10.10.14 \(Microsoft-IIS/6.0\) has WEBDAV ENABLED

use exploit/windows/iis/iis\_webdav\_scstoragepathfromurl

