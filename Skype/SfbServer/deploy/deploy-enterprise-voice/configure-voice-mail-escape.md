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
ms.openlocfilehash: c9a858ead9261944c162cb10fda63840f8de86d3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233575"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Skype for Business でボイスメールのエスケープを設定する

**概要:** Skype for business Server 管理シェルを使用して、Skype for Business Server でボイスメールのエスケープを構成する方法について説明します。

ユーザーが携帯電話との同時呼び出しを構成する場合、携帯電話がオフになっているか、バッテリ電力が不足しているか、または範囲外である場合、通常、発信者はユーザーの個人用ボイスメールにルーティングされます。 Skype for Business Server では、ユーザーはビジネス関連の通話を会社のボイスメールシステムにルーティングすることを選ぶことができます。 特に、タイマーは構成可能であり、定義された時間内に電話会社のボイスメールによって通話が応答された場合、Skype for Business Server は、電話会社のボイスメールシステム (およびユーザーの個人ボイスメール) から切断しますが、ユーザーの企業システムの残りのエンドポイントでも、呼び出しが続行されます。 こうすることで、発信者はユーザーの会社のボイスメールに自動的にルーティングされます。

この構成は、Skype for Business Server Management Shell コマンドレット**CsVoicePolicy**を使用して、音声ポリシーレベルで次のパラメーターを指定して実行します。

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

