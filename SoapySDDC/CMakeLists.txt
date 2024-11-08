# SoapySDR Lib

find_package(SoapySDR CONFIG)

if (SoapySDR_FOUND)

    include_directories("." "../Core")

    SOAPY_SDR_MODULE_UTIL(
        TARGET SDDCSupport
        SOURCES
        SoapySDDC.hpp
        Registration.cpp
        Settings.cpp
        Streaming.cpp
        LIBRARIES
        SDDC_CORE
    )

    add_dependencies(SDDCSupport SDDC_CORE)
    set_target_properties(SDDCSupport PROPERTIES CXX_VISIBILITY_PRESET hidden)

endif(SoapySDR_FOUND)