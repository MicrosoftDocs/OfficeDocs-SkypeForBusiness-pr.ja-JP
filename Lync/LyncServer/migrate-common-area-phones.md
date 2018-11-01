---
title: 共通領域電話の移行
TOCTitle: 共通領域電話の移行
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49886903
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 共通領域電話の移行

 

_**トピックの最終更新日:** 2012-09-29_

共通領域電話は、ロビー、調理場、または工場の作業場のような、共有ワークスペースまたは共用エリアによく設置されている IP 電話です。共通領域電話は、Lync Server UC 機能を提供する目的でコンピューターに接続されている必要はありません。Lync Server 2010 展開を Lync Server 2013に移行した後で、レガシ共通領域電話に関連付けられた連絡先オブジェクトも移行する必要があります。Lync Server 管理シェルを使用して、まず Lync Server 2010 共通領域電話に関連付けられたすべての連絡先オブジェクトを取得し、次に Lync Server 2013 プールにそれらのオブジェクトを移動します。

**共通領域電話の移行**

1.  Lync Server 2013 フロントエンド サーバーから、Lync Server 管理シェルを開きます。

2.  コマンド ラインで、次のように入力します。
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  すべての連絡先オブジェクトが Lync Server 2013 プールに移動されたことを確認するには、Lync Server 管理シェルから以下を入力します。
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    すべての連絡先オブジェクトが Lync Server 2013 プールに関連付けられたことを確認してください。

