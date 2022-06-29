---
title: クラウド ボイスメール設定の管理
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
description: ユーザーのボイスメール設定を管理します。
ms.openlocfilehash: 80dad0b2088518c9d6f08ee005eba25cc1e10e2b
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66494852"
---
# <a name="manage-cloud-voicemail-settings-for-users"></a>ユーザーのクラウド ボイスメール設定を管理する

ボイスメール設定を使用すると、個々のユーザーのボイスメール設定を構成できます。

ユーザーのボイスメール設定を構成する前に、「クラウド ボイスメールの[セットアップ」](set-up-phone-system-voicemail.md)を参照してください。 ユーザーのグループにポリシーを設定する方法については、「 [ボイスメール ポリシーの管理」を](manage-voicemail-policies.md)参照してください。

クラウド ボイスメールの既定の設定は次のとおりです。

- ボイスメールが有効になっている。
- プロンプト言語は、ユーザーの優先言語に設定されます。
- 不在時のあいさつ文は無効です。
- Outlook で自動応答が設定されている場合、不在時のあいさつ文は無効になります。
- Outlook の予定表が不在時に表示される不在時のあいさつ文は無効です。
- トレーニングと精度の向上を目的として、ボイスメールと文字起こしデータをサービスと共有することは無効になっています。
- 通話応答ルールは、通常のボイスメールに設定されます。
- 既定のあいさつメッセージの上書きは設定されていません。
- 既定の不在時のあいさつメッセージの上書きは設定されていません。
- 転送先が設定されていません。


ユーザーのクラウド ボイスメール機能を管理するには、Teams 管理センターまたは PowerShell を使用できます。 エンド ユーザーは、[設定] **-> [通話] -> [ボイスメールの構成]** に移動して、Teams クライアントでこれらの設定を構成することもできます。

## <a name="use-teams-admin-center"></a>Teams 管理センターを使用する

Teams 管理センターで次の手順を実行します。

1.  左側のナビゲーションで、[ユーザー] **> [ユーザーの管理** ] に移動し、ユーザーを選択します。

2.  ユーザーの詳細ページで、[ **ボイスメール** ] タブに移動します。

3.  設定を変更します。

4.  **[保存]** を選択します。


## <a name="use-powershell"></a>PowerShell を使用する

PowerShell を使用して、ボイスメール設定を次のように管理することもできます。

- 個々のユーザーのクラウド ボイスメール設定を管理するには、[Set-CsOnlineVoicemailUserSettings コマンドレットを](/powershell/module/skype/set-csonlinevoicemailusersettings)使用します。 

- 設定を表示するには、 [Get-CsOnlineVoicemailUserSettings コマンドレットを](/powershell/module/skype/get-csonlinevoicemailusersettings) 使用します。

- [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) コマンドレットを使用し、ボイスメールEnabled パラメーターを$falseに設定することで、ユーザーのクラウド ボイスメールを無効にすることができます。 

## <a name="voicemail-settings"></a>ボイスメールの設定

- **ボイスメールが有効 -** この設定は、ユーザーに対してクラウド ボイスメールを有効にするかどうかを制御します。 設定が false の場合、クラウド ボイスメール サービスはユーザーに対して使用できず、ユーザーのボイスメールは記録されません。

- **プロンプト言語** - この設定は、クラウド ボイスメールのプロンプトに使用される言語を指定します。 詳細については、「 [あいさつ文とメールの既定の言語を変更する](change-the-default-language-for-greetings-and-emails.md)」を参照してください。

- **あいさつ文の設定** - クラウド ボイスメールは、ユーザーがオフィスにいるときと、ユーザーが不在の場合に、特定のあいさつ文を再生できます。 どちらのあいさつも、ユーザーが記録することも、テキスト読み上げのあいさつも使用できます。

  - **既定のあいさつメッセージの上書き** - ユーザーがあいさつ文を記録していない場合に再生される音声合成あいさつ文を指定します。

  - **Oof Greeting Enabled** - Outlook の設定に関係なく、不在時のあいさつメッセージをボイスメールの入金シナリオで再生するかどうかを指定します。

  - **Oof Greeting Follow Automatic Replies Enabled** - ユーザーが Outlook で自動返信を設定したときに、ボイスメールの入金シナリオで不在時のあいさつを再生するかどうかを指定します。

  - **Oof Greeting Follow Calendar Enabled** - ユーザーが予定表で不在時に設定した場合に、ボイスメールの入金シナリオで不在時のあいさつを再生するかどうかを指定します。

  - **既定の Oof グリーティング プロンプトの上書き** - ユーザーが不在で、不在時のあいさつを記録していない場合に再生されるテキスト読み上げあいさつ文を指定します。

- **通話応答ルール** - この設定では、通話応答ルールを指定します。 ルールは次のとおりです。
  - サービスは、メッセージなしで呼び出しを拒否します。
  - 関連するあいさつ (通常または不在) のみが再生されます。
  - 関連するあいさつ (通常または不在) が再生され、呼び出し元が指定したユーザーまたは電話番号に転送されます。
  -  関連するあいさつ (通常または不在) が再生され、発信者はボイスメールを残すことができます。
  - 関連するあいさつメッセージ (通常または不在) が再生され、発信者はボイスメールを離れることができ、0 キーを押して指定したユーザーまたは電話番号に転送できます。

- **サービス改善のためにデータを共有する** - ボイスメールと文字起こしのデータをサービスと共有してトレーニングし、精度を向上させるかどうかを指定します。 false に設定すると、ユーザーの選択に関係なくボイスメール データは共有されません。

- **通話転送** - 発信者の転送元のユーザーまたは電話番号を指定します。


