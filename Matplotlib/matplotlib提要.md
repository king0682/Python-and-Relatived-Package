1.指定画布，设置画布大小

`fig = plt.figure(figsize=(6,3))`

或

`fig, ax = plt.subplots(figsize=(6,3))`



2.基本画图

* 添加子图

`ax1 = fig.add_subplot(2,2,1)`

* 子图画图

`ax1.plot(x_value, y_value)`

`ax1.scatter(norm_reviews['Fandango_Ratingvalue'], norm_reviews['RT_user_norm'])`

`ax1.hist(norm_reviews['Fandango_Ratingvalue'], bins=20, range=(0, 5))`

* 设置子图x和y轴标签、标题、坐标范围

  ```
  ax1.set_xlabel('Fandango')
  ax1.set_ylabel('Rotten Tomatoes')
  ax1.set_title('Distribution of Fandango Ratings')
  ax1.set_ylim(0, 50) 
  ```



* 画图：（重复几遍就画几条）

`plt.plot(x_value, y_value,c='red',label=label,linewidth=3)`

可以设置颜色，定义标签（便于后来曲线备注呈现），设置线宽

* 曲线呈现：

`plt.legeng(loc='best')`



3.细分形状

* 条形图

  0.定义画布

  `fig, ax = plt.subplots()`

  1.定义字段List

  `num_cols = ["RT_user_norm", "Metacritic_user_nom", "IMDB_norm", "Fandango_Ratingvalue", "Fandango_Stars"]`

  

  2.定义柱高（纵向）

  `bar_heights = norm_reviews.loc[0, num_cols].values`

  定义柱宽（横向）

  `bar_widths = norm_reviews.loc[0, num_cols].values`

  

  3.定义各个柱子离原点距离

  `bar_positions = arange(5) + 0.75`

  

  4.定义展示轴标签和间距

  纵向：

  ```
  tick_positions = range(1,6)
  ax.set_xticks(tick_positions)
  ax.set_xticklabels(num_cols, rotation=45)
  ```

  横向：

  ```
  tick_positions = range(1,6)
  ax.set_yticks(tick_positions)
  ax.set_yticklabels(num_cols)
  ```

  

  5.画条状图

  纵向：

  `ax.bar(bar_positions, bar_heights, 0.3)`

  横向：

  `ax.barh(bar_positions, bar_widths, 0.5)`

  

  6.设置x、y轴标签和标题内容

  ```
  ax.set_xlabel('Rating Source')
  ax.set_ylabel('Average Rating')
  ax.set_title('Average User Rating For Avengers: Age of Ul ')
  ```

  

  7.展示图形

  `plt.show()`



* 散点图

  1.定义图

  `fig, ax = plt.subplots()`

  2.画散点图

  `ax.scatter(norm_reviews['Fandango_Ratingvalue'], norm_reviews['RT_user_norm'])`

  

* 盒图

  1.定义图

  2.画柱状图

  `ax.hist(norm_reviews['Fandango_Ratingvalue', range=(4,5), bins=20])`

* 箱线图

  1.定义图

  2.画箱线图

  `ax.boxplot(norm_reviews['RT_user_norm'])`

* 

n.展示图：

`plt.show()`