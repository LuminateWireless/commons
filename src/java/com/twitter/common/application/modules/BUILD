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

java_library(
  name = 'applauncher',
  deps = [
    '//third_party/java/guice',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/application:action',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/stats',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/util',
  ],
  srcs = ['AppLauncherModule.java']
)

java_library(
  name = 'lifecycle',
  deps = [
    '//third_party/java/javax/inject',
    '//third_party/java/apache/commons-lang',
    '//third_party/java/guava',
    '//third_party/java/guice',
    '//third_party/java/guice:guice-multibindings',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/application:action',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/net:util',
  ],
  srcs = ['LifecycleModule.java', 'LocalServiceRegistry.java']
)

# TODO(William Farner): Split this up further - HTTP should not require thrift and time-series.
java_library(
  name = 'http',
  deps = [
    '//third_party/java/guice',
    ':lifecycle',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/application:action',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/application/http',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/args',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/net/http',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/net/http/handlers',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/net/http/handlers:time-series',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/net/http/handlers/pprof',
  ],
  srcs = ['HttpModule.java']
)

java_library(
  name = 'log',
  deps = [
    '//third_party/java/guice',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/args',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/logging',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/net/http/handlers',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/stats:time-series',
    ':lifecycle',
  ],
  srcs = ['LogModule.java']
)

java_library(
  name = 'stats',
  deps = [
    '//third_party/java/guice',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/application:action',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/args',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/quantity',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/stats:jvm',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/stats:time-series',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/util',
    ':lifecycle',
  ],
  srcs = ['StatsModule.java']
)

java_library(
  name = 'stats_export',
  deps = [
    '//third_party/java/guava',
    '//third_party/java/guice',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/application:action',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/args',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/quantity',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/stats',
    ':lifecycle',
  ],
  srcs = ['StatsExportModule.java']
)

java_library(
  name = 'thrift',
  deps = [
    '//third_party/java/guice',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/application/http',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/net/http',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/net/http/handlers:thrift',
  ],
  srcs = ['ThriftModule.java']
)
