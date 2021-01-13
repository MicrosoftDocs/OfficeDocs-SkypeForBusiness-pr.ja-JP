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
ms.openlocfilehash: c6326360a0e49715feb7e9f9c3c123ec42b9c330
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824927"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Skype for Business でボイス メール エスケープを構成する

**概要:** Skype for Business Server 管理シェルを使用して Skype for Business Server でボイス メール エスケープを構成する方法について説明します。

ユーザーが携帯電話への同時呼び出しを構成する場合、通常、携帯電話がオフになっている、バッテリがオフになっている、または使用範囲が外になっている場合、発信者はユーザーの個人用ボイス メールにルーティングされます。 Skype for Business Server を使用すると、ユーザーは会社のボイス メール システムにルーティングされたビジネス関連の通話を選択できます。 具体的には、タイマーを構成できます。通話が定義された時間の範囲内で通信事業者のボイス メールによって応答された場合、Skype for Business Server は通信事業者のボイス メール システム (およびユーザーの個人用ボイス メール) から切断し、企業システム内のユーザーの残りのエンドポイントは呼び出しを続行します。 これにより、発信者は自動的にユーザーの会社のボイス メールにルーティングされます。

この構成は、次のパラメーターを使用して、音声ポリシー レベルで Skype for Business Server 管理シェル コマンドレット **Set-CsVoicePolicy** を使用して実行します。

### <a name="to-configure-voice-mail-escape"></a>ボイス メール エスケープを構成するには

1. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。

2. **Set-CsVoicePolicy に次のパラメーターを指定します**。

   - **EnableVoicemailEscapeTimer** - エスケープ タイマーを有効または無効にします。

   - **PSTNVoicemailEscapeTimer** - タイムアウト値をミリ秒単位で指定します。 既定値は 1500 ミリ秒で、指定できる値の範囲は 0 ～ 8000 ミリ秒です。

## <a name="example"></a>例

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>関連項目

[通話機能と特権の承認のための音声ポリシーと PSTN 使用法レコードの構成](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

