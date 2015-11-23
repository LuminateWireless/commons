package(default_visibility = ['//visibility:public'])
licenses(['notice'])

java_library(
  name = 'http',
  deps = [
    '//third_party/java/guava',
    '//third_party/java/guice',
    '//third_party/java/guice:guice-servlet',
    '//third_party/java/jetty',
    '//third_party/java/jsr305_annotations',
    '//third_party/java/servlet-api',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/base',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/net/http/handlers:text',
    '//third_party/java/twitter-commons/src/java/com/twitter/common/util:system-mocks',
  ],
  srcs = glob(
    ['*.java'],
    exclude=[
      'JettyHttpServerDispatch.java',
      'RequestLogger.java',
    ]
  )
)
