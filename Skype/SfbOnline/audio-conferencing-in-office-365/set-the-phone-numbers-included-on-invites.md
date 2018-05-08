---
title: 携帯電話への招待に含まれている番号を設定します。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: 03b6f3b2ce270d1dd6e2855dec4ee2af9a2447c8
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="set-the-phone-numbers-included-on-invites"></a>携帯電話への招待に含まれている番号を設定します。

ビジネスおよびマイクロソフトのチーム会議では、Skype を作成し、電話を使用してその会議にダイヤルインするユーザーを許可し、組織内のユーザーを Office 365 での音声会議に使用できます。 、Office 365 では、マイクロソフトのオーディオ会議ブリッジまたは、承認済みの音声会議プロバイダー (ACP) によってホストされているサード ・ パーティ製のオーディオ会議ブリッジを使用するオプションがあります。
  
> [!NOTE]
> 電話会議のすべてのダイヤルイン番号のリストを含んでいるリソースはありません。 かどうかダイヤルインの電話番号では、領域または国/地域を表示するを検索する場合は、 **Skype**を使用して、 > **音声** > **の電話番号**をクリックし、**追加**新しいサービスの番号を****. **国/地域**、**状態の範囲のリストを使用して**と検索をフィルター処理する**市区町村**> また、有料無料のサービスの番号を検索する場合は、**フリー ダイヤル**から**の状態または地域を選択**リストです。
  
会議ブリッジは、組織用のダイヤルイン電話番号のセットを提供します。これらの番号はすべて会議開催者が作成した会議に参加するために使用できますが、会議出席依頼にどの番号を含めるか選ぶことができます。
  
> [!NOTE]
> 会議主催者の会議出席依頼には、1 つの有料電話番号と 1 つの無料電話番号を含めることができますが、会議出席依頼の下部に、会議に参加するために使用できるダイヤルイン電話番号のすべての一覧を表示するリンクも記載されています。 
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>![デバイス ・ ロゴ ・ 30x30.png](../images/sfb-logo-30x30.png) 会議の開催者の既定のダイヤルインの電話番号を設定します。

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. Choose **Admin centers** > **Skype for Business**.
    
3. [ **ユーザー**] を選びます。
    
    ![ビジネス管理センターの Skype のユーザーの選択を示しています](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. 編集しユーザーを選択します。
    
  - 1 人のユーザーを選択するには、ユーザーの名前を選択します。
    
  - ページ上のすべてのユーザーを選択するには、リストの上部にある**表示名**の横のボックスを選択します。
    
  - 複数のユーザーを選択するには、各ユーザーの名前の横のボックスを選択します。
    
5. 右側のウィンドウで、[ **編集**] を選びます。
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. **オーディオ会議**を選択します。
    
7. [**のプロパティ**] ページで、[**プロバイダー名**] ボックスの一覧でユーザーのプロバイダーを選択します。 プロバイダーに応じて、次のボックスに入力します。
    
  - **マイクロソフトではプロバイダー**:**既定の有料電話番号**を使用し、ユーザーの既定の番号を選択するのには**既定の無料電話番号**を一覧表示します。
    
    > [!NOTE]
    > ユーザーの既定の無料電話番号として設定できるようになるには、少なくとも 1 つの無料電話番号が会議ブリッジに割り当てられている必要があります。 フリー ダイヤル番号を取得するには、 [Skype のビジネスおよびマイクロソフトのチームの取得サービスの電話番号](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)を参照してください。 
  
  - **サード パーティ プロバイダー**:**有料電話番号**や**フリー ダイヤル番号**のフィールドを使用して、ユーザーの数値を入力します。
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-reset-audio-conferencing-phone-numbers"></a>![デバイス ・ ロゴ ・ 30x30.png](../images/sfb-logo-30x30.png) 電話会議の電話番号をリセットする

1. [ **Skype for Business 管理センター**] で、[ **電話会議**] を選びます。
    
2. ページの上部で、[ **ユーザー**] を選びます。
    
3. 、リセットするユーザーを選択し、アクション ペインで、[**クリア**] をクリックします。
    
既定では、ユーザーの会議の設定を変更すると、ユーザーに電子メールが送信されます。 これを変更する場合は、「[電話会議の設定が変更されたときのメールの自動送信を有効または無効にする](enable-or-disable-sending-emails-when-their-settings-change.md)」をご覧ください。
  
> [!IMPORTANT]
> ユーザーの電話会議設定を変更するときは、繰り返し発生する今後の Skype for Business 会議および Microsoft Teams 会議が更新されて、出席者に送信されるようにする必要があります。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法

- 時間を節約したり、自動化したりするには、[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) コマンドレットを使用できます。
    
- 特定ユーザーのデフォルトの有料または無料電話番号を変更するには、[[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688)] コマンドレットを使用します。
    
    ユーザーのデフォルトの無料電話番号を変更するには、次を実行します。
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- ユーザーの元の既定の電話番号または所在地に基づいて既定の有料または無料電話番号を変更するには、 **Set-CsOnlineDialInConferencingUserDefaultNumber** コマンドレットを使用します。
    
    > [!NOTE]
    > BridgeID を探すには、 **Get-CsOnlineDialInConferencingBridge** を使用します。
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - 既定の無料電話番号がないユーザー全員の無料電話番号を既定で +18005551234 に設定するには、次を実行します。
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - 既定の無料電話番号が +18005551234 のユーザー全員の無料電話番号を既定で +18005551239 に変更するには、次を実行します。
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 所在地が米国内のユーザー全員の既定の無料電話番号を +18005551234 に設定するには、次を実行します。
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
## <a name="want-to-learn-more-about-windows-powershell"></a>Windows PowerShell に関する詳細についてはしますか。
- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also

[Office 365 での電話会議を使用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
