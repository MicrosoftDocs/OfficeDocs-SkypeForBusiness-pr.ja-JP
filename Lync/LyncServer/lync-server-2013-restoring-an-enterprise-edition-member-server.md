---
title: 'Lync Server 2013: Enterprise Edition のメンバーサーバーを復元する'
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
ms.openlocfilehash: e870b68d1252ea5a203b3c334299fb65b6a56512
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a>Lync Server 2013 で Enterprise Edition メンバーサーバーを復元する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-18_

次のいずれかのサーバーの役割を実行しているサーバーで障害が発生した場合は、このトピックの手順に従ってサーバーを復元します。 複数のサーバーが個別に失敗した場合は、各サーバーの手順に従います。

  - フロントエンド サーバー

  - 仲介サーバー

  - ディレクター

  - 常設チャット サーバー

  - エッジ サーバー

<div>


> [!TIP]  
> 復元を開始する前に、システムのイメージコピーを取得することをお勧めします。 復元中に問題が発生した場合に備えて、この画像をロールバックポイントとして使うことができます。 オペレーティングシステムと SQL Server をインストールした後に画像のコピーを取得し、証明書を復元または reenroll することができます。



</div>

<div>

## <a name="to-restore-a-member-server"></a>メンバーサーバーを復元するには

1.  障害が発生したサーバーと同じ完全修飾ドメイン名 (FQDN) を持つクリーンまたは新しいサーバーを起動し、オペレーティングシステムをインストールして、証明書を復元または reenroll します。
    
    <div>
    

    > [!NOTE]  
    > 組織のサーバー展開手順に従って、この手順を実行します。

    
    </div>

2.  RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、復元しているサーバーにログオンします。

3.  Lync Server のインストールフォルダーまたはメディアを参照し、セットアップ\\\\Amd64\\Setup.exe で [lync server 展開ウィザード] を起動します。

4.  展開ウィザードの指示に従って、次の操作を行います。
    
    1.  **手順 1: ローカル構成ストアをインストール**して、ローカル構成ファイルをインストールします。
    
    2.  **手順 2: lync server のコンポーネントをセットアップまたは削除**して lync server server の役割をインストールする
    
    3.  手順 3: 証明書を割り当てるために**証明書を要求、インストール、または割り当て**ます。
    
    4.  **手順 4: サービスを開始**して、サーバー上のサービスを開始します。
    
    展開ウィザードの実行の詳細については、復元するサーバーの役割の展開ドキュメントを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

