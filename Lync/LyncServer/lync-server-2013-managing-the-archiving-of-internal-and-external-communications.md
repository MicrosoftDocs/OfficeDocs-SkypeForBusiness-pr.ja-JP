---
title: Lync Server 2013 での内部通信および外部通信のアーカイブの管理
TOCTitle: Lync Server 2013 での内部通信および外部通信のアーカイブの管理
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48272433
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での内部通信および外部通信のアーカイブの管理

 

_**トピックの最終更新日:** 2012-10-09_

Lync Server 2013 では、Microsoft Exchange 統合を使用しない場合や、メールボックスがインプレース保持される Exchange 2013 に所属していないユーザーがいる場合に、アーカイブ ポリシーを使用して内部通信および外部通信のアーカイブを有効または無効にできます。これには、次のアーカイブ ポリシーが含まれます。

  - Lync Server 2013 の展開時に既定で作成されたグローバル ポリシー。

  - 特定のサイトまたはユーザーについてアーカイブの実装方法を指定するために作成して使用できる、オプションのサイトレベル ポリシーおよびユーザーレベル ポリシー。

アーカイブ ポリシーは、最初はアーカイブの展開時にセットアップしますが、展開後に変更、追加、および削除できます。Lync Server 2013 コントロール パネルでは、\[**アーカイブと監視**\] グループの \[**アーカイブ ポリシー**\] ページを使用して、グローバル レベル、サイト レベル、およびユーザー レベルでポリシーを管理できます。Lync Server ストレージを Exchange 2013 ストレージと統合した場合、Exchange のユーザー ポリシーが Lync Server 2013 のアーカイブ ポリシーより優先されます。

ポリシーの階層など、ポリシーの実装の詳細については、「計画」、「展開」、または「操作」のドキュメントの「[Lync Server 2013 でのアーカイブのしくみ](lync-server-2013-how-archiving-works.md)」を参照してください。

> [!NOTE]
> アーカイブの実装を制御するには、IM または会議をアーカイブするかどうか、重要モードの使用、削除オプションなどのオプションをアーカイブ構成で指定する必要があります。既定では、グローバル アーカイブ構成またはサイト/プール アーカイブ構成で有効になっているオプションはありません。アーカイブ ポリシーで内部通信または外部通信のアーカイブを有効にするには、その前にアーカイブ構成で適切なオプションをすべて指定する必要があります。詳細については、「操作」のドキュメントの「<a href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Lync Server 2013 での組織、サイト、およびプールのアーカイブ構成オプションの管理</a>」を参照してください。<br />
> 展開で Microsoft Exchange の統合を有効にした場合、Exchange 2013 に所属し、メールボックスがインプレース保持されているユーザーに対してアーカイブが有効となるかどうかが Exchange のポリシーによって制御されます。詳細については、「展開」のドキュメントの「<a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server 統合使用時に使用するアーカイブのポリシーの設定</a>」を参照してください。


## このセクション中

  - [特定のサイトまたはユーザーについて内部通信または外部通信のアーカイブを有効または無効にするアーカイブ ポリシーの作成](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md)

  - [組織、サイト、ユーザーの内部通信または外部通信のアーカイブを有効化または無効化するためのアーカイブ ポリシーの変更](lync-server-2013-changing-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-your-organization-sites-or-us.md)

  - [ユーザーへのアーカイブ ポリシーの適用](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [Exchange Server 統合使用時に使用するアーカイブのポリシーの設定](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [アーカイブ ポリシーの削除](lync-server-2013-deleting-an-archiving-policy.md)

