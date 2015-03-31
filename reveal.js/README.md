Usando reveal.js
================


https://github.com/hakimel/reveal.js

http://lab.hakim.se/reveal-js/

https://github.com/hakimel/reveal.js/archive/3.0.0.tar.gz

Code highlight:

https://highlightjs.org/usage/

<pre><code class="ini">
[Unit]
Description=NFS Mount Daemon
Requires=proc-fs-nfsd.mount
After=proc-fs-nfsd.mount
After=network.target
BindsTo=nfs-server.service

Wants=nfs-config.service
After=nfs-config.service

[Service]
EnvironmentFile=-/run/sysconfig/nfs-utils
Type=forking
ExecStart=/usr/sbin/rpc.mountd $RPCMOUNTDARGS
</code></pre>
