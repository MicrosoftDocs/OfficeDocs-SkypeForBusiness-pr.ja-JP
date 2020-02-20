---
title: 'Lync Server 2013: エンタープライズ Voip のソフトウェア前提条件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Software prerequisites for Enterprise Voice
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48183960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36ec427751fc6593f03af11bfecddf3bd0bb6280
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 のエンタープライズ Voip のソフトウェア前提条件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-03_

エンタープライズ VoIP を展開するインフラストラクチャで、次のソフトウェア前提条件が満たされることを確認します。

  - Lync Server 2013 Standard Edition または Enterprise Edition がインストールされており、ネットワーク上で運用できます。

  - エッジサーバーはすべて、アクセスエッジサービスを実行しているエッジサーバー、音声ビデオエッジサービス、Web 会議エッジサービス、リバースプロキシなど、境界ネットワークに展開され、動作しています。

  - Microsoft Exchange Server 2007 Service Pack 3 (SP3)、Microsoft Exchange Server 2010、または Microsoft Exchange Server 2013 は、Exchange ユニファイドメッセージングと Lync Server を統合し、豊富な通知を提供して、ログ情報を呼び出してLync エンドポイント。

  - 1人以上のユーザーが作成され、Lync Server に対して有効になっています。

  - Lync クライアントとデバイスが正常に展開されました。

  - トポロジビルダーは、ネットワーク上のサーバーにインストールされます。

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a>次のステップ: セキュリティおよび構成の前提条件の確認

エンタープライズ VoIP のソフトウェア前提条件を確認したら、ドキュメントを使用してエンタープライズ VoIP 展開の準備を続行できます。

1.  「 [Lync Server 2013 のエンタープライズ voip のセキュリティおよび構成の前提条件](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md)」で説明されているように、セキュリティ、ユーザー構成、およびハードウェアの前提条件を確認します。

2.  「 [Lync server 2013 の仲介サーバーのファイル](lync-server-2013-install-the-files-for-mediation-server.md)をインストールする」の説明に従って、仲介サーバーをインストールします。これは、仲介サーバーがフロントエンドプールまたは Standard Edition サーバー展開プロセスの一部としてインストールされているためで、スタンドアロンの仲介サーバーまたはプールを展開する場合に*限ら*れます。

3.  「Configure[トランク In Lync Server 2013](lync-server-2013-configuring-trunks.md)」で説明されているように、トランク接続を構成してユーザーに PSTN 接続を提供します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

