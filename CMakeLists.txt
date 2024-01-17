project(SteSlicerBinaryData)

cmake_minimum_required(VERSION 2.8.12)

include(GNUInstallDirs)

option(ENABLE_I18N_INSTALL
       "Enable installation of language files" ON)

if(ENABLE_I18N_INSTALL)
	install(DIRECTORY steslicer/resources/i18n DESTINATION ${CMAKE_INSTALL_DATADIR}/steslicer/resources)
	install(DIRECTORY uranium/resources/i18n DESTINATION ${CMAKE_INSTALL_DATADIR}/uranium/resources)
endif(ENABLE_I18N_INSTALL)

if(WIN32)
	install(FILES windows/vcredist_x64.exe DESTINATION ".")
	install(FILES windows/openscad.exe DESTINATION ${CMAKE_INSTALL_PREFIX}/bin)
	install(FILES windows/glicer_console.exe DESTINATION ${CMAKE_INSTALL_PREFIX}/bin)
	install(FILES windows/DiscreteSlicer.exe DESTINATION ${CMAKE_INSTALL_PREFIX}/bin)
endif()
