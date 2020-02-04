---
title: 'Lync Server 2013: lync についての注意-Lync On Lync の Skype 接続'
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
ms.openlocfilehash: 053c29573ccac6a67473db8ba46b80cf1cdf3dcc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="note-about-lync-skype-connectivity-in-lync-server-2013-for-lync-online-customers"></a><span data-ttu-id="60196-102">Lync Online ユーザー向けの lync Server 2013 での Lync についての注-Skype 接続</span><span class="sxs-lookup"><span data-stu-id="60196-102">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60196-103">_**最終更新日:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="60196-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="60196-104">このドキュメントは、Lync Server のオンプレミス管理者が Lync をセットアップするのに役立つように作成されました。 Skype の接続を設定します。</span><span class="sxs-lookup"><span data-stu-id="60196-104">This document was written to help Lync Server on-premise administrators set up Lync-Skype connectivity.</span></span><span data-ttu-id="60196-105">Lync-Skype 接続は、Office 365 の一部である Lync Online の機能でもあります。</span><span class="sxs-lookup"><span data-stu-id="60196-105">  Lync-Skype connectivity is also a feature of Lync Online, which is part of Office 365.</span></span> <span data-ttu-id="60196-106">Lync-Skype の接続機能は、Office 365 ポータル内の Lync 管理センターから有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="60196-106">You can enable the Lync-Skype connectivity feature from the Lync Administration Center within the Office 365 portal.</span></span>

<span data-ttu-id="60196-107">Office 365 中堅企業向け、Office 365 Enterprise、Office 365 エデュケーション、office 365 for Government: Office 365 ポータルにサインインして、 **Lync 管理センター**に移動します。</span><span class="sxs-lookup"><span data-stu-id="60196-107">For Office 365 Midsize Business, Office 365 Enterprise, Office 365 Education, and Office 365 for Government: Sign in to the Office 365 portal and navigate to the **Lync Administration Center**.</span></span> <span data-ttu-id="60196-108">**外部通信**に移動します。</span><span class="sxs-lookup"><span data-stu-id="60196-108">Go to **External Communications**.</span></span> <span data-ttu-id="60196-109">[**パブリック IM サービスプロバイダー**] で [**有効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60196-109">Under **Public IM Service Providers**, click **Enable**.</span></span> <span data-ttu-id="60196-110">Lync-Skype 接続への個々のユーザーアクセスを制御する場合は、個々のユーザーの外部通信設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="60196-110">If you want to control individual user access to Lync-Skype Connectivity, you can do so by editing individual users’ External Communications settings.</span></span>

<span data-ttu-id="60196-111">Office 365 Small Business Premium の場合: Office 365 にサインインし、[**管理者\>サービスの\>設定] で [インスタントメッセージング、会議、会議**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="60196-111">For Office 365 Small Business Premium: Sign in to Office 365, and go to **Admin \> Service Settings \> Instant messaging, meetings and conferencing**.</span></span> <span data-ttu-id="60196-112">外部通信を有効にします。</span><span class="sxs-lookup"><span data-stu-id="60196-112">Turn on External communications.</span></span> <span data-ttu-id="60196-113">[外部通信] スイッチは、lync を使用する他の組織との両方の接続と通信を有効にします。</span><span class="sxs-lookup"><span data-stu-id="60196-113">The External communications switch turns on both Lync-Skype connectivity and communications with other organizations that use Lync.</span></span> <span data-ttu-id="60196-114">Lync Online の使用を開始した時点によっては、"オン" 状態の外部通信スイッチが、他の Lync 組織との通信がアクティブ化されていることだけが最初に表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="60196-114">Depending on when you started using Lync Online, the External communications switch in an "on" state may initially indicate only that communications with other Lync organizations is activated.</span></span> <span data-ttu-id="60196-115">Lync-Skype の接続を有効にするには、スイッチをオフにしてからもう一度オンにします。</span><span class="sxs-lookup"><span data-stu-id="60196-115">To turn on Lync-Skype Connectivity, simply toggle the switch off and then back on again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

