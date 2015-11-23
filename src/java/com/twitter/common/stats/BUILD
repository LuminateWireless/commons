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
  name = 'stat',
  deps = [],
  srcs = ['Stat.java'],
)

java_library(
  name = 'stats-provider',
  deps = [
    '//third_party/java/guava',
    ':stat',
  ],
  srcs = [
    'StatsProvider.java',
  ],
)

java_library(
  name = 'stat-registry',
  deps = [
    ':stat',
  ],
  srcs = [
    'RecordingStat.java',
    'StatRegistry.java'
  ],
)

java_library(
  name = 'stats',
  deps = [
    '//third_party/java/guava',
    '//third_party/java/jsr305_annotations',
    ':stat-registry',
    ':stats-provider',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/application:action',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/collections',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/quantity',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/util:sampler',
    ':stat',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/util:system-mocks',
  ],
  srcs = [
    'Elapsed.java',
    'MovingAverage.java',
    'MovingWindowDelta.java',
    'NumericStatExporter.java',
    'Percentile.java',
    'PipelineStats.java',
    'Ratio.java',
    'Rate.java',
    'RecordingStatImpl.java',
    'RequestStats.java',
    'SlidingStats.java',
    'SampledStat.java',
    'StatImpl.java',
    'Stats.java',
  ],
)

java_library(
  name = 'jvm',
  deps = [
    ':stats',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/quantity',
  ],
  srcs = [ 'JvmStats.java' ],
)

java_library(
  name = 'time-series',
  deps = [
    '//third_party/java/guava',
    '//third_party/java/guice',
    ':stat-registry',
    ':stats',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/application:action',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/collections',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/quantity',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/util:system-mocks',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
  ],
  srcs = [
    'TimeSeries.java',
    'TimeSeriesRepository.java',
    'TimeSeriesRepositoryImpl.java',
  ],
)

java_library(
  name = 'util',
  deps = [
    '//third_party/java/guava',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/util:util',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/quantity',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/util:system-mocks',
  ],
  srcs = [
    'ApproximateHistogram.java',
    'CounterMap.java',
    'CounterMapWithTopKey.java',
    'Entropy.java',
    'Histogram.java',
    'Histograms.java',
    'Precision.java',
    'PrintableHistogram.java',
    'ReservoirSampler.java',
    'Significance.java',
    'Statistics.java',
    'StatisticsInterface.java',
    'Windowed.java',
    'WindowedApproxHistogram.java',
    'WindowedHistogram.java',
    'WindowedStatistics.java',
  ],
)
