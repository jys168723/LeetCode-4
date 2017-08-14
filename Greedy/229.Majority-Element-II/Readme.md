### 229.Majority-Element-II

本题属于贪心法，没有固定的套路，属于脑洞型。

设置两个元素X1，X2和对应的count1和count2.

如果新元素与之任何一个相同，则对应计数器加1；如果有一个计数器已经是零，则这个新元素就成为对应的X；如果与X1和X2都不同，则两个计数器都减一，而新元素本身也被舍弃。

假设这个数组中只有一个元素是majority element的话，那么每次遇到上述最后一种情况“消除三个数”的操作，都至少能带走两个非majority element。这就保证每一轮的操作，已经记录加上剩余的所有元素里，majority element总是占1/3多。

假设这个数组中有两个元素是majority element的话，那么每次遇到“消除三个数”的操作，可能会带走两个majority element。但这样的操作不会超过N/3次（因为这种情况下非majority element不会超过N/3），所以最终X1和X2仍然都会留存的是majority element.

注意，遍历完之后，最后剩下的两个X都有可能是答案，需要单独验证。

显然，本题可以扩展到定义大于 N/4, N/5 ... 的majority element。只要设置更多的X即可。