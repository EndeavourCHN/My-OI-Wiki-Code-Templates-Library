# 二分查找 (Binary Search)

### 基本思想

在**已排序**的序列中，通过不断缩小搜索范围来快速定位目标元素：
1. 维护搜索区间 `[left, right]`
2. 每次取中间元素 `mid` 与目标比较
3. 根据比较结果收缩左边界或右边界

### 实现

```cpp
int l = 1, r = n + 1;
while (l < r) {
    int mid = (l + r) / 2;
    if (a[mid] >= x) r = mid;
    else l = mid + 1;
}
if (l <= n && a[l] == x) { // 确认找到，输出索引，即 l 指向的位置
    cout << l << endl;
}
else cout << -1 << endl; // 未找到，输出 -1
```

### 复杂度分析

- ​时间复杂度​​： $O(\log n)$
- ​空间复杂度​​： $O(1)$ 