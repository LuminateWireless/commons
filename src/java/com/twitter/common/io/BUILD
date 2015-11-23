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
  name = 'io',
  deps = [
    '//third_party/java/apache/commons-io',
    '//third_party/java/apache/commons-lang',
    '//third_party/java/guava',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
  ],
  srcs = [
    'Codec.java',
    'CompatibilityCodec.java',
    'FileUtils.java'
  ]
)

java_library(
  name = 'base64zlibcodec',
  deps = [
    '//third_party/java/apache/commons-codec',
    '//third_party/java/apache/commons-lang',
    '//third_party/java/gson',
    '//third_party/java/guava',
  ],
  srcs = ["Base64ZlibCodec.java"]
)

java_library(
  name = 'streamer',
  deps = [
    '//third_party/java/guava',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
  ],
  srcs = [ 'Streamer.java' ]
)

# java_library(
#   name = 'thrift',
#   deps = [
#     '//third_party/java/guava',
#     '//third_party/thrift',
#     '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
#     ':io',
#   ],
#   srcs = [ 'ThriftCodec.java' ]
# )

java_library(
  name = 'json',
  deps = [
    '//third_party/java/gson',
    '//third_party/java/guava',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
    ':io',
  ],
  srcs = [ 'JsonCodec.java' ]
)
