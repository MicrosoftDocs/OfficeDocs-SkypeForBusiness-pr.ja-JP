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
description: Microsoft Teams でユーザーの電話会議 PIN をリセットする方法と PIN に関する重要な事実について説明します。
ms.openlocfilehash: 7ea380fbeb722337eaec598823b12dbe18f49918
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117635"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Microsoft Teams で電話会議の PIN をリセットする

PIN は、電話会議に対応している Microsoft Teams ユーザーごとに作成される番号で構成されるコードです。 電話会議 PIN は、会議の開催者が自分が会議の開催者であり、電話で会議を開始するために使用されます。 Microsoft Teams アプリを使用して会議を開始する場合、PIN は必要ありません。 ユーザーが自分の PIN を忘れて、電話会議で有効になっていたときに送信されたメールで PIN を見つからなかった場合、管理者は自分の PIN をリセットするか、自分の PIN をリセットできます。
  
会議は、認証されたユーザーが Microsoft Teams アプリを使用して参加するか、開催者が電話で自分の PIN で参加するときに開始できます。 会議の開始に PIN が必要な場合、電話で参加するユーザーはロビーで待機し、会議が開始するまで保留音を聞くことになります。 会議の開催者が、電話で会議を開始するための PIN を要求しない場合、発信者は会議に参加しようとするときに PIN の提示を求められません。

## <a name="reset-a-users-pin"></a>ユーザーの PIN をリセットする

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. [編集 **] をクリックします**。

3. [電話 **会議] の [PIN の** リセット] **をクリックします**。

4. [リセット] **をクリックします**。
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-their-own-pin"></a>ユーザーに自分の PIN をリセットする

1. ユーザーにアクセスを許可します [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) 。
2. [PIN **のリセット] をクリックします**。 

> [!NOTE]
> GCCH の場合は、次の場所に移動します https://webdir2g.online.gov.skypeforbusiness.us/lscp/usp/pstnconferencing 。

## <a name="what-else-should-you-know-about-pins"></a>PIN について知っておくべきその他のこと

- セキュリティ上の目的で、PIN がリセットされた場合、PIN は管理者に 1 回だけ表示されます。 管理者が PIN をリセットすると、PIN は *********** として表示されます。
    
- ユーザーへのメールの自動送信は既定で有効になっています。ユーザーが電話会議で有効になっている場合、または PIN がリセットされた場合、ユーザーは自分の PIN が記載されたメールを受信します。 ただし、メールの自動送信を無効にした場合、PIN リセット メールはユーザーに送信されません。PIN 情報を手動でユーザーに送信する必要があります。
    
- 会議が始まると、ロビー内のすべてのユーザーが自動的に会議に参加します。 たとえば、開始前に 2 人の参加者が会議に参加しようとする場合、参加者はロビーに置かれ、保留音を聞き、会議の開催者が自分の PIN を使って電話で参加すると、会議が開始され、ロビーの参加者が会議に参加します。
    
- 既定の設定では、匿名の発信者による会議の開始を許可しません。
    
- ユーザーを電話会議用に有効にした場合、既定では、ユーザーは会議情報と PIN を含むメールを送信します。 PIN がリセットされた場合、ユーザーに設定されているプライマリ SMTP アドレス (エイリアス) に新しい PIN がメールで送信されるので、ユーザーは Microsoft 365 または Office 365 メールボックスを持っている必要があります。
    
- 電話会議をセットアップするときに、組織内の PIN に必要な数字を設定します。 PIN は 4 ~ 12 桁で指定できます。既定値は 5 です。 PIN の長さの設定を変更した場合、この設定は新しく生成された PIN にのみ適用され、電話会議で有効になっている既存のユーザーの PIN 設定には適用されません。 「 [電話会議の PIN の長さを設定する」を参照してください](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)。
    
- 既定では、メールはユーザーの Microsoft 365 Office 365 プライマリ SMTP アドレスに設定されます。 Microsoft 365 以外のアドレスまたは Office 365 以外のアドレス (Hotmail または MSN のメール アドレスなど) にメールを送信できます。 既定のメール アドレスを上書きするには、既定のメール Windows PowerShell。 これは、ユーザーが Microsoft 365 または 365 で Exchange メールボックスを持Office便利です。

    

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。 Windows PowerShell では、単一の管理ポイントを使用して Microsoft 365 または Office 365 を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Microsoft 365 または Office 365 を他のユーザーとWindows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。
  
## <a name="related-topics"></a>関連トピック

[ユーザーの会議 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)