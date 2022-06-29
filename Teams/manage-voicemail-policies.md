---
title: ボイスメール ポリシーを管理する
author: crowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
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
ms.openlocfilehash: 7af4fa89dd495679a3ec755dd2e902012ad1ef77
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66240516"
---
# <a name="manage-cloud-voicemail-policies-for-your-users"></a>ユーザーのクラウド ボイスメール ポリシーを管理する

> [!WARNING]
> Skype for Business顧客の場合、Microsoft Teams 通話ポリシーを使用してボイスメールを無効にすると、Skype for Business ユーザーのボイスメール サービスが無効になる場合もあります。

ボイスメール ポリシーを使用すると、通話応答ルール、ボイスメール文字起こし、文字起こしの不適切なマスク、文字起こしの翻訳、システム プロンプト言語などの機能について、既存または新しいボイスメール ポリシーを構成してユーザーのグループに割り当てることができます。

ポリシーを指定する前に、「[クラウド ボイスメールのセットアップ」](set-up-phone-system-voicemail.md)を参照してください。 個々のユーザーの設定を管理する方法については、「 [ボイスメール の設定を管理する](manage-voicemail-settings.md)」を参照してください。

ボイスメール ポリシーを管理するには、Teams 管理センターまたは New-CsOnlineVoicemailPolicy PowerShell コマンドレットを使用します。 

ユーザーの既定のポリシーは次のとおりです。

- ボイスメールの文字起こしが有効になっている。
- ボイスメールの文字起こし変換が有効になっています。
- ボイスメール文字起こしの不適切なマスクは無効です。
- 最大記録時間は 5 分に設定されます。
- 通話応答ルールの編集が有効になっている。
- プライマリとセカンダリのシステム プロンプト言語は null に設定され、ユーザーのボイスメール言語設定が使用されます。

自動的に作成されるグローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てることができます。

> [!IMPORTANT]
> Microsoft 365 のボイスメール サービスは、ボイスメール ポリシーをキャッシュし、6 時間ごとにキャッシュを更新します。 そのため、ポリシーの変更が適用されるまでに最大で 6 時間かかる場合があります。

## <a name="use-teams-admin-center"></a>Teams 管理センターを使用する

### <a name="create-a-custom-voicemail-policy"></a>カスタム ボイスメール ポリシーを作成する

カスタム ボイスメール ポリシーを作成するには、次の手順に従います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、 **ボイス** > **ボイスメール ポリシー** に移動します。

2. **[追加]** を選択します。

3. ボイスメール ポリシーで使用する機能をオンまたはオフにします。

4. **[保存]** を選択します。

### <a name="edit-a-voicemail-policy"></a>ボイスメール ポリシーを編集する

既存のボイスメール ポリシーを編集するには、次の手順に従います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、 **ボイス** > **ボイスメール ポリシー** を選択します。

2. 変更するポリシーの横にあるをクリックし、[ **編集]** を選択します。

3. 必要な変更を加え、[保存] をクリック **します**。

> [!IMPORTANT]
> TranscriptionDisabled および TranscriptionProfanityMaskingEnabled という事前構成済みのポリシー インスタンスを編集または削除することはできません。


### <a name="assign-a-custom-voicemail-policy-to-users"></a>ユーザーにカスタム ボイスメール ポリシーを割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="use-powershell"></a>PowerShell を使用する

PowerShell を使用して、既存または新しいボイスメール ポリシーを構成して割り当てることもできます。 PowerShell を使用してポリシーを管理するには、次のコマンドレットを使用します。

- [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy)

- [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

- [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)

- [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/grant-csonlinevoicemailpolicy)

- [Remove-CsOnlineVoicemailPolicy](/powershell/module/skype/remove-csonlinevoicemailpolicy)

## <a name="voicemail-policy-settings"></a>ボイスメール ポリシーの設定
  
- **文字起こしを有効にする** - この設定は、クラウド ボイスメール サービスが記録されたボイスメールのテキスト変換を生成し、ボイスメール メッセージに含めるかどうかを制御します。 文字起こしは、記録されたボイスメールで検出された言語に基づいて行われます。

- **文字起こし変換** - この設定は、クラウド ボイスメール サービスが記録されたボイスメールの文字起こしを翻訳するかどうかを制御します。 ボイスメール レシーバーの優先言語への翻訳が試行されます。

- **文字起こしの不適切な表現のマスク** - この設定は、クラウド ボイスメール サービスがボイスメールの文字起こしで見つかった不適切な表現をマスクするかどうかを制御します。

- **最大録音時間** - 最大録音時間は、ボイスメールを記録できる最大時間を制御します。 既定値は 5 分です。

- **通話応答ルール** - この設定は、ユーザーが Microsoft Teams でボイスメール通話応答ルールを構成できるかどうかを制御します。

- **デュアル言語システムプロンプト** - 既定では、ボイスメール システムのプロンプトは、ボイスメールの設定時にユーザーが選択した言語の発信者に表示されます。 ボイスメール システムプロンプトを 2 つの言語で表示する必要がある場合は、プライマリ言語とセカンダリ言語を設定でき、同じでない場合があります。

### <a name="share-data-for-service-improvements"></a>サービス改善のためにデータを共有する

ボイスメールと文字起こしデータをサービスと共有してトレーニングし、精度を向上させるかどうかを指定します。 false に設定すると、ユーザーの選択に関係なくボイスメール データは共有されません。


## <a name="related-articles"></a>関連記事


