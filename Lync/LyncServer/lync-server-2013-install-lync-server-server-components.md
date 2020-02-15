---
title: 'Lync Server 2013: Lync Server サーバーコンポーネントのインストール'
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
ms.openlocfilehash: 180e9c1892b1c296247cfc9dd3ab7a67972e9606
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-server-components-for-lync-server-2013"></a>Lync Server 2013 のサーバーコンポーネントのインストール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-05-05_

これらの手順を実行する前に、ローカル管理者および Active Directory の RTCUniversalReadOnlyAdmins グループのメンバーの両方であるドメインユーザーアカウントを使用してサーバーにログオンしていることを確認してください。

Lync server 展開ウィザードを使用して、各 Lync server の役割に必要なコンポーネントをインストールし、サーバーをアクティブ化します。 この記事では、Lync インフラストラクチャに Standard Edition サーバーまたはフロントエンドサーバーを展開する手順について説明します。

<div>

## <a name="to-install-lync-server-components"></a>Lync Server コンポーネントをインストールするには

1.  Lync Server 展開ウィザードが実行されていない場合は、Lync をインストールするサーバー上で開始します。

2.  [ **Lync Server システムのインストールまたは更新**] をクリックします。

3.  展開ウィザードで、[**ステップ 1: ローカル構成ストアのインストール**] に緑のチェックマークが付いていることを確認します。つまり、このサーバーには、ストアのローカルコピーが正常にインストールされています。 チェックされていない場合は、ローカル構成ストアをサーバーにインストールする必要があります。 「 [Lync Server 2013 のローカル構成ストアをインストールする」](lync-server-2013-install-the-local-configuration-store.md)の手順に従って、ここに戻ってください。

4.  サーバーに Lync Server 2013 コンポーネントをインストールする準備ができたら、[**手順 2: Lync Server コンポーネントのセットアップまたは削除**] の横にある [**実行**] をクリックします。

5.  [ **Lync Server コンポーネント**のセットアップ] ページで、[**次へ**] をクリックして、公開したトポロジで定義されているようにコンポーネントを設定します。

6.  [**コマンドの実行**] ページには、セットアップが行われたときに、コマンドとインストール情報の概要が表示されます。 完了したら、一覧を使用して表示するログを選択し、[**ログの表示**] をクリックします。

7.  Lync Server 2013 コンポーネントのセットアップが完了し、必要に応じてログを確認した後、[**完了**] をクリックして、インストールでこの手順を完了します。
    
    <div>
    

    > [!NOTE]  
    > サーバーを再起動するように求めるメッセージが表示された場合 (Windows デスクトップのインストールが必要な場合があります)、そのことを必ずお勧めします。 コンピューターがバックアップされて実行されている場合は、上記のステップ3から始めて、上記の手順を再度実行する必要があります (展開ウィザードで手順2をもう一度実行してください)。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

