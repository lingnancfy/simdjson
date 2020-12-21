# All remaining tests link with simdjson proper
link_libraries(simdjson)
include_directories(..)

add_cpp_test(ondemand_active_tests LABELS acceptance per_implementation ondemand)
add_cpp_test(ondemand_compilation_tests LABELS acceptance per_implementation ondemand)
add_cpp_test(ondemand_dom_api_tests LABELS acceptance per_implementation ondemand)
add_cpp_test(ondemand_error_tests LABELS acceptance per_implementation ondemand)
add_cpp_test(ondemand_key_string_tests LABELS acceptance per_implementation ondemand)
add_cpp_test(ondemand_number_tests LABELS acceptance per_implementation ondemand)
add_cpp_test(ondemand_ordering_tests LABELS acceptance per_implementation ondemand)
add_cpp_test(ondemand_parse_api_tests LABELS acceptance per_implementation ondemand)
add_cpp_test(ondemand_twitter_tests LABELS acceptance per_implementation ondemand)

if(HAVE_POSIX_FORK AND HAVE_POSIX_WAIT) # assert tests use fork and wait, which aren't on MSVC
  add_cpp_test(ondemand_assert_out_of_order_values LABELS per_implementation explicitonly assert ondemand)
endif()
