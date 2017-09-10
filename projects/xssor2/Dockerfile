#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#      http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#
################################################################################

FROM fedora:latest
MAINTAINER xi4okui@gmail.com

RUN dnf -y install git python
RUN cd /opt && git clone https://github.com/evilcos/xssor2
RUN cd /opt/xssor2 && pip install -r requirement.txt

ENV RHOST 127.0.0.1 

EXPOSE 8000

ENTRYPOINT sed -i "s/xssor.io/$RHOST:8000/g" /opt/xssor2/xssor/payload/probe.js && cd /opt/xssor2 && python manage.py runserver 0.0.0.0:8000
