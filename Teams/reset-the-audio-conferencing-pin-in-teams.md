---
title: Microsoft Teams で電話会議の PIN をリセットする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: MICROSOFT TEAMS でユーザーの電話会議 PIN をリセットする方法と、PIN に関する重要な事実について説明します。
ms.openlocfilehash: ece69ec231408cc860f2fad803d92d22feaca781
ms.sourcegitcommit: cae94cd5761baafde51aea1137e6d164722eead9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2021
ms.locfileid: "53075380"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Microsoft Teams で電話会議の PIN をリセットする

PIN は、電話会議を有効にしているユーザーごとにMicrosoft Teams番号で構成されるコードです。 電話会議 PIN は、会議の開催者が会議の開催者を識別し、電話で会議を開始するために使用されます。 会議を開始Microsoft Teamsアプリを使用する場合、PIN は必要ありません。 ユーザーが自分の PIN を忘れて、電話会議を有効にした場合に送信されたメールで PIN が見つからなかった場合、管理者は PIN をリセットするか、自分の PIN をリセットできます。
  
認証されたユーザーが Microsoft Teams アプリを使用して参加した場合、または開催者が電話で PIN を使用して参加するときに、会議を開始できます。 会議を開始するために PIN が必要な場合、電話で参加するユーザーはロビーに配置され、開催者が許可するまで保留音を聞きます。 会議の開催者が、電話で会議を開始するための PIN を要求しない場合、発信者は会議に参加しようとするときに PIN の提示を求められません。

## <a name="reset-a-users-pin"></a>ユーザーの PIN をリセットする

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. [編集] **をクリックします**。

3. [ **電話会議] の [PIN** のリセット **] をクリックします**。

4. [リセット] **をクリックします**。
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-their-own-pin"></a>ユーザーに自分の PIN をリセットする

1. ユーザーに に移動します [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) 。
2. [PIN **のリセット] をクリックします**。 

> [!NOTE]
> GCCH の場合は、 に移動します https://webdir2g.online.gov.skypeforbusiness.us/lscp/usp/pstnconferencing 。

## <a name="what-else-should-you-know-about-pins"></a>PIN について知っておくべきその他のこと

- セキュリティ上の目的で、PIN がリセットされた場合、PIN は管理者に 1 回だけ表示されます。 管理者が PIN をリセットすると、PIN は *********** と表示されます。
    
- ユーザーへのメールの自動送信は既定で有効になっています。ユーザーが電話会議を有効にした場合、または PIN がリセットされた場合、ユーザーは PIN を含むメールを受信します。 ただし、メールの自動送信を無効にした場合、PIN リセット メールはユーザーに送信されません。PIN 情報をユーザーに手動で送信する必要があります。
    
- 会議が開始されると、ロビーのすべてのユーザーが自動的に会議に参加します。 たとえば、2 人の参加者が開始される前に会議に参加しようとする場合、その参加者はロビーに配置され、保留音を聞き、会議の開催者が電話で PIN を使用して参加すると、会議が開始され、ロビーの参加者が会議に参加します。
    
- 既定の設定では、匿名の発信者による会議の開始を許可しません。
    
- ユーザーが電話会議を有効にした場合、既定では、会議情報と PIN を含むメールが送信されます。 PIN をリセットすると、ユーザーに設定されているプライマリ SMTP アドレス (エイリアス) に新しい PIN が電子メールで送信されるので、ユーザーは Microsoft 365 または Office 365 メールボックスを持っている必要があります。
    
- 電話会議を設定するときに、組織内の PIN に必要な数字を設定します。 PIN は 4 桁から 12 桁まで指定できます。既定値は 5 です。 PIN の長さの設定を変更した場合、この設定は新しく生成された PIN にのみ適用され、電話会議が有効になっている既存のユーザーの PIN 設定には適用されません。 「 [電話会議会議の PIN の長さを設定する」を参照してください](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)。
    
- 既定では、メールはユーザーのプライマリ SMTP Microsoft 365またはOffice 365に設定されます。 メールアドレスは、Microsoft 365または MSN メール Office 365など、Hotmailアドレスに送信できます。 既定のメール アドレスは、既定のメール アドレスを無効にWindows PowerShell。 これは、ユーザーがメールボックス内にメールボックスを持Exchange持Microsoft 365場合Office 365。

    

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。 このWindows PowerShell、1 つの管理Microsoft 365または Office 365 を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。
  
## <a name="related-topics"></a>関連トピック

[ユーザーの会議 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)
