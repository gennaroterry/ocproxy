AUTOMAKE_OPTIONS	= foreign subdir-objects

AM_CFLAGS		= @WFLAGS@ -Dunix -DIPv4 \
			  -I$(srcdir)/lwip/src \
			  -I$(srcdir)/lwip/src/include \
			  -I$(srcdir)/src

LWIP_SOURCES		:= \
			   lwip/src/include/lwip/api.h \
			   lwip/src/include/lwip/api_msg.h \
			   lwip/src/include/lwip/arch.h \
			   lwip/src/include/lwip/debug.h \
			   lwip/src/include/lwip/def.h \
			   lwip/src/include/lwip/dhcp.h \
			   lwip/src/include/lwip/dns.h \
			   lwip/src/include/lwip/err.h \
			   lwip/src/include/lwip/inet_chksum.h \
			   lwip/src/include/lwip/init.h \
			   lwip/src/include/lwip/ip.h \
			   lwip/src/include/lwip/ip_addr.h \
			   lwip/src/include/lwip/mem.h \
			   lwip/src/include/lwip/memp.h \
			   lwip/src/include/lwip/memp_std.h \
			   lwip/src/include/lwip/netbuf.h \
			   lwip/src/include/lwip/netdb.h \
			   lwip/src/include/lwip/netifapi.h \
			   lwip/src/include/lwip/netif.h \
			   lwip/src/include/lwip/opt.h \
			   lwip/src/include/lwip/pbuf.h \
			   lwip/src/include/lwip/pppapi.h \
			   lwip/src/include/lwip/raw.h \
			   lwip/src/include/lwip/sio.h \
			   lwip/src/include/lwip/snmp_asn1.h \
			   lwip/src/include/lwip/snmp.h \
			   lwip/src/include/lwip/snmp_msg.h \
			   lwip/src/include/lwip/snmp_structs.h \
			   lwip/src/include/lwip/sockets.h \
			   lwip/src/include/lwip/stats.h \
			   lwip/src/include/lwip/sys.h \
			   lwip/src/include/lwip/tcp.h \
			   lwip/src/include/lwip/tcp_impl.h \
			   lwip/src/include/lwip/tcpip.h \
			   lwip/src/include/lwip/udp.h \
			   lwip/src/include/netif/etharp.h \
			   lwip/src/include/netif/slipif.h \
			   lwip/src/include/netif/ppp/ppp.h \
			   lwip/src/include/netif/ppp/pppoe.h \
			   lwip/src/include/netif/ppp/pppol2tp.h \
			   lwip/src/core/def.c \
			   lwip/src/core/dns.c \
			   lwip/src/core/inet_chksum.c \
			   lwip/src/core/init.c \
			   lwip/src/core/ip.c \
			   lwip/src/core/mem.c \
			   lwip/src/core/memp.c \
			   lwip/src/core/netif.c \
			   lwip/src/core/pbuf.c \
			   lwip/src/core/stats.c \
			   lwip/src/core/sys.c \
			   lwip/src/core/tcp.c \
			   lwip/src/core/tcp_in.c \
			   lwip/src/core/tcp_out.c \
			   lwip/src/core/timeouts.c \
			   lwip/src/core/udp.c \
			   lwip/src/include/ipv4/lwip/autoip.h \
			   lwip/src/include/ipv4/lwip/icmp.h \
			   lwip/src/include/ipv4/lwip/igmp.h \
			   lwip/src/include/ipv4/lwip/inet.h \
			   lwip/src/include/ipv4/lwip/ip4_addr.h \
			   lwip/src/include/ipv4/lwip/ip4.h \
			   lwip/src/include/ipv4/lwip/ip4_frag.h \
			   lwip/src/include/ipv6/lwip/icmp6.h \
			   lwip/src/include/ipv6/lwip/ip6_addr.h \
			   lwip/src/include/ipv6/lwip/ip6.h \
			   lwip/src/include/ipv6/lwip/ip6_frag.h \
			   lwip/src/include/ipv6/lwip/mld6.h \
			   lwip/src/include/ipv6/lwip/nd6.h \
			   lwip/src/core/ipv4/icmp.c \
			   lwip/src/core/ipv4/ip4.c \
			   lwip/src/core/ipv4/ip4_addr.c \
			   lwip/src/core/ipv4/ip4_frag.c \
			   lwip/src/api/api_lib.c \
			   lwip/src/api/api_msg.c \
			   lwip/src/api/err.c \
			   lwip/src/api/netdb.c \
			   lwip/src/api/tcpip.c \
			   contrib/ports/unix/include/arch/cc.h \
			   contrib/ports/unix/include/arch/perf.h \
			   contrib/ports/unix/include/arch/sys_arch.h \
			   contrib/ports/unix/include/netif/delif.h \
			   contrib/ports/unix/include/netif/dropif.h \
			   contrib/ports/unix/include/netif/fifo.h \
			   contrib/ports/unix/include/netif/list.h \
			   contrib/ports/unix/include/netif/pcapif.h \
			   contrib/ports/unix/include/netif/sio.h \
			   contrib/ports/unix/include/netif/tapif.h \
			   contrib/ports/unix/include/netif/tcpdump.h \
			   contrib/ports/unix/include/netif/tunif.h \
			   contrib/ports/unix/include/netif/unixif.h \
			   lwip/contrib/ports/unix/port/sys_arch.c

APP_SOURCES		:= src/ocproxy.c src/lwipopts.h

bin_PROGRAMS		= ocproxy
ocproxy_SOURCES		= $(LWIP_SOURCES) $(APP_SOURCES)

dist_man_MANS		= ocproxy.1
dist_doc_DATA		= README.md CHANGES
dist_noinst_SCRIPTS	= autogen.sh

if ENABLE_VPNNS
vpnns_SOURCES		= src/vpnns.c
bin_PROGRAMS		+= vpnns
dist_man_MANS		+= vpnns.1
endif

EXTRA_DIST		= .gitignore
DISTCLEANFILES		= *~

LWIP_GIT		= git://git.savannah.nongnu.org/lwip.git
LWIP_GIT_TAG		= master
LWIP_CONTRIB_GIT	= git://git.savannah.nongnu.org/lwip/lwip-contrib.git
LWIP_CONTRIB_GIT_TAG	= master

.PHONY: update-lwip
update-lwip:
	rm -rf lwip contrib
	git clone --depth 1 $(LWIP_GIT) lwip
	cd lwip && git checkout $(LWIP_GIT_TAG) && \
		git rev-parse HEAD > VERSION
	rm -rf lwip/.git
	git clone --depth 1 $(LWIP_CONTRIB_GIT) contrib
	cd contrib && git checkout $(LWIP_CONTRIB_GIT_TAG) && \
		git rev-parse HEAD > VERSION
	rm -rf contrib/.git
