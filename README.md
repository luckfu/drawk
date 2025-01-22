# drawk
    drawk是为在notebook等实验环境下方便观察股票数据的基于pyecharts的封装，方便根据pd.Dataframe数据绘制k线(OHLC)，交易量，macd或自定义数据。

## 基于pyecharts画k线分析图 
   * df中必须包含['open', 'close', 'low', 'high']
   * 如果需要绘制交易量，df中需要[‘volume’]
   * 如果需要绘制macd，df中需要 ['macd','dif','dea']
   * 自定义显示区值，如cci，如果df中有_cci_flag(_name_flag)列，会在相应显示数据位置显示标记
   * 自定义显示区值，如需显示多条数据线，用列表指出，如['MTM','MAMTM'] ,MTM和MAMTM必须在df中存在
     ```
      chart=data.plot(area=['V',['MTM','MAMTM']])
     ```
## 样例
![image](https://github.com/luckfu/drawk/raw/master/df.png)

```
from drawk import KChartData
data=KChartData(code,df,precision=2)
chart=data.plot(area=['V','cci'], 
     vlines=['vMA5','vMA30'],
     klines=['upper','middle','lower'])
chart.load_javascript()
chart.render_notebook()
```
![image](https://github.com/luckfu/drawk/raw/master/drawk.gif)

## 增加通过mplfinance 方式绘制k线图，无法交互，但是速度快
```
mpf_plot(dft.tail(300));
```
![image](https://github.com/luckfu/drawk/raw/master/mpf_plot.png)
