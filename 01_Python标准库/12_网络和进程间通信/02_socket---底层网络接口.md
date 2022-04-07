:# socket --- 底层网络接口
## TCP客户端程序开发流程
- TCP网络应用程序开发分为
	- TCP客户端程序开发
	- TCP服务端程序开发
- 提示
	- 客户端程序是指运行在用户设备上的程序
	- 服务端程序是指运行在服务器设备上的程序，专门为客户端提供数据服务

### TCP客户端程序开发流程介绍
1. 创建客户端套接字对象（买电话）
2. 和服务端套接字建立连接（打电话）
3. 发送数据（说话）
4. 接收数据（接听）
5. 关闭客户端套接字（挂电话)

![image](https://user-images.githubusercontent.com/12490550/162151088-bb03f23b-0ad1-41b5-b764-35621c39d605.png)

## socket类的介绍
```
导入socket模块
import socket
创建客户端socket对象使用socket类
socket.socket(AddressFamily, Type)
```
客户端socket类的参数和方法说明:

|参数名|说明|
|---|---|
|AddressFamily|IP地址类型, 分为TPv4和IPv6|
|Type|传输协议类型|

### 开发客户端使用到的函数

|方法名|说明|
|---|---|
|connect|和服务端套接字建立连接|
|send|发送数据|
|recv|接收数据|
|close|关闭连接|

### 创建TCP客户端套接字
```
# 创建udp的套接
# AF_INET: ipv4地址类
# SOCK_STREAM: TCP传输协议类
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
# ...这里是使用套接字的功能（省略）...
# 不用的时候，关闭套接
s.close()

```
### TCP客户端程序发送消息
```
import socket
# 创建tcp socket
tcp_client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
# 目的信息
server_ip = input(“请输入服务器ip:”)
server_port = int(input(“请输入服务器port:”))
# 连接服务器套接字
tcp_client_socket.connect((server_ip, server_port))
# 提示用户输入数据
send_data = input(“请输入要发送的数据：”)
tcp_client_socket.send(send_data.encode(”utf-8“))
# 注意：如果是windows的网络调试助手使用gbk编
# 关闭套接字
tcp_client_socket.close()
```
### TCP客户端程序接收消息
```
import socke
# 创建tcp socket
tcp_client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
server_ip = input("请输入服务器ip:")
server_port = int(input("请输入服务器port:"))
# 连接服务器套接字
tcp_client_socket.connect((server_ip, server_port))
send_data = input("请输入要发送的数据：")
tcp_client_socket.send(send_data.encode(”utf-8"))
# 接收对方发送过来的数据，最大接收1024个字节
recvData = tcp_client_socket.recv(1024)
print('接收到的数据为:', recvData.decode(’utf-8'))
# 关闭套接字
tcp_client_socket.close()
```
### TCP服务端程序开发流程介绍
1. 创建服务端端套接字对象 
2. 绑定IP地址和端口号
3. 设置监听
4. 等待接受客户端的连接请求
5. 接收数据
6. 发送数据
7. 关闭套接字

![image](https://user-images.githubusercontent.com/12490550/162151088-bb03f23b-0ad1-41b5-b764-35621c39d605.png)

## socket类的介绍
```
导入socket模块
import socket
创建客户端socket对象使用socket类
socket.socket(AddressFamily, Type)
```
客户端socket类的参数和方法说明:

|参数名|说明|
|---|---|
|AddressFamily|IP地址类型, 分为TPv4和IPv6|
|Type|传输协议类型|

### 开发服务端使用到的函数

|方法名|说明|
|---|---|
|bind|绑定IP地址和端口号|
|listen|设置监听|
|accept|等待接受客户端的连接请求|
|send|发送数据|
|recv|接收数据|

### TCP服务端程序接收消息
```
import socket
# 创建socket
tcp_server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
# 设置端口号复用，让程序退出端口号立即释放
tcp_server_socket.setsockopt(socket.SOL_SOCKET, socket.SO_REUSEADDR, True) 
tcp_server_socket.bind((‘’, 7788)) 
#绑定IP地址和端口号
# 设置监听
tcp_server_socket.listen(128)
# 128:表示最大等待连接数
# 如果有新的客户端来连接服务端，那么就产生一个新的套接字专门为这个客户端服务
client_socket, clientAddr = tcp_server_socket.accept()
recv_data = client_socket.recv(1024)  
# 接收1024个字节
print(‘接收到的数据为:’, recv_data.decode(‘utf-8’))
client_socket.close()
# 关闭为这个服务与客户端的套接字
tcp_server_socket.close()
# 关闭为这个服务端套接字
```


