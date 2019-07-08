# SQL 語法（[參考自](https://www.1keydata.com/tw/sql/sql.html)）

## 自訂義簡寫
```
Row：欄位值
Column：第一列
Table：表格
Value：數值
?：運算符
Table1,2,3：不同的表格
A1,2,3：表格別名
A1.Row：表格中的欄位
X,Y：欄位別名
```
## Select：查詢
```
Select Row From Table;
```
## Distinct：列出不重複資料
```
Select Distinct Row From Table;
```
## Where：選擇性地列出資料
```
Selec Row From Table Where Column 條件 Value;
```
## And/Or：複雜條件
```
Select Row From Table Where Column ? "Value" Or {Column ? "Value" And Column ? "Value"};
```
## In：選擇包含特定值
```
Select Row From Table Where Column In('Value','Value');
```
## Between：選擇範圍內的值
```
Select Row From Table Between 'Value' And 'Value';
```
## 萬用字元："%","_"
```
%：任何數量的字元
_：單一字元
```
## Like：配合萬用字元來查詢
```
Select Row From Table Where Column Like " %A_B%C_"; 
    EX："任意字元+A+單一字元+B+任意字元C+單一字元" = "123+A+4+B+567+C+8"
```
## Order By：排序查詢結果
```
Select Row From Table Where Order By Row ASC/DESC
```
## Fun：Function 函數 
```
Select Fun(Row) From Table;
```
## AVG()：平均值 
```
Select AVG(Row) From Table;
```
## Count()：資料筆數 
```
Select Count(Row) From Table;
EX：不重複筆數[Select Count(Distinct Row) From Table;]
```
## MAX()：最大值 
```
Select MAX(Row) From Table;
```
## Min()：最小值 
```
Select Min() From Table;
```
## SUM()：總和 
```
Select SUM() From Table;
```
## Group By：集成，依所使用函數來分類 
```
Select Row , Fun(Row) From Table Group By Row;
```
## Having：針對函數所產生的值做比較查詢（不一定要包含 Group By）
```
Select Row , Fun(Row) From Table Group By Row Having Fun(Row) ? Value;
```
## 別名：簡單來說就是變數名稱 
```
Select "表格別名".Row "欄位別名" From Table "表格別名";
```
## As：指定別名
```
Select "表格別名".Row as "欄位別名" From Table As "表格別名";
```
## Join 連接表格的概念，Where Table1.Row = Table2.Row 
```
Select A1.Row As X,SUM(A2.Row) As Y From Table1 As A1 , Table2 As A2 Group  Where A1.Row = A2.Row Group By A1.Row;
```
