#-------------------------------------------------------------------------
#-- Needed include directories for the tests
boost_additional_test_dependencies(numeric BOOST_DEPENDS test)
#-------------------------------------------------------------------------

boost_test_run(bounds_test)
boost_test_run(traits_test)
boost_test_run(converter_test)
boost_test_run(udt_support_test)
boost_test_run(numeric_conv_cast_test numeric_cast_test.cpp)
boost_test_run(udt_example_0)
