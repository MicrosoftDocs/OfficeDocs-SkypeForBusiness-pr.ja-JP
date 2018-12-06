---
title: Exchange Server 統合使用時に使用するアーカイブのポリシーの設定
TOCTitle: Exchange Server 統合使用時に使用するアーカイブのポリシーの設定
ms:assetid: 8b9b2bad-a4b3-42e1-85a7-04022e9442ad
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205063(v=OCS.15)
ms:contentKeyID: 48272773
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exchange Server 統合使用時に使用するアーカイブのポリシーの設定

 

_**トピックの最終更新日:** 2012-10-09_

Exchange 2013 に所属するユーザーのメールボックスがインプレース保持されている場合、Exchange インプレース保持ポリシーにより、これらのユーザーのアーカイブが制御されます。展開に Microsoft Exchange 統合を使用する場合、Exchange 2013 に所属するユーザーに対しては、Exchange 2013 ポリシーが Lync Server アーカイブ ポリシーよりも優先されます。Exchange アーカイブ ポリシーの構成については、Exchange 2013 のドキュメントを参照してください。Lync Server 2013 に所属するユーザーに対するユーザー ポリシーの設定の詳細については、「展開」のドキュメントの「[Lync Server でのアーカイブのユーザー ポリシーの設定](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)」を参照してください。ポリシーの効果の詳細については、「計画」のドキュメント、「展開」のドキュメント、または「操作」のドキュメントの「[Lync Server 2013 でのアーカイブのしくみ](lync-server-2013-how-archiving-works.md)」を参照してください。

> [!NOTE]
> Exchange 2013 と Lync Server 2013 を同じフォレストに展開した場合、Exchange 2013 インプレース保持ポリシーがアーカイブを制御します。Exchange 2013 と Lync Server 2013 がそれぞれ別のフォレストに展開した場合は、「<a href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 のアーカイブの展開チェックリスト</a>」の「Deploying Lync Server and Microsoft Exchange in Different Forests」を参照してください。

