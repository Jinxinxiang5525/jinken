torch 与 numpy 对比

两者相互转换：

           np_data=np.arange(6).reshape((2,3))    #用numpy创建一个矩阵
           
           torch_data=torch.from_numpy(np_data)   #numpy 2 torch
           
           tensor2array = torch_data.numpy()      #torch 2 numpy
      
--------------------------------------------------------------------------      
           
#利用函数，例如abs，mean

data=[-1,-2,1,2]

tensor = torch.FloatTensor(data) 

print(

    '\nabs',
    
    '\nnumpy:',np.abs(data),
    
    '\ntorch:',torch.abs(tensor)   #torch.abs()括号中得是tensor，不能直接用data
    
)

-----------------------------------------------------

a=torch.tensor([1.,2,3,4],requires_grad=True)  ->返回梯度值，如果为False，则后续a.grad不能执行

b=torch.tensor([1.,2,3,4],requires_grad=False)

c=torch.sum(a*2)

c.backward()   ->返回偏导值，逐次累加到a.grad中

print(a.grad)  ->tensor([2.,2.,2.,2.])

d=torch.mean(a)

d.backward()

print(a.grad)  ->tensor([2.2500,2.2500,2.2500,2.2500])

e=torch.mean(a*2)

e.backward()

print(a.grad)  ->tensor([2.7500,2.7500,2.7500,2.7500])

---------------------------------------------------------
激励函数

![image](https://github.com/Jinxinxiang5525/jinken/blob/main/%E6%BF%80%E5%8A%B1%E5%87%BD%E6%95%B0.png)
