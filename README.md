# OOAD-WEEK11
State Diagram
##ส่งการบ้าน
###1.State Diagram[เปิดปิดจอโทรศัพท์]
```
@startuml
[*] --> Active

state Active {
  [*] -> ScreenOff
 ScreenOff --> ScreenOn : put power button
 ScreenOn --> ScreenOff : put power button
}
@enduml
```
![](http://www.plantuml.com/plantuml/img/SoWkIImgAStDuOhMYbNGrRLJS4mkoInBvU82IfIaGdaArLmA2c05TWh1oKMfgNd-QMbS22PO8vINfs2bK51Qeb2GNvvQf91KMbAIdyU5aDH5DWARqbekXzIy5A2B0000)
###2.State Diagram[การทอดไข่]
```
@startuml
[*] -up-> First
First -right-> Second
Second --> Third
Third -left-> Last
First : add beaten egg
Second : stir eggs in a cup
Third : pour stirred eggs the heated oil
Last : Served
@enduml
```
![](http://www.plantuml.com/plantuml/img/FOwn3i8m34JtVCNDIFc13gWJ4rlP44EeJHAff9NZzFj9Kc0vI-TtPuzPdMXvB-P-Ui2MpPvnYPBLT8MLw8DMS-9vJMIE0LkTMuX2fYlimgz6NTq_ES0HuSbEEO6z_qK7P8tId8oOu32NxTioO5kBzBqm7OW6HcWbX3KkfXsetCIoCvcH4zNVFm00)
###3.State Diagram[เครื่องซักผ้า]
```
@startuml
[*] -up-> First
First -right-> Second
Second --> Third
Third -left-> Last
First : take shirts in Washing machine
Second : take washing powder
Third : putting money
Last : Wash
@enduml
```
![](http://www.plantuml.com/plantuml/img/FKux3i8m3Drz2iz8la07r8c93IG6n10rfereaoXnL75xd11OthFUJnwpc2HbM-5-U22LI4SykPG56Y8bDo-YueMdu2ry2KcLw-AIXOP8Apzhwcp-pG75l1Yp-fBHURmPlVsCcvcK-JVLStjtOzWjfpuxO2mYhHGylw7EgrYNO6HlzUyF)
###4.State Diagram[เปิดปิดไฟด้วยบลูทูธ]
```
@startuml
scale 350 width
[*] --> Bluetooth

state Bluetooth {
  [*] --> Control
  Control --> Bluetooth_Lamp : Data Coltrol
  Bluetooth_Lamp --> LED_STATUS : Status Coltrol(Data_Return)
}

state Bluetooth_Lamp {
  [*] --> Chack_value
  Chack_value --> Logic_Active:New Data Active 
  Logic_Active --> Data_Retrun : Data Status
  state Logic_Active {
     LedOn -> LedOff
     LedOff-> LedOn
  }
}
@enduml
```
![](http://www.plantuml.com/plantuml/img/PP4_2y8m4CNtV8eRLH04SN4G_zIjA5YTH49e4rkCYRGN7SJlxiMqr6gcoxlVoxqZymf5YUwgMPKABM4y6S6Zo31dny49XiCPBBMJQ2qfZ5YKhG1F1j1WAskmj9gKkkgQUIokDvX2950GeMlsf-yjyJhYoNwnFoI49pJHLOsXvzry9z6LfizUVu728vrKkKWl_2w8yCdQMnXbpqNA5oaMTpdTo4T85-v0_7V_OsZcbyuqkuI418Si7OjFGYUMsTQ0dqU5KgseL2qQqbwqq5oQZFxY3G00)
###5.State Diagram[การโปรแกรม]
```
@startuml

[*] --> State1
State1 --> [*]
State1 : Program
State1 : Run Program

State1 -> State2
State2:Debug
State2 --> [*]

@enduml
```
![](http://www.plantuml.com/plantuml/img/SoWkIImgAStDuUAArefLqDMrKmWkIIn9DUI2K60He0oCQwKGK9IVNfIOYn08Ais32y9rGOqnWWWOMRca9fMcGpbmCxaSKlDIW7O30000)
###6.Activity Diagram[สัญญาณไฟจราจร]
```
@startuml
(*)If "plug in" then
-l->[No]"Fan off"
else
-r-> [Yes] "Green Led"
If "60 minute" then
-l-> [No]"Green Led"
else
-r-> [Yes] "Red Led"
if "60 minute" then
-l-> [No]"Red Led"
else
-r->[Yes] "Yellow"
if "60 minute" then
-r-> [No]"Yellow"
else
-l-> [Yes]"Green Led"
Endif
@enduml
```
![](http://www.plantuml.com/plantuml/img/VP0z2y90343t_8fmame7JewbYueW3cwbT2XSJW_ILEu3_xuVzSg1w9ptNaBg47iVqy2mM2qF5jMDqmMTA8nN4j2ig_OqTchN2uxMAY0E1Dhh2jk6GeTgxua4ZsGKlFpD6WSdAL9Hm7UY0ByYPpBJnFrDpDWS-FWDCO_t7xhFUgOcc_FwyhAj66UX9Z7Fdpm0)
###7.Activity Diagram[เปิดปิดคอม]
```
@startuml
(*)  --> "TurnOff Computer"
If "Take power Button" then
--> [No]"TurnOff Computer"
else
--> [Yes] "Boot main Login"
If "True ID" then
--> [Yes] "Show Desktop"
-->(*)
else
--> [No]"Boot main Login"
Endif
Endif
@enduml
```
![](http://www.plantuml.com/plantuml/img/ROz12uCm38Nl_HMXfstWNnZYt44Oxh1Tnl1GC9sYJKgRuj-VeWTXk-IGb_UzbpoA2PBSg0wd8q2MdK4_Kw2xjN1XvvDWqAgoyzOC29ud350a4IODqY6fnVAkkVbZmp7YghymDg0BPW5dUe8RVthQk24XLEMUjbu_EfwWn3W8Uxq8SyCTSedy0LwfxUqsSwHsVkmB)
###8.Activity Diagram[เครื่องต้มถั่วอัตโนมัติหยอดเหรียญ]
```
@startuml
title Bean Vending Auto Machine

(*) -l-> "Bean Vending Auto Machine"
if "select bean" then
  -->[false] "Bean Vending Auto Machine"#DAA520
else 
  -l->[true] "Display Show Pay Money"#FF7F50
  -l->receive money
  if "Fully" then
   -->[no] "Display Show Pay Money"
  else
   -->[yes] Display show Wait #DAA520
   -->Boil Been
  endif
  
  if "3minite" then
      -->[no] Display show Wait
  else
  -->Pay Product#FF7F50
  endif
  if "Valus receive not equals price been" then
  -->[True]Change#00FF7F
  -->==BEFORE_END==
  else
  -->[False]Don't Change#FF0000
  -->==BEFORE_END===
endif
-->(*)
@enduml
```
![](http://www.plantuml.com/plantuml/img/VL9BJy904BxlhvYKWu-aIQCXdae0ozvGeWOEX9Yr37IJPHUxivh-UsU1YaInbpxcUytNxNjIDOMD4QJ980nHMPYYNMgxXa4W1sDLLjgY49VNLv2Qj0V9ML0Yz0eIZmPBWZT69K0LMW6GfhtvIXcFY__edM8mwDva0Xa8aSLsSwf3P1NQRurguBbodp3XXx6ps2GTAUzaDpk0QonHVo1iueo_nJWo6DDy1zabiUwy86EYVGjjq2-WXVe8dIbDq2RTeuPE6wvkPn3tMl7zu7wxqLOJ7lr_HFWbU_HcI8mqgTqob7HSibMFqbDbWeTsPUi8y3rmnx2jTOdSFvxs_nABlA-KNMCdowBaVf3dmv5yV1gzZXwAF3_9C9UxVrOuUq5me4gPyVKNDHVxU3pWmoBw_COdwmi0)
###9.Activity Diagram[เปิดปิดประตูด้วยคีย์การ์ด]
```
@startuml
(*)  --> "Door Lock"
If "have key kard" then
  -->==BEFORE_END===
--> [No]"Door Lock"
else
--> [Yes] "Data Chack"
If "True ID" then
--> [Yes] "Open Door"
-->(*)
else
  -->==BEFORE_END===

Endif
Endif
@enduml
```
![](http://www.plantuml.com/plantuml/img/SoWkIImgAStDuTBGqbHGqDMrKr1ooSylKl39JyvMul9CKr3AI2nBLSXEhLJ8JYnAKL8eoKZDumAhjBLrSdNp3tADT_LpiRMrvG9fZlRBZqKs83MdE1KY4PbQ70iqEx4aKS4v8n5cU4XHQQg2fmlKM2I5_WMfUGeWWvH0ea37GOp2QZ6NQrvAPXgKT4ZDIm7w1m00)
###10.Activity Diagram[เปิดพัดลม]
```
@startuml
(*)If "Plug in" then
  -->==BEFORE_END===
--> [No]"Off"
else
--> [Yes] "Switf On"
If "switf1" then
  -->[Yes]==BEFORE_225D===
--> [Yes] "Open fan"
-->(*)
else
If "switf2" then
  -->[Yes]==BEFORE_225D===
else

If "switf3" then
  -->[Yes]==BEFORE_225D===

Endif
Endif
@enduml
```
![](http://www.plantuml.com/plantuml/img/SoWkIImgAStDuTBGqlHCKr0Ao2bDLyZCKr8eoKZDur9GqDMrixLrSdNp3tADT_LpiRMrvG8AAKJxvSSg-QUbAN6bvXIdGeGYKujZ5PI2opDBqXJyyvIuGCOLWtY6oAQ1bS6DD38oHPW9CS2_83LF8IqHQ01G4EWgY0rmmum86mRMWD1XJ5W7bsjUIcOQb7H8pKi1XWW0)
