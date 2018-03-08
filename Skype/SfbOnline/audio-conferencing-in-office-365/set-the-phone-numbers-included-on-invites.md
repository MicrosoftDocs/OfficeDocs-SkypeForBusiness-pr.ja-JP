---
title: "携帯電話への招待に含まれる数値を設定します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Skype for Business Online の会議に参加する発信者の既定の電話番号を作成する手順を取得します。 "
ms.openlocfilehash: 8baf3d79b360a5d95da4b9ead6bae12cd488712c
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="set-the-phone-numbers-included-on-invites"></a>携帯電話への招待に含まれる数値を設定します。

Office 365 で音声会議 Business および Microsoft チームの会議に Skype を作成し、電話を使用して、その会議にダイヤルインするように、組織のユーザーを有効にします。Office 365 で、Microsoft の電話会議ブリッジまたは承認されている電話会議プロバイダー (ACP) でホストされているサードパーティ電話会議ブリッジを使用するオプションがあります。
  
> [!NOTE]
> 電話会議のすべてのダイヤルイン番号の一覧を含むリソースはありません。ないか確認ダイヤルイン電話番号利用可能な領域または国/地域を検索する場合は、 **Skype for Business 管理センター**を使って > **音声** > **電話番号**をクリックし、**追加****新しいサービス番号**.**国/地域**、**状態/地域のリストを使用して**と検索をフィルター処理するのには、**市区町村**> も、有料の無料サービス番号、探している場合は**フリー ダイヤル**から、**状態/地域を選びます**] ボックスの一覧です。
  
会議ブリッジによって、組織のダイヤルイン電話番号のセットができます。会議の開催者が作成した会議に参加するすべての使われていることができますが、会議の出席依頼に含めるものを選択することができます。
  
> [!NOTE]
> 最大の 1 つの有料電話番号との会議の開催者、会議の出席依頼のフリー ダイヤル電話番号を 1 つがありますも会議に参加するのに使用できるすべてのダイヤルイン電話番号の完全な一覧を開いている各会議出席依頼の下部にあるリンクがあります。 
  
## <a name="setting-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>会議の開催者の既定のダイヤルイン電話番号を設定します。

1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **管理センター**] を選びます > **Skype for Business**します。
    
3. **ユーザー**を選択します。
    
    ![Skype for Business 管理センターでユーザーを選択して表示します。](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. 編集するユーザーを選択します。
    
  - 1 人のユーザーを選択するには、ユーザーの名前を選択します。
    
  - ページ上のすべてのユーザーを選択するには、リストの上部にある**表示名**の横のボックスを選択します。
    
  - 複数のユーザーを選択するには、各ユーザーの名前の横のボックスを選択します。
    
5. 右のパネルで [**編集**] を選びます。
    
    ![[編集] アイコンを選択します。](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. **電話会議**を選択します。
    
7. **プロパティ**ページで、[**プロバイダー名**] ボックスの一覧で、ユーザーのプロバイダーを選択します。プロバイダーによっては、次のボックスを実行します。
    
  - **Microsoft はプロバイダー**:**有料電話番号が既定値**を使用し、ユーザーの既定の番号を選択する**既定のフリー ダイヤル番号**が一覧表示します。
    
    > [!NOTE]
    > 1 つ以上のフリー ダイヤル番号は、前に、ユーザーの既定のフリー ダイヤル番号に設定することができます、会議ブリッジを割り当てる必要があります。フリー ダイヤルの番号を移動するには、 [Skype for Business とチームの Microsoft の取得サービスの電話番号](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)を参照してください。 
  
  - **サード パーティがプロバイダー**:**有料電話番号**と**フリー ダイヤル番号**フィールドを使用して、ユーザーの数値を入力します。
    
## <a name="reset-audio-conferencing-phone-numbers"></a>電話会議の電話番号を再設定します。

1. **Skype for Business 管理センター**では、**電話会議**を選択します。
    
2. ページの上部で、[**ユーザー**] を選びます。
    
3. 、リセットするユーザーを選択し、[アクション] ウィンドウで、[**クリア**] をクリックします。
    
既定では、ユーザーの会議の設定を変更する場合は、メールは、ユーザーに送信します。これを変更するには、[有効にするか音声会議の設定を変更するときに、送信メールを無効にする](enable-or-disable-sending-emails-when-their-settings-change.md)を参照してください。
  
> [!IMPORTANT]
> ユーザーの電話会議の設定を変更すると、定期的な予定と将来の Skype for Business や Microsoft チームの会議が更新され、出席者に送信する必要があります。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法を知りたいとしていますか。

- 時間を節約し、自動化したりには、[セット CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688)コマンドレットを使用することができます。
    
- 既定の有料またはフリー ダイヤルの番号を特定のユーザーを変更するのにには、[セット CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688)コマンドレットを使用します。
    
    ユーザーの既定のフリー ダイヤル番号を変更するには、次のコマンドを実行します。
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- 既定の有料またはフリー ダイヤルの元の既定の番号またはその場所に基づくユーザー数を変更するのには、**セット CsOnlineDialInConferencingUserDefaultNumber**コマンドレットを使用します。
    
    > [!NOTE]
    > [BridgeID を検索するには、 **Get CsOnlineDialInConferencingBridge**を使用します。
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - 既定のフリー ダイヤル番号を設定するには、1 +18005551234 せずにすべてのユーザーに実行します。
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - +18005551239 に、既定のフリー ダイヤル番号として +18005551234 を持つすべてのユーザーの既定のフリー ダイヤル番号を変更するには、次のコマンドを実行します。
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - +18005551234 米国内にあるすべてのユーザーの既定のフリー ダイヤル番号を設定するには、次のコマンドを実行します。
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
## <a name="want-to-learn-more-about-windows-powershell"></a>Windows PowerShell の詳細を確認したい場合
- Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。
    
  - [Windows PowerShell で Office 365 を管理する最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell を使用して、Skype for Business Online の管理するには](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>関連トピック

[Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。](set-up-audio-conferencing.md)
  

