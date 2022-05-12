---
title: ボイスメール ポリシーを管理する
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: ユーザーのボイスメール ポリシーを管理します。
ms.openlocfilehash: 3f4c64194fc9e2b24c59dc7bc06ed972e801a6a8
ms.sourcegitcommit: cd9a1f7afaaf053741c81022e7052bf6f8008fcc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2022
ms.locfileid: "65370830"
---
# <a name="setting-voicemail-policies-in-your-organization"></a>組織内のボイスメール ポリシーの設定

> [!WARNING]
> Skype for Business顧客の場合、Microsoft Teams通話ポリシーを使用してボイスメールを無効にすると、Skype for Business ユーザーのボイスメール サービスも無効になる可能性があります。

ボイスメール ポリシーを使用して、クラウド ボイスメールに関連するさまざまな機能を制御できます。

## <a name="voicemail-organization-defaults-for-all-users"></a>すべてのユーザーのボイスメール組織の既定値
- ボイスメールの文字起こしが有効になっている。
- ボイスメールの文字起こし変換が有効になっています。
- ボイスメール文字起こしの不適切なマスクは無効です。
- 最大記録時間は 5 分に設定されます。
- 通話応答ルールの編集が有効になっている。
- プライマリとセカンダリのシステム プロンプト言語は null に設定され、ユーザーのボイスメール言語設定が使用されます。

自動的に作成されるグローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てることができます。

## <a name="create-a-custom-voicemail-policy"></a>カスタム ボイスメール ポリシーを作成する

カスタム ボイスメール ポリシーを作成するには、次の手順に従います。

1. Microsoft Teams管理センターの左側のナビゲーションで、**VoiceVoicemail** >  ポリシーに移動します。
2. **[追加]** を選択します。
3. ボイスメール ポリシーで使用する機能をオンまたはオフにします。
4. **[保存]** を選択します。

## <a name="edit-a-voicemail-policy"></a>ボイスメール ポリシーを編集する

既存のボイスメール ポリシーを編集するには、次の手順に従います。

1. Microsoft Teams管理センターの左側のナビゲーションで、**VoiceVoicemail** >  ポリシーを選択します。
2. 変更するポリシーの横にあるをクリックし、[ **編集]** を選択します。
3. 必要な変更を加え、[保存] をクリック **します**。

> [!IMPORTANT]
> TranscriptionDisabled および TranscriptionProfanityMaskingEnabled という事前構成済みのポリシー インスタンスを編集または削除することはできません。


## <a name="assign-a-custom-voicemail-policy-to-users"></a>ユーザーにカスタム ボイスメール ポリシーを割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="voicemail-policy-settings"></a>ボイスメール ポリシーの設定
  
### <a name="enable-transcription"></a>文字起こしを有効にする

この設定は、クラウド ボイスメール サービスが記録されたボイスメールのテキスト変換を生成し、ボイスメール メッセージに含めるかどうかを制御します。 文字起こしは、記録されたボイスメールで検出された言語に基づいて行われます。

### <a name="transcription-translation"></a>文字起こしの翻訳

この設定は、クラウド ボイスメール サービスが記録されたボイスメールの文字起こしを変換するかどうかを制御します。 ボイスメール レシーバーの優先言語への翻訳が試行されます。

### <a name="transcription-profanity-masking"></a>文字起こしの不適切な表現のマスキング

この設定は、クラウド ボイスメール サービスがボイスメールの文字起こしで見つかった不適切な表現をマスクするかどうかを制御します。

### <a name="maximum-recording-duration"></a>最大記録期間

最大録音長は、ボイスメールを記録できる最大時間を制御します。 既定値は 5 分です。

### <a name="call-answering-rules"></a>通話応答ルール

この設定は、ユーザーがMicrosoft Teamsでボイスメール通話応答ルールを構成できるかどうかを制御します。

### <a name="dual-language-system-prompts"></a>デュアル言語システムのプロンプト

既定では、ボイスメール システムのプロンプトは、ボイスメールの設定時にユーザーが選択した言語で発信者に表示されます。 ボイスメール システムプロンプトを 2 つの言語で表示する必要がある場合は、プライマリ言語とセカンダリ言語を設定でき、同じでない場合があります。

### <a name="share-data-for-service-improvements"></a>サービス改善のためにデータを共有する

ボイスメールと文字起こしデータをサービスと共有してトレーニングし、精度を向上させるかどうかを指定します。 false に設定すると、ユーザーの選択に関係なくボイスメール データは共有されません。


> [!IMPORTANT]
> Microsoft 365およびOffice 365のボイスメール サービスは、ボイスメール ポリシーをキャッシュし、6 時間ごとにキャッシュを更新します。 そのため、ポリシーの変更が適用されるまでに最大で 6 時間かかる場合があります。

## <a name="related-articles"></a>関連記事

[New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy)

[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

[Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)

[Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/grant-csonlinevoicemailpolicy)

[Remove-CsOnlineVoicemailPolicy](/powershell/module/skype/remove-csonlinevoicemailpolicy)
