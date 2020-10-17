---
title: すべての Exchange UM 連絡先オブジェクトが従来のプールから削除されていることを確認する
description: すべての Exchange UM 連絡先オブジェクトが従来のプールから削除されていることを確認します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af5dea6cf746c55d8fecf074e132f721c380de1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555513"
---
# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a><span data-ttu-id="6cf2a-103">すべての Exchange UM 連絡先オブジェクトが従来のプールから削除されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="6cf2a-103">Verify that all Exchange UM Contact objects are removed from the legacy pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6cf2a-104">_**トピックの最終更新日:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="6cf2a-104">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="6cf2a-105">**Ocsumutil**ツールまたは**Get-csexumcontact**コマンドレットを使用して、Exchange UM 連絡先オブジェクトが従来の Office Communications Server 2007 R2 プールから削除されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6cf2a-105">Use either the **OCSUmUtil** tool or the **Get-CsExumContact** cmdlet to verify that Exchange UM contact objects have been removed from the legacy Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="6cf2a-106">**OCSUmUtil** は次のフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="6cf2a-106">**OCSUmUtil** is located in the following folder:</span></span>

<span data-ttu-id="6cf2a-107">% Program Files% \\ Common Files \\ Lync Server 2013 \\ サポート \\OcsUMUtil.exe</span><span class="sxs-lookup"><span data-stu-id="6cf2a-107">%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe</span></span>

<span data-ttu-id="6cf2a-108">**OCSUmUtil** は、次の条件を満たすユーザー アカウントから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cf2a-108">**OCSUmUtil** must be run from a user account that has:</span></span>

  - <span data-ttu-id="6cf2a-109">RTCUniversalServerAdmins および RTCUniversalUserAdmins グループ (Exchange Server ユニファイド メッセージングの設定を読み取る権利が割り当てられている) に属している</span><span class="sxs-lookup"><span data-stu-id="6cf2a-109">Membership in the RTCUniversalServerAdmins and RTCUniversalUserAdmins group (which includes rights to read Exchange Server Unified Messaging settings)</span></span>

  - <span data-ttu-id="6cf2a-110">指定された組織単位 (OU) コンテナーに連絡先オブジェクトを作成するドメイン権限</span><span class="sxs-lookup"><span data-stu-id="6cf2a-110">Domain rights to create contact objects in the specified organizational unit (OU) container</span></span>

<span data-ttu-id="6cf2a-111">**Get-help**コマンドレットの使用の詳細については、「Lync Server Management Shell」のドキュメントの「[取得-csexumcontact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cf2a-111">For details about using the **Get-CsExumContact** cmdlet, see [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

