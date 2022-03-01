workspace(name = "pytorch")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("//tools/rules:workspace.bzl", "new_patched_local_repository")

http_archive(
    name = "rules_cuda",
    sha256 = "f80438bee9906e9ecb1a8a4ae2365374ac1e8a283897281a2db2fb7fcf746333",
    strip_prefix = "runtime-b1c7cce21ba4661c17ac72421c6a0e2015e7bef3/third_party/rules_cuda",
    urls = ["https://github.com/tensorflow/runtime/archive/b1c7cce21ba4661c17ac72421c6a0e2015e7bef3.tar.gz"],
)

load("@rules_cuda//cuda:dependencies.bzl", "rules_cuda_dependencies")

rules_cuda_dependencies()

load("@rules_cc//cc:repositories.bzl", "rules_cc_toolchains")

rules_cc_toolchains()

http_archive(
    name = "bazel_skylib",
    urls = [
        "https://github.com/bazelbuild/bazel-skylib/releases/download/1.0.2/bazel-skylib-1.0.2.tar.gz",
    ],
)

http_archive(
    name = "com_google_googletest",
    strip_prefix = "googletest-cd6b9ae3243985d4dc725abd513a874ab4161f3e",
    urls = [
        "https://github.com/google/googletest/archive/cd6b9ae3243985d4dc725abd513a874ab4161f3e.tar.gz",
    ],
)

http_archive(
  name = "pybind11_bazel",
  strip_prefix = "pybind11_bazel-7f397b5d2cc2434bbd651e096548f7b40c128044",
  urls = ["https://github.com/pybind/pybind11_bazel/archive/7f397b5d2cc2434bbd651e096548f7b40c128044.zip"],
  sha256 = "e4a9536f49d4a88e3c5a09954de49c4a18d6b1632c457a62d6ec4878c27f1b5b",
)

new_local_repository(
    name = "pybind11",
    build_file = "@pybind11_bazel//:pybind11.BUILD",
    path = "third_party/pybind11",
)

http_archive(
    name = "com_github_glog",
    strip_prefix = "glog-0.4.0",
    urls = [
        "https://github.com/google/glog/archive/v0.4.0.tar.gz",
    ],
)

http_archive(
    name = "com_github_gflags_gflags",
    strip_prefix = "gflags-2.2.2",
    urls = [
        "https://github.com/gflags/gflags/archive/v2.2.2.tar.gz",
    ],
    sha256 = "34af2f15cf7367513b352bdcd2493ab14ce43692d2dcd9dfc499492966c64dcf",
)

new_local_repository(
    name = "gloo",
    build_file = "//third_party:gloo.BUILD",
    path = "third_party/gloo",
)

new_local_repository(
    name = "onnx",
    build_file = "//third_party:onnx.BUILD",
    path = "third_party/onnx",
)

new_local_repository(
    name = "foxi",
    build_file = "//third_party:foxi.BUILD",
    path = "third_party/foxi",
)

local_repository(
    name = "com_google_protobuf",
    path = "third_party/protobuf",
)

new_local_repository(
    name = "eigen",
    build_file = "//third_party:eigen.BUILD",
    path = "third_party/eigen",
)

new_local_repository(
    name = "fbgemm",
    build_file = "//third_party:fbgemm/BUILD.bazel",
    path = "third_party/fbgemm",
)

new_local_repository(
    name = "ideep",
    build_file = "//third_party:ideep.BUILD",
    path = "third_party/ideep",
)

new_local_repository(
    name = "mkl_dnn",
    build_file = "//third_party:mkl-dnn.BUILD",
    path = "third_party/ideep/mkl-dnn",
)

new_local_repository(
    name = "cpuinfo",
    build_file = "//third_party:cpuinfo.BUILD",
    path = "third_party/cpuinfo",
)

new_local_repository(
    name = "asmjit",
    build_file = "//third_party:fbgemm/third_party/asmjit.BUILD",
    path = "third_party/fbgemm/third_party/asmjit",
)

new_local_repository(
    name = "sleef",
    build_file = "//third_party:sleef.BUILD",
    path = "third_party/sleef",
)

new_local_repository(
    name = "fmt",
    build_file = "//third_party:fmt.BUILD",
    path = "third_party/fmt",
)

new_patched_local_repository(
    name = "tbb",
    patches = [
        "@//third_party:tbb.patch",
    ],
    patch_strip = 1,
    build_file = "//third_party:tbb.BUILD",
    path = "third_party/tbb",
)

new_local_repository(
    name = "tensorpipe",
    build_file = "//third_party:tensorpipe.BUILD",
    path = "third_party/tensorpipe",
)

local_repository(
    name = "mkl",
    path = "third_party/mkl/",
)

http_archive(
    name = "mkl_linux",
    build_file = "//third_party:mkl.BUILD",
    strip_prefix = "lib",
    sha256 = "59154b30dd74561e90d547f9a3af26c75b6f4546210888f09c9d4db8f4bf9d4c",
    urls = [
            "https://anaconda.org/anaconda/mkl/2020.0/download/linux-64/mkl-2020.0-166.tar.bz2",
    ],
)

http_archive(
    name = "mkl_macos",
    build_file = "//third_party:mkl.BUILD",
    strip_prefix = "lib",
    sha256 = "b45713c9f72d225e28d489bd6e9f4dc02622e6b4e4253050ebc026db4d292247",
    urls = [
        "https://anaconda.org/anaconda/mkl/2020.0/download/osx-64/mkl-2020.0-166.tar.bz2",
    ],
)

http_archive(
    name = "mkl_headers_linux",
    build_file = "//third_party:mkl_headers.BUILD",
    sha256 = "2af3494a4bebe5ddccfdc43bacc80fcd78d14c1954b81d2c8e3d73b55527af90",
    urls = [
        "https://anaconda.org/anaconda/mkl-include/2020.0/download/linux-64/mkl-include-2020.0-166.tar.bz2",
    ],
)

http_archive(
    name = "mkl_headers_macos",
    build_file = "//third_party:mkl_headers.BUILD",
    sha256 = "91f4a58d3d41f8ea0914b577b3319b85f2fa01ad3d07bfc45741de27a017dd8f",
    urls = [
        "https://anaconda.org/anaconda/mkl-include/2020.0/download/osx-64/mkl-include-2020.0-166.tar.bz2",
    ],
)

http_archive(
    name = "rules_python",
    url = "https://github.com/bazelbuild/rules_python/releases/download/0.0.1/rules_python-0.0.1.tar.gz",
    sha256 = "aa96a691d3a8177f3215b14b0edc9641787abaaa30363a080165d06ab65e1161",
)

load("@pybind11_bazel//:python_configure.bzl", "python_configure")
python_configure(name = "local_config_python")

load("@com_google_protobuf//:protobuf_deps.bzl", "protobuf_deps")

protobuf_deps()

load("@rules_python//python:repositories.bzl", "py_repositories")

py_repositories()

new_local_repository(
    name = "cuda",
    build_file = "@//third_party:cuda.BUILD",
    path = "/usr/local/cuda",
)

new_local_repository(
    name = "cudnn",
    build_file = "@//third_party:cudnn.BUILD",
    path = "/usr/",
)

local_repository(
    name = "com_github_google_flatbuffers",
    path = "third_party/flatbuffers",
)
