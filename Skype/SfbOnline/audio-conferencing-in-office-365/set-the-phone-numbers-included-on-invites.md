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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Skype for Business Online会議に参加するため、呼び出し元の規定電話番号を作成する手順を取得します。 '
ms.openlocfilehash: d4ab76fc99483812d2be6b2f7009be361f33c3c9
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23851487"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a>Skype for Business Onlineの招待状に含まれる電話番号を設定する

> [!Note]
> Microsoft Teamsの会議招待状の電話番号についての詳細は、「 [Microsoft Teamsの招待状に含める電話番号を設定](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams)」を参照してください。.

Office 365の電話会議では、組織内のユーザー はSkype for Business会議を作成することができ、その後、電話を利用してそれらの会議にダイアルインできます。 Office 365では、Microsoft電話会議ブリッジ、または承認済みの電話会議プロバイダー(ACP) によってホストされているサードパーティの電話会議ブリッジを使用するオプションがあります。
  
> [!NOTE]
> 電話会議のすべてのダイヤルイン番号のリストを含んでいるリソースはありません。 ご利用のエリアまたは国や地域で利用可能なダイヤルイン電話番号があるかどうかを知るには、[**Skype for Business 管理センター**] > [**音声**] > [**電話番号**] と移動して、[**追加**] をクリックしてから [**新しいサービス番号**] をクリックします。 [ **国/地域**]、[**州/地域**] および [**市区町村**]のリストを使って検索を絞り込みます。> また、無料電話番号サービスを探している場合には、[**無料電話番号**] を [**州/地域**] リストから選択します。
  
会議ブリッジは、組織用のダイヤルイン電話番号のセットを提供します。これらの番号はすべて会議開催者が作成した会議に参加するために使用できますが、会議出席依頼にどの番号を含めるか選ぶことができます。
  
> [!NOTE]
> 会議主催者の会議出席依頼には、1 つの有料電話番号と 1 つの無料電話番号を含めることができますが、会議出席依頼の下部に、会議に参加するために使用できるダイヤルイン電話番号のすべての一覧を表示するリンクも記載されています。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>会議の開催者に、既定のダイヤルイン電話番号の設定

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. [**管理センター**]  >  [**Skype for Business**]を選択します。
    
3. [ **ユーザー**] を選択します。
    
    ![Skype for Business 管理センターで、ユーザーの選択を表示](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. 編集しユーザーを選択します。
    
  - 1 人のユーザーを選択するには、ユーザーの名前を選択します。
    
  - ページに表示されているすべてのユーザーを選ぶには、一覧の一番上の [ **表示名**] の横にあるチェック ボックスをオンにします。
    
  - 複数のユーザーを選択するには、各ユーザーの名前の横のボックスを選択します。
    
5. 右側のウィンドウで、[ **編集**] を選びます。
    
    ![[編集] アイコンを選択します。](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6.  **電話会議**を選択します。
    
7. [ **のプロパティ** ] ページの、[ **プロバイダー名** ] ボックスの一覧でユーザーのプロバイダーを選択します。 プロバイダーに応じて、次のボックスに入力します。
    
  - **Microsoft がプロバイダーの場合**: [ **既定の有料電話番号**] と [ **既定の無料電話番号**] の一覧を使用してユーザーの既定の番号を選びます。
    
    > [!NOTE]
    > ユーザーの既定の無料電話番号として設定できるようになるには、少なくとも 1 つの無料電話番号が会議ブリッジに割り当てられている必要があります。 無料電話番号を取得するには、 「[Skype for Business サービスの電話番号を取得する](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)」を参照してください。 
  
  - **サード パーティがプロバイダーの場合**: [ **有料電話番号**] と [ **無料電話番号**] フィールドを使用してユーザーの番号を入力します。


## <a name="reset-audio-conferencing-phone-numbers"></a>電話会議の電話番号をリセットする

1. [ **Skype for Business 管理センター**] で、[ **電話会議**] を選びます。
    
2. ページの上部で、[ **ユーザー**] を選びます。
    
3. リセットするユーザーを選択し、操作ウィンドウで [**クリア**] をクリックします。
    
既定では、ユーザーの会議の設定を変更すると、ユーザーに電子メールが送信されます。 これを変更する場合は、「[電話会議の設定が変更されたときのメールの自動送信を有効または無効にする](enable-or-disable-sending-emails-when-their-settings-change.md)」をご覧ください。
  
> [!IMPORTANT]
> ユーザーの電話会議設定を変更するときは、繰り返し発生する今後の Skype for Business 会議が更新されて、出席者に送信されるようにする必要があります。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法

- 時間を節約したり、自動化したりするには、[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) コマンドレットを使用できます。
    
- 特定ユーザーのデフォルトの有料または無料電話番号を変更するには、[[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688)] コマンドレットを使用します。
    
    ユーザーのデフォルトの無料電話番号を変更するには、次を実行します。
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- ユーザーの元の既定の電話番号または所在地に基づいて既定の有料または無料電話番号を変更するには、 **Set-CsOnlineDialInConferencingUserDefaultNumber** コマンドレットを使用します。
    
    > [!NOTE]
    > BridgeID を探すには、 **Get-CsOnlineDialInConferencingBridge** コマンドレットを使用します。
  
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
## <a name="want-to-learn-more-about-windows-powershell"></a>Windows PowerShell の詳細情報
- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also

[Office 365 での電話会議を使用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
