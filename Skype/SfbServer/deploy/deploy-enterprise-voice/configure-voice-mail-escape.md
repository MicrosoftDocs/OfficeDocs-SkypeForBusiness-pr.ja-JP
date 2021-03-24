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
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Skype for Business でボイス メール エスケープを構成する

**概要:** Skype for Business Server 管理シェルを使用して Skype for Business Server でボイス メール エスケープを構成する方法について説明します。

ユーザーが携帯電話への同時呼び出し音を構成すると、通常、携帯電話がオフになっている場合、バッテリーの電源が切れ、または範囲外の場合、発信者はユーザーの個人用ボイス メールにルーティングされます。 Skype for Business Server を使用すると、ビジネス関連の通話を企業のボイス メール システムにルーティングできます。 具体的には、タイマーを構成し、通話が定義された範囲内で通信事業者のボイス メールによって応答された場合、Skype for Business Server は通信事業者のボイス メール システム (およびユーザーの個人用ボイス メール) から切断され、企業システム内のユーザーの残りのエンドポイントは引き続き呼び出されます。 これにより、発信者は自動的にユーザーの企業ボイス メールにルーティングされます。

この構成は、次のパラメーターを使用して、音声ポリシー レベルで Skype for Business Server 管理シェル コマンドレット **Set-CsVoicePolicy** を使用して実行されます。

### <a name="to-configure-voice-mail-escape"></a>ボイス メール エスケープを構成するには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。

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