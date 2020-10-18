---
title: 'Lync Server 2013: ボイスメールエスケープの構成'
description: 'Lync Server 2013: ボイスメールエスケープの構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice mail escape
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49733761
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afbb2dd10c7ff8809eb8dfbcc64e40a599aa06a4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575113"
---
# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a><span data-ttu-id="bfe1a-103">Lync Server 2013 でのボイスメールエスケープの構成</span><span class="sxs-lookup"><span data-stu-id="bfe1a-103">Configuring voice mail escape in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfe1a-104">_**トピックの最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="bfe1a-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="bfe1a-105">ユーザーが携帯電話に同時呼び出しを構成すると、携帯電話がオフになっている場合、バッテリ電源が切れている場合、または範囲外にある場合、通常、発信者はユーザーの個人ボイスメールにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="bfe1a-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user’s personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="bfe1a-106">Lync Server 2013 を使用すると、ユーザーは会社のボイスメールシステムにビジネス関連の通話をルーティングすることを選択できます。</span><span class="sxs-lookup"><span data-stu-id="bfe1a-106">With Lync Server 2013, users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="bfe1a-107">具体的には、タイマーを構成することができ、定義された時間内に電話会社のボイスメールによって通話に応答した場合、Lync Server は電話会社のボイスメールシステム (およびユーザーの個人用ボイスメール) から切断されますが、企業システムの残りのエンドポイントは引き続き鳴ります。</span><span class="sxs-lookup"><span data-stu-id="bfe1a-107">Specifically, a timer can be configured, and if the call is answered by the carrier’s voice mail within the range of time defined, Lync Server will disconnect from the carrier’s voice mail system (and the user’s personal voice mail), while the user’s remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="bfe1a-108">これにより、発信者は自動的にユーザーの会社のボイス メールにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="bfe1a-108">This way, the caller is automatically routed to the user’s corporate voice mail.</span></span>

<span data-ttu-id="bfe1a-109">この構成は、Lync Server 管理シェルコマンドレット Set-csvoicepolicy を使用して、音声ポリシーレベルで次のパラメーターを **設定**して実行します。</span><span class="sxs-lookup"><span data-stu-id="bfe1a-109">This configuration is performed using the Lync Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

<div>

## <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="bfe1a-110">ボイスメールエスケープを構成するには</span><span class="sxs-lookup"><span data-stu-id="bfe1a-110">To configure voice mail escape</span></span>

1.  <span data-ttu-id="bfe1a-111">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfe1a-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bfe1a-112">**Set-csvoicepolicy**に次のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="bfe1a-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>
    
      - <span data-ttu-id="bfe1a-113">**EnableVoicemailEscapeTimer** -エスケープタイマーを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="bfe1a-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>
    
      - <span data-ttu-id="bfe1a-114">**PSTNVoicemailEscapeTimer** -タイムアウト値をミリ秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="bfe1a-114">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds.</span></span> <span data-ttu-id="bfe1a-115">既定値は 1500 ミリ秒で、指定できる値の範囲は 0 ～ 8000 ミリ秒です。</span><span class="sxs-lookup"><span data-stu-id="bfe1a-115">The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="bfe1a-116">例</span><span class="sxs-lookup"><span data-stu-id="bfe1a-116">Example</span></span>

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bfe1a-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="bfe1a-117">See Also</span></span>


[<span data-ttu-id="bfe1a-118">Lync Server 2013 での通話機能と特権の承認のための音声ポリシーと PSTN 使用法レコードの構成</span><span class="sxs-lookup"><span data-stu-id="bfe1a-118">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

