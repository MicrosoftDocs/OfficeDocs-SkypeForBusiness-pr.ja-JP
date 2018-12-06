---
title: Lync Server でのアーカイブのユーザー ポリシーの設定
TOCTitle: Lync Server でのアーカイブのユーザー ポリシーの設定
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48271565
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server でのアーカイブのユーザー ポリシーの設定

 

_**トピックの最終更新日:** 2012-10-10_

Lync Server 2013 に所属する特定のユーザーに対してアーカイブを有効または無効にするには、1 つ以上のユーザー ポリシーを作成して構成し、適切なポリシーを特定のユーザーまたはユーザー グループに適用する必要があります。ユーザー ポリシーはサイト ポリシーとグローバル ポリシーに優先しますが、Lync Server 2013 に所属するユーザーにのみ適用されます。

ユーザーは常に Lync Server に所属します。Microsoft Exchange 統合が有効になっている場合、Microsoft Exchange Server 2013 にメールボックスを持つユーザーは、Lync Server のアーカイブ ポリシーを管理される必要がありません。アーカイブを使用するこれらのユーザーは Exchange インプレース保持によって管理されます。

グローバル ポリシー、サイト ポリシー、ユーザー ポリシーの階層を含むアーカイブ ポリシーのしくみの詳細については、「計画」、「展開」、または「操作」のドキュメントの「[Lync Server 2013 でのアーカイブのしくみ](lync-server-2013-how-archiving-works.md)」 を参照してください。

> [!NOTE]
> 展開で Microsoft Exchange 統合を有効にした場合に、Exchange 2013 に所属するユーザーに対してアーカイブが有効になるかどうかは Exchange インプレース保持ポリシーによって制御されます。これらのユーザーのアーカイブでは、ユーザーのメールボックスがインプレース保持の状態になっている必要があります。詳細については、「展開」のドキュメントの「<a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server 統合使用時に使用するアーカイブのポリシーの設定</a>」を参照してください。<br />
> アーカイブを有効にする前に、すべての該当するオプションをアーカイブ構成で指定する必要があります。詳細については、「展開」のドキュメントの「<a href="lync-server-2013-configuring-archiving-options.md">アーカイブ オプションの構成</a>」を参照してください。


## このセクション中

  - [Lync Server でのアーカイブ用のユーザー ポリシーの作成と構成](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [ユーザーへの Lync Server アーカイブ ポリシーの適用](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

