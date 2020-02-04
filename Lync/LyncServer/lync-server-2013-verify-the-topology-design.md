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
ms.openlocfilehash: 85266477df342c16ed69c0507813b905c608745c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-the-topology-design-in-lync-server-2013"></a>Lync Server 2013 でのトポロジ設計の確認

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-01-02_

トポロジビルダーは、トポロジを自動的に確認します。 トポロジエラーは検証エラーとして識別され、サーバーの役割の横に表示される検証エラーアイコンによって示されます。 トポロジが配置のトポロジを正しく表すことも確認することが重要です。

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a>公開前にトポロジを確認するには

1.  すべての簡易 URL が正しく構成されていることを確認します。

2.  SQL Server ベースのサーバーがオンラインになっていることを確認します。また、トポロジ ビルダーがインストールされているコンピューターでこのサーバーが使用できることを確認します。必要なファイアウォール規則などを確認してください。

3.  ファイル共有が使用可能であり、適切なアクセス許可が定義されていることを確認します。

4.  トポロジで、展開要件を満たす正しいサーバーの役割が定義されていることを確認します。

5.  サーバーが Active Directory ドメインサービスに存在することを確認します。 この問題は、サーバーをドメインに参加している場合に自動的に発生します。

トポロジの検証が完了して検証エラーがないことが確認できたら、トポロジの公開の準備に移ります。 検証エラーがある場合は、トポロジを公開する前に修正する必要があります。 トポロジの公開について詳しくは、「 [Lync Server 2013 でトポロジを発行する](lync-server-2013-publish-the-topology.md)」をご覧ください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

