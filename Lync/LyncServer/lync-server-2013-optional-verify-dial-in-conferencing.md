---
title: 'Lync Server 2013: (オプション) ダイヤルイン会議の検証'
description: 'Lync Server 2013: (オプション) ダイヤルイン会議の検証。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing
ms:assetid: 3e2b4220-8fb3-442f-98b1-78447adb321f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425905(v=OCS.15)
ms:contentKeyID: 48183941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5e8d3734e89555bf4b298ac68e1e3bd67b1d901
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572539"
---
# <a name="optional-verify-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="fa80f-103">オプションLync Server 2013 でのダイヤルイン会議の確認</span><span class="sxs-lookup"><span data-stu-id="fa80f-103">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa80f-104">_**トピックの最終更新日:** 2011-01-21_</span><span class="sxs-lookup"><span data-stu-id="fa80f-104">_**Topic Last Modified:** 2011-01-21_</span></span>

<span data-ttu-id="fa80f-105">ダイヤルイン会議の設定の Web ページとダイヤルイン アクセス番号が正しく動作していることを確認するには、以下を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa80f-105">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>

  - <span data-ttu-id="fa80f-106">簡単な URL にサインインして、ダイヤルイン会議の設定の Web ページをテストします。</span><span class="sxs-lookup"><span data-stu-id="fa80f-106">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>

  - <span data-ttu-id="fa80f-p101">この後のスクリプトを実行して、特定のプールでそのアクセス番号が正しく動作することをテストします。 このスクリプトは、アクセス番号への通話をシミュレートします。 このスクリプトを使用するには、特定のプールでホストされている 1 つの統合コミュニケーション (UC) クライアントの SIP アドレスと資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="fa80f-p101">Test that access numbers work correctly for a specific pool by running the script later in this topic. This script simulates calls to access numbers. You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>

<span data-ttu-id="fa80f-110">このステップはオプションです。</span><span class="sxs-lookup"><span data-stu-id="fa80f-110">This step is optional.</span></span>

<div>

## <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="fa80f-111">特定のプールのアクセス番号をテストするには</span><span class="sxs-lookup"><span data-stu-id="fa80f-111">To test access numbers for a specific pool</span></span>

1.  <span data-ttu-id="fa80f-112">RTCUniversalServerAdmins グループのメンバーか、**Cs-ServerAdministrator** または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="fa80f-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="fa80f-113">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa80f-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="fa80f-114">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fa80f-114">Run the following at the command prompt:</span></span>
    
        $credentials = Get-Credential
           User name:  testuser1@contoso.com
           Password:   ********
        Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
    
    <span data-ttu-id="fa80f-p102">結果レポートに、コマンドの成否と特定の診断情報が表示されます。 –Verbose フラグには、検出されたアクセス番号の数とその詳細に関する情報が、より詳しく表示されます。</span><span class="sxs-lookup"><span data-stu-id="fa80f-p102">The resulting report shows either Success or Failure, along with specific diagnostic information. The –Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

