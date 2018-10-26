---
title: Lync Server 2013 での組織、サイト、およびプールのアーカイブ構成オプションの管理
TOCTitle: Lync Server 2013 での組織、サイト、およびプールのアーカイブ構成オプションの管理
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48271761
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での組織、サイト、およびプールのアーカイブ構成オプションの管理

 

_**トピックの最終更新日:** 2012-11-01_

Lync Server 2013 コントロール パネルでアーカイブ構成を使用して、アーカイブの実装方法を指定します。これには、以下のアーカイブ構成が含まれます。

  - Lync Server 2013 を展開するとき、既定で作成されるグローバル構成。

  - 特定のサイトまたはプールについてアーカイブを実装する方法を指定する目的で、作成して使用できる省略可のサイトレベル構成およびプール レベル構成。

アーカイブ構成は、最初はアーカイブの展開時に設定しますが、展開後に変更、追加、および削除できます。Lync Server 2013 コントロール パネルでは、\[**アーカイブと監視**\] グループの \[**アーカイブ構成**\] ページを使用して、グローバル レベル、サイト レベル、およびユーザー レベルで構成を管理できます。指定できるオプション、アーカイブ構成の階層など、アーカイブ構成の実装方法の詳細については、「計画」、「展開」、または「操作」のドキュメントの「[Lync Server 2013 でのアーカイブのしくみ](lync-server-2013-how-archiving-works.md)」を参照してください。

> [!NOTE]
> アーカイブを使用するには、Lync Server 2013 に所属するユーザーについて、アーカイブ ポリシーを構成して、内部通信、外部通信、またはその両方のいずれに対してアーカイブを有効にするかを指定する必要があります。既定では、アーカイブは内部通信および外部通信のどちらに対しても有効になっていません。Microsoft Exchange 統合を使用する場合は、メールボックスがインプレース保持に設定され、Exchange 2013 に所属するすべてのユーザーのアーカイブをサポートするように Exchange 2013 を有効にして、構成する必要があります。<br />
> アーカイブを有効にする前に、このセクションの説明に従って、展開および必要に応じて特定のサイトやプールに対して適切なアーカイブ構成を指定する必要があります。アーカイブを有効にする方法の詳細については、「展開」のドキュメントで「<a href="lync-server-2013-configuring-and-assigning-archiving-policies.md">アーカイブ ポリシーの構成と割り当て</a>」を参照してください。


**Lync Server 管理シェル コマンドレットを使用してアーカイブ構成情報を表示するには**

  - また、Lync ServerWindows PowerShell と **Get-CsArchivingConfiguration** コマンドレットを使用してアーカイブ構成情報を表示できます。このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。
    
    Lync Server 管理シェルでは、以下のコマンドを使用して、アーカイブ構成設定のすべての情報を表示できます。
    
        Get-CsArchivingConfiguration

## このセクション中

  - [特定のサイトまたはプールのアーカイブを管理するためのアーカイブ構成の作成](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [IM または会議セッションのアーカイブの有効化または無効化](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [アーカイブ データの削除の有効と無効の切り替え](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [アーカイブが失敗した場合に IM および Web 会議セッションを禁止または許可するための重要モードの有効化または無効化](lync-server-2013-enabling-or-disabling-critical-mode-to-block-or-allow-im-and-web-conferencing-sessions-if-archiving-fails.md)

  - [Lync Server 2013 でのフェデレーション パートナーに対するアーカイブ免責事項の送信の有効化または無効化](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Exchange ストレージとの統合の有効化または無効化](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [アーカイブ構成の削除](lync-server-2013-deleting-an-archiving-configuration.md)

## 関連項目

#### その他のリソース

[Lync Server 2013 アーカイブの管理](lync-server-2013-managing-archiving.md)

