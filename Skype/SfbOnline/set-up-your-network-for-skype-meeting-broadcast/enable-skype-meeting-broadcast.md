---
title: Skype 会議ブロードキャストを有効にする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: 組織のユーザーが Skype 会議ブロードキャストを使用できるようにする前に、それを有効にしておく必要があります。この手順を実行するには、Windows PowerShell の使い方を知っておく必要があります。Windows PowerShell に慣れていない場合は、マイクロソフトのパートナーに依頼してこの手順を実行することを考慮してください。
ms.openlocfilehash: 699b82af07b263331ee5508326bf3e7ed015848e
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370865"
---
# <a name="enable-skype-meeting-broadcast"></a>Skype 会議ブロードキャストを有効にする

[] 組織のユーザーが Skype 会議ブロードキャストを使用できるようにする前に、それを有効にしておく必要があります。この手順を実行するには、Windows PowerShell の使い方を知っておく必要があります。Windows PowerShell に慣れていない場合は、[マイクロソフトのパートナー](https://go.microsoft.com/fwlink/?linkid=391089)に依頼してこの手順を実行することを考慮してください。

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Skype for Business 管理センターを使用して Skype 会議ブロードキャストを有効にする

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**

1. Office 365 のグローバル管理者アカウントを使用してサインイン[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)。
    
2. Office 365 の管理センターで**管理センター**に移動する > **ビジネス用の Skype**です。
    
3. **ビジネス管理センターの Skype**では、**オンライン会議**に移動 > **会議のブロードキャスト**、および、 **Skype 会議のブロードキャストを有効にする**] を選択をします。
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>PowerShell を使用して Skype 会議ブロードキャストを有効にする

1. Windows PowerShell のバージョン 3.0 以上を実行していることを確認します。
    
2. 3.0 以降のバージョンが実行されていることを確認する場合: **[スタート] メニュー** > **[Windows PowerShell]**。
    
3. [ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。
    
4. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。
    
5. Skype for Business Online 用の Windows PowerShell モジュールもインストールする必要があります。このモジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、Microsoft ダウンロード センターの「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。再起動を求めるメッセージが表示されたら、コンピューターを再起動します。
    
6. [ **スタート**] メニューで [ **Windows PowerShell**] をクリックします。
    
7. [ **Windows PowerShell**] ウィンドウで、以下のコマンドを実行して、Office 365 の組織に接続します。
    
   ```
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. 以下のコマンドを実行して、現在の Skype 会議ブロードキャストの構成を確認します。
    
   ```
   Get-CsBroadcastMeetingConfiguration
   ```

    _EnableBroadcastMeeting_ パラメーターが `False` に設定されていることを確認します。
    
     ![組織に対して Skype Meeting Broadcast を有効にするコマンドレット。](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. 以下のコマンドを実行して、組織の Skype 会議ブロードキャストを有効にします。
    
   ```
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    `Get-CsBroadcastMeetingConfiguration` をもう一度実行すると、設定が有効になっていることを確認できます。
    
     ![組織に対して Skype Meeting Broadcast を有効にするコマンドレット。](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > 変更後は、Skype 会議ブロードキャストのポータルに変更が反映されるまでに最長で 1 時間かかる場合があります。 
  
10. これで、ユーザーは組織の他のユーザーとブロードキャスト会議を開催できます。会議を開催するには、ユーザーに「[Skype 会議ブロードキャストとは](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)」を参照するように指示してください。
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>ネットワークを構成して、外部の出席者に会議をブロードキャストする

ファイアウォールが構成されている場合に組織外 (フェデレーションされていない組織) の参加者とブロードキャストを開催する場合は、「[Skype 会議ブロードキャスト用にネットワークをセットアップする](set-up-your-network-for-skype-meeting-broadcast.md)」の手順に従ってネットワークを構成する必要があります。 
  
ファイアウォールの構成に慣れていない場合は、[マイクロソフトのパートナー](https://go.microsoft.com/fwlink/?linkid=391089)に依頼してこの手順を実行することを考慮してください。
  
この手順をスキップして、代わりに別の組織をフェデレーションに追加する場合は、「[ユーザーが外部の Skype for Business ユーザーに連絡できるようにする](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)」をご覧ください。 
  
## <a name="related-topics"></a>See also

[Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Skype for Business Online のセットアップ](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 