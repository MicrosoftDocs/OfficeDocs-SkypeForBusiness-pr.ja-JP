---
title: 'Lync Server 2013: Enterprise Edition メンバーサーバーの復元'
description: 'Lync Server 2013: Enterprise Edition メンバーサーバーの復元。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f9838f030205d92988e185798d982f835122c9f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576053"
---
# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a>Lync Server 2013 での Enterprise Edition メンバーサーバーの復元

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-18_

次のいずれかのサーバーの役割を実行しているサーバーで障害が発生した場合は、このトピックの手順に従ってサーバーを復元します。 複数のサーバーで個別に障害が発生した場合は、各サーバーで手順を実行します。

  - フロント エンド サーバー

  - 仲介サーバー

  - ディレクター

  - 常設チャット サーバー

  - エッジ サーバー

<div>


> [!TIP]  
> 復元を開始する前に、システムのイメージコピーを取得することをお勧めします。 復元中に問題が発生した場合に備えて、このイメージをロールバックポイントとして使用できます。 オペレーティングシステムと SQL Server をインストールした後、画像コピーを取得し、証明書を復元または reenroll することができます。



</div>

<div>

## <a name="to-restore-a-member-server"></a>メンバー サーバーを復元するには

1.  障害が発生したサーバーと同じ完全修飾ドメイン名 (FQDN) を持つクリーンサーバーまたは新しいサーバーを起動し、オペレーティングシステムをインストールしてから、証明書を復元または reenroll します。
    
    <div>
    

    > [!NOTE]  
    > 組織で定めるサーバーの展開手順に従って、この手順を実行します。

    
    </div>

2.  RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、復元するサーバーにログオンします。

3.  Lync Server インストールフォルダーまたはメディアを参照し、セットアップ amd64Setup.exe にある Lync Server 展開ウィザードを起動し \\ \\ \\ ます。

4.  展開ウィザードに従って、次の操作を行います。
    
    1.  [**ステップ 1: ローカル構成ストアのインストール**] を実行して、ローカル構成ファイルをインストールします。
    
    2.  [ **ステップ 2: lync Server コンポーネントのセットアップまたは削除** を実行して、lync server のサーバーの役割をインストールする」を実行します。
    
    3.  [**ステップ 3: 証明書の要求、インストール、または割り当て**] を実行して、証明書を割り当てます。
    
    4.  [**ステップ 4: サービスの開始**] を実行して、サーバー上でサービスを開始します。
    
    展開ウィザードの実行の詳細については、「展開」のドキュメントの「復元」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

