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
description: 組織の既定のボイスメール応答メッセージで別の言語を使用するように Skype for Business をセットアップする方法について説明します。
ms.openlocfilehash: 9941ba697300d7dd1426e278d8d42900621cf58a
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904332"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a>応答メッセージとメールに使用する既定の言語を変更する

[グローバル管理者](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)である場合は、Skype for business で、既定のボイスメール応答メッセージを別の言語で再生するように設定できます。 既定のシステム応答メッセージは、たとえば「内田です。ただいま、席を外しております。 発信音の後に、メッセージを録音してください。 終わりましたら、電話を切るか、シャープを押して別のオプションを選択してください。」のようになっています。 
  
 **最初に、次の重要な情報をお読みください。**
  
- **利用できる言語は組織の場所によって決まります** 。 たとえば、組織が米国内にある場合は、既定の言語を英語またはスペイン語に設定できます。 組織がカナダにある場合は、英語とフランス語から選べます。 サポートされる言語のリストについては、「[Skype for Business からのボイスメールの応答メッセージに使用する言語](languages-for-voicemail-greetings-and-messages.md)」をご覧ください。
    
- **個々のユーザのボイスメールの応答メッセージとボイスメールメッセージの言語を変更します。** ユーザーの優先 lanaguage を変更することができます。これにより、Outlook メールボックスに送信されるボイスメールの応答メッセージとボイスメールメッセージの言語が変更されます。 手順については、「Office 365 の言語と地域設定を設定するhttps://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region)方法」を参照してください。 
    
    > [!NOTE]
    > [Microsoft 365 For Business の [表示言語とタイムゾーンの変更](https://support.office.com/en-us/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US)] にある手順に従って、ユーザーが自分のあいさつ文の言語を変更することができます。
  
- **発信ボイス メール メッセージを録音する場合は、** 「[Skype for Business ボイス メールの確認とオプション](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)」をご覧ください。 Microsoft Teams の場合-ユーザーは、[ [Teams デスクトップクライアント](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)] の設定からボイスメールの設定を変更できます

- **ボイスメールプロンプトの言語を変更しますか?** Skype for Business につい[https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail)ては、[**プロンプト言語**] で新しい言語を選択します。 Microsoft Teams の場合-ユーザーは、 [Teams のデスクトップクライアント設定](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)からボイスメールの応答メッセージを変更することができます。
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a>組織のユーザー全員に対してシステムの言語を変更する

1. [グローバル管理者](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)アカウントでサインイン[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)します。 
    
2. Microsoft 365 管理センターで、[**設定** > **Settings** > の構成] の [**組織プロファイル**] を選びます。 
    
     ![[設定]、[組織プロファイル] の選択を示すスクリーンショット。](media/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. [ **編集**] を選びます。
    
    ![[編集] オプションが表示されたスクリーンショット。](media/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. [ **優先言語**] リストから、組織内のすべてのユーザーのための言語を選択します。
    
5. [ **保存**] を選びます。
    
## <a name="related-articles-for-the-admin"></a>管理者向けの関連記事

- [電話システムと通話プラン](calling-plan-landing-page.md)
    
- [通話プランの設定](set-up-calling-plans.md)
    
- [Skype for Business Server でオンプレミスの PSTN 接続を使用して、Office 365 で電話システムを計画する](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a>関連トピック

- [一般法人向け Office 365 で表示言語とタイム ゾーンを変更する](https://support.office.com/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- [Office 2010 以降で別の言語を使用できるようにする](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)
    
- [キーボード レイアウトの言語を有効化または変更する](https://support.office.com/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    
  
 
