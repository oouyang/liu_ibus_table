## liu_ibus_table

盡量與官方版本使用習慣一致的方向調整

### 使用方法: (適用於任何版本 Ubuntu/Debian )

先使用aptitude(或 apt-get )指令安裝 ibus-table 套件:

    sudo aptitude install ibus-table

確定已 cd 到檔案所在的資料夾底下，在terminal輸入以下指令:

    sudo ibus-table-createdb -s liu_ibus_table.txt -n liu.db

把剛剛產生出來的 .db檔以及資料夾裡原有的icon複製到ibus-table資料夾底下

    sudo cp liu.db /usr/share/ibus-table/tables/
    sudo cp liu.png /usr/share/ibus-table/icons/

請登出系統，重新登入，才能使剛才的修改生效。

登入後修改ibus偏好設定。

    輸入法 -> 選取輸入法 -> 漢語 -> 嘸蝦米
    -> 按下旁邊加入按鈕 -> 再關閉視窗即可

### 字根表說明

#### liu_ibus_table.txt

* 網路上所散布較完整的字元表，並過濾冗餘字元，使 ibus-table-createdb 不會產生錯誤訊息

### 加字加詞擴充說明

#### customize.txt

* 可將自訂字詞加在此檔，然後重新建立table

```sh
head -n -2  liu_ibus_table.txt > cust_table.txt && cat customize.txt >> cust_table.txt && tail -2 liu_ibus_table.txt >> cust_table.txt
    
sudo ibus-table-createdb -s cust_table.txt -n liu.db
    
sudo cp liu.db /usr/share/ibus-table/tables/
sudo cp liu.png /usr/share/ibus-table/icons/
```


* 表格說明:
    每行由空白分割最後一個欄位為優先權，為了與原本liu_ibus_table.txt區分，最好由101開始，避免選字上的問題

    
