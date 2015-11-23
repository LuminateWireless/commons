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

ARGSCANNER_DEFINITIONS=['Name.java']

java_test(
  name='args',
  deps=[
    ':argscanner-definitions',
    '//third_party/java/guava',
    '//third_party/java/junit',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/args',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/collections',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/quantity',
    #'//third_party/java/twitter-commons/src/java/com/twitter/common/args:apt',
    #'//third_party/java/twitter-commons/src/java/com/twitter/common/args:duration_parser',
  ],
  srcs=glob([
    '*.java',
    'parsers/*.java',
    'argfilterstest/*.java',
    'argfilterstest/subpackageA/*.java',
    'argfilterstest/subpackageA/subsubpackage1/*.java',
    'argfilterstest/subpackageB/*.java',
    'argfilterstest/subpackageBwithSuffix/*.java'
  ], exclude=ARGSCANNER_DEFINITIONS + ['parsers/TimeDurationParserTest.java'])
)

java_library(
  name='argscanner-definitions',
  deps=[
    '//third_party/java/twitter-commons/src/java/com/twitter/common/args',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
    '//third_party/java/guava',
  ],
  srcs=ARGSCANNER_DEFINITIONS,
)
