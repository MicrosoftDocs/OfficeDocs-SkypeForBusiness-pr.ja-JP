---
title: Lync Server 2013 クライアントを展開する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48184100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 331241dea4f047928913550764c995a7c6f05260
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a>Lync Server 2013 クライアントを展開する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-19_

ユーザーを Lync Server 2013 に移行した後、次の手順を実行します。

1.  新しい Lync Server 2013 サーバーでクライアントバージョンフィルターを使用して、最新の更新プログラムがインストールされているクライアントのみがサインインできるようにします。

2.  必要に応じて、クライアントのブートストラップに必要なグループ ポリシー設定を構成します。 詳細については、「展開」のドキュメントの「 [Lync Server 2013 でのクライアントブートストラップポリシーの構成](lync-server-2013-configuring-client-bootstrapping-policies.md)」を参照してください。 これらの設定の構成は、既存のクライアント ブートストラップ ポリシーの変更または新しいクライアント ブートストラップ ポリシーの作成を行う場合にのみ必要です。 クライアント ブートストラップ ポリシーを構成する予定がない場合や、従来のクライアント ブートストラップ ポリシーをそのまま有効にしておく場合、何もする必要はありません。

3.  Lync Server 2013 コントロールパネル、Lync Server 2013 管理シェル、またはその両方を使用して、特定のユーザーまたはユーザーグループに対して他のユーザーおよびクライアントポリシーを構成します。 詳細については、「計画」のドキュメントの「 [Lync 2013 の新しい設定と変更された設定](lync-server-2013-new-and-changed-settings-for-lync-2013.md)」を参照してください。

4.  最新バージョンの Lync Server 2013 クライアントを最新の累積的な更新プログラムと共に展開します。 詳細については、「展開」のドキュメントの「 [Lync Server 2013 でのクライアントとデバイスの展開](lync-server-2013-deploying-clients-and-devices.md)」を参照してください。

5.  オプション組織で Lync Server 2013 の拡張プレゼンスプライバシーモードが必要な場合は、移行の完了後に、以前のクライアントバージョンがサインインできないようにするためのクライアントバージョンポリシールールを定義します。 その後、拡張プレゼンスのプライバシー モードを有効にします。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync 2013 enhanced プレゼンスプライバシーモードを有効にしないでください。特定のサーバープールのすべてのユーザーには、最新のクライアントバージョンがインストールされています。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

