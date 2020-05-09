# drawk
## 基于pyecharts画k线分析图
   * 程序基于pyecharts二次集成，方便根据pd.Dataframe数据绘制k线，交易量，macd等信息
   * df中必须包含['open', 'close', 'low', 'high']
   * 如果需要绘制交易量，df中需要‘volume’
## 样例
‘’‘
from drawk import KChartData
data=KChartData(code,df,precision=2)
chart=data.plot(area=['V','cci'], 
     vlines=['vMA5','vMA30'],
     klines=['upper','middle','lower'])
chart.load_javascript()
chart.render_notebook()
‘’‘
