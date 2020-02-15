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
ms.openlocfilehash: dc6c5e5f3f9fc92f56ee1f044419f67f5ded32ce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "41987022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="619a3-102">Lync Server 2013 のエンタープライズ Voip のソフトウェア前提条件</span><span class="sxs-lookup"><span data-stu-id="619a3-102">Software prerequisites for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="619a3-103">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="619a3-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="619a3-104">エンタープライズ VoIP を展開するインフラストラクチャで、次のソフトウェア前提条件が満たされることを確認します。</span><span class="sxs-lookup"><span data-stu-id="619a3-104">Verify that the infrastructure in which you intend to deploy Enterprise Voice meets the following software prerequisites:</span></span>

  - <span data-ttu-id="619a3-105">Lync Server 2013 Standard Edition または Enterprise Edition がインストールされており、ネットワーク上で運用できます。</span><span class="sxs-lookup"><span data-stu-id="619a3-105">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="619a3-106">エッジサーバーはすべて、アクセスエッジサービスを実行しているエッジサーバー、音声ビデオエッジサービス、Web 会議エッジサービス、リバースプロキシなど、境界ネットワークに展開され、動作しています。</span><span class="sxs-lookup"><span data-stu-id="619a3-106">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers running Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="619a3-107">Microsoft Exchange Server 2007 Service Pack 3 (SP3)、Microsoft Exchange Server 2010、または Microsoft Exchange Server 2013 は、Exchange ユニファイドメッセージングと Lync Server を統合し、豊富な通知を提供して、ログ情報を呼び出してLync エンドポイント。</span><span class="sxs-lookup"><span data-stu-id="619a3-107">Either Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 or Microsoft Exchange Server 2013 is required for integrating Exchange Unified Messaging with Lync Server and to provide rich notifications and call log information to the Lync endpoints.</span></span>

  - <span data-ttu-id="619a3-108">1人以上のユーザーが作成され、Lync Server に対して有効になっています。</span><span class="sxs-lookup"><span data-stu-id="619a3-108">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="619a3-109">Lync クライアントとデバイスが正常に展開されました。</span><span class="sxs-lookup"><span data-stu-id="619a3-109">Lync clients and devices have been successfully deployed.</span></span>

  - <span data-ttu-id="619a3-110">トポロジビルダーは、ネットワーク上のサーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="619a3-110">Topology Builder is installed on a server on your network.</span></span>

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a><span data-ttu-id="619a3-111">次のステップ: セキュリティおよび構成の前提条件の確認</span><span class="sxs-lookup"><span data-stu-id="619a3-111">Next Steps: Verify Security and Configuration Prerequisites</span></span>

<span data-ttu-id="619a3-112">エンタープライズ VoIP のソフトウェア前提条件を確認したら、ドキュメントを使用してエンタープライズ VoIP 展開の準備を続行できます。</span><span class="sxs-lookup"><span data-stu-id="619a3-112">After verifying software prerequisites for Enterprise Voice, you can use the documentation to continue preparing for deploying Enterprise Voice:</span></span>

1.  <span data-ttu-id="619a3-113">「 [Lync Server 2013 のエンタープライズ voip のセキュリティおよび構成の前提条件](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md)」で説明されているように、セキュリティ、ユーザー構成、およびハードウェアの前提条件を確認します。</span><span class="sxs-lookup"><span data-stu-id="619a3-113">Verify security, user configuration, and hardware perquisites, as described in [Security and configuration prerequisites for Enterprise Voice in Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).</span></span>

2.  <span data-ttu-id="619a3-114">「 [Lync server 2013 の仲介サーバーのファイル](lync-server-2013-install-the-files-for-mediation-server.md)をインストールする」の説明に従って、仲介サーバーをインストールします。これは、仲介サーバーがフロントエンドプールまたは Standard Edition サーバー展開プロセスの一部としてインストールされているためで、スタンドアロンの仲介サーバーまたはプールを展開する場合に*限ら*れます。</span><span class="sxs-lookup"><span data-stu-id="619a3-114">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but *only* if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

3.  <span data-ttu-id="619a3-115">「Configure[トランク In Lync Server 2013](lync-server-2013-configuring-trunks.md)」で説明されているように、トランク接続を構成してユーザーに PSTN 接続を提供します。</span><span class="sxs-lookup"><span data-stu-id="619a3-115">Configure trunk connections to provide PSTN connectivity for users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

