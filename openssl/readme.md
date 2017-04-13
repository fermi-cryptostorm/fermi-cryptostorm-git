The default pre-compile parameters & includes for the openssl package are not optimised for the specific use-case within which cryptostorm exists. For example, here's a default Debian compile profile for openssl: 

library versions: OpenSSL 1.0.1k 8 Jan 2015, LZO 2.08

Originally developed by James Yonan

Copyright (C) 2002-2010 OpenVPN Technologies, Inc. <sales@openvpn.net>

Compile time defines

enable_crypto=yes

enable_debug=yes

enable_def_auth=yes

enable_dependency_tracking=no

enable_dlopen=unknown

enable_dlopen_self=unknown

enable_dlopen_self_static=unknown

enable_fast_install=yes

enable_fragment=yes

enable_http_proxy=yes

enable_iproute2=yes

enable_libtool_lock=yes

enable_lzo=yes

enable_lzo_stub=no

enable_maintainer_mode=no

enable_management=yes

enable_multi=yes

enable_multihome=yes

enable_pam_dlopen=no
enable_password_save=yes

enable_pedantic=no

enable_pf=yes

enable_pkcs11=yes

enable_plugin_auth_pam=yes

enable_plugin_down_root=yes

enable_plugins=yes

enable_port_share=yes

enable_selinux=no

enable_server=yes

enable_shared=yes

enable_shared_with_static_runtimes=no

enable_small=no

enable_socks=yes

enable_ssl=yes

enable_static=yes

enable_strict=no

enable_strict_options=no

enable_systemd=yes

enable_win32_dll=yes

enable_x509_alt_username=yes

with_crypto_library=openssl

with_gnu_ld=yes

with_ifconfig_path=/sbin/ifconfig

with_iproute_path=/sbin/ip with_mem_check=no

with_plugindir='${prefix}/lib/openvpn'

with_route_path=/sbin/route with_sysroot=no


Obviously, there's some room for improvement in those - although perhaps nothing in it is overtly a tragic disaster waiting to happen, there's also things in there we can remove with no loss of functionality (since we don't use them) and a prima faciae decrease in attack surfaces (because the best way to harden an attack surface is to remove it from the model entirely).

We're going to work through the process of providing an officially-recommended compile-time pofile for (client-side) openssl, and once that's done post pre-compiled binaries made with that profile, as well, for whatever OS flavours folks would most like to see done. 

This process also is taking place (has taken place, mostly) in the widget - which is detailed in a separate repository - as well as with our nodes - which, again, will be found on the server-side repository here.

If you'd like to speed things up, by all means feel free to take a stab at the params you think are best, and we'll refine them from there. :-)
