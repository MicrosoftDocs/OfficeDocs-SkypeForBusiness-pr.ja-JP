---
title: 'Lync Server 2013: Lync On の Lync-Skype 接続に関する注意事項'
description: 'Lync Server 2013: Lync On の Lync-Skype の接続性に関するメモ。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Note about Lync-Skype connectivity for Lync On
ms:assetid: 1d0f5c1a-74c6-468f-9877-ad2b1ddf355f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440169(v=OCS.15)
ms:contentKeyID: 57793359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f7d9758f277f2f987677c2c0ffa0a4447ba31d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579203"
---
# <a name="note-about-lync-skype-connectivity-in-lync-server-2013-for-lync-online-customers"></a><span data-ttu-id="b3c9c-103">Lync Online のお客様のための Lync Server 2013 の接続の Lync-Skype に関する注意</span><span class="sxs-lookup"><span data-stu-id="b3c9c-103">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3c9c-104">_**トピックの最終更新日:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="b3c9c-104">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="b3c9c-105">このドキュメントは、Lync Server の社内管理者が Lync-Skype 接続をセットアップできるようにするために作成されました。</span><span class="sxs-lookup"><span data-stu-id="b3c9c-105">This document was written to help Lync Server on-premise administrators set up Lync-Skype connectivity.</span></span><span data-ttu-id="b3c9c-106">Lync-Skype 接続は、Office 365 および Microsoft 365 の一部である Lync Online の機能でもあります。</span><span class="sxs-lookup"><span data-stu-id="b3c9c-106">  Lync-Skype connectivity is also a feature of Lync Online, which is part of Office 365 and Microsoft 365.</span></span> <span data-ttu-id="b3c9c-107">管理センター内の Lync 管理センターから Lync-Skype 接続機能を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b3c9c-107">You can enable the Lync-Skype connectivity feature from the Lync Administration Center within the admin center.</span></span>

<span data-ttu-id="b3c9c-108">Microsoft 365 中規模企業、Office 365 Enterprise、Microsoft 365 エデュケーション、および Office 365 for Government: Office の365ポータルまたは Microsoft の365管理センターにサインインし、 **Lync 管理センター**に移動します。</span><span class="sxs-lookup"><span data-stu-id="b3c9c-108">For Microsoft 365 Midsize Business, Office 365 Enterprise, Microsoft 365 Education, and Office 365 for Government: Sign in to the Office 365 portal or Microsoft 365 admin center and navigate to the **Lync Administration Center**.</span></span> <span data-ttu-id="b3c9c-109">[ **外部通信**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="b3c9c-109">Go to **External Communications**.</span></span> <span data-ttu-id="b3c9c-110">[ **パブリック IM サービスプロバイダー**] の下で、[ **有効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3c9c-110">Under **Public IM Service Providers**, click **Enable**.</span></span> <span data-ttu-id="b3c9c-111">個々のユーザーの Lync-Skype 接続へのアクセスを制御するには、個々のユーザーの外部通信設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="b3c9c-111">If you want to control individual user access to Lync-Skype Connectivity, you can do so by editing individual users’ External Communications settings.</span></span>

<span data-ttu-id="b3c9c-112">Microsoft 365 Small Business Premium の場合: Microsoft 365 にサインインし、 **管理者 \> サービス設定の [ \> インスタントメッセージング]、[会議と会議]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="b3c9c-112">For Microsoft 365 Small Business Premium: Sign in to Microsoft 365, and go to **Admin \> Service Settings \> Instant messaging, meetings and conferencing**.</span></span> <span data-ttu-id="b3c9c-113">外部通信を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b3c9c-113">Turn on External communications.</span></span> <span data-ttu-id="b3c9c-114">外部通信スイッチは、Lync を使用する他の組織との Lync-Skype 接続と通信の両方を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b3c9c-114">The External communications switch turns on both Lync-Skype connectivity and communications with other organizations that use Lync.</span></span> <span data-ttu-id="b3c9c-115">Lync Online の使用を開始した時期によっては、"オン" 状態の外部通信スイッチが、他の Lync 組織との通信がアクティブ化されていることのみを最初に示している場合があります。</span><span class="sxs-lookup"><span data-stu-id="b3c9c-115">Depending on when you started using Lync Online, the External communications switch in an "on" state may initially indicate only that communications with other Lync organizations is activated.</span></span> <span data-ttu-id="b3c9c-116">Lync-Skype の接続をオンにするには、スイッチの電源をオフにしてから再度オンに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="b3c9c-116">To turn on Lync-Skype Connectivity, simply toggle the switch off and then back on again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

