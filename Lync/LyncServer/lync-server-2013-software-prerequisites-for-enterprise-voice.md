---
title: 'Lync Server 2013: エンタープライズ VoIP のソフトウェア前提条件'
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
ms.openlocfilehash: cb85a8da9fe0d009f46ef23b919aeb9fd006fab4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 のエンタープライズ VoIP のソフトウェア前提条件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-03_

エンタープライズボイスを展開するインフラストラクチャが、次のソフトウェアの前提条件を満たしていることを確認します。

  - Lync Server 2013 Standard Edition または Enterprise Edition がネットワークにインストールされ、動作する。

  - すべてのエッジサーバーは、アクセスエッジサービスを実行するエッジサーバー、A/V Edge サービス、Web 会議エッジサービス、リバースプロキシなど、境界ネットワークで展開され、動作します。

  - Microsoft Exchange Server 2007 Service Pack 3 (SP3)、Microsoft Exchange Server 2010、または Microsoft Exchange Server 2013 は、Exchange ユニファイドメッセージングと Lync Server の統合、および詳細な通知の提供と、Lync のエンドポイント。

  - Lync Server の1人以上のユーザーが作成され、有効になっている。

  - Lync クライアントとデバイスが正常に展開されました。

  - トポロジビルダーは、ネットワーク上のサーバーにインストールされます。

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a>次の手順: セキュリティと構成の前提条件を確認する

エンタープライズ Voip のソフトウェア前提条件を確認した後、ドキュメントを使用して、エンタープライズ Voip の展開の準備を続けます。

1.  「 [Lync Server 2013 でのエンタープライズ voip のセキュリティと構成の前提条件](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md)」の説明に従って、セキュリティ、ユーザーの構成、ハードウェアの条件を確認します。

2.  「 [Lync server 2013 に「仲介サーバー用のファイルをインストール](lync-server-2013-install-the-files-for-mediation-server.md)する」の説明に従って、仲介サーバーをインストールします。ただし、仲介された場合は、仲介サーバーがフロントエンドプールまたは Standard Edition サーバー展開プロセスの一環としてインストールされている*ためです。*

3.  「 [Lync Server 2013 での trunks の構成](lync-server-2013-configuring-trunks.md)」で説明されているように、トランク接続を構成してユーザーに PSTN 接続を提供します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

