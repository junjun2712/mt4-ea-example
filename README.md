# mt4-ea-example


datetime OrderOpenTime( )
对于当前选择定单返回买入时间。

注解:定单必须用OrderSelect()函数提前选定。

示例:
  if(OrderSelect(10, SELECT_BY_POS)==true)
    Print("定单10 买入时间",OrderOpenTime());
  else
    Print("OrderSelect 返回的错误 ",GetLastError());


int OrderType( )
对于当前选择定单返回定单类型。可以是以下的任意值:
OP_BUY -买进,
OP_SELL - 卖出，
OP_BUYLIMIT - 挂单买入限定，
OP_BUYSTOP - 挂单停止限定，
OP_SELLLIMIT - 挂单卖出限定,
OP_SELLSTOP - 挂单停止限定。

注解: 定单必须由OrderSelect()函数选择。

示例:
  int order_type;
  if(OrderSelect(12, SELECT_BY_POS)==true)
    {
     order_type=OrderType();
     // ...
    }
  else
    Print("OrderSelect() 返回错误 - ",GetLastError());
    
    
double OrderProfit( )
对于选择定单返回净盈利值 (除掉期和佣金外)。对于开仓位当前不真实盈利。对于平仓为固定盈利。
对于当前选择定单返回盈利。

注解:定单必须用OrderSelect()函数提前选定。

示例:
  if(OrderSelect(10, SELECT_BY_POS)==true)
    Print("定单 10 盈利",OrderProfit());
  else
    Print("OrderSelect返回的错误",GetLastError());
