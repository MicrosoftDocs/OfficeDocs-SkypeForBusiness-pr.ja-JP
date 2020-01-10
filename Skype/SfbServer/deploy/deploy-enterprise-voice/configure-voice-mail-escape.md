---
title: Skype for Business でボイスメールのエスケープを設定する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: '概要: skype for business Server 管理シェルを使用して、Skype for Business Server でボイスメールのエスケープを構成する方法について説明します。'
ms.openlocfilehash: 27f283f4bfb64aa950bd9e72a9d6fdc17df91ba0
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001217"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a><span data-ttu-id="084b8-103">Skype for Business でボイスメールのエスケープを設定する</span><span class="sxs-lookup"><span data-stu-id="084b8-103">Configure voice mail escape in Skype for Business</span></span>

<span data-ttu-id="084b8-104">**概要:** Skype for business Server 管理シェルを使用して、Skype for Business Server でボイスメールのエスケープを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="084b8-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="084b8-105">ユーザーが携帯電話との同時呼び出しを構成する場合、携帯電話がオフになっているか、バッテリ電力が不足しているか、または範囲外である場合、通常、発信者はユーザーの個人用ボイスメールにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="084b8-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="084b8-106">Skype for Business Server では、ユーザーはビジネス関連の通話を会社のボイスメールシステムにルーティングすることを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="084b8-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="084b8-107">特に、タイマーは構成可能であり、定義された時間内に電話会社のボイスメールによって通話が応答された場合、Skype for Business Server は、電話会社のボイスメールシステム (およびユーザーの個人ボイスメール) から切断しますが、ユーザーの企業システムの残りのエンドポイントでも、呼び出しが続行されます。</span><span class="sxs-lookup"><span data-stu-id="084b8-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="084b8-108">こうすることで、発信者はユーザーの会社のボイスメールに自動的にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="084b8-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>

<span data-ttu-id="084b8-109">この構成は、Skype for Business Server Management Shell コマンドレット**CsVoicePolicy**を使用して、音声ポリシーレベルで次のパラメーターを指定して実行します。</span><span class="sxs-lookup"><span data-stu-id="084b8-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="084b8-110">ボイス メール エスケープを構成するには</span><span class="sxs-lookup"><span data-stu-id="084b8-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="084b8-111">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="084b8-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="084b8-112">**Set-CsVoicePolicy** に対して次のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="084b8-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>

   - <span data-ttu-id="084b8-113">**EnableVoicemailEscapeTimer** - エスケープ タイマーを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="084b8-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>

   - <span data-ttu-id="084b8-p102">**PSTNVoicemailEscapeTimer**: タイムアウト値をミリ秒単位で指定します。既定値は 1500 ミリ秒で、指定できる値の範囲は 0 ～ 8000 ミリ秒です。</span><span class="sxs-lookup"><span data-stu-id="084b8-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

## <a name="example"></a><span data-ttu-id="084b8-116">例</span><span class="sxs-lookup"><span data-stu-id="084b8-116">Example</span></span>

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a><span data-ttu-id="084b8-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="084b8-117">See also</span></span>

[<span data-ttu-id="084b8-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span><span class="sxs-lookup"><span data-stu-id="084b8-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

