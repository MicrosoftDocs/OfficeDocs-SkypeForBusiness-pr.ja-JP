---
title: 応答メッセージとメールに使用する既定の言語を変更する
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh
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
description: 組織の既定のボイスメール応答Microsoft Teams別Skype for Business言語を使用する方法について学習します。
ms.openlocfilehash: 4c509edf6efa2fe660a59772f3266e6d49be8d31
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014421"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a>応答メッセージとメールに使用する既定の言語を変更する

グローバル管理者の場合[は、既定の](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)ボイスメール応答Skype for Business別の言語で再生するメッセージを設定できます。 既定のシステム応答メッセージは、たとえば「内田です。ただいま、席を外しております。 発信音の後に、メッセージを録音してください。 終わりましたら、電話を切るか、シャープを押して別のオプションを選択してください。」のようになっています。
  
 **最初に、次の重要な情報をお読みください。**
  
- **利用できる言語は組織の場所によって決まります** 。 たとえば、組織が米国内にある場合は、既定の言語を英語またはスペイン語に設定できます。 組織がカナダにある場合は、英語とフランス語から選べます。 サポートされている言語の一覧については、TeamsとSkype for Businessを参照してください。
  - [Microsoft Teamsサポートされている言語](languages-for-voicemail-greetings-and-messages.md)
  - [Skype for Businessサポートされている言語](/skypeforbusiness/what-is-phone-system-in-office-365/phone-system-voicemail/languages-for-voicemail-greetings-and-messages)

- **個々のユーザーのボイスメール応答メッセージとボイスメール メッセージの言語を変更する。** ユーザーの優先言語を変更できます。この言語を使用すると、ボイスメール応答メッセージとボイスメール メッセージが自分のメールボックスに送信Outlookされます。 詳細については、「言語または言語の言語と地域の設定を設定する[Microsoft 365」をOffice 365。](/office365/troubleshoot/access-management/set-language-and-region)

  > [!NOTE]
  > ユーザーはサイン インした後に設定を操作して自身のあいさつ文の言語を変更できます。 詳細については、「Microsoft 365 for Business で表示言語とタイム ゾーン[を変更する」を参照してください。](https://support.office.com/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US)
  
- **発信ボイス メール メッセージを録音する場合は、** 「[Skype for Business ボイス メールの確認とオプション](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)」をご覧ください。 [Microsoft Teams - ユーザーは、デスクトップ クライアントの設定からボイス[メールTeams変更できます。](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)

- **ボイスメール プロンプトの言語を変更しますか。** [Skype for Business - [ [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) プロンプト言語] で新しい言語 **を選択します**。 [Microsoft Teams - ユーザーは、デスクトップ クライアントの設定からボイスメール応答[Teamsを変更できます。](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)

## <a name="change-the-system-language-for-everyone-in-your-organization"></a>組織のユーザー全員に対してシステムの言語を変更する

1. でグローバル管理者 [アカウントで](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) サインインします [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 。

2. [組織Microsoft 365 管理センター プロファイル]**を**  >  **設定設定**  >  **選択します**。

     ![[組織プロファイル] を設定選択した後、組織プロファイルを示すスクリーンショット。](media/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. [ **編集**] を選びます。

    ![[編集] オプションを示すスクリーンショット。](media/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. [ **優先言語**] リストから、組織内のすべてのユーザーのための言語を選択します。

5. [ **保存**] を選びます。

## <a name="related-articles-for-the-admin"></a>管理者向けの関連記事

- [電話システムと通話プラン](calling-plan-landing-page.md)

- [通話プランの設定](set-up-calling-plans.md)

- [オンプレミス電話システム PSTN Microsoft 365接続Office 365を使用して、オンプレミスの PSTN 接続を使用して、オンプレミスの PSTN 接続をSkype for Business Server](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)

## <a name="related-topics"></a>関連項目

- [Microsoft 365 for Business で表示言語とタイム ゾーンOffice 365変更する](https://support.office.com/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)

- [Office 2010 以降で別の言語を使用できるようにする](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)

- [キーボード レイアウトの言語を有効化または変更する](https://support.office.com/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
