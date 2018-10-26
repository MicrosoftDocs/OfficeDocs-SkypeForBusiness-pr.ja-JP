---
title: Exchange ストレージとの統合の有効化または無効化
TOCTitle: Exchange ストレージとの統合の有効化または無効化
ms:assetid: c08b9ba5-04f6-452a-b44c-c130f1564a34
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205228(v=OCS.15)
ms:contentKeyID: 48273473
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exchange ストレージとの統合の有効化または無効化

 

_**トピックの最終更新日:** 2012-10-09_

Lync Server 2013 コントロール パネル では、アーカイブ構成を使用して、Exchange ストレージとの統合を有効または無効にします。これには、次のアーカイブ構成が含まれます。

  - Lync Server 2013 を展開するときに既定で作成されるグローバル構成。

  - 特定のサイトまたはプールに対するアーカイブの実装方法を指定するために作成して使用できる、オプションのサイトレベルおよびプールレベルのポリシー。

指定できるオプションやアーカイブ構成の階層など、アーカイブ構成の実装方法の詳細については、「計画」のドキュメント、「展開」のドキュメント、または「操作」のドキュメントの「[Lync Server 2013 でのアーカイブのしくみ](lync-server-2013-how-archiving-works.md)」を参照してください。

## Microsoft Exchange ストレージとの統合を有効または無効にするには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、\[**監視とアーカイブ**\] をクリックし、\[**アーカイブ構成**\] をクリックします。

4.  アーカイブ構成一覧で、適切なグローバル構成、サイト構成、またはプール構成の名前をクリックし、\[**編集**\]、\[**詳細の表示**\] の順にクリックして、次の操作を実行します。
    
      - Exchange 2013 ストレージとの統合を有効にするには、\[**Microsoft Exchange 統合**\] チェック ボックスをオンにします。
    
      - Exchange 2013 ストレージとの統合を無効にするには、\[**Microsoft Exchange 統合**\] チェック ボックスをオフにします。

5.  \[**確定**\] をクリックします。

## 関連項目

#### 概念

[Lync Server 2013 でのアーカイブのしくみ](lync-server-2013-how-archiving-works.md)  

#### その他のリソース

[Lync Server 2013 での組織、サイト、およびプールのアーカイブ構成オプションの管理](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

