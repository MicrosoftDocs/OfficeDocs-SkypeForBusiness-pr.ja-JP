---
title: Skype for Business Onlineの招待状に含まれる電話番号を設定する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: 956c2fa23f61f0c0e24cd1c2a0802bd3f1397bb1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113223"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a>Skype for Business Onlineの招待状に含まれる電話番号を設定する

> [!Note]
> Microsoft Teamsの会議招待状の電話番号についての詳細は、「 [Microsoft Teamsの招待状に含める電話番号を設定](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams)」を参照してください。.

Microsoft 365 または Office 365 の電話会議を使用すると、組織内のユーザーは Skype for Business 会議を作成し、ユーザーが電話を使ってそれらの会議にダイヤルインできます。 Microsoft 365 および Office 365 では、承認済みの電話会議プロバイダー (ACP) によってホストされる Microsoft 電話会議ブリッジまたはサードパーティの電話会議ブリッジを使用することができます。
  
> [!NOTE]
> 電話会議のすべてのダイヤルイン番号のリストを含んでいるリソースはありません。 お客様の地域または国/地域で利用できるダイヤルイン電話番号が見当たっている場合は **、Skype for Business** 管理センターの [音声電話番号] を使用して、[追加] をクリックし、[新しいサービス番号] をクリックします。  >    >     [ **国/地域**]、[**州/地域**] および [**市区町村**]のリストを使って検索を絞り込みます。> また、無料電話番号サービスを探している場合には、[**無料電話番号**] を [**州/地域**] リストから選択します。
  
会議ブリッジは、組織用のダイヤルイン電話番号のセットを提供します。これらの番号はすべて会議開催者が作成した会議に参加するために使用できますが、会議出席依頼にどの番号を含めるか選ぶことができます。
  
> [!NOTE]
> 会議主催者の会議出席依頼には、1 つの有料電話番号と 1 つの無料電話番号を含めることができますが、会議出席依頼の下部に、会議に参加するために使用できるダイヤルイン電話番号のすべての一覧を表示するリンクも記載されています。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>会議開催者の既定のダイヤルイン電話番号を設定する

1. 仕事用または学校用のアカウントでサインインします。
    
2. [**管理センター**]  >  [**Skype for Business**]を選択します。
    
3. [ **ユーザー**] を選びます。
    
    ![Skype for Business 管理センターで、ユーザーの選択を表示](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. 編集するユーザーを選択します。
    
   - 1 人のユーザーを選択するには、ユーザーの名前を選択します。
    
   - ページ上のすべてのユーザーを選択するには、リストの上部にある [表示名] **の横にある** ボックスを選択します。
    
   - 複数のユーザーを選択するには、各ユーザーの名前の横のボックスを選択します。
    
5. 右側のウィンドウで、[ **編集**] を選びます。
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6.  **電話会議** を選択します。
    
7. [プロパティ **] ページ** の [プロバイダー名 **]** ボックスの一覧で、ユーザーのプロバイダーを選択します。 プロバイダーに応じて、次のボックスに入力します。
    
   - **Microsoft はプロバイダーです。** 既定の **有料電話番号** と既定の無料電話番号リストを使用して、ユーザーの既定の番号を選択します。
    
     > [!NOTE]
     > ユーザーの既定の無料電話番号として設定できるようになるには、少なくとも 1 つの無料電話番号が会議ブリッジに割り当てられている必要があります。 無料電話番号を取得するには、「Skype for Business のサービス電話番号を取得する [」を参照してください](/microsoftteams/getting-service-phone-numbers)。 
  
   - **サードパーティはプロバイダーです。** ユーザーの番号を入力するには、有料電話番号と無料電話番号のフィールドを使用します。


## <a name="reset-audio-conferencing-phone-numbers"></a>電話会議の電話番号をリセットする

1. [ **Skype for Business 管理センター**] で、[ **電話会議**] を選びます。
    
2. ページの上部で、[ **ユーザー**] を選びます。
    
3. リセットするユーザーを選択し、操作ウィンドウで [**クリア**] をクリックします。
    
既定では、ユーザーの会議の設定を変更すると、ユーザーに電子メールが送信されます。 これを変更する場合は、「[電話会議の設定が変更されたときのメールの自動送信を有効または無効にする](enable-or-disable-sending-emails-when-their-settings-change.md)」をご覧ください。
  
> [!IMPORTANT]
> ユーザーの電話会議の設定を変更する場合は、定期的な会議と今後の Skype for Business 会議を更新して出席者に送信する必要があります。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- 時間を節約したり、自動化したりするには、[Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) コマンドレットを使用できます。
    
- 特定ユーザーのデフォルトの有料または無料電話番号を変更するには、[[Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser)] コマンドレットを使用します。
    
    ユーザーのデフォルトの無料電話番号を変更するには、次を実行します。
    
  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- ユーザーの元の既定の電話番号または所在地に基づいて既定の有料または無料電話番号を変更するには、 **Set-CsOnlineDialInConferencingUserDefaultNumber** コマンドレットを使用します。
    
    > [!NOTE]
    > BridgeID を見つけるには **、Get-CsOnlineDialInConferencingBridge コマンドレットを使用** します。
  
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - 既定の無料電話番号がないユーザー全員の無料電話番号を既定で +18005551234 に設定するには、次を実行します。
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - 既定の無料電話番号が +18005551234 のユーザー全員の無料電話番号を既定で +18005551239 に変更するには、次を実行します。
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 所在地が米国内のユーザー全員の既定の無料電話番号を +18005551234 に設定するには、次を実行します。
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a>詳細については、次のWindows PowerShell。
- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Microsoft 365 または Office 365 PowerShell を使用する必要がある理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShellは、多くのユーザーに対して同時に設定変更を行う場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性の点で多くの利点があります。 次のトピックでこれらの利点について説明します。
    
  - [Microsoft 365 または Office 365 を他のユーザーとWindows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>関連項目

[Microsoft 365 または Office 365 で電話会議を試用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)