#Virtualenv 

�ܹ���������ͬ�汾�� Python ��װ��ÿһ�������ڸ��Ե���Ŀ�� ��ʵ���ϲ�û�а�װ������ Python ������ֻ���ṩ��һ�ַ�ʽʹ�û������ֶ����������Ǽ�ʶ�� virtualenv ��ô�����ġ�

������� Mac OS X �� Linux�£���������������ܻ�����:
'''
$ sudo easy_install virtualenv
'''
�˴�����ͼƬ������

���߸��õ�:
'''
$ sudo pip install -i http://mirrors.aliyuncs.com/pypi/simple virtualenv
'''
����������������ϵͳ�а�װ virtualenv�����������ܻ�����ڰ��������С������ʹ�� Ubuntu ���볢��:
'''
$ sudo apt-get install python-virtualenv
'''
������� Windows �²���û�а�װ easy_install ��������ȱ��밲װ easy_install �� Ҫ���ȡ����İ�װ��Ϣ����鿴 Windows �µ� pip �� distribute ��һ����װ�� easy_install �� �����������������Ҫȥ�� sudo ǰ׺��

һ���ɹ���װ virtualenv������ shell �����Լ��Ļ�������ͨ���ᴴ��һ����Ŀ�ļ���myproject�����´��� venv �ļ��У����ļ��о���һ������� Python ����:
'''
$ mkdir myproject
$ cd myproject
$ virtualenv venv
New python executable in venv/bin/python
Installing distribute............done.
'''
���ڣ�ֻҪ����Ҫ��ĳ����Ŀ�Ϲ�����ֻҪ������Ӧ�Ļ������� OS X �� Linux �£���������:
'''
$ . venv/bin/activate
'''
������Ǹ� Windows �û����������������Ϊ���׼��:
'''
$ venv\scripts\activate
'''
�������ַ�ʽ���������ܹ�ʹ����� virtualenv (ע����� shell ��ʾ����ʾ���ǻ�Ļ���)��

������ֻ��Ҫ�������µ�������������� virtualenv �е� flask:
'''
$ pip install -i http://mirrors.aliyuncs.com/pypi/simple flask
'''
�����һ�о�Ϊ��׼��������

#ȫ�ְ�װ

�������װ����Ҳ�ǿ��еģ������Ҳ��Ƽ���ֻ��Ҫ�� root Ȩ������ pip:
'''
$ sudo pip install -i http://mirrors.aliyuncs.com/pypi/simple flask
'''
(�� Windows ϵͳ�ϣ��ڹ���ԱȨ�޵�������ʾ�������������������Ҫ sudo��)

#�������µ� Flask (Living on the Edge)

�������Ҫ�����°�� Flask �ɻ���������ַ�ʽ�������ʹ�� pip ��ȡ�����汾�� ����������һ�� git checkout���������ַ�ʽ����Ȼ�Ƽ�ʹ�� virtualenv��

��һ���µ� virtualenv �ϻ�ȡһ�� git checkout���ڿ���ģʽ������:
'''
$ git clone https://github.com/shiyanlou/flask
Initialized empty Git repository in ~/dev/flask/.git/
$ cd flask
$ virtualenv venv --distribute
New python executable in venv/bin/python
Installing distribute............done.
$ . venv/bin/activate
$ python setup.py develop
...
Finished processing dependencies for Flask
'''
�����ȡ������ϵ������ git head ��Ϊ virtualenv �еĵ�ǰ�汾��Ȼ����ֻ��Ҫִ�� git pull origin �����������°汾��

û�� git �»�ȡ���µĿ����汾����Ҫ������:
'''
$ mkdir flask
$ cd flask
$ virtualenv venv --distribute
$ . venv/bin/activate
New python executable in venv/bin/python
Installing distribute............done.
$ pip install -i http://mirrors.aliyuncs.com/pypi/simple Flask==dev
...
Finished processing dependencies for Flask==dev
'''