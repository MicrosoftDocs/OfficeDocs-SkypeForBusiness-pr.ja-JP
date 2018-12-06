---
title: SNMP アプリケーションの構成
TOCTitle: SNMP アプリケーションの構成
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412972(v=OCS.15)
ms:contentKeyID: 48273531
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# SNMP アプリケーションの構成

 

_**トピックの最終更新日:** 2012-10-03_

Lync Server 2013には、場所情報サービスを簡易ネットワーク管理プロトコル (SNMP) アプリケーションに接続するときに使用できる標準の Web サービス インターフェイスが組み込まれています。SNMP アプリケーションは、MAC アドレスをポートおよびスイッチの情報と照合します。

SNMP アプリケーションがインストールされているが、場所情報サービスが、場所データベース内で一致する情報を見つけられない場合、クライアントによって示される MAC アドレスを使用して、自動的にアプリケーションについて照会します。次に場所情報サービスは、SNMP アプリケーションによって戻されたポートおよびスイッチ情報を使用して、場所データベースに再照会します。

詳細については、「[Set-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsWebServiceConfiguration)」を参照してください。

> [!NOTE]
> MAC アドレスは、Windows 8を実行しているコンピューター上では使用できません。


## SNMP アプリケーションの URL を構成するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  次のコマンドレットを使用して SNMP アプリケーションの URL を構成します。
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>"

