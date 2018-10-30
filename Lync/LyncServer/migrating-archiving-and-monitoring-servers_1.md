---
title: アーカイブおよび監視サーバーの移行
TOCTitle: アーカイブおよび監視サーバーの移行
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49887043
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アーカイブおよび監視サーバーの移行

 

_**トピックの最終更新日:** 2012-10-02_

アーカイブ サーバーと監視サーバーを Office Communications Server 2007 R2 に展開している場合、これらのサーバーは、フロントエンド プールを移行してからでないと Lync Server 2013 環境に展開できません。組織にアーカイブ機能と監視機能が欠かせない場合は、移行前にアーカイブと監視をパイロット プールに追加して、移行プロセス中もアーカイブ機能と監視機能を使用できるように対処する必要があります。

移行および共存フェーズで、アーカイブ機能と監視機能が必要な場合は、次の点を考慮してください。

  - アーカイブ データと監視データは、Lync Server 2013 の展開に移動されません。レガシ環境を使用停止にする前にバックアップしたデータは、Office Communications Server 2007 R2 でのアクティビティの履歴になります。

  - Office Communications Server 2007 R2 バージョンのアーカイブ サーバーと監視サーバーは、Office Communications Server 2007 R2 フロントエンド プールにのみ関連付けることができます。Lync Server 2013 では、アーカイブと監視はサーバーの役割ではなく、Lync Server 2013 フロントエンド プールに統合されたサービスになっています。

  - レガシ展開と Lync Server 2013 の展開が共存している間は、Office Communications Server 2007 R2 バージョンのアーカイブ サーバーと監視サーバーは、Office Communications Server 2007 R2 プールに所属するユーザーのデータを収集します。Lync Server 2013 バージョンのアーカイブ サーバーと監視サーバーは、Lync Server 2013 プールに所属するユーザーのデータを収集します。
    
    > [!NOTE]
    > 移行フェーズの間も、レガシ エッジ サーバーと新しい Lync Server 2013 パイロット プールを使用していると、Office Communications Server 2007 R2 バージョンのアーカイブ サーバーは引き続き、Office Communications Server 2007 R2 プールに所属するユーザーのデータを収集し、Lync Server 2013 バージョンのアーカイブ サーバーは、Lync Server 2013 プールに所属するユーザーのデータを収集します。


  - サードパーティのアーカイブおよび監視ソリューションをアーカイブ サーバーと監視サーバーで併用する場合は、そのサードパーティ ソリューションと Lync Server 2013 を統合するタイミングと統合方法についてベンダーに問い合わせてください。

