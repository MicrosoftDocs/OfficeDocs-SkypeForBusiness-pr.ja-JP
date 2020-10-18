---
title: 'Lync Server 2013: 電話会議ポリシー情報の表示'
description: 'Lync Server 2013: 電話会議ポリシーの情報を表示します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View conferencing policy information
ms:assetid: e99fdc4d-926a-4e36-ac99-ab5035568847
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721918(v=OCS.15)
ms:contentKeyID: 49733852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e463c500e48f4032c8dab3a3787715f7265be9c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579433"
---
# <a name="view-conferencing-policy-information-in-lync-server-2013"></a><span data-ttu-id="dbdb9-103">Lync Server 2013 での会議ポリシー情報の表示</span><span class="sxs-lookup"><span data-stu-id="dbdb9-103">View conferencing policy information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbdb9-104">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="dbdb9-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="dbdb9-105">Lync Server 2013 コントロールパネルでは、会議ポリシーを使用して、展開での会議の実装方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="dbdb9-105">In Lync Server 2013 Control Panel, you use conferencing policies to control how conferencing is implemented in your deployment.</span></span> <span data-ttu-id="dbdb9-106">これには、次の会議ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dbdb9-106">This includes the following conferencing policies:</span></span>

  - <span data-ttu-id="dbdb9-107">Lync Server 2013 を展開するときに既定で作成されるグローバルポリシー。</span><span class="sxs-lookup"><span data-stu-id="dbdb9-107">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="dbdb9-108">特定のサイトまたはユーザーに対する会議の実装方法を指定するために作成して使用できるオプションのサイトレベルおよびユーザーレベルのポリシー。</span><span class="sxs-lookup"><span data-stu-id="dbdb9-108">Optional site-level and user-level policy that you can create and use to specify how conferencing is implemented for specific sites or users.</span></span>

<div>

## <a name="to-view-conferencing-policy-settings"></a><span data-ttu-id="dbdb9-109">会議ポリシーの設定を表示するには</span><span class="sxs-lookup"><span data-stu-id="dbdb9-109">To view conferencing policy settings</span></span>

1.  <span data-ttu-id="dbdb9-110">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="dbdb9-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dbdb9-111">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="dbdb9-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dbdb9-112">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbdb9-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dbdb9-113">左側のナビゲーション バーで、[**会議**] をクリックし、[**会議ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbdb9-113">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="dbdb9-114">[**会議ポリシー**] ページで、表示する会議ポリシーをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbdb9-114">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>

5.  <span data-ttu-id="dbdb9-p103">[**ファイル フィルターの編集**] で、[**詳細の表示**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="dbdb9-p103">In **Edit File Filter**, select the **Show Details…** check box.</span></span>
    
    <span data-ttu-id="dbdb9-117">**会議ポリシーの編集 \<policy\> -** 選択したポリシーの設定を表示して開きます。</span><span class="sxs-lookup"><span data-stu-id="dbdb9-117">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span> <span data-ttu-id="dbdb9-118">設定の構成の詳細については、「 [Lync Server 2013 で会議ポリシーを作成または変更する](lync-server-2013-create-or-modify-a-conferencing-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbdb9-118">For details about configuring the settings, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span>

</div>

<div>

## <a name="viewing-conferencing-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="dbdb9-119">Windows PowerShell コマンドレットを使用して会議ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="dbdb9-119">Viewing Conferencing Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="dbdb9-120">会議ポリシーは、Windows PowerShell と Get-CsConferencingPolicy コマンドレットを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="dbdb9-120">Conferencing policies can be viewed by using Windows PowerShell and the Get-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="dbdb9-121">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="dbdb9-121">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="dbdb9-122">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbdb9-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-conferencing-policies"></a><span data-ttu-id="dbdb9-123">電話会議ポリシーを表示するには</span><span class="sxs-lookup"><span data-stu-id="dbdb9-123">To view conferencing policies</span></span>

  - <span data-ttu-id="dbdb9-124">すべての電話会議ポリシーに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="dbdb9-124">To view information about all your conferencing policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="dbdb9-125">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dbdb9-125">That will return information similar to this:</span></span>
    
        Identity                                  : Global
        AllowIPAudio                              : True
        AllowIPVideo                              : True
        AllowMultiView                            : True
        Description                               :
        AllowParticipantControl                   : True
        AllowAnnotations                          : True
        DisablePowerPointAnnotations              : False
        AllowUserToScheduleMeetingsWithAppSharing : True
        AllowNonEnterpriseVoiceUsersToDialOut     : False
        AllowAnonymousUsersToDialOut              : False
        AllowAnonymousParticipantsInMeetings      : True
        AllowExternalUsersToSaveContent           : True
        AllowExternalUserControl                  : False
        AllowExternalUsersToRecordMeeting         : False
        AllowPolls                                : True
        AllowSharedNotes                          : True
        EnableDialInConferencing                  : True
        EnableAppDesktopSharing                   : Desktop
        AllowConferenceRecording                  : False
        EnableP2PRecording                        : False
        EnableFileTransfer                        : True
        EnableP2PFileTransfer                     : True
        EnableP2PVideo                            : True
        AllowLargeMeetings                        : False
        EnableDataCollaboration                   : True
        MaxVideoConferenceResolution              : VGA
        MaxMeetingSize                            : 250
        AudioBitRateKb                            : 200
        VideoBitRateKb                            : 50000
        AppSharingBitRateKb                       : 50000
        FileTransferBitRateKb                     : 50000
        TotalReceiveVideoBitRateKb                : 6000
        EnableMultiViewJoin                       : True

</div>

<span data-ttu-id="dbdb9-126">詳細については、 [get-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbdb9-126">For more information, see the help topic for the [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

