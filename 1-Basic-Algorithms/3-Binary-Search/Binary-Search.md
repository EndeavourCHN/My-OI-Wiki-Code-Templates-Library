# 二分

试想这样一种情况：欲从 $n$ 个数中寻找目标值，若采用常规方法从头遍历，时间复杂度为 $O(n)$ ；如果每次将寻找区间一分为二，判断目标值在哪一半，那么时间复杂度可降低至 $O(\log{n})$ 。

在长度为 $n$ 的升序数组 $a$ 中查找 $x$ 第一次出现的位置示例：

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
else cout << -1 << endl; // 未找到，输出-1
```
