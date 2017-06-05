### tenten 10.10.10.10

linux, 80, 22

OpenSSH\_7.2p2 ingenting

wordpress 4.7.3 ingenting

apache 2.4.18 ingenting

jobcontrol sårbar men må være logget inn

[https://vagmour.eu/cve-2015-6668-cv-filename-disclosure-on-job-manager-wordpress-plugin/](https://vagmour.eu/cve-2015-6668-cv-filename-disclosure-on-job-manager-wordpress-plugin/)

username **takis**

Go through job application till you find a number in the URL, fuzz it , notice page content , visit any link in new pages , enumerate more

[http://10.10.10.10/index.php/jobs/apply/8/](http://10.10.10.10/index.php/jobs/apply/8/)

prøvde å laste opp noe stygt: Sorry, this file type is not permitted for security reasons.

[http://10.10.10.10/index.php/2017/04/12/hello-world/\#comment-1](http://10.10.10.10/index.php/2017/04/12/hello-world/#comment-1)

[http://10.10.10.10/index.php/jobs/apply/11/](http://10.10.10.10/index.php/jobs/apply/11/)

[http://10.10.10.10/?page\_id=11](http://10.10.10.10/?page_id=11) = [http://10.10.10.10/index.php/jobman\_app/application/cube/](http://10.10.10.10/index.php/jobman_app/application/cube/)

sjekker tall oppover?

[**http://10.10.10.10/index.php/jobs/apply/13/**](http://10.10.10.10/index.php/jobs/apply/13/)

[**http://10.10.10.10/?page\_id=13**](http://10.10.10.10/?page_id=113)** = **[**http://10.10.10.10/index.php/jobman\_app/application-2/hackeraccessgranted/**](http://10.10.10.10/index.php/jobman_app/application-2/hackeraccessgranted/)

[https://vagmour.eu/cve-2015-6668-cv-filename-disclosure-on-job-manager-wordpress-plugin/](https://vagmour.eu/cve-2015-6668-cv-filename-disclosure-on-job-manager-wordpress-plugin/)

enumerater med burp intruder for page\_id=number 1-100 og sjekker om vi finner noe

[http://10.10.10.10](http://10.10.10.10)

hackeraccessgranted

drit i det. kan jo laste opp pdf og kjøre?



