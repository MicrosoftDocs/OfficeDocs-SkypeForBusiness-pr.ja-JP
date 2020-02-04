---
title: 'Lync Server 2013: Lync Server のサーバー コンポーネントのインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server server components
ms:assetid: 186aed6e-7adf-4a92-9f2e-f9a4de5ff202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398239(v=OCS.15)
ms:contentKeyID: 48183528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f039f9363469663410f08f078a3b7e17a170075
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-server-components-for-lync-server-2013"></a>Lync Server 2013 のサーバー コンポーネントのインストール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-05-05_

以下の手順を実行する前に、ローカル管理者と、Active Directory の RTCUniversalReadOnlyAdmins グループのメンバーの両方のドメインユーザーアカウントでサーバーにログオンしていることを確認してください。

Lync Server 展開ウィザードを使って、各 Lync server の役割に必要なコンポーネントをインストールし、サーバーをアクティブ化します。 この記事では、Lync インフラストラクチャに Standard Edition サーバーまたはフロントエンドサーバーを展開する手順について説明します。

<div>

## <a name="to-install-lync-server-components"></a>Lync Server コンポーネントをインストールするには

1.  Lync Server 展開ウィザードが実行されていない場合は、Lync をインストールするサーバーで起動します。

2.  [ **Lync Server System のインストールまたは更新**] をクリックします。

3.  展開ウィザードで、[**手順 1: ローカル構成ストアをインストール**する] が緑のチェックマークであることを確認します。つまり、このサーバーには、ストアのローカルコピーが正常にインストールされていることを意味します。 オンになっていない場合は、サーバーにローカル構成ストアをインストールする必要があります。 「 [Lync Server 2013 でローカル構成ストアをインストールする」](lync-server-2013-install-the-local-configuration-store.md)の手順に従って、ここに戻ります。

4.  サーバーに Lync Server 2013 コンポーネントをインストールする準備ができたら、「**手順 2: Lync Server コンポーネントをセットアップまたは削除**する」の横にある [**実行**] をクリックします。

5.  [ **Lync Server コンポーネントのセットアップ**] ページで、[**次**へ] をクリックして、公開したトポロジで定義されたコンポーネントをセットアップします。

6.  [**コマンドの実行**] ページには、セットアップが行われるときのコマンドとインストール情報の概要が表示されます。 終了したら、表示するログをリストから選び、[**ログの表示**] をクリックします。

7.  Lync Server 2013 コンポーネントのセットアップが完了し、必要に応じてログを確認したら、[**完了**] をクリックして、インストールの手順を完了します。
    
    <div>
    

    > [!NOTE]  
    > サーバーを再起動するように求めるメッセージが表示された場合 (インストールする必要がある場合に発生する場合があります) は、そのようなことをお勧めします。 コンピューターがバックアップされて実行されている場合は、上記の手順3を実行してから、上記の手順をもう一度実行する必要があります (基本的に、展開ウィザードで手順2を実行します)。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

