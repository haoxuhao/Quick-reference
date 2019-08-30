# Notes for python 
- in python: True=1; False=0
- PILֻ.Image 只有在需要的时候才加载像素数据,　如果只需获取图像宽高时可以用这个 
- time.time() 返回浮点秒
- numpy dtype转换需要使用以下方式，否则会导致shape的变化,output=np.float32(input)

- 自定义模块如果有文件夹包含，需要添加__init__.py 文件，该文件可以为空，模块文件需要具有可执行权限

- 使用numpy时注意dtype uint8 是无符号8位数范围为（0，255），运算会导致溢出。特别注意

- numpy.sum(a,axis=(1,2)) #即保持其他维度不变，1，2维度求和

- python 中“\”表示浮点数除法， “\\”表示整数除法，返回不大于结果的最大整数 参考 https://www.cnblogs.com/yymn/p/8084985.html

- range 用法
```python
for i in range(0, 33, 4):
	 print(i,end=",")   
#0, 4, 8, 12, 16, 20, 24, 28, 32
```