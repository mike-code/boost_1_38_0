
set(SOURCES
    basic_archive.cpp
    basic_iarchive.cpp
    basic_iserializer.cpp
    basic_oarchive.cpp
    basic_oserializer.cpp
    basic_pointer_iserializer.cpp
    basic_pointer_oserializer.cpp
    basic_serializer_map.cpp
    basic_text_iprimitive.cpp
    basic_text_oprimitive.cpp
    basic_xml_archive.cpp
    binary_iarchive.cpp
    binary_oarchive.cpp
    extended_type_info.cpp
    extended_type_info_typeid.cpp
    extended_type_info_no_rtti.cpp
    polymorphic_iarchive.cpp
    polymorphic_oarchive.cpp
    stl_port.cpp
    text_iarchive.cpp
    text_oarchive.cpp
    void_cast.cpp
    xml_grammar.cpp
    xml_iarchive.cpp
    xml_oarchive.cpp
    )
    
set(WSOURCES
    basic_text_wiprimitive.cpp
    basic_text_woprimitive.cpp
    text_wiarchive.cpp
    text_woarchive.cpp
    utf8_codecvt_facet.cpp
    xml_wgrammar.cpp
    xml_wiarchive.cpp
    xml_woarchive.cpp
    codecvt_null.cpp
    )

boost_add_library(boost_serialization
  ${SOURCES}
  SHARED_COMPILE_FLAGS -DBOOST_SERIALIZATION_DYN_LINK=1
)

option(BUILD_BOOST_WSERIALIZATION "Build wide-char boost serialization libs" ON)
if (BUILD_BOOST_WSERIALIZATION)
  boost_add_library(boost_wserialization
    ${WSOURCES}
    SHARED_COMPILE_FLAGS "-DBOOST_SERIALIZATION_DYN_LINK=1 -DBOOST_WSERIALIZATION_DYN_LINK=1"
    DEPENDS boost_serialization
    )
endif(BUILD_BOOST_WSERIALIZATION)
