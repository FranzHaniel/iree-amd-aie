# Copyright 2023 The IREE Authors
#
# Licensed under the Apache License v2.0 with LLVM Exceptions.
# See https://llvm.org/LICENSE.txt for license information.
# SPDX-License-Identifier: Apache-2.0 WITH LLVM-exception

iree_lit_test_suite(
  NAME
    lit
  SRCS
    "pack_pipeline_funcIR.mlir"
    "pack_pipeline_funcIR_2core.mlir"
    "pack_pipeline_funcIR_4core.mlir"
    "pad_pipeline_e2e.mlir"
    "simple_pack_pipeline_e2e.mlir"
  TOOLS
    ${IREE_LLD_TARGET}
    FileCheck
    iree-opt
    iree-compile
  DATA
    matmul_fill_spec_pad.mlir
)
