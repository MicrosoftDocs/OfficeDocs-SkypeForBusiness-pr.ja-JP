---
title: セカンダリ場所情報サービスの構成
TOCTitle: セカンダリ場所情報サービスの構成
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398138(v=OCS.15)
ms:contentKeyID: 48271165
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# セカンダリ場所情報サービスの構成

 

_**トピックの最終更新日:** 2012-10-30_

Lync Server 2013 は、場所情報サービスにセカンダリ ロケーション ソース (SLS) データベースを示すために使用できる Web サービス インターフェイスを提供します。SLS データベースに接続するこの Web サービス インターフェイスは、場所情報サービスの WSDL に準拠する必要があります。場所データベースとセカンダリ場所データベースの両方が構成されている場合、場所情報サービスはまず、場所データベースに対するクエリを実行し、一致するものが見つからなければ、クライアントからの場所要求を SLS データベースに送信します。その場所が SLS 内にある場合、場所情報サービスはその場所をクライアントに送信します。

詳細については、Lync Server 管理シェルのドキュメントで以下のコマンドを参照してください。

  - **Set-CsWebServiceConfiguration**

## セカンダリ場所データベースを構成するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  次のコマンドレットを実行して、セカンダリ場所データベースの場所の URL を構成します。
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>"

