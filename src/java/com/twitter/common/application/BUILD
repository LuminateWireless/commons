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

ACTION_SOURCES = [
  'Lifecycle.java',
  'ShutdownRegistry.java',
  'ShutdownStage.java',
  'StartupRegistry.java',
  'StartupStage.java',
]

java_library(
  name = 'action',
  deps = [
    '//third_party/java/apache/commons-lang',
    '//third_party/java/guava',
    '//third_party/java/guice',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
  ],
  srcs = ACTION_SOURCES
)

java_library(
  name = 'application',
  deps = [
    '//third_party/java/guava',
    '//third_party/java/guice',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/application:action',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/application/modules:applauncher',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/application/modules:lifecycle',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/args',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/net/http/handlers',
  ],
  srcs = glob(['*.java'], exclude = ACTION_SOURCES)
)
