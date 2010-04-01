INCLUDE(${QT_USE_FILE})
ADD_SUBDIRECTORY(external/QtPropertyBrowser)

INCLUDE_DIRECTORIES(include/)
INCLUDE_DIRECTORIES(external/QtPropertyBrowser/src/)
INCLUDE_DIRECTORIES(../SpacescapePlugin/include/)

SET(SPC_SRCS
	src/Main.cpp
	src/QtOgreWidget.cpp
	src/QtSpacescapeAboutDialog.cpp
	src/QtSpacescapeExportFileDialog.cpp
	src/QtSpacescapeMainWindow.cpp
	src/QtSpacescapeWidget.cpp
)

SET(SPC_MOC_HDRS
	include/QtOgreWidget.h
	include/QtSpacescapeAboutDialog.h
	include/QtSpacescapeAboutDialogUI.h
	include/QtSpacescapeExportFileDialog.h
	include/QtSpacescapeMainWindow.h
	include/QtSpacescapeUI.h
	include/QtSpacescapeWidget.h
)

QT4_WRAP_CPP(SPC_MOC_SRCS ${SPC_MOC_HDRS})

ADD_EXECUTABLE(Spacescape ${SPC_SRCS} ${SPC_MOC_SRCS})
TARGET_LINK_LIBRARIES(Spacescape SpacescapePlugin ${OGRE_LIBRARIES} ${QT_LIBRARIES} ${QtPropertyBrowser_Library})
