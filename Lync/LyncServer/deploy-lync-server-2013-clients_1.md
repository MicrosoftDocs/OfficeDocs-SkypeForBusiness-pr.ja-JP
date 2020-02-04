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
ms.openlocfilehash: ffc6ee3831968c34bcdb501fcdf543626546e2c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a>Lync Server 2013 クライアントを展開する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-19_

ユーザーを Lync Server 2013 に移行した後で、次の操作を行います。

1.  新しい Lync Server 2013 サーバーでクライアントバージョンフィルターを使用して、最新の更新プログラムがインストールされているクライアントのみがサインインに参加できるようにします。

2.  必要に応じて、クライアントブートストラップに必要なグループポリシー設定を構成します。 詳細については、展開ドキュメントの「 [Lync Server 2013 でのクライアントブートストラップポリシーの構成](lync-server-2013-configuring-client-bootstrapping-policies.md)」を参照してください。 これらの設定を構成する必要があるのは、既存のクライアントブートストラップポリシーを変更する場合、または新しいクライアントブートストラップポリシーを設定する場合のみです。 クライアントブートストラップポリシーの構成を計画していない場合、またはレガシクライアントブートストラップポリシーを引き続き有効にする必要がある場合は、何もする必要はありません。

3.  Lync Server 2013 コントロールパネル、Lync Server 2013 管理シェル、またはその両方を使用して、特定のユーザーまたはユーザーグループの他のユーザーとクライアントのポリシーを構成します。 詳細については、計画ドキュメントの「 [Lync 2013 の新しい設定と変更された設定](lync-server-2013-new-and-changed-settings-for-lync-2013.md)」を参照してください。

4.  最新バージョンの Lync Server 2013 クライアントと最新の累積更新プログラムを展開します。 詳細については、展開ドキュメントの「 [Lync Server 2013 でのクライアントとデバイスの展開](lync-server-2013-deploying-clients-and-devices.md)」を参照してください。

5.  省略組織で Lync Server 2013 強化されたプレゼンスプライバシーモードが必要な場合は、移行が完了した後で、以前のバージョンのクライアントでサインインできないように、クライアントのバージョンポリシールールを定義します。 次に、拡張プレゼンスプライバシーモードを有効にします。
    
    <div>
    

    > [!IMPORTANT]  
    > 特定のサーバープールのすべてのユーザーが最新のクライアントバージョンをインストールしているまで、Lync 2013 拡張プレゼンスプライバシーモードを有効にしないでください。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

