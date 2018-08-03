```
import numpy as np
from matplotlib import pyplot as plt




#指数平滑公式
def exponential_smoothing(alpha,s):
    s2=np.zeros(s.shape)       #s.shape定义返回数组的形状   输入参数：类似数组(比如列表，元组等)或是数组  
                            #返回：一个整形数字的元组。元组中的每个元素表示相应的数组的每一维的长度
    #zeros(shape,dtype=float,order='C')  
    #返回：返回一个给定形状和类型的用0填充的数组   order可选参数  c代表行优先，f代表列优先
    #print(s2)
    s2[0]=s[0]
    for i in range(1,len(s2)):
        s2[i]=alpha*s[i]+(1-alpha)*s2[i-1]
    return s2




#绘制曲线
def show_data(new_year,pre_year,data,s_pre_single,s_pre_double,s_pre_triple):
    year,time_id,number=data.T
    plt.figure(figsize=(14,6),dpi=80)    #设置绘图区域的大小和像素
    plt.plot(year,number,color='yellow',label='actual value')    #将实际值的折线设置为黄色
    plt.plot(new_year[1:],s_pre_single[2:],color='red',label='single prediction value')    #将一次指数平滑法计算的预测值的折线设置为红色
    plt.plot(new_year[1:],s_pre_double[2:],color='blue',label='double prediction value')   #将二次指数平滑法计算的预测值的折线设置为蓝色
    plt.plot(new_year[1:],s_pre_triple[2:],color='green',label='triple prediction value')   #将三次指数平滑法计算的预测值的折线设置为绿色
    plt.legend(loc='lower right')    #显示图例的位置，这里为右下方
    plt.title('Projects')
    plt.xlabel('year')    #x轴标签
    plt.ylabel('number')   #     y轴标签
    plt.xticks(new_year)       #设置x轴的刻度线为new_year
    plt.show()
    
    
    
    
def main():
    alpha=0.7     #设置alpha,即平滑系数
    pre_year=np.array([2016,2017])     #将需要预测的两年存入numpy的array对象里
    data=np.loadtxt('C:\\Users\\Desktop\\es.txt',delimiter=',',dtype=float)    #用numpy读取数据
    year,time_id,number=data.T     #将数据分别赋值给YEAR,TIME_ID,NUMBER
    initial_line=np.array([1993,0,number[0]])     #初始化  由于平滑指数是根据上一期的数值进行预测的，
    #原始数据中的最早数据为1994，没有1993年的数据，这里定义1993年的数据和1994年数据相同
    #print(initial_line)
    initial_data=np.insert(data,0,values=initial_line,axis=0)     #插入初始化数据
    #print(initial_data)
    #print(len(initial_data))
    initial_year,initial_time_id,initial_number=initial_data.T     #插入初始化年  
    #print(initial_number)
    #一次指数平滑
    #print(initial_time_id)
    s_single=exponential_smoothing(alpha,initial_number)    #计算一次指数平滑
    #print('一次指数平滑预测值为'+str(s_single))
    #print(len(s_single))
    #print(len(initial_time_id))
    a_single=initial_number    #真实值
    b_single=s_single           #预测值
    s_pre_single=np.zeros(s_single.shape)    #建立预测轴
    for i in range(1,len(initial_time_id)):
        s_pre_single[i]=(alpha)*a_single[i]+(1-alpha)*b_single[i-1]    #循环计算每一年的一次指数平滑法的预测值
        #print(s_pre_single[i])
        #print(a_single[i])
        #print(b_single[i])
        
    pre_next_year=(alpha)*a_single[-1]+(1-alpha)*b_single[-1]    #预测下一年
    pre_next_two_year = (alpha)*a_single[-1]+(1-alpha)*b_single[-1]   #预测下两年#一次指数平滑只能预测一个，所以为了画图便于展示，令2017年的预测值和2016年的预测值相等
    #print(len(s_pre_single))
    
    s_pre_single=np.insert(s_pre_single,len(s_pre_single),values=np.array([pre_next_year,pre_next_two_year]), axis=0)   #组合预测值
    #print(s_pre_single)
    #print(len(s_pre_single))
    
    
    
    for i in range(0,len(s_single)):
        MSE1=0
        MSE1=(int(initial_number[i])-int(s_single[i]))**2+MSE1
        MSE1=(MSE1)/int(len(initial_time_id))     #计算均方误差
        #print(MSE1)
        
    print ('一次指数平滑的第一个预测值为:'+str(pre_next_year)+'   '+'一次指数平滑的第二个预测值为'+str(pre_next_two_year)+'    '+'一次指数平滑的均方误差为:'+str(MSE1))
    
    #二次指数平滑
    #print(initial_time_id)
    s_double=exponential_smoothing(alpha, s_single)   #计算二次指数平滑   #二次平滑指数是在一次指数平滑的基础上进行的，三次指数平滑以此类推
    #print(s_double)
    #print(len(s_double))
    a_double = 2*s_single-s_double     #计算二次指数平滑的a
    b_double = (alpha/(1-alpha))*(s_single-s_double)     #计算二次指数平滑的b
    s_pre_double = np.zeros(s_double.shape)    #建立预测轴
    for i in range(1, len(initial_time_id)):
        s_pre_double[i] = a_double[i-1]+b_double[i-1]   #循环计算每一年的二次指数平滑法的预测值，#下面三次指数平滑法原理相同
        #print(s_pre_double[i])
        #print(a_double[i-1])
        #print(b_double[i-1])
        
        
    pre_next_year=a_double[-1]+b_double[-1]*1    #预测下一年
    pre_next_two_year = a_double[-1]+b_double[-1]*2   #预测下两年
    s_pre_double = np.insert(s_pre_double, len(s_pre_double), values=np.array([pre_next_year, pre_next_two_year]), axis=0)    #组合预测值
    #print(s_pre_double)
    #print(len(s_pre_double))
    for i in range(0, len(s_double)):
       MSE2 = 0
       MSE2 = (int(initial_number[i]) - int(s_double[i])) ** 2 + MSE2
      # print(info_data_sales[i][j], S1_1[i][j])
       MSE2 = (MSE2) / int(len(initial_time_id))  ##得到均方误差
       #print (MSE2)
    print ('二次指数平滑的第一个预测值为:'+str(pre_next_year)+'   '+'二次指数平滑的第二个预测值为'+str(pre_next_two_year)+'    '+'二次指数平滑的均方误差为:'+str(MSE2))
    
    
    #三次指数平滑
    #print(initial_time_id)
    s_triple = exponential_smoothing(alpha, s_double)


    a_triple = 3*s_single-3*s_double+s_triple
    b_triple = (alpha/(2*((1-alpha)**2)))*((6-5*alpha)*s_single -2*((5-4*alpha)*s_double)+(4-3*alpha)*s_triple)
    c_triple = ((alpha**2)/(2*((1-alpha)**2)))*(s_single-2*s_double+s_triple)


    s_pre_triple = np.zeros(s_triple.shape)       #建立预测轴


    for i in range(1, len(initial_time_id)):
        s_pre_triple[i] = a_triple[i-1]+b_triple[i-1]*1 + c_triple[i-1]*(1**2)
        #print(s_pre_triple[i])


    pre_next_year = a_triple[-1]+b_triple[-1]*1 + c_triple[-1]*(1**2)      #预测下一年
    pre_next_two_year = a_triple[-1]+b_triple[-1]*2 + c_triple[-1]*(2**2)       #预测下两年
    s_pre_triple = np.insert(s_pre_triple, len(s_pre_triple), values=np.array([pre_next_year, pre_next_two_year]), axis=0)      #组合预测值
    #print(s_pre_triple)
    #print(len(s_pre_triple))
    for i in range(0, len(s_triple)):
       MSE3 = 0
       MSE3 = (int(initial_number[i]) - int(s_triple[i])) ** 2 + MSE3
      # print(info_data_sales[i][j], S1_1[i][j])
       MSE3 = (MSE3) / int(len(initial_time_id))       ##得到均方误差
       #print(MSE3)
    print ('三次指数平滑的第一个预测值为:'+str(pre_next_year)+'      '+'三次指数平滑的第二个预测值为'+str(pre_next_two_year)+'     '+'三次指数平滑的均方误差为:'+str(MSE3))
    new_year = np.insert(year, len(year), values=pre_year, axis=0)
    #print(len(year))
    #print(pre_year)
    #print(new_year)
    output = np.array([new_year, s_pre_single,s_pre_double, s_pre_triple])
    print(output)
    show_data(new_year, pre_year, data,s_pre_single,s_pre_double, s_pre_triple)#传入预测值和数据
    
if __name__ == '__main__':
    main()
```
