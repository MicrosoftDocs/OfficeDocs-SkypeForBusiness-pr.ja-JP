---
title: アーカイブ ポリシーの構成と割り当て
TOCTitle: アーカイブ ポリシーの構成と割り当て
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48273248
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アーカイブ ポリシーの構成と割り当て

 

_**トピックの最終更新日:** 2012-10-01_

Lync Server 2013 では、ポリシーを使用して Lync Server 2013 に所属しているユーザーの内部通信および外部通信のアーカイブを有効化/無効化します。これには、次のアーカイブ ポリシーが含まれます。

  - Lync Server 2013 を展開するときに既定で作成されるグローバル ポリシー。

  - 特定のサイトまたはユーザーに対するアーカイブの実装方法を指定するために作成して使用できるオプションのサイトレベルおよびユーザーレベルのポリシー。

アーカイブ ポリシーは、最初はアーカイブの展開時にセットアップしますが、展開後に変更、追加、および削除できます。Lync Server 2013 コントロール パネルで、\[**アーカイブおよび監視**\] グループの \[**アーカイブ ポリシー**\] ページを使用して、ポリシーをグローバル レベル、サイト レベル、およびユーザー レベルで管理できます。

> [!NOTE]
> アーカイブの実装を制御するには、重要モード、削除オプション、IM と会議のどちらをアーカイブするかなどのアーカイブ構成のオプションを指定する必要があります。既定では、グローバル アーカイブ構成やサイトまたはプール アーカイブ構成で有効になっているオプションはありません。アーカイブ ポリシーで内部通信または外部通信のアーカイブを有効にする前に、すべての該当するオプションをアーカイブ構成で指定する必要があります。詳細については、「操作」のドキュメントの「<a href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Lync Server 2013 での組織、サイト、およびプールのアーカイブ構成オプションの管理</a>」を参照してください。<br />
> Lync Server ストレージを Exchange 2013 ストレージと統合する場合、Exchange ユーザー ポリシーは Lync Server 2013 アーカイブ ポリシーよりも優先されますが、メールボックスを持っていた Exchange 2013 に所属しているユーザーの場合のみはインプレース保持になります。


ポリシーの階層など、ポリシーの実装方法の詳細については、「計画」のドキュメント、「展開」のドキュメント、「操作」のドキュメントの「[Lync Server 2013 でのアーカイブのしくみ](lync-server-2013-how-archiving-works.md)」を参照してください。展開後にポリシーを管理する方法の詳細については、「操作」のドキュメントの「[Lync Server 2013 での内部通信および外部通信のアーカイブの管理](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)」を参照してください。

## このセクション中

  - [アーカイブ用のグローバル ポリシーの構成](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [アーカイブ用のサイト ポリシーの設定](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [ユーザーのアーカイブ ポリシーの設定](lync-server-2013-setting-up-archiving-policies-for-users.md)

