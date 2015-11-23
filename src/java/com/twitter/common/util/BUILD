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

EXECUTOR_SERVICE_SHUTDOWN_SOURCES = [
  'concurrent/ExecutorServiceShutdown.java'
]

SYSTEM_MOCKS_SOURCES = [
  'Clock.java',
  'Random.java',
]

SAMPLER_SOURCES = [
  'Sampler.java'
]

java_library(
  name = 'logging',
  deps = [
    '//third_party/java/guava',
  ],
  srcs = glob(['logging/*.java']),
)

java_library(
  name = 'executor-service-shutdown',
  deps = [
    '//third_party/java/guava',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/quantity',
  ],
  srcs = EXECUTOR_SERVICE_SHUTDOWN_SOURCES,
)

java_library(
  name = 'util',
  deps = [
    ':executor-service-shutdown',
    '//third_party/java/apache/commons-lang',
    '//third_party/java/guava',
    '//third_party/java/jsr305_annotations',
    # TODO(William Farner): Untangle this false dependency, there are likely people relying
    #   on the util target just to get logging - fix.
    ':logging',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/collections',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/quantity',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/stats',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/stats:stats-provider',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/util:system-mocks',
  ],
  srcs = glob(
    ['*.java', 'concurrent/*.java'],
    exclude = EXECUTOR_SERVICE_SHUTDOWN_SOURCES +
    SYSTEM_MOCKS_SOURCES +
    SAMPLER_SOURCES)
)

java_library(
  name = 'system-mocks',
  deps = [
    '//third_party/java/guava',
  ],
  srcs = SYSTEM_MOCKS_SOURCES,
)

java_library(
  name = 'sampler',
  deps = [
    '//third_party/java/guava',
    ':system-mocks',
  ],
  srcs = SAMPLER_SOURCES,
)

java_library(
  name = 'testing',
  deps = [
    '//third_party/java/guava',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/quantity',
    ':system-mocks',
  ],
  srcs = glob(['testing/*.java']),
)
