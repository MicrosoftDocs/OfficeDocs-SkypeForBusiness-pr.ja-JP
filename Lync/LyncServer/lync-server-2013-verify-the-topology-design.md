---
title: 'Lync Server 2013: トポロジ設計の確認'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 361713c22842abee7de1d8e29de498f4d4ad5cc7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-the-topology-design-in-lync-server-2013"></a>Lync Server 2013 でのトポロジ設計の確認

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-01-02_

トポロジビルダーは、トポロジを自動的に確認します。 トポロジ エラーはすべて検証エラーとして特定され、サーバー役割の横に検証エラー アイコンを表示して示されます。 トポロジが展開のトポロジを正しく表しているかどうかを検証することも大切です。

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a>公開の前にトポロジを検証するには

1.  すべての簡易 URL が正しく構成されていることを確認します。

2.  SQL Server ベースのサーバーがオンラインになっていること、およびトポロジビルダーがインストールされているコンピューターで使用できることを確認します (必要なファイアウォール規則も含めます)。

3.  ファイル共有が使用可能であり、適切なアクセス許可が定義されていることを確認します。

4.  トポロジで、展開要件を満たす正しいサーバーの役割が定義されていることを確認します。

5.  サーバーが Active Directory ドメインサービスに存在することを確認します。 サーバーをドメインに加えている場合、これは自動で確認されます。

トポロジの検証が完了して検証エラーがないことが確認できたら、トポロジの公開の準備に移ります。 検証エラーがある場合は、エラーを修正してからでないとトポロジは公開できません。 トポロジの公開の詳細については、「 [Lync Server 2013 でトポロジを公開する](lync-server-2013-publish-the-topology.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

