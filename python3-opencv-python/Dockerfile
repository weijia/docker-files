FROM python:3.7


RUN pip install tensorflow
RUN pip install numpy
RUN pip install scipy
RUN pip install opencv-python
RUN pip install pillow
RUN pip install matplotlib
RUN pip install h5py
RUN pip install keras
RUN pip install https://github.com/OlafenwaMoses/ImageAI/releases/download/2.0.1/imageai-2.0.1-py3-none-any.whl

WORKDIR /usr/src/app
RUN git clone https://github.com/weijia/django-dev-server.git


WORKDIR /usr/src/app/django-dev-server
RUN pip install -r requirements-python3.txt -i http://pypi.douban.com/simple/ --trusted-host pypi.douban.com


RUN echo 'ALLOWED_HOSTS = ["*"]' >> local/local_settings/allowed_hosts.py

EXPOSE 8000
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]





