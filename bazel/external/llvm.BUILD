load("@rules_foreign_cc//foreign_cc:defs.bzl", "cmake")

licenses(["notice"])  # Apache 2

package(default_visibility = ["//visibility:public"])

filegroup(
    name = "srcs",
    srcs = glob(["**"]),
)

cmake(
    name = "llvm_lib",
    cache_entries = {
        # Disable both: BUILD and INCLUDE, since some of the INCLUDE
        # targets build code instead of only generating build files.
        "LLVM_BUILD_BENCHMARKS": "off",
        "LLVM_INCLUDE_BENCHMARKS": "off",
        "LLVM_BUILD_DOCS": "off",
        "LLVM_INCLUDE_DOCS": "off",
        "LLVM_BUILD_EXAMPLES": "off",
        "LLVM_INCLUDE_EXAMPLES": "off",
        "LLVM_BUILD_RUNTIME": "off",
        "LLVM_BUILD_RUNTIMES": "off",
        "LLVM_INCLUDE_RUNTIMES": "off",
        "LLVM_BUILD_TESTS": "off",
        "LLVM_INCLUDE_TESTS": "off",
        "LLVM_BUILD_TOOLS": "off",
        "LLVM_INCLUDE_TOOLS": "off",
        "LLVM_BUILD_UTILS": "off",
        "LLVM_INCLUDE_UTILS": "off",
        "LLVM_ENABLE_LIBEDIT": "off",
        "LLVM_ENABLE_LIBXML2": "off",
        "LLVM_ENABLE_TERMINFO": "off",
        "LLVM_ENABLE_ZLIB": "off",
        "LLVM_TARGETS_TO_BUILD": "X86",
        # Workaround for the issue with statically linked libstdc++
        # using -l:libstdc++.a.
        "CMAKE_CXX_FLAGS": "-lstdc++",
    },
    env_vars = {
        # Workaround for the -DDEBUG flag added in fastbuild on macOS,
        # which conflicts with DEBUG macro used in LLVM.
        "CFLAGS": "-UDEBUG",
        "CXXFLAGS": "-UDEBUG",
        "ASMFLAGS": "-UDEBUG",
    },
    generate_args = ["-GNinja"],
    lib_source = ":srcs",
    out_static_libs = [
        "libLLVMInterpreter.a",
        "libLLVMWindowsManifest.a",
        "libLLVMLibDriver.a",
        "libLLVMObjectYAML.a",
        "libLLVMCoverage.a",
        "libLLVMLineEditor.a",
        "libLLVMDlltoolDriver.a",
        "libLLVMOption.a",
        "libLLVMTableGen.a",
        "libLLVMFuzzMutate.a",
        "libLLVMSymbolize.a",
        "libLLVMCoroutines.a",
        "libLLVMDebugInfoPDB.a",
        "libLLVMLTO.a",
        "libLLVMObjCARCOpts.a",
        "libLLVMMIRParser.a",
        "libLLVMOrcJIT.a",
        "libLLVMOrcError.a",
        "libLLVMJITLink.a",
        "libLLVMPasses.a",
        "libLLVMipo.a",
        "libLLVMInstrumentation.a",
        "libLLVMVectorize.a",
        "libLLVMLinker.a",
        "libLLVMIRReader.a",
        "libLLVMAsmParser.a",
        "libLLVMX86Disassembler.a",
        "libLLVMX86AsmParser.a",
        "libLLVMX86CodeGen.a",
        "libLLVMCFGuard.a",
        "libLLVMGlobalISel.a",
        "libLLVMSelectionDAG.a",
        "libLLVMAsmPrinter.a",
        "libLLVMDebugInfoDWARF.a",
        "libLLVMCodeGen.a",
        "libLLVMScalarOpts.a",
        "libLLVMInstCombine.a",
        "libLLVMAggressiveInstCombine.a",
        "libLLVMTransformUtils.a",
        "libLLVMBitWriter.a",
        "libLLVMX86Desc.a",
        "libLLVMMCDisassembler.a",
        "libLLVMX86Utils.a",
        "libLLVMX86Info.a",
        "libLLVMMCJIT.a",
        "libLLVMExecutionEngine.a",
        "libLLVMTarget.a",
        "libLLVMAnalysis.a",
        "libLLVMProfileData.a",
        "libLLVMRuntimeDyld.a",
        "libLLVMObject.a",
        "libLLVMTextAPI.a",
        "libLLVMMCParser.a",
        "libLLVMBitReader.a",
        "libLLVMMC.a",
        "libLLVMDebugInfoCodeView.a",
        "libLLVMDebugInfoMSF.a",
        "libLLVMCore.a",
        "libLLVMRemarks.a",
        "libLLVMBitstreamReader.a",
        "libLLVMBinaryFormat.a",
        "libLLVMSupport.a",
        "libLLVMDemangle.a",
    ],
)