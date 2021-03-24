---
title: Skype for Business でボイス メール エスケープを構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: '概要: Skype for Business Server 管理シェルを使用して Skype for Business Server でボイス メール エスケープを構成する方法について説明します。'
ms.openlocfilehash: c74142cf3b0f6c9d5a871e116d8e163a095ad3cd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106373"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a><span data-ttu-id="ecace-103">Skype for Business でボイス メール エスケープを構成する</span><span class="sxs-lookup"><span data-stu-id="ecace-103">Configure voice mail escape in Skype for Business</span></span>

<span data-ttu-id="ecace-104">**概要:** Skype for Business Server 管理シェルを使用して Skype for Business Server でボイス メール エスケープを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ecace-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="ecace-105">ユーザーが携帯電話への同時呼び出し音を構成すると、通常、携帯電話がオフになっている場合、バッテリーの電源が切れ、または範囲外の場合、発信者はユーザーの個人用ボイス メールにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="ecace-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="ecace-106">Skype for Business Server を使用すると、ビジネス関連の通話を企業のボイス メール システムにルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="ecace-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="ecace-107">具体的には、タイマーを構成し、通話が定義された範囲内で通信事業者のボイス メールによって応答された場合、Skype for Business Server は通信事業者のボイス メール システム (およびユーザーの個人用ボイス メール) から切断され、企業システム内のユーザーの残りのエンドポイントは引き続き呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ecace-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="ecace-108">これにより、発信者は自動的にユーザーの企業ボイス メールにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="ecace-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>

<span data-ttu-id="ecace-109">この構成は、次のパラメーターを使用して、音声ポリシー レベルで Skype for Business Server 管理シェル コマンドレット **Set-CsVoicePolicy** を使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="ecace-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="ecace-110">ボイス メール エスケープを構成するには</span><span class="sxs-lookup"><span data-stu-id="ecace-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="ecace-111">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ecace-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="ecace-112">**Set-CsVoicePolicy に次のパラメーターを指定します**。</span><span class="sxs-lookup"><span data-stu-id="ecace-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>

   - <span data-ttu-id="ecace-113">**EnableVoicemailEscapeTimer** - エスケープ タイマーを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="ecace-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>

   - <span data-ttu-id="ecace-114">**PSTNVoicemailEscapeTimer** - タイムアウト値をミリ秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="ecace-114">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds.</span></span> <span data-ttu-id="ecace-115">既定値は 1500 ミリ秒で、指定できる値の範囲は 0 ～ 8000 ミリ秒です。</span><span class="sxs-lookup"><span data-stu-id="ecace-115">The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

## <a name="example"></a><span data-ttu-id="ecace-116">例</span><span class="sxs-lookup"><span data-stu-id="ecace-116">Example</span></span>

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a><span data-ttu-id="ecace-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ecace-117">See also</span></span>

[<span data-ttu-id="ecace-118">通話機能と特権の承認のための音声ポリシーと PSTN 使用法レコードの構成</span><span class="sxs-lookup"><span data-stu-id="ecace-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges)