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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: 組織内のユーザーが Skype 会議ブロードキャストを使用できるようにするには、それを有効にする必要があります。 これを行うには、Windows PowerShell の使い方を知っている必要があります。 Windows PowerShell がわからない場合は、Microsoft パートナーを採用してこの手順を実行することを検討してください。
ms.openlocfilehash: 6ad681972bb62fa1790290a90d4281fe4ccd8571
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692632"
---
# <a name="enable-skype-meeting-broadcast"></a>Skype 会議ブロードキャストを有効にする

組織内のユーザーが Skype 会議ブロードキャストを使用できるようにするには、それを有効にする必要があります。 これを行うには、Windows PowerShell の使い方を知っている必要があります。 Windows PowerShell がわからない場合は、 [Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089)を採用してこの手順を実行することを検討してください。

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Skype for Business 管理センターを使用して Skype 会議ブロードキャストを有効にする

![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**

1. Office 365 グローバル管理者アカウントまたは Skype for Business 管理者アカウントでサインイン[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)します。
    
2. 管理センターで、[**管理センター** > **チーム**] に移動します。
    
3. **Teams 管理センター**で、[従来の**ポータル** > **オンライン会議** > **ブロードキャスト会議**] に移動し、[ **Skype 会議ブロードキャストを有効に**する] を選択します。
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>PowerShell を使用して Skype 会議ブロードキャストを有効にする

1. Windows PowerShell のバージョン3.0 またはそれ以降を実行していることを確認します。
    
2. 3.0 以降のバージョンが実行されていることを確認する場合: **[スタート] メニュー** > **[Windows PowerShell]**。
    
3. [ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。
    
4. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。 Windows PowerShell をバージョン4.0 にダウンロードして更新するには、「 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 」を参照してください。 メッセージが表示されたら、コンピューターを再起動します。
    
5. Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。
    
6. [**スタート] メニュー**で、[ **Windows PowerShell**] を選びます。
    
7. [ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。
    
   ```PowerShell
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. 次を実行して、現在の Skype 会議ブロードキャストの構成を確認します。
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    パラメーター _EnableBroadcastMeeting_がに`False`設定されていることを確認します。
    
     ![組織の Skype 会議ブロードキャストを有効にするコマンドレット。](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. 次を実行して、組織の Skype 会議ブロードキャストを有効にします。
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    設定が有効になっていることを確認`Get-CsBroadcastMeetingConfiguration`するには、もう一度実行します。
    
     ![組織の Skype 会議ブロードキャストを有効にするコマンドレット。](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > 変更を加えた後は、Skype 会議ブロードキャストのポータルに変更が反映されるまでに最長で1時間かかることがあります。 
  
10. ユーザーは、社内の他のユーザーとブロードキャスト会議を開催できるようになりました。 開始するには、「 [Skype 会議ブロードキャストとは](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)」を参照してください。
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>外部の出席者との会議をブロードキャストするようにネットワークを設定する

ファイアウォールを使用していて、一般法人以外の人とのブロードキャストを保留にする場合は、次の手順を使用してネットワークを設定する必要があります。 [Skype 会議ブロードキャスト用にネットワーク](set-up-your-network-for-skype-meeting-broadcast.md)をセットアップする必要があります。 
  
ファイアウォールの設定が整っていない場合は、この手順を実行するために[Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089)を採用することを検討してください。
  
この手順をスキップして、別の企業をフェデレーションに追加する場合は、「[ユーザーが外部の Skype For business ユーザーに連絡できるように](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)する」を参照してください。 
  
## <a name="related-topics"></a>関連トピック

[Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Skype for Business Online のセットアップ](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
