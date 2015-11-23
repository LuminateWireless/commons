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

TEXT_SOURCES = ['TextResponseHandler.java']

STRING_TEMPLATE_SOURCES = ['StringTemplateServlet.java']

THRIFT_SOURCES = ['ThriftServlet.java']

TIME_SERIES_SOURCES = ['TimeSeriesDataSource.java']

PARAMS_SOURCES = ['HttpServletRequestParams.java']

java_library(
  name='text',
  deps=[
    '//third_party/java/servlet-api',
  ],
  srcs=TEXT_SOURCES
)

java_library(
  name='string-template',
  deps=[
    '//third_party/java/guava',
    '//third_party/java/guice',
    '//third_party/java/servlet-api',
    '//third_party/java/stringtemplate',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/util/templating',
  ],
  srcs=STRING_TEMPLATE_SOURCES
)

java_library(
  name='handlers',
  deps=[
    '//third_party/java/apache/commons-codec',
    '//third_party/java/gson',
    '//third_party/java/guava',
    '//third_party/java/guice',
    '//third_party/java/servlet-api',
    '//third_party/java/stringtemplate',
    '//third_party/java/apache/commons-lang',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/stats:stat',
    ':params',
    ':string-template',
    ':text',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/quantity',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/stats',
  ],
  srcs=glob(['*.java'],
            exclude=TEXT_SOURCES +
            STRING_TEMPLATE_SOURCES +
            THRIFT_SOURCES +
            TIME_SERIES_SOURCES +
            PARAMS_SOURCES),
  resources=[
    #'src/resources/com/twitter/common/net/http/handlers:log'
  ]
)

# java_library(
#   name='thrift',
#   deps=[
#     '//third_party/java/guava',
#     '//third_party/java/guice',
#     '//third_party/java/servlet-api',
#     '//third_party/java/stringtemplate',
#     '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
#     # TODO(John Sirois): the only need is for the non-existent thrift:monitoring
#     '//third_party/java/twitter-commons/src/java/com/twitter/common/thrift',
#     ':string-template',
#   ],
#   srcs=THRIFT_SOURCES,
#   resources=[
#     'src/resources/com/twitter/common/net/http/handlers:thrift'
#   ]
# )

java_library(
  name='time-series',
  deps=[
    '//third_party/java/gson',
    '//third_party/java/guava',
    '//third_party/java/guice',
    '//third_party/java/servlet-api',
    '//third_party/java/jsr305_annotations',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/collections',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/stats:time-series',
  ],
  srcs=TIME_SERIES_SOURCES
)

java_library(
  name='params',
  deps=[
    '//third_party/java/guava',
    '//third_party/java/guice',
    '//third_party/java/jsr305_annotations',
    '//third_party/java/servlet-api',
  ],
  srcs=PARAMS_SOURCES
)
