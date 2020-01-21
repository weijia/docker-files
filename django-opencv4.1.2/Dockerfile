FROM weijia/opencv:ubuntu16.04-opencv4.1.2



RUN sudo apt-get update
RUN sudo apt-get install -y software-properties-common
RUN sudo add-apt-repository ppa:deadsnakes/ppa
RUN sudo apt-get update
RUN sudo apt-get install -y python3.7
RUN sudo apt-get install -y python3-pip
RUN pip3 install --upgrade pip

RUN pip3 install tensorflow -i http://pypi.douban.com/simple/ --trusted-host pypi.douban.com
RUN pip3 install numpy -i http://pypi.douban.com/simple/ --trusted-host pypi.douban.com
RUN pip3 install scipy -i http://pypi.douban.com/simple/ --trusted-host pypi.douban.com
RUN pip3 install opencv-python -i http://pypi.douban.com/simple/ --trusted-host pypi.douban.com
RUN pip3 install pillow -i http://pypi.douban.com/simple/ --trusted-host pypi.douban.com

RUN pip3 install matplotlib==3.0 -i http://pypi.douban.com/simple/ --trusted-host pypi.douban.com
RUN pip3 install h5py -i http://pypi.douban.com/simple/ --trusted-host pypi.douban.com
RUN pip3 install keras -i http://pypi.douban.com/simple/ --trusted-host pypi.douban.com
RUN pip3 install https://github.com/OlafenwaMoses/ImageAI/releases/download/2.0.1/imageai-2.0.1-py3-none-any.whl


WORKDIR /usr/src/app
RUN git clone https://github.com/weijia/django-dev-server.git


WORKDIR /usr/src/app/django-dev-server
RUN pip install zipp==1.0.0 -i http://pypi.douban.com/simple/ --trusted-host pypi.douban.com
RUN pip install -r requirements-python3.txt -i http://pypi.douban.com/simple/ --trusted-host pypi.douban.com


RUN echo 'ALLOWED_HOSTS = ["*"]' >> local/local_settings/allowed_hosts.py
RUN python3 manage.py migrate
RUN python3 manage.py create_default_super_user

EXPOSE 8000
CMD ["python3", "manage.py", "runserver", "0.0.0.0:8000"]





