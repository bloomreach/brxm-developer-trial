# Copyright 2020 Hippo B.V. (http://www.onehippo.com)
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#   http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

FROM maven:3-jdk-8-alpine AS build

ARG MAVEN_USER
ARG MAVEN_PASSWORD
ARG MAVEN_OPTS=-Xmx1024m

COPY settings.xml /usr/share/maven/ref/
COPY app /app
WORKDIR /app

RUN mvn --settings /usr/share/maven/ref/settings.xml -Dmaven.repo.local=/usr/share/maven/ref/repository clean verify \
 && mvn --settings /usr/share/maven/ref/settings.xml -Dmaven.repo.local=/usr/share/maven/ref/repository -P cargo.run cargo:install

FROM maven:3-jdk-8-alpine

WORKDIR /app

COPY --from=build /usr/share/maven/ref /usr/share/maven/ref

VOLUME ["/app"]
EXPOSE 8000 8080

ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh", "sh", "-c", "mvn clean verify && $@", "/dev/stdin"]

CMD ["mvn -P cargo.run"]
