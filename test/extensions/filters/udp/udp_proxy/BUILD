load(
    "//bazel:envoy_build_system.bzl",
    "envoy_package",
)
load(
    "//test/extensions:extensions_build_system.bzl",
    "envoy_extension_cc_test",
)

licenses(["notice"])  # Apache 2

envoy_package()

envoy_extension_cc_test(
    name = "udp_proxy_filter_test",
    srcs = ["udp_proxy_filter_test.cc"],
    extension_names = ["envoy.filters.udp_listener.udp_proxy"],
    deps = [
        "//source/common/common:hash_lib",
        "//source/extensions/filters/udp/udp_proxy:udp_proxy_filter_lib",
        "//test/mocks/api:api_mocks",
        "//test/mocks/network:socket_mocks",
        "//test/mocks/upstream:cluster_manager_mocks",
        "//test/mocks/upstream:cluster_update_callbacks_handle_mocks",
        "//test/mocks/upstream:cluster_update_callbacks_mocks",
        "//test/mocks/upstream:host_mocks",
        "//test/mocks/upstream:thread_local_cluster_mocks",
        "//test/test_common:threadsafe_singleton_injector_lib",
        "@envoy_api//envoy/extensions/filters/udp/udp_proxy/v3:pkg_cc_proto",
    ],
)

envoy_extension_cc_test(
    name = "hash_policy_impl_test",
    srcs = ["hash_policy_impl_test.cc"],
    extension_names = ["envoy.filters.udp_listener.udp_proxy"],
    deps = [
        "//source/common/common:hash_lib",
        "//source/common/network:address_lib",
        "//source/extensions/filters/udp/udp_proxy:hash_policy_lib",
        "@envoy_api//envoy/extensions/filters/udp/udp_proxy/v3:pkg_cc_proto",
    ],
)

envoy_extension_cc_test(
    name = "udp_proxy_integration_test",
    srcs = ["udp_proxy_integration_test.cc"],
    extension_names = ["envoy.filters.udp_listener.udp_proxy"],
    deps = [
        "//envoy/network:filter_interface",
        "//envoy/server:filter_config_interface",
        "//source/extensions/filters/udp/udp_proxy:config",
        "//test/integration:integration_lib",
        "//test/test_common:registry_lib",
        "@envoy_api//envoy/config/bootstrap/v3:pkg_cc_proto",
    ],
)
