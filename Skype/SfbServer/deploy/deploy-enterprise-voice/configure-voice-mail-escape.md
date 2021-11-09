---
title: ボイス メール エスケープを構成Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: '概要: 管理シェルを使用して、Skype for Business Serverでボイス メール エスケープSkype for Business Server説明します。'
ms.openlocfilehash: 7bd18056362fc4ed6ffdede31515b6eb41d8b134
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60865324"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>ボイス メール エスケープを構成Skype for Business

**概要:** 管理シェルを使用して、Skype for Business Serverボイス メール エスケープを構成Skype for Business Server説明します。

ユーザーが携帯電話への同時呼び出し音を構成すると、通常、携帯電話がオフになっている場合、バッテリーの電源が切れ、または範囲外の場合、発信者はユーザーの個人用ボイス メールにルーティングされます。 このSkype for Business Server、ユーザーは企業のボイス メール システムにビジネス関連の通話をルーティングできます。 具体的には、タイマーを構成できます。通話が定義された範囲内で通信事業者のボイス メールによって応答された場合、Skype for Business Server は通信事業者のボイス メール システム (およびユーザーの個人用ボイス メール) から切断され、企業システム内のユーザーの残りのエンドポイントは引き続き呼び出されます。 これにより、発信者は自動的にユーザーの企業ボイス メールにルーティングされます。

この構成は、Skype for Business Server管理シェル コマンドレット **Set-CsVoicePolicy** を音声ポリシー レベルで使用して、次のパラメーターを使用して実行されます。

### <a name="to-configure-voice-mail-escape"></a>ボイス メール エスケープを構成するには

1. 管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[管理シェルSkype for Business Server **クリックします**。

2. **Set-CsVoicePolicy に次のパラメーターを指定します**。

   - **EnableVoicemailEscapeTimer** - エスケープ タイマーを有効または無効にします。

   - **PSTNVoicemailEscapeTimer** - タイムアウト値をミリ秒単位で指定します。 既定値は 1500 ミリ秒で、指定できる値の範囲は 0 ～ 8000 ミリ秒です。

## <a name="example"></a>例

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>関連項目

[通話機能と特権の承認のための音声ポリシーと PSTN 使用法レコードの構成](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges)