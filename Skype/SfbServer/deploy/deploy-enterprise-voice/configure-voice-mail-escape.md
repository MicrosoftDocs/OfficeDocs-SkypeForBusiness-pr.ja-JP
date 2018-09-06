---
title: ビジネス用の Skype でボイス メールのエスケープを構成します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: '概要: ビジネス サーバー管理シェルには、Skype を使用して、Skype のビジネス サーバーのボイス メールのエスケープを構成する方法を説明します。'
ms.openlocfilehash: 4d93f188b137c3ecea014b8e407456e20195cbe1
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23261365"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a><span data-ttu-id="963d8-103">ビジネス用の Skype でボイス メールのエスケープを構成します。</span><span class="sxs-lookup"><span data-stu-id="963d8-103">Configure voice mail escape in Skype for Business</span></span>

<span data-ttu-id="963d8-104">**の概要:** ビジネス サーバー管理シェルには、Skype を使用して、Skype のビジネス サーバーのボイス メールのエスケープを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="963d8-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="963d8-105">ユーザーは、携帯電話の同時呼び出しを構成、呼び出し元は通常場合に送られますユーザーの個人用のボイス メール、携帯電話のオン/オフ、バッテリ電源では、範囲外です。</span><span class="sxs-lookup"><span data-stu-id="963d8-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="963d8-106">ビジネス サーバーの Skype でユーザーをビジネスに関連する通話を企業内のボイス メール システムにルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="963d8-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="963d8-107">具体的には、タイマーを構成することができ、Skype ビジネス サーバーのユーザーの中に通信事業者のボイス メール システム (およびユーザーの個人用のボイス メール) から切断する場合は、応答が定義されている時間の範囲内での通信事業者のボイス メール、企業のシステムの残りのエンドポイントでは、鳴り続けます。</span><span class="sxs-lookup"><span data-stu-id="963d8-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="963d8-108">この方法では、呼び出し元はユーザーの企業のボイス メールに自動的にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="963d8-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>

<span data-ttu-id="963d8-109">ビジネス サーバー管理シェル コマンドレット**セット CsVoicePolicy**、レベルの音声ポリシー、次のパラメーターでは、Skype を使用して、この構成が実行されます。</span><span class="sxs-lookup"><span data-stu-id="963d8-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="963d8-110">ボイス メール エスケープを構成するには</span><span class="sxs-lookup"><span data-stu-id="963d8-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="963d8-111">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="963d8-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="963d8-112">**Set-CsVoicePolicy** に対して次のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="963d8-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>

   - <span data-ttu-id="963d8-113">**EnableVoicemailEscapeTimer** - エスケープ タイマーを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="963d8-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>

   - <span data-ttu-id="963d8-p102">**PSTNVoicemailEscapeTimer**: タイムアウト値をミリ秒単位で指定します。既定値は 1500 ミリ秒で、指定できる値の範囲は 0 ～ 8000 ミリ秒です。</span><span class="sxs-lookup"><span data-stu-id="963d8-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

## <a name="example"></a><span data-ttu-id="963d8-116">例</span><span class="sxs-lookup"><span data-stu-id="963d8-116">Example</span></span>

```
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a><span data-ttu-id="963d8-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="963d8-117">See also</span></span>

[<span data-ttu-id="963d8-118">通話機能と特権を承認するには、音声ポリシーと PSTN 使用法レコードの構成</span><span class="sxs-lookup"><span data-stu-id="963d8-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

