---
title: 'Lync Server 2013: ユーザーのコールパークを有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Call Park for users
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48184814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3046cc7daf0dd1fbaba16ffff4e8f41ee6d2e757
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-call-park-for-users-in-lync-server-2013"></a><span data-ttu-id="357d1-102">Lync Server 2013 でユーザーのコールパークを有効にする</span><span class="sxs-lookup"><span data-stu-id="357d1-102">Enable Call Park for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="357d1-103">_**トピックの最終更新日:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="357d1-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="357d1-104">ユーザーは、音声ポリシーのコールパークが有効になるまで、通話をパークしたり保留された通話を取得したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="357d1-104">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="357d1-105">既定では、すべてのユーザーに対してコールパークが無効になります。</span><span class="sxs-lookup"><span data-stu-id="357d1-105">By default, Call Park is disabled for all users.</span></span>



</div>

<span data-ttu-id="357d1-106">通話パークは、グローバルスコープまたはサイトスコープまたはユーザースコープで有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="357d1-106">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="357d1-107">ユーザースコープはサイトスコープより優先され、サイトスコープはグローバルスコープより優先されます。</span><span class="sxs-lookup"><span data-stu-id="357d1-107">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="357d1-108">複数の音声ポリシーがある場合は、グローバルポリシーだけでなく、すべてのポリシーを確認してコールパークを有効にします。</span><span class="sxs-lookup"><span data-stu-id="357d1-108">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="357d1-109">Lync Server コントロールパネルを使用してユーザーのコールパークを有効にするには</span><span class="sxs-lookup"><span data-stu-id="357d1-109">To Use Lync Server Control Panel to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="357d1-110">**RTCUniversalServerAdmins**グループのメンバーとして、または**CsVoiceAdministrator**、 **Csserveradministrator**、または**csadministrator**管理者役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="357d1-110">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="357d1-111">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="357d1-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="357d1-112">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="357d1-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="357d1-113">左側のナビゲーション バーで [**音声ルーティング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="357d1-113">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="357d1-114">[**音声ポリシー** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="357d1-114">Click the **Voice Policy** tab.</span></span>

5.  <span data-ttu-id="357d1-115">既存の音声ポリシーをダブルクリックして、[**音声ポリシーの編集**] ダイアログボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="357d1-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>

6.  <span data-ttu-id="357d1-116">[**通話機能**] の [**コールパークを有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="357d1-116">Under **Calling features**, select **Enable call park**.</span></span>

7.  <span data-ttu-id="357d1-117">[ **OK]** をクリックして音声ポリシーを保存します。</span><span class="sxs-lookup"><span data-stu-id="357d1-117">Click **OK** to save the voice policy</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="357d1-118">コマンドレットを使用してユーザーのコールパークを有効にするには</span><span class="sxs-lookup"><span data-stu-id="357d1-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="357d1-119">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator 管理者役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="357d1-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>

2.  <span data-ttu-id="357d1-120">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="357d1-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="357d1-121">実行</span><span class="sxs-lookup"><span data-stu-id="357d1-121">Run:</span></span>
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    <span data-ttu-id="357d1-122">たとえば、既定のグローバル音声ポリシーのコールパークを有効にするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="357d1-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="357d1-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="357d1-123">See Also</span></span>


[<span data-ttu-id="357d1-124">Lync Server 2013 で音声ポリシーを作成し、PSTN 使用法レコードを構成する</span><span class="sxs-lookup"><span data-stu-id="357d1-124">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

