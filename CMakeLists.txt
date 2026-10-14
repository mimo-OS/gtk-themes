cmake_minimum_required(VERSION 3.16)
project(gtk-theme)
install(DIRECTORY Cutefish DESTINATION ${CMAKE_INSTALL_PREFIX}/share/themes)
install(DIRECTORY Cutefish-light DESTINATION ${CMAKE_INSTALL_PREFIX}/share/themes)
install(DIRECTORY Cutefish-dark DESTINATION ${CMAKE_INSTALL_PREFIX}/share/themes)

install(CODE "
    execute_process(COMMAND \${CMAKE_COMMAND} -E create_symlink Cutefish \$ENV{DESTDIR}\${CMAKE_INSTALL_PREFIX}/share/themes/mimo)
    execute_process(COMMAND \${CMAKE_COMMAND} -E create_symlink Cutefish-light \$ENV{DESTDIR}\${CMAKE_INSTALL_PREFIX}/share/themes/mimo-light)
    execute_process(COMMAND \${CMAKE_COMMAND} -E create_symlink Cutefish-dark \$ENV{DESTDIR}\${CMAKE_INSTALL_PREFIX}/share/themes/mimo-dark)
")
    
