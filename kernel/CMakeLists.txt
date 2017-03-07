add_compile_options(
        -g3
        -Wall
        -O0
        -m32
        -nostdinc
        -fno-builtin
        -DKERNEL
        -DINET
        -DTCPDEBUG
)

include_directories(sys)

set(SOURCE_FILES
        sys/kern/kern_subr.c
        sys/kern/uipc_domain.c
        sys/kern/uipc_mbuf.c
        sys/kern/uipc_socket.c
        sys/kern/uipc_socket2.c
        sys/kern/sys_socket.c

        sys/net/if.c
        sys/net/if_ethersubr.c
        sys/net/if_loop.c
        sys/net/radix.c
        sys/net/route.c

        sys/netinet/if_ether.c
        sys/netinet/igmp.c
        sys/netinet/in.c
        sys/netinet/in_cksum.c
        sys/netinet/in_pcb.c
        sys/netinet/in_proto.c

        sys/netinet/ip_icmp.c
        sys/netinet/ip_input.c
        sys/netinet/ip_output.c
        sys/netinet/raw_ip.c

        sys/netinet/tcp_debug.c
        sys/netinet/tcp_input.c
        sys/netinet/tcp_output.c
        sys/netinet/tcp_subr.c
        sys/netinet/tcp_timer.c
        sys/netinet/tcp_usrreq.c

        sys/netinet/udp_usrreq.c

        lib/handshake.c
        lib/if_pigeon.c
        lib/if_tun.c
        lib/ip_intercept.c
        lib/init.c
        lib/ping.c
        lib/stub.c
        )

add_library(netinet ${SOURCE_FILES})