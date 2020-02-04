---
title: 'Lync Server 2013: 1-1 のボイスルーティングを構成する E9'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an E9-1-1 voice route
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398496(v=OCS.15)
ms:contentKeyID: 48184384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d40d2ee5dcb0dd7f759751bdab0d3e09f4ebc577
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-e9-1-1-voice-route-in-lync-server-2013"></a><span data-ttu-id="8bc26-102">Lync Server 2013 での E9 音声ルートの構成</span><span class="sxs-lookup"><span data-stu-id="8bc26-102">Configure an E9-1-1 voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bc26-103">_**最終更新日:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="8bc26-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="8bc26-104">E9-1-1 を展開するには、まず緊急通話用のボイス ルートを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bc26-104">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="8bc26-105">ボイスルートの作成の詳細については、「 [Lync Server 2013 での音声ルートの作成](lync-server-2013-create-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8bc26-105">For details about creating voice routes, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span> <span data-ttu-id="8bc26-106">展開にプライマリ SIP トランクおよびセカンダリ SIP トランクが含まれている場合などは、複数のルートを定義できます。</span><span class="sxs-lookup"><span data-stu-id="8bc26-106">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8bc26-107">E9 の招待状に位置情報を含めるには、E9 サービスプロバイダーに接続する SIP トランクをゲートウェイ経由でルーティングするように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bc26-107">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="8bc26-108">そのためには、 <STRONG>set-cstrunkconfiguration</STRONG>コマンドレットの EnablePIDFLOSupport フラグを True に設定します。</span><span class="sxs-lookup"><span data-stu-id="8bc26-108">To do this, set the EnablePIDFLOSupport flag on the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to True.</span></span> <span data-ttu-id="8bc26-109">EnablePIDFLOSupport の既定値は False です。</span><span class="sxs-lookup"><span data-stu-id="8bc26-109">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="8bc26-110">例えば：<CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE></span><span class="sxs-lookup"><span data-stu-id="8bc26-110">For example: <CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE></span></span><BR><span data-ttu-id="8bc26-111">フォールバック公衆交換電話網 (PSTN) ゲートウェイと Emergency Location Identification Number (ELIN) ゲートウェイに対して、場所の受信を有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8bc26-111">It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>



</div>

<span data-ttu-id="8bc26-112">ボイスルートの使用について詳しくは、次のコマンドレットの Lync Server 管理シェルに関するドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8bc26-112">For details about working with voice routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="8bc26-113">**Set-CsPstnUsage**</span><span class="sxs-lookup"><span data-stu-id="8bc26-113">**Set-CsPstnUsage**</span></span>

  - <span data-ttu-id="8bc26-114">**Get-CsPstnUsage**</span><span class="sxs-lookup"><span data-stu-id="8bc26-114">**Get-CsPstnUsage**</span></span>

  - <span data-ttu-id="8bc26-115">**新規-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="8bc26-115">**New-CsVoiceRoute**</span></span>

  - <span data-ttu-id="8bc26-116">**Get-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="8bc26-116">**Get-CsVoiceRoute**</span></span>

  - <span data-ttu-id="8bc26-117">**Set-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="8bc26-117">**Set-CsVoiceRoute**</span></span>

  - <span data-ttu-id="8bc26-118">**Remove-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="8bc26-118">**Remove-CsVoiceRoute**</span></span>

<div>

## <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="8bc26-119">E9-1-1 のボイス ルートを構成するには</span><span class="sxs-lookup"><span data-stu-id="8bc26-119">To configure an E9-1-1 voice route</span></span>

1.  <span data-ttu-id="8bc26-120">RTCUniversalServerAdmins グループのメンバーまたは CsVoiceAdministrator 管理者役割のメンバーであるアカウントを使用してコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8bc26-120">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>

2.  <span data-ttu-id="8bc26-121">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8bc26-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8bc26-122">次のコマンドレットを実行して、新しい PSTN 使用法レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="8bc26-122">Run the following cmdlet to create a new PSTN usage record.</span></span>
    
    <span data-ttu-id="8bc26-123">これは、[場所のポリシー] の [**PSTN**] 設定で使用する名前と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bc26-123">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="8bc26-124">展開には複数の電話使用法レコードが含まれますが、次の例では、使用可能な PSTN 使用法の現在の一覧に "Emergency Usage" を追加しています。</span><span class="sxs-lookup"><span data-stu-id="8bc26-124">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="8bc26-125">詳細については、「[ボイスポリシーと PSTN 使用状況レコードを構成する」を参照してください。 Lync Server 2013 で通話機能と特権を承認](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)します。</span><span class="sxs-lookup"><span data-stu-id="8bc26-125">For details, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  <span data-ttu-id="8bc26-126">次のコマンドレットを実行して、前のステップで作成した PSTN 使用法レコードで新しいボイス ルートを作成します。</span><span class="sxs-lookup"><span data-stu-id="8bc26-126">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="8bc26-127">この番号パターンは、[場所のポリシー] の [**緊急ダイヤル文字列**] 設定で使用する番号パターンと同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bc26-127">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="8bc26-128">Lync は緊急通話に "+" を追加するため、"+" 記号が必要です。</span><span class="sxs-lookup"><span data-stu-id="8bc26-128">A "+" sign is needed because Lync adds "+" to emergency calls.</span></span> <span data-ttu-id="8bc26-129">"Co1-pstngateway-1" は、E9-1-1 サービス プロバイダーの SIP トランク サービス ID または ELIN ゲートウェイ サービス ID です。</span><span class="sxs-lookup"><span data-stu-id="8bc26-129">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="8bc26-130">次の例では、ボイス ルートの名前として、"EmergencyRoute" を使用しています。</span><span class="sxs-lookup"><span data-stu-id="8bc26-130">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  <span data-ttu-id="8bc26-p105">必要に応じて、SIP トランク接続では、次のコマンドレットを実行することをお勧めします。これにより、E9-1-1 サービス プロバイダーの SIP トランクで処理されない通話用のローカル ルートが作成されます。このルートは、E9-1-1サービス プロバイダーに接続できない場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8bc26-p105">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider’s SIP trunk. This route will be used if the connection to the E9-1-1 service provider is not available.</span></span>
    
    <span data-ttu-id="8bc26-133">次の例では、ユーザーの音声ポリシーに "ローカル" 使用法があることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="8bc26-133">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

</div>

</div>

<span> </span>

</div>

</div>

</div>

