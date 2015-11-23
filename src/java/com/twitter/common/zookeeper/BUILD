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
  name = 'client',
  deps = [
    '//third_party/java/apache/commons-lang',
    '//third_party/java/guava',
    '//third_party/java/jsr305_annotations',
    '//third_party/zookeeper/src/java:zookeeper',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/net:util',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/quantity',
  ],
  srcs = [ 'ZooKeeperClient.java', 'ZooKeeperUtils.java' ]
)

java_library(
  name = 'node',
  deps = [
    ':client',
    '//third_party/java/guava',
    '//third_party/java/jsr305_annotations',
    '//third_party/zookeeper/src/java:zookeeper',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/collections',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/util',
  ],
  srcs = [ 'ZooKeeperNode.java' ]
)

java_library(
  name = 'map',
  deps = [
    ':client',
    '//third_party/java/guava',
    '//third_party/zookeeper/src/java:zookeeper',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/util',
  ],
  srcs = [ 'ZooKeeperMap.java' ]
)

java_library(
  name = 'lock',
  deps = [
    ':client',
    '//third_party/java/guava',
    '//third_party/java/jsr305_annotations',
    '//third_party/zookeeper/src/java:zookeeper',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
  ],
  srcs = [ 'DistributedLock.java', 'DistributedLockImpl.java' ]
)

java_library(
  name = 'group',
  deps = [
    ':client',
    '//third_party/java/apache/commons-lang',
    '//third_party/java/guava',
    '//third_party/java/jsr305_annotations',
    '//third_party/zookeeper/src/java:zookeeper',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/util',
  ],
  srcs = [ 'Group.java' ]
)

java_library(
  name = 'partitioner',
  deps = [
    '//third_party/java/guava',
    '//third_party/java/jsr305_annotations',
    '//third_party/zookeeper/src/java:zookeeper',
    ':client',
    ':group',
  ],
  srcs = [ 'Partitioner.java' ]
)

java_library(
  name = 'candidate',
  deps = [
    ':client',
    ':group',
    '//third_party/java/jsr305_annotations',
    '//third_party/java/guava',
    '//third_party/zookeeper/src/java:zookeeper',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
  ],
  srcs = [ 'Candidate.java', 'CandidateImpl.java' ]
)

# No-thrift yet
#
# java_library(
#   name = 'server-set',
#   deps = [
#     ':client',
#     ':group',
#     '//third_party/java/gson',
#     '//third_party/java/guava',
#     '//third_party/zookeeper/src/java:zookeeper',
#     '//third_party/java/twitter-commons/src/java/com/twitter/common/args',
#     '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
#     '//third_party/java/twitter-commons/src/java/com/twitter/common/io',
#     '//third_party/java/twitter-commons/src/java/com/twitter/common/io:json',
#     '//third_party/java/twitter-commons/src/java/com/twitter/common/io:thrift',
#     '//third_party/java/twitter-commons/src/java/com/twitter/common/net:dynamic-host-set',
#     '//third_party/java/twitter-commons/src/java/com/twitter/common/util',
#     'src/thrift/com/twitter/thrift',
#   ],
#   srcs = [
#     'CompoundServerSet.java',
#     'ServerSet.java',
#     'ServerSets.java',
#     'ServerSetImpl.java',
#     'StaticServerSet.java',
#   ]
# )

# java_library(
#   name = 'singleton-service',
#   deps = [
#     ':candidate',
#     ':client',
#     ':server-set',
#     '//third_party/java/guava',
#     '//third_party/java/jsr305_annotations',
#     '//third_party/zookeeper/src/java:zookeeper',
#     #'src/thrift/com/twitter/thrift',
#   ],
#   srcs = [ 'SingletonService.java' ]
# )

# TODO(John Sirois): A legacy convenience target - adjust users and remove
java_library(
  name = 'zookeeper',
  exports = [
    ':candidate',
    ':client',
    ':group',
    ':lock',
    ':map',
    ':node',
    ':partitioner',
    # ':server-set',
    # ':singleton-service',
  ]
)

# java_library(
#   name = 'testing',
#   deps = [
#     '//third_party/java/apache/commons-io',
#     '//third_party/java/guava',
#     '//third_party/java/guava:guava-testlib',
#     '//third_party/java/junit',
#     # '3rdparty/jvm/com/google/testing:tl4j',
#     '//third_party/zookeeper/src/java:zookeeper',
#     ':client',
#     '//third_party/java/twitter-commons/src/java/com/twitter/common/application:action',
#     '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
#     '//third_party/java/twitter-commons/src/java/com/twitter/common/collections',
#     '//third_party/java/twitter-commons/src/java/com/twitter/common/io',
#     '//third_party/java/twitter-commons/src/java/com/twitter/common/quantity',
#   ],
#   srcs = glob(['testing/*.java']),
# )
