---
title: 1 人のユーザーをパイロット プールに移動する
TOCTitle: 1 人のユーザーをパイロット プールに移動する
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48273916
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 1 人のユーザーをパイロット プールに移動する

 

_**トピックの最終更新日:** 2012-09-26_

Lync Server 2013 コントロール パネル または Lync Server 2013 管理シェル を使用して、ユーザーを Lync Server 2010 プールから Lync Server 2013 パイロット プールへ移動できます。次の例のレジストラー プール列では、 **pool01.contoso.net** が Lync Server 2010 プールであり、これら 6 人のユーザーはすべてこのプールに接続しています。次の手順に従って、 Lync Server 2013 コントロール パネル と Lync Server 管理シェル を使用してユーザーを Lync Server 2013 プールに移動します。

## Lync Server 2013 コントロール パネルを使用してユーザーを移動するには

**Lync Server 2013 コントロール パネル内のユーザー一覧**

![Lync Server コントロール パネル、\[ユーザーの移動\] ダイアログ ボックス](images/JJ205401.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server コントロール パネル、[ユーザーの移動] ダイアログ ボックス")

1.  RTCUniversalServerAdmins グループ、CsAdministrator 管理者ロール、または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。

2.  \[**Lync Server コントロール パネル**\] を開きます。

3.  \[**ユーザー**\]、\[検索\] の順にクリックして、\[**ユーザー検索**\] をクリックします。

4.  Lync Server 2013 プールに移動するユーザーを選択します。この例では、Sara Davis というユーザーを移動します。

5.  \[**アクション**\] メニューの \[**選択されたユーザーをプールに移動**\] をクリックします。

6.  ドロップダウン リストから、Lync Server 2013 プールをクリックします。

7.  \[**アクション**\] をクリックし、\[**選択されたユーザーをプールに移動**\] をクリックします。\[**OK**\] をクリックします。
    
    ![\[ユーザーの移動\]、\[移動先レジストラー プール\] ダイアログ ボックス](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "[ユーザーの移動]、[移動先レジストラー プール] ダイアログ ボックス")  

8.  ユーザーの \[**レジストラー プール**\] 列に Lync Server 2013 プールが表示されていることを確認します。このプールが表示されていれば、ユーザーは正常に移動しています。

## Lync Server 2013 管理シェルを使用してユーザーを移動するには

1.  Lync Server 管理シェルを開きます。

2.  コマンドラインで、次のように入力します。
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  次に、コマンドラインで、次のように入力します。
    
        Get-CsUser -Identity "David Pelton"

4.  **RegistrarPool** ID は Lync Server 2013 プールをポイントしています。この ID が存在することは、ユーザーが正常に移動されたことを示します。
    
    ![Identity フィルターを使用した Get-CsUser コマンドレットの出力](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Identity フィルターを使用した Get-CsUser コマンドレットの出力")  
    
    > [!NOTE]
    > <strong>Get-CsUser</strong> コマンドレットの詳細を確認するには、<strong>Get-Help Get-CsUser –Detailed</strong> を実行してください。

