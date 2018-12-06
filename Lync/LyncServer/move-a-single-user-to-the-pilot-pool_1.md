---
title: 1 人のユーザーをパイロット プールに移動する
TOCTitle: 1 人のユーザーをパイロット プールに移動する
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49887021
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 1 人のユーザーをパイロット プールに移動する

 

_**トピックの最終更新日:** 2012-09-28_

Lync Server 2013 コントロール パネルまたは Lync Server 2013 管理シェルを使用して、 Office Communications Server 2007 R2 プールから Lync Server 2013 パイロット プールにユーザーを移動できます。以下の例の \[レジストラー プール\] 列で、 **\<Office Communications Server\>** は Office Communications Server 2007 R2 プールであり、6 人のユーザーはすべてこのプールに接続されています。以下の手順では、 Lync Server 2013 コントロール パネルおよび Lync Server 管理シェルを使用して、1 人のユーザーを Lync Server 2013 プールに移動します。

![Lync Server コントロール パネルでの OCS ユーザーの検索](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Lync Server コントロール パネルでの OCS ユーザーの検索")

## Lync Server 2013 コントロール パネルを使用してユーザーを移動するには

1.  RTCUniversalServerAdmins グループ、CsAdministrator 管理者ロール、または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。

2.  Lync Server コントロール パネルを開きます。

3.  \[**ユーザー**\] をクリックします。

4.  \[**ユーザー検索**\] タブの \[**検索**\] ボタンをクリックします。

5.  次に、\[**フィルターの追加**\] をクリックします。

6.  \[**Office Communications Server ユーザー**\] が \[**True**\] のフィルターを作成します。

7.  \[**検索**\] をクリックして Office Communications Server 2007 R2 のレガシ ユーザーを検索します。
    
    ![Lync Server コントロール パネルでの OCS ユーザーの検索](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Lync Server コントロール パネルでの OCS ユーザーの検索")  

8.  Lync Server 2013 プールに移動するユーザーを選択します。この例では、Sara Davis というユーザーを移動します。

9.  \[**アクション**\] メニューの \[**選択されたユーザーをプールに移動**\] をクリックします。

10. ドロップダウン リストから \[Lync Server 2013 プール\] をクリックします。

11. \[**アクション**\] をクリックし、\[**選択されたユーザーをプールに移動**\] をクリックします。\[**OK**\] をクリックします。
    
    ![\[ユーザーの移動\] ダイアログ ボックスの転送先プールの設定](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "[ユーザーの移動] ダイアログ ボックスの転送先プールの設定")  

12. ユーザーの \[**レジストラー プール**\] 列に Lync Server 2013 プールが表示されていることを確認します。このプールが表示されていれば、ユーザーは正常に移動しています。

## Lync Server 2013 管理シェルを使用してユーザーを移動するには

1.  Lync Server 管理シェルを開きます。

2.  コマンドラインで、次のように入力します。
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  次に、コマンドラインで、次のように入力します。
    
        Get-CsUser -Identity "David Pelton"

4.  **RegistrarPool** ID は Lync Server 2013 プールをポイントしています。この ID が存在することは、ユーザーが正常に移動されたことを示します。
    
    ![Identity フィルターを使用した Get-CsUser コマンドレットの出力](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Identity フィルターを使用した Get-CsUser コマンドレットの出力")  
    
    > [!NOTE]
    > <strong>Get-CsUser</strong> コマンドレットの詳細を確認するには、<strong>Get-Help Get-CsUser –Detailed</strong> を実行してください。

