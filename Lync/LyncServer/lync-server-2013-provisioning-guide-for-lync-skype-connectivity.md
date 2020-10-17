---
title: 'Lync Server 2013: Lync-Skype 接続のプロビジョニングガイド'
description: 'Lync Server 2013: Lync-Skype 接続のプロビジョニングガイド。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Provisioning guide for Lync-Skype connectivity
ms:assetid: 69adda9b-5b72-4538-9be6-079b2f462e09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440173(v=OCS.15)
ms:contentKeyID: 57793363
ms.date: 11/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9859a7a621ba4329fe0436fe50a0d9de1d0ae1ef
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569093"
---
# <a name="provisioning-guide-for-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="c9ad9-103">Lync Server 2013 での Lync-Skype 接続のプロビジョニングガイド</span><span class="sxs-lookup"><span data-stu-id="c9ad9-103">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9ad9-104">_**トピックの最終更新日:** 2014-11-26_</span><span class="sxs-lookup"><span data-stu-id="c9ad9-104">_**Topic Last Modified:** 2014-11-26_</span></span>

<span data-ttu-id="c9ad9-105">Lync Server 2013 は、Skype との接続をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c9ad9-105">Lync Server 2013 supports connectivity with Skype.</span></span> <span data-ttu-id="c9ad9-106">この接続により、Lync 2013 ユーザーは Skype ユーザーの Microsoft アカウント (MSA) を使用して Skype 連絡先を追加できます。</span><span class="sxs-lookup"><span data-stu-id="c9ad9-106">This connectivity enables your Lync 2013 users to add Skype contacts by using the Skype user’s Microsoft Account (MSA).</span></span> <span data-ttu-id="c9ad9-107">Skype クライアントは、Lync ユーザーを連絡先リストに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="c9ad9-107">Skype clients can also add Lync users to their contact list.</span></span> <span data-ttu-id="c9ad9-108">Lync Server で管理上設定されたポリシーに基づいて、Lync および Skype ユーザーはインスタントメッセージングを使用して通信したり、お互いのプレゼンスを確認したり、音声およびビデオ通話を開始したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="c9ad9-108">Based on policies administratively set in Lync Server, Lync and Skype users will be able to communicate using instant messaging, see each other’s presence, and initiate audio and video calls.</span></span> <span data-ttu-id="c9ad9-109">Lync-Skype 接続は Lync Online の機能でもあり、Microsoft 365 管理センター内の Lync 管理センターから Lync Online の顧客に対して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c9ad9-109">Lync-Skype connectivity is also a feature of Lync Online, and can be enabled for Lync Online customers from the Lync Administration Center within the Microsoft 365 admin center.</span></span>

<div>

> [!IMPORTANT]  
> <span data-ttu-id="c9ad9-110">Lync Server がパブリックインスタントメッセージング接続 (PIC) を使用して Windows Messenger と接続するように既に構成されている場合、展開は既に Lync-Skype 接続用に構成されています。</span><span class="sxs-lookup"><span data-stu-id="c9ad9-110">If Lync Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Lync-Skype connectivity.</span></span> <span data-ttu-id="c9ad9-111">検討する必要があるのは、既存の Messenger PIC エントリの名前を Skype に変更することだけです。</span><span class="sxs-lookup"><span data-stu-id="c9ad9-111">The only change you may want to consider is to rename your existing Messenger PIC entry as Skype.</span></span> <span data-ttu-id="c9ad9-112">詳細については、このガイドの「Lync の Skype PIC プロバイダー設定を構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9ad9-112">For details, see Configure the Skype PIC provider setting for Lync later in this guide.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c9ad9-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c9ad9-113">In This Section</span></span>

  - [<span data-ttu-id="c9ad9-114">Lync Online のお客様のための Lync Server 2013 の接続の Lync-Skype に関する注意</span><span class="sxs-lookup"><span data-stu-id="c9ad9-114">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>](lync-server-2013-note-about-lync-skype-connectivity-for-lync-on.md)

  - [<span data-ttu-id="c9ad9-115">Lync server 2013 からの Lync Server パブリック IM 接続プロビジョニングサイトへのアクセス</span><span class="sxs-lookup"><span data-stu-id="c9ad9-115">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>](lync-server-2013-accessing-the-lync-server-public-im-connectivity-provisioning-site.md)

  - [<span data-ttu-id="c9ad9-116">Lync Server 2013 での Lync-Skype 接続の有効化</span><span class="sxs-lookup"><span data-stu-id="c9ad9-116">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-enabling-lync-skype-connectivity.md)

  - [<span data-ttu-id="c9ad9-117">エンドユーザーとしての Lync Server 2013 での Lync-Skype 接続の使用</span><span class="sxs-lookup"><span data-stu-id="c9ad9-117">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

  - [<span data-ttu-id="c9ad9-118">よく寄せられる質問: Lync Server 2013 を Skype 接続用にプロビジョニングする</span><span class="sxs-lookup"><span data-stu-id="c9ad9-118">Frequently Asked Questions: Provisioning Lync Server 2013 for Skype connectivity</span></span>](lync-server-2013-frequently-asked-questions-provisioning-lync-server-for-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

