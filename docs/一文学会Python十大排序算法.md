## 一文学会Python十大排序算法

> 本文已在个人Github开源项目：[PythonGuide](https://github.com/hellgoddess/PythonGuide)中收录，其中包含Python各个方向的自学编程路线、面试题集合/面经及系列技术文章等，并且不断收集了上百本著名的计算机书籍pdf版本，会不断的更新与完善开源项目...
>
> 本文作者：海森堡

![image-20210423193028151](https://gitee.com/chushi123/picgo/raw/master/picture/image-20210423193028151.png)

>  关键术语说明

- **稳定** ：如果a原本在b前面，而a=b，排序之后a仍然在b的前面；
- **不稳定** ：如果a原本在b的前面，而a=b，排序之后a可能会出现在b的后面；
- **内排序** ：所有排序操作都在内存中完成；
- **外排序** ：由于数据太大，因此把数据放在磁盘中，而排序通过磁盘和内存的数据传输才能进行；
- **时间复杂度** ： 一个算法执行所耗费的时间。
- **空间复杂度** ：运行完一个程序所需内存的大小。

![](https://gitee.com/chushi123/picgo/raw/master/picture/image-20210423192325972.png)

### 1.冒泡排序（Bubble Sort）

冒泡排序时针对**相邻元素之间**的比较，可以将大的数慢慢“沉底”(数组尾部)

![1](https://gitee.com/chushi123/picgo/raw/master/picture/1.gif)

```python
#-*-coding:utf-8-*-
def bubble_sort(alist):
    """冒泡排序"""
    n = len(alist)
    for j in range(0, n-1):
         count = 0  # 优化排序
         for i in range(0, n-1-j):
             # 班长从头走到尾
             if alist[i] > alist[i+1]:
                 alist[i], alist[i+1] = alist[i+1], alist[i]
                count += 1
         if 0 == count:
             break

if __name__ == '__main__':
    li = [9, 8, 7, 6, 2, 3, 4, 1]
    print(li)
    bubble_sort(li)
    print(li)
```

## 2.选择排序（Selection Sort）

 **选择排序(Selection-sort)** 是一种简单直观的排序算法。它的工作原理：首先在未排序序列中找到最小（大）元素，存放到排序序列的起始位置，然后，再从剩余未排序元素中继续寻找最小（大）元素，然后放到已排序序列的末尾。以此类推，直到所有元素均排序完毕。

![](https://gitee.com/chushi123/picgo/raw/master/picture/849589-20171015224719590-1433219824.gif)

```python
#-*-coding:utf-8-*-
def select_sort(alist):
    """ιζ©ζεΊ"""
    n = len(alist)
    for j in range(n-1):
        min_index = j
        for i in range(j+1, n):
            if alist[min_index] > alist[i]:
                min_index = i
        alist[j], alist[min_index] = alist[min_index], alist[j]
```

## 3.插入排序（Insertion Sort）

 **插入排序（Insertion-Sort）** 的算法描述是一种简单直观的排序算法。它的工作原理是通过构建有序序列，对于未排序数据，在已排序序列中从后向前扫描，找到相应位置并插入。插入排序在实现上，通常采用in-place排序（即只需用到O(1)的额外空间的排序），因而在从后向前扫描过程中，需要反复把已排序元素逐步向后挪位，为最新元素提供插入空间。

![](https://gitee.com/chushi123/picgo/raw/master/picture/3.gif)

```python
#-*-coding:utf-8-*-
def insertSort(relist):
    len_ = len(relist)
    for i in range(1, len_):
        for j in range(i):
            if relist[i] < relist[j]:
                relist.insert(j,relist[i])
                relist.pop(i+1)
                break
    return relist

a = [9,8,7,6,5,4,3,2,1]
print(insertSort(a))
```

## 4.希尔排序（Shell Sort）

**希尔排序是希尔（Donald Shell）** 于1959年提出的一种排序算法。希尔排序也是一种插入排序，它是简单插入排序经过改进之后的一个更高效的版本，也称为缩小增量排序，同时该算法是冲破O(n2）的第一批算法之一。它与插入排序的不同之处在于，它会优先比较距离较远的元素。希尔排序又叫缩小增量排序。

  希尔排序是把记录按下表的一定增量分组，对每组使用直接插入排序算法排序；随着增量逐渐减少，每组包含的关键词越来越多，当增量减至1时，整个文件恰被分成一组，算法便终止。

![](https://gitee.com/chushi123/picgo/raw/master/picture/image-20210423221737356.png)

```python
def shell_sort(nums):
    n = len(nums)
    gap = n // 2
    while gap:
        for i in range(gap, n):
            while i - gap >= 0 and nums[i - gap] > nums[i]:
                nums[i - gap], nums[i] = nums[i], nums[i - gap]
                i -= gap
        gap //= 2
    return nums

```



## 5. 归并排序（Merge Sort）

 **归并排序** 是建立在归并操作上的一种有效的排序算法。该算法是采用分治法（Divide and Conquer）的一个非常典型的应用。归并排序是一种稳定的排序方法。将已有序的子序列合并，得到完全有序的序列；即先使每个子序列有序，再使子序列段间有序。若将两个有序表合并成一个有序表，称为2-路归并。

![](https://gitee.com/chushi123/picgo/raw/master/picture/5.gif)

```python
#-*-coding:utf-8-*-
def merge(left, right):
    result = []
    while left and right:
        result.append(left.pop(0) if left[0] <= right[0] else right.pop(0))
    while left:
        result.append(left.pop(0))
    while right:
        result.append(right.pop(0))
    return result

def mergeSort(relist):
    if len(relist) <= 1:
        return relist
    mid_index = len(relist)//2
    left = mergeSort(relist[:mid_index])
    right = mergeSort(relist[mid_index:])
    return merge(left, right)

print(mergeSort([9,8,7,6,5,4]))
```

## 6.快速排序

  **快速排序** 的基本思想：通过一趟排序将待排记录分隔成独立的两部分，其中一部分记录的关键字均比另一部分的关键字小，则可分别对这两部分记录继续进行排序，以达到整个序列有序。

![](https://gitee.com/chushi123/picgo/raw/master/picture/6.gif)

一

```python
#-*-coding:utf-8-*-
def quick_sort(alist, first, last):
    """快速排序"""
    if first >= last:
        return
    mid_value = alist[first]
    low = first
    high = last
    while low < high:
        while low < high and alist[high] >= mid_value:
            high -= 1
        alist[low] = alist[high]

        while low < high and alist[low] < mid_value:
            low += 1
        alist[high] = alist[low]
    # 从循环退出时，low == high
    alist[low] = mid_value
    # 对low左边的列表执行快速排序
    quick_sort(alist, first, low-1)
    # 对low右边的列表执行快速排序
    quick_sort(alist, low+1, last)


if __name__ == '__main__':
    li = [0, 6, 7, 9, 8, 6, 2, 3, 1, 4, 5]
    print(li)
    quick_sort(li, 0, len(li)-1)
    print(li)
```

二：

```python
#-*-coding:utf-8-*-
def quick_sort(nums):
    if not nums:
        return []
    div = nums[0]
    left = quick_sort([l for l in nums[1:] if l <= div])
    right = quick_sort([r for r in nums[1:] if r > div])
    return left + [div] + right
```

## 7.堆排序（Heap Sort）

  **堆排序（Heapsort）** 是指利用堆这种数据结构所设计的一种排序算法。堆积是一个近似完全二叉树的结构，并同时满足堆积的性质：即子结点的键值或索引总是小于（或者大于）它的父节点。

![7.2](https://gitee.com/chushi123/picgo/raw/master/picture/7.2.gif)

```python
def heap_sort(nums):
    # 调整堆
    # 迭代写法
    def adjust_heap(nums, startpos, endpos):
        newitem = nums[startpos]
        pos = startpos
        childpos = pos * 2 + 1
        while childpos < endpos:
            rightpos = childpos + 1
            if rightpos < endpos and nums[rightpos] >= nums[childpos]:
                childpos = rightpos
            if newitem < nums[childpos]:
                nums[pos] = nums[childpos]
                pos = childpos
                childpos = pos * 2 + 1
            else:
                break
        nums[pos] = newitem
    
    # 递归写法
    def adjust_heap(nums, startpos, endpos):
        pos = startpos
        chilidpos = pos * 2 + 1
        if chilidpos < endpos:
            rightpos = chilidpos + 1
            if rightpos < endpos and nums[rightpos] > nums[chilidpos]:
                chilidpos = rightpos
            if nums[chilidpos] > nums[pos]:
                nums[pos], nums[chilidpos] = nums[chilidpos], nums[pos]
                adjust_heap(nums, pos, endpos)

    n = len(nums)
    # 建堆
    for i in reversed(range(n // 2)):
        adjust_heap(nums, i, n)
    # 调整堆
    for i in range(n - 1, -1, -1):
        nums[0], nums[i] = nums[i], nums[0]
        adjust_heap(nums, 0, i)
    return nums

```

## 8.计数排序（Counting Sort）

 **计数排序** 的核心在于将输入的数据值转化为键存储在额外开辟的数组空间中。 作为一种线性时间复杂度的排序，计数排序要求输入的数据必须是有确定范围的整数。

![](https://gitee.com/chushi123/picgo/raw/master/picture/8.gif)

```python
def counting_sort(nums):
    if not nums: return []
    n = len(nums)
    _min = min(nums)
    _max = max(nums)
    tmp_arr = [0] * (_max - _min + 1)
    for num in nums:
        tmp_arr[num - _min] += 1
    j = 0
    for i in range(n):
        while tmp_arr[j] == 0:
            j += 1
        nums[i] = j + _min
        tmp_arr[j] -= 1
    return nums

```

## 9.桶排序（Bucket Sort）

桶排序是计数排序的升级版，原理是：输入数据服从均匀分布的，将数据分到有限数量的桶里，每个桶再分别排序（有可能再使用别的算法或是以递归方式继续使用桶排序，此文编码采用递归方式）

算法描述：

人为设置一个桶的BucketSize，作为每个桶放置多少个不同数值（意思就是BucketSize = 5，可以放5个不同数字比如[1, 2, 3,4,5]也可以放 100000个3，只是表示该桶能存几个不同的数值）
遍历待排序数据，并且把数据一个一个放到对应的桶里去
对每个不是桶进行排序，可以使用其他排序方法，也递归排序
不是空的桶里数据拼接起来

```python
def bucket_sort(nums, bucketSize):
    if len(nums) < 2:
        return nums
    _min = min(nums)
    _max = max(nums)
    # 需要桶个数
    bucketNum = (_max - _min) // bucketSize + 1
    buckets = [[] for _ in range(bucketNum)]
    for num in nums:
        # 放入相应的桶中
        buckets[(num - _min) // bucketSize].append(num)
    res = []

    for bucket in buckets:
        if not bucket: continue
        if bucketSize == 1:
            res.extend(bucket)
        else:
            # 当都装在一个桶里,说明桶容量大了
            if bucketNum == 1:
                bucketSize -= 1
            res.extend(bucket_sort(bucket, bucketSize))
    return res

```

## 10.基数排序（Radix Sort）

  **基数排序**也是非比较的排序算法，对每一位进行排序，从最低位开始排序，复杂度为O(kn),为数组长度，k为数组中的数的最大的位数；

  **基数排序**是按照低位先排序，然后收集；再按照高位排序，然后再收集；依次类推，直到最高位。有时候有些属性是有优先级顺序的，先按低优先级排序，再按高优先级排序。最后的次序就是高优先级高的在前，高优先级相同的低优先级高的在前。基数排序基于分别排序，分别收集，所以是稳定的。

![](https://gitee.com/chushi123/picgo/raw/master/picture/10.gif)

```python
def Radix_sort(nums):
    if not nums: return []
    _max = max(nums)
    # 最大位数
    maxDigit = len(str(_max))
    bucketList = [[] for _ in range(10)]
    # 从低位开始排序
    div, mod = 1, 10
    for i in range(maxDigit):
        for num in nums:
            bucketList[num % mod // div].append(num)
        div *= 10
        mod *= 10
        idx = 0
        for j in range(10):
            for item in bucketList[j]:
                nums[idx] = item
                idx += 1
            bucketList[j] = []
    return nums

```

参考文章：https://blog.csdn.net/MobiusStrip/article/details/83785159?depth_1-utm_source=distribute.pc_relevant.none-task&utm_source=distribute.pc_relevant.none-task

