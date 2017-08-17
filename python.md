## 零碎
* 使用setup.py安装python模块  
  下载模块包，解压，进入模块文件夹，执行`python setup.py install`
  
* 如果代码中出现中文，需要在文件开头加上中文注释，如果开头不声明保存编码的格式是什么，那么它会默认使用ASKII码保存文件。  
  `#coding=utf-8` 或者 `#coding=gbk`
  
* 如何在引号中引用变量  
  ```
  >>> a = "Frank"
  >>> print("I am " + a + "!")
  I am Frank!
  ```

## DataFrame
* reindex用法
```
>>> index = ['Firefox', 'Chrome', 'Safari', 'IE10', 'Konqueror']
>>> df = pd.DataFrame({
...      'http_status': [200,200,404,404,301],
...      'response_time': [0.04, 0.02, 0.07, 0.08, 1.0]},
...       index=index)
>>> df
           http_status  response_time
Firefox            200           0.04
Chrome             200           0.02
Safari             404           0.07
IE10               404           0.08
Konqueror          301           1.00

>>> new_index= ['Safari', 'Iceweasel', 'Comodo Dragon', 'IE10',
...             'Chrome']
>>> df.reindex(new_index)
               http_status  response_time
Safari               404.0           0.07
Iceweasel              NaN            NaN
Comodo Dragon          NaN            NaN
IE10                 404.0           0.08
Chrome               200.0           0.02

>>> df.reindex(new_index, fill_value=0)
               http_status  response_time
Safari                 404           0.07
Iceweasel                0           0.00
Comodo Dragon            0           0.00
IE10                   404           0.08
Chrome                 200           0.02
```

## numpy
* random.permutation用法
```
>>> np.random.permutation(10)
array([1, 7, 4, 3, 0, 9, 2, 5, 8, 6])
>>> np.random.permutation([1, 4, 9, 12, 15])
array([15,  1,  9,  4, 12])
>>> arr = np.arange(9).reshape((3, 3))
>>> np.random.permutation(arr)
array([[6, 7, 8],
       [0, 1, 2],
       [3, 4, 5]])
```

* `testing.assert_array_almost_equal`用法
> 说明：如果两个对象没有在指定精确度达到相等，则抛出错误异常，否则正常执行，没有任何输出结果
```
>>> np.testing.assert_array_almost_equal([1.0,2.333,np.nan],
                                         [1.0,2.333,np.nan])
                                         
>>> np.testing.assert_array_almost_equal([1.0,2.33333,np.nan],
...                                      [1.0,2.33339,np.nan], decimal=5)
...
<type 'exceptions.AssertionError'>:
AssertionError:
Arrays are not almost equal

(mismatch 50.0%)
 x: array([ 1.     ,  2.33333,      NaN])
 y: array([ 1.     ,  2.33339,      NaN])
>>> np.testing.assert_array_almost_equal([1.0,2.33333,np.nan],
...                                      [1.0,2.33333, 5], decimal=5)
<type 'exceptions.ValueError'>:
ValueError:
Arrays are not almost equal
 x: array([ 1.     ,  2.33333,      NaN])
 y: array([ 1.     ,  2.33333,  5.     ])
```

* `zeros`用法
> 返回一个指定类型和结构的数据，填充值为 0
```
>>> np.zeros(5)
array([ 0.,  0.,  0.,  0.,  0.])

>>> np.zeros((5,), dtype=np.int)
array([0, 0, 0, 0, 0])

>>> np.zeros((2, 1))
array([[ 0.],
       [ 0.]])
       
>>> s = (2,2)
>>> np.zeros(s)
array([[ 0.,  0.],
       [ 0.,  0.]])
```

* `eye`
> 返回一个二维数组，对角线上的值为 1，其他地方为 0
```
>>> np.eye(2, dtype=int)
array([[1, 0],
       [0, 1]])
       
>>> np.eye(3, k=1)  # k 可指定对角线的位置，默认为 0
array([[ 0.,  1.,  0.],
       [ 0.,  0.,  1.],
       [ 0.,  0.,  0.]])
       
>>> np.eye(3)
array([[ 1.,  0.,  0.],
       [ 0.,  1.,  0.],
       [ 0.,  0.,  1.]])
```

* `argmax`
> 返回最大值的索引
```
>>> b = np.arange(6)
>>> b[1] = 5
>>> b
array([0, 5, 2, 3, 4, 5])
>>> np.argmax(b) # Only the first occurrence is returned.
1
```

## `Python`内置函数
* `enumerate()`
1. 描述：enumerate() 函数用于将一个可遍历的数据对象(如列表、元组或字符串)组合为一个索引序列，同时列出数据和数据下标，一般用在 for 循环当中。
2. 用法示例：
```
>>>seasons = ['Spring', 'Summer', 'Fall', 'Winter']
>>> list(enumerate(seasons))
[(0, 'Spring'), (1, 'Summer'), (2, 'Fall'), (3, 'Winter')]

>>> list(enumerate(seasons, start=1))       # 小标从 1 开始
[(1, 'Spring'), (2, 'Summer'), (3, 'Fall'), (4, 'Winter')]

>>>seq = ['one', 'two', 'three']
>>> for i, element in enumerate(seq):
...     print i, seq[i]
... 
0 one
1 two
2 three
```

