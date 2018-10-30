---
title: ポリシーと設定のインポート
TOCTitle: ポリシーと設定のインポート
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48273317
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ポリシーと設定のインポート

 

_**トピックの最終更新日:** 2012-09-28_

Office Communications Server 2007 R2 のトポロジ情報と Lync Server 2013 のパイロット プールをマージした後、 Lync Server 2013 管理シェル コマンドレットを実行して、 Office Communications Server 2007 R2 のポリシーと構成設定を Lync Server 2013 のパイロット プールに移行する必要があります。

**Import-CsLegacyConfiguration** コマンドレットは、ポリシー、ボイス ルート、ダイヤル プラン、Communicator Web Access の URL、ダイヤルイン アクセス番号を Lync Server 2013 にインポートします。

## ポリシーと設定を移行するには

1.  Lync Server 2013 フロントエンド サーバーで、 Lync Server 管理シェルを開始します。

2.  コマンドラインで、次のように入力します。
    
        Import-CsLegacyConfiguration
    
    ポリシーがインポートされたら、次の手順に従って、インポートされたポリシーを Lync Server コントロール パネルに表示します。

## インポートされたポリシーを表示するには

1.  Lync Server 2013 コントロール パネルを開きます。

2.  \[**音声のルーティング**\] をクリックし、インポートされたポリシーを表示します。

3.  \[**電話会議**\] をクリックし、インポートされたポリシーを表示します。

4.  \[**フェデレーションと外部アクセス**\] をクリックし、インポートされたポリシーを表示します。

5.  \[**監視およびアーカイブ**\] をクリックし、インポートされたポリシーを表示します。

