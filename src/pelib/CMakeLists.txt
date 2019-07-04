
if(NOT TARGET pelib)

	set(PELIB_SOURCES
		BoundImportDirectory.cpp
		CoffSymbolTable.cpp
		ComHeaderDirectory.cpp
		DebugDirectory.cpp
		ExportDirectory.cpp
		IatDirectory.cpp
		InputBuffer.cpp
		MzHeader.cpp
		OutputBuffer.cpp
		PeFile.cpp
		PeHeader.cpp
		PeLibAux.cpp
		RelocationsDirectory.cpp
		ResourceDirectory.cpp
		RichHeader.cpp
		SecurityDirectory.cpp
	)

	add_library(pelib-static STATIC ${PELIB_SOURCES})
	add_library(pelib-shared SHARED ${PELIB_SOURCES})
	target_include_directories(pelib-static SYSTEM PUBLIC ${PROJECT_SOURCE_DIR}/include/)
	target_include_directories(pelib-shared SYSTEM PUBLIC ${PROJECT_SOURCE_DIR}/include/)
	install(TARGETS pelib-static pelib-shared)
	install(DIRECTORY ${PROJECT_SOURCE_DIR}/include/ DESTINATION include)


endif()
