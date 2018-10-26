---
title: 複数のユーザーをパイロット プールに移動する
TOCTitle: 複数のユーザーをパイロット プールに移動する
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49887056
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 複数のユーザーをパイロット プールに移動する

 

_**トピックの最終更新日:** 2012-10-02_

Lync Server 2013 コントロール パネルまたは Lync Server 2013 管理シェルを使用すると、複数のユーザーを Office Communications Server 2007 R2 プールから Lync Server 2013 パイロット プールに移動できます。

## Lync Server 2013 コントロール パネルを使用して複数のユーザーを移動するには

1.  \[**Lync Server コントロール パネル**\] を開きます。

2.  \[**ユーザー検索**\] タブの \[**検索**\] ボタンをクリックします。

3.  次に、\[**フィルターの追加**\] をクリックします。

4.  \[**Office Communications Server ユーザー**\] が \[**True**\] のフィルターを作成します。

5.  \[**検索**\] をクリックして Office Communications Server 2007 R2 のレガシ ユーザーを検索します。

6.  Lync Server 2013 プールに移動する 2 人のユーザーを選択します。この例では、Chen Yang および Claus Hansen というユーザーを移動します。
    
    ![OCS ユーザーの検索により表示されたユーザー一覧](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "OCS ユーザーの検索により表示されたユーザー一覧")  

7.  \[**アクション**\] メニューで、\[**選択されたユーザーをプールに移動**\] をクリックします。

8.  ドロップダウン リストから \[Lync Server 2013 プール\] をクリックします。

9.  \[**アクション**\] をクリックし、\[**選択されたユーザーをプールに移動**\] をクリックします。\[OK\] をクリックします。
    
    ![\[ユーザーの移動\]、\[移動先レジストラー プール\] ダイアログ ボックス](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "[ユーザーの移動]、[移動先レジストラー プール] ダイアログ ボックス")  

10. ユーザーの \[**レジストラー プール**\] 列に Lync Server 2013 プールが表示されていることを確認します。このプールが表示されていれば、ユーザーは正常に移動しています。

## Lync Server 2013 管理シェルを使用して複数のユーザーを移動するには

1.  Lync Server 2013 管理シェルを開きます。

2.  コマンド ラインで、次のように入力します。 **User1** と **User2** には、移動する特定のユーザーの名前を指定します。 **pool\_FQDN** には、移動先プールの名前を指定します。この例では、ユーザー Hao Chen と Katie Jordan を移動します。
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![レガシ ユーザーを移動するコマンドレットの例](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "レガシ ユーザーを移動するコマンドレットの例")  

3.  コマンド ラインで、次のように入力します。
    
        Get-CsUser -Identity "User1"

4.  **レジストラー プール** ID は、前の手順で **pool\_FQDN** に指定したプールを指しています。この ID が存在していることにより、ユーザーが正常に移動されたことを確認できます。手順 4. を繰り返して、 **User2** が移動されていることを確認します。
    
    ![PowerShell、Get-UsUser -Identity コマンドレットの出力](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "PowerShell、Get-UsUser -Identity コマンドレットの出力")  

## Lync Server 2013 管理シェルを使用して、すべてのユーザーを同時に移動するには

この例では、すべてのユーザーが Office Communications Server 2007 R2 プール (pool01.contoso.net) に戻されています。 Lync Server 2013 管理シェルを使用して、すべてのユーザーを同時に Lync Server 2013 プール (pool02.contoso.net) に移動します。

1.  \[**Lync Server 2013 管理シェル**\] を開きます。

2.  コマンドラインで、次のように入力します。
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![プール内のすべてのレガシ ユーザーを移動するコマンドレットの例](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "プール内のすべてのレガシ ユーザーを移動するコマンドレットの例")  

3.  次に、いずれかのパイロット ユーザーに対して **Get-CsUser** を実行します。
    
        Get-CsUser -Identity "Hao Chen"

4.  各ユーザーの **レジストラー プール** ID は、前の手順で "pool\_FQDN" に指定したプールを指しています。この ID が存在していることにより、ユーザーが正常に移動されたことを確認できます。

5.  また、 Lync Server 2013 コントロール パネルでユーザーの一覧を表示して、レジストラー プールの値が Lync Server 2013 プールを指していることを確認できます。
    
    ![Lync Server 2013 コントロール パネル、ユーザー一覧](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 コントロール パネル、ユーザー一覧")

