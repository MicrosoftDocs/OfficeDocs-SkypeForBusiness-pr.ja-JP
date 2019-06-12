---
title: 'Lync Server 2013: エンタープライズ VoIP のソフトウェア前提条件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Software prerequisites for Enterprise Voice
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48183960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ac981d7a30a85d25d2dfb376cfa34f812e898bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="b8c5f-102">Lync Server 2013 のエンタープライズ VoIP のソフトウェア前提条件</span><span class="sxs-lookup"><span data-stu-id="b8c5f-102">Software prerequisites for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8c5f-103">_**最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="b8c5f-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="b8c5f-104">エンタープライズボイスを展開するインフラストラクチャが、次のソフトウェアの前提条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b8c5f-104">Verify that the infrastructure in which you intend to deploy Enterprise Voice meets the following software prerequisites:</span></span>

  - <span data-ttu-id="b8c5f-105">Lync Server 2013 Standard Edition または Enterprise Edition がネットワークにインストールされ、動作する。</span><span class="sxs-lookup"><span data-stu-id="b8c5f-105">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="b8c5f-106">すべてのエッジサーバーは、アクセスエッジサービスを実行するエッジサーバー、A/V Edge サービス、Web 会議エッジサービス、リバースプロキシなど、境界ネットワークで展開され、動作します。</span><span class="sxs-lookup"><span data-stu-id="b8c5f-106">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers running Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="b8c5f-107">Microsoft Exchange Server 2007 Service Pack 3 (SP3)、Microsoft Exchange Server 2010、または Microsoft Exchange Server 2013 は、Exchange ユニファイドメッセージングと Lync Server の統合、および詳細な通知の提供と、Lync のエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="b8c5f-107">Either Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 or Microsoft Exchange Server 2013 is required for integrating Exchange Unified Messaging with Lync Server and to provide rich notifications and call log information to the Lync endpoints.</span></span>

  - <span data-ttu-id="b8c5f-108">Lync Server の1人以上のユーザーが作成され、有効になっている。</span><span class="sxs-lookup"><span data-stu-id="b8c5f-108">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="b8c5f-109">Lync クライアントとデバイスが正常に展開されました。</span><span class="sxs-lookup"><span data-stu-id="b8c5f-109">Lync clients and devices have been successfully deployed.</span></span>

  - <span data-ttu-id="b8c5f-110">トポロジビルダーは、ネットワーク上のサーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b8c5f-110">Topology Builder is installed on a server on your network.</span></span>

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a><span data-ttu-id="b8c5f-111">次の手順: セキュリティと構成の前提条件を確認する</span><span class="sxs-lookup"><span data-stu-id="b8c5f-111">Next Steps: Verify Security and Configuration Prerequisites</span></span>

<span data-ttu-id="b8c5f-112">エンタープライズ Voip のソフトウェア前提条件を確認した後、ドキュメントを使用して、エンタープライズ Voip の展開の準備を続けます。</span><span class="sxs-lookup"><span data-stu-id="b8c5f-112">After verifying software prerequisites for Enterprise Voice, you can use the documentation to continue preparing for deploying Enterprise Voice:</span></span>

1.  <span data-ttu-id="b8c5f-113">「 [Lync Server 2013 でのエンタープライズ voip のセキュリティと構成の前提条件](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md)」の説明に従って、セキュリティ、ユーザーの構成、ハードウェアの条件を確認します。</span><span class="sxs-lookup"><span data-stu-id="b8c5f-113">Verify security, user configuration, and hardware perquisites, as described in [Security and configuration prerequisites for Enterprise Voice in Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).</span></span>

2.  <span data-ttu-id="b8c5f-114">「 [Lync server 2013 に「仲介サーバー用のファイルをインストール](lync-server-2013-install-the-files-for-mediation-server.md)する」の説明に従って、仲介サーバーをインストールします。ただし、仲介サーバーがフロントエンドプールの一部としてインストールされているため、スタンドアロンの仲介サーバーまたはプールを展開する場合に*限り*ます。併置されている場合は、Standard Edition サーバー展開プロセス。</span><span class="sxs-lookup"><span data-stu-id="b8c5f-114">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but *only* if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

3.  <span data-ttu-id="b8c5f-115">「 [Lync Server 2013 での trunks の構成](lync-server-2013-configuring-trunks.md)」で説明されているように、トランク接続を構成してユーザーに PSTN 接続を提供します。</span><span class="sxs-lookup"><span data-stu-id="b8c5f-115">Configure trunk connections to provide PSTN connectivity for users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

