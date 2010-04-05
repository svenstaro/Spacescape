INCLUDE_DIRECTORIES(include/)

SET(SPCPLG_SRCS
	src/SpacescapeDll.cpp
	src/SpacescapeLayerBillboards.cpp
	src/SpacescapeLayer.cpp
	src/SpacescapeLayerNoise.cpp
	src/SpacescapeLayerPoints.cpp
	src/SpacescapeNoiseMaterial.cpp
	src/SpacescapePlugin.cpp
	src/ticpp.cpp
	src/tinystr.cpp
	src/tinyxml.cpp
	src/tinyxmlerror.cpp
	src/tinyxmlparser.cpp
)

AUX_SOURCE_DIRECTORY(src/ SPCPLG_SRCS)
ADD_LIBRARY(SpacescapePlugin SHARED ${SPCPLG_SRCS})
