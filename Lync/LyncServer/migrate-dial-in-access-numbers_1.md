---
title: ダイヤルイン アクセス番号の移行
TOCTitle: ダイヤルイン アクセス番号の移行
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48272133
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ダイヤルイン アクセス番号の移行

 

_**トピックの最終更新日:** 2012-09-26_

ダイヤルイン アクセス番号の移行では、**Import-CsLegacyConfiguration** コマンドレット (以前に「[ポリシーと設定のインポート](import-policies-and-settings.md)」で実行済み) を実行することによるダイヤル プランの移行、および **Move-CsApplicationEndpoint** コマンドレットを実行することによる連絡先オブジェクトの移行という 2 つの手順が必要です。

## ダイヤルイン アクセス番号を移行するには

1.  Office Communications Server 2007 R2 管理ツールを開きます。

2.  コンソール ツリーでフォレスト ノードを右クリックし、\[**プロパティ**\]、\[**会議アテンダントのプロパティ**\] の順にクリックします。

3.  \[**アクセスの電話番号**\] タブで、\[**プールによるサービス提供**\] をクリックして、関連するプールでアクセスの電話番号を並べ替え、移行元のプールのすべてのアクセス番号を識別します。

4.  各アクセス番号の SIP URI を識別するには、アクセス番号をダブルクリックして \[**会議アテンダント番号の編集**\] ダイアログ ボックスを開き、\[**SIP URI**\] を探します。

5.  Lync Server 管理シェルを開きます。

6.  各ダイヤルイン アクセス番号を Lync Server 2013 でホストされるプールに移動するには、次のコマンドを実行します。
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  Office Communications Server 2007 R2 管理ツールの \[**アクセスの電話番号**\] タブで、移行元の Office Communications Server 2007 R2 プールにダイヤルイン アクセス番号が残っていないことを確認します。

