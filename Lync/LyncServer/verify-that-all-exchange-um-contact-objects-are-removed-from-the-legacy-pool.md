---
title: すべての Exchange UM 連絡先オブジェクトが従来のプールから削除されていることを確認する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79183039cedc058d479d52fa80ce09a70ffd73b3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a><span data-ttu-id="3f77d-102">すべての Exchange UM 連絡先オブジェクトが従来のプールから削除されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="3f77d-102">Verify that all Exchange UM Contact objects are removed from the legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f77d-103">_**トピックの最終更新日:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="3f77d-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="3f77d-104">**Ocsumutil**ツールまたは**Get-csexumcontact**コマンドレットを使用して、Exchange UM 連絡先オブジェクトが従来の Office Communications Server 2007 R2 プールから削除されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3f77d-104">Use either the **OCSUmUtil** tool or the **Get-CsExumContact** cmdlet to verify that Exchange UM contact objects have been removed from the legacy Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="3f77d-105">**OCSUmUtil** は次のフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="3f77d-105">**OCSUmUtil** is located in the following folder:</span></span>

<span data-ttu-id="3f77d-106">% Program Files%\\Common Files\\Lync Server 2013\\サポート\\ocsumutil</span><span class="sxs-lookup"><span data-stu-id="3f77d-106">%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe</span></span>

<span data-ttu-id="3f77d-107">**OCSUmUtil** は、次の条件を満たすユーザー アカウントから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f77d-107">**OCSUmUtil** must be run from a user account that has:</span></span>

  - <span data-ttu-id="3f77d-108">RTCUniversalServerAdmins および RTCUniversalUserAdmins グループ (Exchange Server ユニファイド メッセージングの設定を読み取る権利が割り当てられている) に属している</span><span class="sxs-lookup"><span data-stu-id="3f77d-108">Membership in the RTCUniversalServerAdmins and RTCUniversalUserAdmins group (which includes rights to read Exchange Server Unified Messaging settings)</span></span>

  - <span data-ttu-id="3f77d-109">指定された組織単位 (OU) コンテナーに連絡先オブジェクトを作成するドメイン権限</span><span class="sxs-lookup"><span data-stu-id="3f77d-109">Domain rights to create contact objects in the specified organizational unit (OU) container</span></span>

<span data-ttu-id="3f77d-110">**Get-help**コマンドレットの使用の詳細については、「Lync Server Management Shell」のドキュメントの「[取得-csexumcontact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f77d-110">For details about using the **Get-CsExumContact** cmdlet, see [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

