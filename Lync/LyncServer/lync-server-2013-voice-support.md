---
title: Lync Server 2013 音声サポート
description: Lync Server 2013 音声サポート。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice support
ms:assetid: d151caa8-2ee4-4bfa-be53-428570aae1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398896(v=OCS.15)
ms:contentKeyID: 48185436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b97b8e5ade1d97d458117adc04f161077abc9beb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554013"
---
# <a name="voice-support-in-lync-server-2013"></a><span data-ttu-id="9bc1b-103">Lync Server 2013 での音声のサポート</span><span class="sxs-lookup"><span data-stu-id="9bc1b-103">Voice support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9bc1b-104">_**トピックの最終更新日:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="9bc1b-104">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="9bc1b-105">展開にフロントエンドプールが含まれている場合は、Microsoft によって提供される VoIP (Voice over IP) ソリューションであるエンタープライズ voip のサポートを展開できます。</span><span class="sxs-lookup"><span data-stu-id="9bc1b-105">If your deployment includes a Front End pool, you can deploy support for Enterprise Voice, the Voice over IP (VoIP) solution offered by Microsoft.</span></span> <span data-ttu-id="9bc1b-106">ボイスオーバー IP (VoIP) は、従来の PBX ベーステレフォニーに代わるソフトウェアベースの代替手段です。</span><span class="sxs-lookup"><span data-stu-id="9bc1b-106">Voice over IP (VoIP) is a software-based alternative to traditional PBX-based telephony.</span></span> <span data-ttu-id="9bc1b-107">VoIP 通話の操作性は従来のテレフォニーの動作に似ていますが、エンタープライズ Voip には、より高度なコミュニケーションとコラボレーションを可能にする機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9bc1b-107">Although the VoIP call experience is similar to the traditional telephony experience, Enterprise Voice includes features that enable richer communication and collaboration.</span></span> <span data-ttu-id="9bc1b-108">たとえば、エンタープライズ Voip 展開を構成して、Lync 2013 および Lync Phone Edition ユーザーが組織のアドレス帳の連絡先の拡張プレゼンス情報または場所情報を表示できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="9bc1b-108">For example, your Enterprise Voice deployment can be configured to make it possible for Lync 2013 and Lync Phone Edition users to view enhanced presence information or location information for contacts in your organization’s address book.</span></span> <span data-ttu-id="9bc1b-109">Lync Server 2013 の一部の機能は、他の Lync Server 2013 ワークロードと Exchange ユニファイドメッセージング (UM) との統合によって有効になります。</span><span class="sxs-lookup"><span data-stu-id="9bc1b-109">Some Lync Server 2013 features are enabled through integration with other Lync Server 2013 workloads and with Exchange Unified Messaging (UM).</span></span> <span data-ttu-id="9bc1b-110">エンタープライズ Voip で使用できる機能、および展開を計画する方法の詳細については、「計画」のドキュメントの「 [planning For Enterprise voice In Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bc1b-110">For details about the features and functionality available with Enterprise Voice and how to plan for deployment, see [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9bc1b-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9bc1b-111">In This Section</span></span>

  - [<span data-ttu-id="9bc1b-112">Lync Server 2013 での SIP トランキングのサポート</span><span class="sxs-lookup"><span data-stu-id="9bc1b-112">SIP trunking support in Lync Server 2013</span></span>](lync-server-2013-sip-trunking-support.md)

  - [<span data-ttu-id="9bc1b-113">Lync Server 2013 での直接 SIP 接続のサポート</span><span class="sxs-lookup"><span data-stu-id="9bc1b-113">Direct SIP connections support in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections-support.md)

  - [<span data-ttu-id="9bc1b-114">Lync Server 2013 での Exchange ユニファイドメッセージング (UM) のサポート</span><span class="sxs-lookup"><span data-stu-id="9bc1b-114">Exchange Unified Messaging (UM) support in Lync Server 2013</span></span>](lync-server-2013-exchange-unified-messaging-um-support.md)

  - [<span data-ttu-id="9bc1b-115">Lync Server 2013 での E9-1-1 のサポート</span><span class="sxs-lookup"><span data-stu-id="9bc1b-115">E9-1-1 support in Lync Server 2013</span></span>](lync-server-2013-e9-1-1-support.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

