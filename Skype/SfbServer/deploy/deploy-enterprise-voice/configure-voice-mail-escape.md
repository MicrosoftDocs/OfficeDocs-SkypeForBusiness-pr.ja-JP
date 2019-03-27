---
title: ビジネス用の Skype でボイス メールのエスケープを構成します。
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: '概要: ビジネス サーバー管理シェルには、Skype を使用して、Skype のビジネス サーバーのボイス メールのエスケープを構成する方法を説明します。'
ms.openlocfilehash: 6c1c6977949eb45c28cce482f98be67295ee4eef
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891868"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>ビジネス用の Skype でボイス メールのエスケープを構成します。

**の概要:** ビジネス サーバー管理シェルには、Skype を使用して、Skype のビジネス サーバーのボイス メールのエスケープを構成する方法について説明します。

ユーザーは、携帯電話の同時呼び出しを構成、呼び出し元は通常場合に送られますユーザーの個人用のボイス メール、携帯電話のオン/オフ、バッテリ電源では、範囲外です。 ビジネス サーバーの Skype でユーザーをビジネスに関連する通話を企業内のボイス メール システムにルーティングできます。 具体的には、タイマーを構成することができ、Skype ビジネス サーバーのユーザーの中に通信事業者のボイス メール システム (およびユーザーの個人用のボイス メール) から切断する場合は、応答が定義されている時間の範囲内での通信事業者のボイス メール、企業のシステムの残りのエンドポイントでは、鳴り続けます。 この方法では、呼び出し元はユーザーの企業のボイス メールに自動的にルーティングされます。

ビジネス サーバー管理シェル コマンドレット**セット CsVoicePolicy**、レベルの音声ポリシー、次のパラメーターでは、Skype を使用して、この構成が実行されます。

### <a name="to-configure-voice-mail-escape"></a>ボイス メール エスケープを構成するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

2. **Set-CsVoicePolicy** に対して次のパラメーターを指定します。

   - **EnableVoicemailEscapeTimer** - エスケープ タイマーを有効または無効にします。

   - **PSTNVoicemailEscapeTimer**: タイムアウト値をミリ秒単位で指定します。既定値は 1500 ミリ秒で、指定できる値の範囲は 0 ～ 8000 ミリ秒です。

## <a name="example"></a>例

```
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>関連項目

[Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

