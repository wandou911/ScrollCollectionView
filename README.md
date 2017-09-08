# ScrollCollectionView
在Scrollview中添加CollectionView 实现放大缩小

项目中有个功能 需要实现UICollectionView的放大和缩小，变想到在把UICollectionView 添加到UIScollview 上 结果总是出现：
The view returned from viewForZoomingInScrollView: must be a subview of the scroll view. It can not be the scroll view itself.'
查了很多方法没有找到解决方法，后来参考一篇文章 发现需要移除UICollectionView的pinchGestureRecognizer手势

在viewDidLoad方法添加如下两行代码 问题解决
UIGestureRecognizer *gesture = self.mCollectionView.pinchGestureRecognizer;
[self.mCollectionView removeGestureRecognizer:gesture];
