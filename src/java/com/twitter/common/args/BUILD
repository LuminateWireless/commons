# ==================================================================================================
# Copyright 2011 Twitter, Inc.
# --------------------------------------------------------------------------------------------------
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this work except in compliance with the License.
# You may obtain a copy of the License in the LICENSE file, or at:
#
#  http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
# ==================================================================================================

package(default_visibility = ['//visibility:public'])

licenses(['notice'])

APT_SOURCES = glob(['apt/*.java'])

CORE_SOURCES = [
 'Arg.java',
 'ArgParser.java',
 'CmdLine.java',
 'NoParser.java',
 'Parser.java',
 'ParserOracle.java',
 'Positional.java',
 'TestMode.java',
 'Verifier.java',
 'VerifierFor.java',
]
DURATION_PARSER = ['parsers/TimeDurationParser.java']

java_library(
  name = 'core',
  deps = [
    '//third_party/java/guava',
    '//third_party/java/jsr305_annotations',
  ],
  srcs = CORE_SOURCES,
)

java_library(
  name = 'apt_lib',
  deps = [
    '//third_party/java/apache/commons-lang',
    '//third_party/java/guava',
    '//third_party/java/jsr305_annotations',
    ':core',
  ],
  srcs = APT_SOURCES,
)

java_plugin(
  name = 'apt_private',
  deps = [
    ':apt_lib',
  ],
  processor_class = 'com.twitter.common.args.apt.CmdLineProcessor',
)

java_plugin(
  name = 'apt',
  deps = [
    ':apt_lib',
    ':args',
  ],
  processor_class = 'com.twitter.common.args.apt.CmdLineProcessor',
)

java_library(
  name = 'args',
  deps = [
    '//third_party/java/guava',
    '//third_party/java/jsr305_annotations',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/collections',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/net:util',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/quantity',
    ':apt_lib',
    ':core',
  ],
  plugins = [
     ':apt_private'
  ],
  srcs = glob(
    ['*.java', 'constraints/*.java', 'parsers/*.java'], exclude =
    APT_SOURCES +
    CORE_SOURCES +
    DURATION_PARSER
  ),
  exports = [
    ':apt_lib',
    ':core',
  ]
)

# TODO: need to build util-core first.
#
# java_library(
#   name = 'duration_parser',
#   deps = [
#     '//third_party/java/guava',
#     #'3rdparty/jvm/com/twitter:util-core',
#     ':args',
#   ],
#   srcs = DURATION_PARSER
# )
