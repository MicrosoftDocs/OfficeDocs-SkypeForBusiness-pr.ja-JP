---
title: 'Lync Server 2013: プールのフェールバック'
TOCTitle: プールのフェールバック
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48272257
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのプールのフェールバック

 

_**トピックの最終更新日:** 2012-11-01_

障害が起きたプール (この例では Pool1) がオンラインに戻ったら、次の手順を実行して、展開を通常の状態に稼働状態に戻します。

フェールバック プロセスは完了するまで数分かかることに注意してください。参考として、20,000 名のユーザーのプールでは、最大 60 分かかることが予想されます。

1.  次のコマンドレットを入力して、もともと Pool1 に属していて Pool2 にフェールオーバーされたユーザーをフェールバックします。
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

それ以外の操作は必要ありません。中央管理サーバーをフェールオーバーした場合は、それを Pool2 に置いておくことができます。

