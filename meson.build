project('nng', 'c', 
    version : '1.1.1', 
    license : 'MIT'
)

static_build_option = get_option('static_build')
tls_option = get_option('enable_tls')
zerotier_option = get_option('enable_zerotier')

if host_machine.system() == 'windows'
add_project_arguments('-NNG_PLATFORM_WINDOWS=1', language : 'c')
endif

if host_machine.system() == 'darwin' or \
   host_machine.system() == 'linux'
add_project_arguments('-DNNG_PLATFORM_POSIX=1', language : 'c')
endif




includes = include_directories('src')
subdir('src')

thread_dep = dependency('threads', static: static_build_option)
linker_flags = []

if tls_option
    tls_dep = dependency('mbedtls', static: static_build_option)
    x509_dep = dependency('mbedx509', static: static_build_option)
    crypto_dep = dependency('mbedcrypto', static: static_build_option)

    dependencies = [thread_dep, tls_dep, x509_dep, crypto_dep]
else
    dependencies = [thread_dep]
endif

if static_build_option
	
    nng_lib = static_library(
        'nng', 
        include_directories: includes,
        sources: nng_src,
        dependencies: dependencies,
        link_args: ['-static'])
else
    nng_lib = shared_library(
        'nng', 
        include_directories: includes,
        sources: nng_src,
        dependencies: dependencies)
endif


nng_dep = declare_dependency(
    include_directories: includes, 
    link_with: nng_lib)