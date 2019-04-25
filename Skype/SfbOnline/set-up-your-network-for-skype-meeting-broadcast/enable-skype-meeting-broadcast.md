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
description: 組織内のユーザーは、Skype の会議のブロードキャストを使用できます、前に有効にする必要があります。 これを行うには、Windows PowerShell を使用する方法を理解する必要があります。 Windows PowerShell がわからない場合は、自動的にこの手順を実行するマイクロソフトのパートナーの採用を検討してください。
ms.openlocfilehash: 699b82af07b263331ee5508326bf3e7ed015848e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226821"
---
# <a name="enable-skype-meeting-broadcast"></a>Skype 会議ブロードキャストを有効にする

組織内のユーザーは、Skype の会議のブロードキャストを使用できます、前に有効にする必要があります。 これを行うには、Windows PowerShell を使用する方法を理解する必要があります。 Windows PowerShell がわからない場合は、自動的にこの手順を実行するのには[マイクロソフトのパートナー](https://go.microsoft.com/fwlink/?linkid=391089)の採用を検討してください。

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>ビジネス管理センターに、Skype を使用して、Skype 会議のブロードキャストを有効にします。

![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**

1. [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) で、Office 365 全体の管理者アカウントを使用してサインインします。
    
2. Office 365 の管理センターで**管理センター**に移動する > **ビジネス用の Skype**です。
    
3. **ビジネス管理センターの Skype**では、**オンライン会議**に移動 > **会議のブロードキャスト**、および、 **Skype 会議のブロードキャストを有効にする**] を選択をします。
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>PowerShell を使用して、Skype 会議のブロードキャストを有効にします。

1. 3.0 以降の Windows PowerShell のバージョンを実行していることを確認します。
    
2. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
3. [ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。
    
4. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。
    
5. Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。
    
6. [**スタート] メニュー**から**Windows PowerShell**を選択します。
    
7. [ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。
    
   ```
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. 実行して、現在の Skype 会議のブロードキャストの構成を確認します。
    
   ```
   Get-CsBroadcastMeetingConfiguration
   ```

    パラメーター _EnableBroadcastMeeting_に設定されていることを確認`False`。
    
     ![Skype 会議をブロードキャストを有効にする組織のコマンドレットです。](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. Skype 会議のブロードキャストの組織を実行して有効。 にします。
    
   ```
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    実行して、設定が有効になっていることを確認することができます`Get-CsBroadcastMeetingConfiguration`もう一度。
    
     ![Skype の会議のブロードキャストは、組織のコマンドレットを有効にします。](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > 変更を加えた後、かかる場合があります 1 時間 Skype 会議のブロードキャストのポータルで有効にします。 
  
10. ユーザーは、ビジネスで他のユーザーと会議をブロードキャストを今すぐ保持できます。 ポイントするために開始、 [Skype の会議のブロードキャストとは何ですか?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>外部の出席者を含む会議をブロードキャストするのには、ネットワークを構成します。

ブロードキャスト (メンバーは、ビジネスの連合)、組織外からの人を保持する場合、ファイアウォールがある場合、次の手順を使用してネットワークを構成する必要があります: [Skype 会議のブロードキャストのネットワークをセットアップ](set-up-your-network-for-skype-meeting-broadcast.md)します。 
  
した経験がお使いのファイアウォールを構成する場合は、自動的にこの手順を実行するのには[マイクロソフトのパートナー](https://go.microsoft.com/fwlink/?linkid=391089)の採用を検討してください。
  
この手順を省略し、代わりに別のビジネスをフェデレーションに追加するのには、[ビジネス ユーザー向けの外部の Skype に連絡を許可する](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)を参照してください。 
  
## <a name="related-topics"></a>関連トピック

[Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Skype for Business Online のセットアップ](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 