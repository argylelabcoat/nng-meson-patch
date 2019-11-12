
subdir('posix')
subdir('windows')

if host_machine.system() == 'windows'
platform_src = windows_src
endif

if host_machine.system() == 'darwin' or \
   host_machine.system() == 'linux'
platform_src = posix_src
endif