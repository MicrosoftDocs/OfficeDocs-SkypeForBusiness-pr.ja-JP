---
title: 'Lync Server 2013: 会議の構成設定を表示する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View meeting configuration settings
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49733828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b3107045d62b244c7ee89dbb47228bc5dd72583
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848201"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="2bf89-102">Lync Server 2013 で会議の構成設定を表示する</span><span class="sxs-lookup"><span data-stu-id="2bf89-102">View meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bf89-103">_**最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="2bf89-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="2bf89-104">Lync Server 2013 コントロールパネルで、会議の構成設定を使用して、展開での会議の実装方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="2bf89-104">In Lync Server 2013 Control Panel, you use meeting configuration setting to control how meetings are implemented in your deployment.</span></span> <span data-ttu-id="2bf89-105">これには、次の会議の設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2bf89-105">This includes the following meeting configurations:</span></span>

  - <span data-ttu-id="2bf89-106">Lync Server 2013 を展開するときに既定で作成されるグローバル構成。</span><span class="sxs-lookup"><span data-stu-id="2bf89-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="2bf89-107">特定のサイトまたはユーザーに対して会議を実装する方法を指定するために作成および使用できる、オプションのサイトレベルとユーザーレベルの構成。</span><span class="sxs-lookup"><span data-stu-id="2bf89-107">Optional site-level and user-level configurations that you can create and use to specify how meetings are implemented for specific sites or users.</span></span>

<div>

## <a name="to-view-meeting-configuration-settings"></a><span data-ttu-id="2bf89-108">会議の構成設定を表示するには</span><span class="sxs-lookup"><span data-stu-id="2bf89-108">To view meeting configuration settings</span></span>

1.  <span data-ttu-id="2bf89-109">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="2bf89-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2bf89-110">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2bf89-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2bf89-111">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2bf89-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2bf89-112">左側のナビゲーションバーで、[**会議**] をクリックし、[**会議の設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2bf89-112">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="2bf89-113">[**会議の構成**] ページで、表示する会議構成をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2bf89-113">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>

5.  <span data-ttu-id="2bf89-114">[**ファイルフィルターの編集**] で、[**詳細の表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2bf89-114">In **Edit File Filter**, select the **Show Details…**</span></span> <span data-ttu-id="2bf89-115">チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2bf89-115">check box.</span></span>
    
    <span data-ttu-id="2bf89-116">[**会議の構成\<の\>編集]-** 選択したポリシーの設定が表示されたポリシーが開きます。</span><span class="sxs-lookup"><span data-stu-id="2bf89-116">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span> <span data-ttu-id="2bf89-117">設定の構成の詳細については、「 [Lync Server 2013 で会議構成設定のコレクションを作成または変更する](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bf89-117">For details about configuring the settings, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span>

</div>

<div>

## <a name="viewing-meeting-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2bf89-118">Windows PowerShell コマンドレットを使用して会議の構成情報を表示する</span><span class="sxs-lookup"><span data-stu-id="2bf89-118">Viewing Meeting Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2bf89-119">会議の構成設定を表示するには、Windows PowerShell と、「Csmeeting 構成」コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2bf89-119">Meeting configuration settings can be viewed by using Windows PowerShell and the Get-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="2bf89-120">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="2bf89-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2bf89-121">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bf89-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-meeting-configuration-information"></a><span data-ttu-id="2bf89-122">会議の構成情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="2bf89-122">To view meeting configuration information</span></span>

  - <span data-ttu-id="2bf89-123">すべての会議の構成設定に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2bf89-123">To view information about all your meeting configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsMeetingConfiguration
    
    <span data-ttu-id="2bf89-124">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bf89-124">That will return information similar to this:</span></span>
    
        Identity                        : Global
        PstnCallersBypassLobby          : True
        EnableAssignedConferenceType    : True
        DesignateAsPresenter            : Company
        AssignedConferenceTypeByDefault : True
        AdmitAnonymousUsersByDefault    : True
        RequireRoomSystemsAuthorization : False
        LogoURL                         :
        LegalURL                        :
        HelpURL                         :
        CustomFooterText                :
        AllowConferenceRecording        : True

</div>

<span data-ttu-id="2bf89-125">詳細については、「 [Cs会議構成](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)コマンドレットのヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bf89-125">For more information, see the help topic for the [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

