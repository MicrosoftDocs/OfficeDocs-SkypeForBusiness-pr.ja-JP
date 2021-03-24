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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 組織の既定のボイスメール応答メッセージに別の言語を使用する Skype for Business をセットアップする方法について説明します。
ms.openlocfilehash: f6fb890d52e052afffccbfe753ab5b3b8a1bb338
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102673"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a>応答メッセージとメールに使用する既定の言語を変更する

グローバル管理者 [の場合は](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)、別の言語で既定のボイスメール応答メッセージを再生する Skype for Business を設定できます。 既定のシステム応答メッセージは、たとえば「内田です。ただいま、席を外しております。 発信音の後に、メッセージを録音してください。 終わりましたら、電話を切るか、シャープを押して別のオプションを選択してください。」のようになっています。 
  
 **最初に、次の重要な情報をお読みください。**
  
- **利用できる言語は組織の場所によって決まります** 。 たとえば、組織が米国内にある場合は、既定の言語を英語またはスペイン語に設定できます。 組織がカナダにある場合は、英語とフランス語から選べます。 サポートされる言語のリストについては、「[Skype for Business からのボイスメールの応答メッセージに使用する言語](languages-for-voicemail-greetings-and-messages.md)」をご覧ください。
    
- **個々のユーザーのボイスメール応答メッセージとボイスメール メッセージの言語を変更する。** ユーザーに優先する言語を変更できます。この場合、ボイスメール応答メッセージと Outlook メールボックスに送信されるボイスメール メッセージの言語が変更されます。 手順については、「Microsoft 365 または Office 365 の言語と地域の設定を設定する方法」 https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region) (. 
    
    > [!NOTE]
    > [ユーザーは、Microsoft 365 for Business](https://support.office.com/en-us/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US)の表示言語とタイム ゾーンの変更に関する手順に従って、サインイン後に設定を使用して独自の応答メッセージの言語を変更できます。
  
- **発信ボイス メール メッセージを録音する場合は、** 「[Skype for Business ボイス メールの確認とオプション](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)」をご覧ください。 Microsoft Teams の場合 - ユーザーは Teams デスクトップ クライアントの設定から [ボイスメールの設定を変更できます](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)

- **ボイスメール プロンプトの言語を変更しますか?** Skype for Business の場合 - [  [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) プロンプト言語] で新しい言語 **を選択します**。 Microsoft Teams の場合 - ユーザーは Teams デスクトップ クライアント設定からボイスメール応答 [メッセージを変更できます](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a>組織のユーザー全員に対してシステムの言語を変更する

1. グローバル管理者 [アカウントでサインイン](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) します [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 。 
    
2. Microsoft 365 管理センターで、[設定の設定] 組織  >  **プロファイル**  >  **を選択します**。 
    
     ![[設定]、次に [組織プロファイル] の順に選択しているスクリーンショット。](media/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. [ **編集**] を選びます。
    
    ![[編集] オプションを示すスクリーンショット。](media/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. [ **優先言語**] リストから、組織内のすべてのユーザーのための言語を選択します。
    
5. [ **保存**] を選びます。
    
## <a name="related-articles-for-the-admin"></a>管理者向けの関連記事

- [電話システムと通話プラン](calling-plan-landing-page.md)
    
- [通話プランの設定](set-up-calling-plans.md)
    
- [Skype for Business Server でオンプレミス PSTN 接続Office Microsoft 365 または Office 365 の電話システムを計画する](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
    
## <a name="related-topics"></a>関連項目

- [Microsoft 365 または Office 365 for Business で表示言語とタイム ゾーンを変更する](https://support.office.com/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- [Office 2010 以降で別の言語を使用できるようにする](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)
    
- [キーボード レイアウトの言語を有効化または変更する](https://support.office.com/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    
  
