---
title: 応答メッセージとメールに使用する既定の言語を変更する
author: crowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: Microsoft Teams とSkype for Businessを設定して、組織の既定のボイスメールあいさつ文に別の言語を使用する方法について説明します。
ms.openlocfilehash: 30e122c0d41c93326cdfa39de4c0ceb3a6d55cd2
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66241126"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a>応答メッセージとメールに使用する既定の言語を変更する

クラウド ボイスメールでは、さまざまな言語設定を使用してあいさつ文を再生し、文字起こし翻訳を生成し、ボイスメール メッセージを生成します。 言語設定は、既定でテナント レベル、ポリシー別、または特定のユーザーに対して個別に指定できます。

## <a name="greetings"></a>挨拶
あいさつ文はボイスメールを離れる発信者に対して再生され、次の種類にすることができます。

- システムあいさつ文
- 呼び出されるユーザーによって記録されたカスタムあいさつ文
- 呼び出されるユーザーに対して指定されたカスタムテキスト読み上げあいさつ

システム案内応答の再生に使用される言語は、優先度順に、ユーザーに割り当てられたオンライン ボイスメール ポリシーで指定されたプライマリとセカンダリのプロンプト言語、ユーザーに指定された優先言語、または既定のテナント言語です。

カスタムあいさつ文と不在時のあいさつ文は、ユーザーが選択した言語でユーザーによって記録されます。

ユーザーまたはテナント管理者がユーザーに対してカスタムテキスト読み上げあいさつ文を指定する場合、音声の生成に使用される言語は、テキスト読み上げあいさつ文と共に指定された PromptLanguage です。

カスタムテキスト読み上げあいさつ文は、ユーザーに対してカスタムあいさつ文が記録されていない場合にのみ使用されます。

## <a name="transcription"></a>転写
呼び出し元のユーザーに対してオンライン ボイスメール ポリシーによって有効になっている場合、クラウド ボイスメールは発信者が残したボイスメールを文字起こししようとします。 音声検出を使用して、オーディオ コンテンツで使用される言語を理解し、可能であれば、検出された言語を使用してコンテンツを文字起こしします。

## <a name="transcription-translation"></a>文字起こしの翻訳
呼び出されるユーザーのオンライン ボイスメール ポリシーによって有効になっている場合、クラウド ボイスメールは、書き起こされたボイスメールを変換します。 音声検出中に検出された言語から、ユーザーに指定された優先言語または既定のテナント言語に優先順位を付けて変換されます。

## <a name="voicemail-message-template"></a>ボイスメール メッセージ テンプレート
クラウド ボイスメールは、ユーザーまたは既定のテナント言語に指定された優先言語に基づいて、優先度順に言語テンプレートを使用してボイスメール メッセージを生成します。

## <a name="setting-the-preferred-language-for-a-user"></a>ユーザーの優先言語を設定する
Azure Active Directory またはオンプレミスの Active Directoryで PowerShell を使用して、ユーザーの優先言語を設定できます。 詳細については、「[Microsoft 365 またはOffice 365の言語と地域の設定を設定する方法](/office365/troubleshoot/access-management/set-language-and-region)」を参照してください。

ユーザーは、サインイン後に設定を使用して独自の優先言語を変更できます。 詳細については、「[Microsoft 365 for Business で表示言語とタイム ゾーンを変更する」を参照してください](https://support.office.com/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US)。

## <a name="change-the-system-language-for-everyone-in-your-organization"></a>組織のユーザー全員に対してシステムの言語を変更する

1. [グローバル管理者](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)アカウントで[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)サインインします。

2. Microsoft 365 管理センターで、[**組織の設定の組織** プロファイル **の設定** > ]  >  を選択 **します**。

3. [ **組織情報] を選択します**。

4. [ **優先言語**] リストから、組織内のすべてのユーザーのための言語を選択します。

5. [ **保存**] を選びます。

**利用できる言語は組織の場所によって決まります** 。 たとえば、組織が米国内にある場合は、既定の言語を英語またはスペイン語に設定できます。 組織がカナダにある場合は、英語とフランス語から選べます。

## <a name="supported-languages-in-cloud-voicemail"></a>クラウド ボイスメールでサポートされている言語
Microsoft Teams とSkype for Businessのクラウド ボイスメールでサポートされている言語の一覧については、[サポートされている言語クラウド ボイスメール](languages-for-voicemail-greetings-and-messages.md)参照してください。
  

## <a name="custom-greeting-recorded-by-a-user"></a>ユーザーが記録したカスタムあいさつ文
ユーザーは、独自のカスタムおよび不在時のカスタムあいさつ文を記録できます。 [Teams デスクトップ クライアントの設定](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)と[ボイスメールとオプションSkype for Business確認](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)するを参照してください。

## <a name="custom-text-to-speech-greeting-specified-for-a-user"></a>ユーザーに対して指定されたカスタムテキスト読み上げあいさつ
テナント管理者は、Teams 管理センターの [ユーザーの詳細] ページの [ボイスメール] タブを使用するか、 [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) コマンドレットを使用して、ユーザーのカスタムテキスト読み上げあいさつおよびプロンプト言語を指定できます。

## <a name="custom-text-to-speech-greeting-specified-by-a-user"></a>ユーザーが指定したカスタムテキスト読み上げあいさつ
ユーザーは、独自のカスタムテキスト読み上げあいさつ文と、あいさつ文に使用する言語を指定できます。 Microsoft Teams の場合、ユーザーは [Teams デスクトップ クライアント設定](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)からボイスメールのあいさつ文を変更できます。 Skype for Business - [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) **プロンプト言語** で新しい言語を選択します。 


## <a name="related-articles"></a>関連記事

[Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings)

[Get-CsOnlineVoicemailUserSettings](/powershell/module/skype/get-csonlinevoicemailusersettings)

[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

[Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)
