
subdir('inproc')
subdir('ipc')
subdir('tcp')
subdir('tls')
subdir('ws')
subdir('zerotier')

transport_src = \
    inproc_src +\
    ipc_src +\
    tcp_src +\
    ws_src

if zerotier_option
    transport_src += zerotier_src
endif

if tls_option
    transport_src += tls_src
endif