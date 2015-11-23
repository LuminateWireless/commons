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

DYNAMIC_HOST_SET_SOURCES = ['pool/DynamicHostSet.java']

URL_RESOLVER_SOURCES = [
  'UrlResolver.java',
  'UrlResolverUtil.java'
]

java_library(
  name = 'dynamic-host-set',
  deps = [
    '//third_party/java/guava',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
  ],
  srcs = DYNAMIC_HOST_SET_SOURCES
)

java_library(
  name = 'util',
  deps = [
    '//third_party/java/apache/commons-codec',
    '//third_party/java/apache/commons-lang',
    '//third_party/java/guava',
    '//third_party/java/jsr305_annotations',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/collections',
  ],
  srcs = glob(['*.java'], exclude = URL_RESOLVER_SOURCES)
)

java_library(
  name = 'url-resolver',
  deps = [
    '//third_party/java/guava',
    '//third_party/java/jsr305_annotations',
    ':util',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/quantity',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/stats:util',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/util',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/util/caching',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/util:system-mocks',
  ],
  srcs = URL_RESOLVER_SOURCES
)

# TODO(John Sirois): tease apart loadbalancing/monitoring/pool
java_library(
  name = 'pool',
  deps = [
    '//third_party/java/apache/commons-codec',
    '//third_party/java/guava',
    '//third_party/java/jsr305_annotations',
    ':dynamic-host-set',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/quantity',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/stats',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/util',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/util:system-mocks',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/stats:stats-provider',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/util:executor-service-shutdown',
  ],
  srcs = glob(['pool/*.java', 'monitoring/*.java', 'loadbalancing/*.java'],
              exclude = DYNAMIC_HOST_SET_SOURCES)
)
