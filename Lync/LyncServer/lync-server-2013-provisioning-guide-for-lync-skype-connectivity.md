---
title: 'Lync Server 2013: Lync と Skype の接続のプロビジョニング ガイド'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Provisioning guide for Lync-Skype connectivity
ms:assetid: 69adda9b-5b72-4538-9be6-079b2f462e09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440173(v=OCS.15)
ms:contentKeyID: 57793363
ms.date: 11/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f595916502a7c7ec27ff220a7b3f138b41e6fc2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-guide-for-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="ceb80-102">Lync Server 2013 での Lync と Skype の接続のプロビジョニング ガイド</span><span class="sxs-lookup"><span data-stu-id="ceb80-102">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ceb80-103">_**最終更新日:** 2014-11-26_</span><span class="sxs-lookup"><span data-stu-id="ceb80-103">_**Topic Last Modified:** 2014-11-26_</span></span>

<span data-ttu-id="ceb80-p101">Lync Server 2013 は、Skype との接続をサポートしています。この接続を使用すると、Lync 2013 ユーザーは、Skype ユーザーの Microsoft Account (MSA) を使用して Skype の連絡先を追加できます。Skype クライアントも、Lync ユーザーを連絡先リストに追加できます。Lync Server で管理上設定されたポリシーに基づいて、Lync ユーザーと Skype ユーザーは、インスタント メッセージを使用して通信し、お互いのプレゼンスを確認し、音声およびビデオ通話を開始できるようになります。Lync と Skype の接続は、Lync Online の機能でもあり、Office 365 ポータル内の Lync 管理センターから Lync Online の顧客に対して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ceb80-p101">Lync Server 2013 supports connectivity with Skype. This connectivity enables your Lync 2013 users to add Skype contacts by using the Skype user’s Microsoft Account (MSA). Skype clients can also add Lync users to their contact list. Based on policies administratively set in Lync Server, Lync and Skype users will be able to communicate using instant messaging, see each other’s presence, and initiate audio and video calls. Lync-Skype connectivity is also a feature of Lync Online, and can be enabled for Lync Online customers from the Lync Administration Center within the Office 365 portal.</span></span>

<div>

> [!IMPORTANT]  
> <span data-ttu-id="ceb80-p102">Lync Server がパブリック インスタント メッセージング接続 (PIC) を使用して Windows Messenger と接続するように既に構成されている場合、展開は、既に Lync と Skype の接続用に構成されています。検討する対象となりうる唯一の変更は、既存の Messenger PIC エントリの名前を Skype などに変更することだけです。詳細については、このガイドで後述する Lync の「Lync 用の Skype PIC プロバイダー設定を構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ceb80-p102">If Lync Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Lync-Skype connectivity. The only change you may want to consider is to rename your existing Messenger PIC entry as Skype. For details, see Configure the Skype PIC provider setting for Lync later in this guide.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ceb80-112">このセクション中</span><span class="sxs-lookup"><span data-stu-id="ceb80-112">In This Section</span></span>

  - [<span data-ttu-id="ceb80-113">Lync Online ユーザー向けの lync Server 2013 での Lync についての注-Skype 接続</span><span class="sxs-lookup"><span data-stu-id="ceb80-113">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>](lync-server-2013-note-about-lync-skype-connectivity-for-lync-on.md)

  - [<span data-ttu-id="ceb80-114">Lync Server 2013 から Lync Server パブリック IM 接続プロビジョニング サイトへのアクセス</span><span class="sxs-lookup"><span data-stu-id="ceb80-114">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>](lync-server-2013-accessing-the-lync-server-public-im-connectivity-provisioning-site.md)

  - [<span data-ttu-id="ceb80-115">Lync Server 2013 での Lync と Skype の接続の有効化</span><span class="sxs-lookup"><span data-stu-id="ceb80-115">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-enabling-lync-skype-connectivity.md)

  - [<span data-ttu-id="ceb80-116">エンド ユーザーとしての Lync Server 2013 での Lync と Skype の接続の使用</span><span class="sxs-lookup"><span data-stu-id="ceb80-116">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

  - [<span data-ttu-id="ceb80-117">FAQ: Skype 接続用の Lync Server 2013 のプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="ceb80-117">Frequently Asked Questions: Provisioning Lync Server 2013 for Skype connectivity</span></span>](lync-server-2013-frequently-asked-questions-provisioning-lync-server-for-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

