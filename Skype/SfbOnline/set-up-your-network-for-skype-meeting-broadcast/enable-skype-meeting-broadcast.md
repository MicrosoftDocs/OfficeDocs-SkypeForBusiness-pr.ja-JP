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
description: 組織内のユーザーが会議ブロードキャストをSkypeするには、会議ブロードキャストを有効にする必要があります。 これを行うには、アプリケーションの使い方をWindows PowerShell。 この手順がわかWindows PowerShell、Microsoft パートナーを採用してこの手順を実行することを検討してください。
ms.openlocfilehash: 6cdd7f12483025697b139203907f87f9cd3dc764
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237013"
---
# <a name="enable-skype-meeting-broadcast"></a>Skype 会議ブロードキャストを有効にする

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> Skype for Businessオンラインは 2021 年 7 月 31 日に廃止され、その時点でサービスへのアクセスが終了します。 お客様には、コミュニケーションとチームワークの中核となるMicrosoft Teamsクライアントであるクライアントへのアップグレードを開始Microsoft 365。

組織内のユーザーが会議ブロードキャストをSkypeするには、会議ブロードキャストを有効にする必要があります。 これを行うには、アプリケーションの使い方をWindows PowerShell。 この手順を実行する方法[Windows PowerShell、Microsoft](https://go.microsoft.com/fwlink/?linkid=391089)パートナーを採用することを検討してください。



> [!NOTE]
> 管理Microsoft Teamsセンターは、管理センター (レガシ ポータルSkype for Business置き換えました。 現在、管理センター Skype for Business管理センターにTeams設定が表示されます。 グローバル管理者の[Azure AD 管理者](/azure/active-directory/roles/permissions-reference)ロールが割り当てられている必要があります。または、Skype for Business 管理センターでSkype for Business機能を管理するには、Teams必要があります。 詳細については、「[Microsoft Teams 管理センターで Skype for Business の設定を管理する](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)」を参照してください。

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>管理Skypeを使用して会議ブロードキャストSkype for Business有効にする

![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**

1. グローバル管理者アカウントでサインインするか、 で管理者Skype for Businessアカウントにサインインします [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 。
    
2. 管理センターで、[管理センター] に **移動Teams。**  >  
    
3. [Teams **管理センターで**、[従来のポータル] [オンライン会議] [ブロードキャスト会議] に移動し、[会議ブロードキャストを有効にする] Skype  >    >  **選択します**。
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>PowerShell Skypeして会議ブロードキャストを有効にする

1. [PowerShell モジュール Teamsインストールします](/microsoftteams/teams-powershell-install)。
    
2. コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. 次のコマンドを実行Skype会議ブロードキャストの構成を確認します。
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    _パラメーター EnableBroadcastMeeting が に設定_ されています `False` 。
    
     ![Skype会議ブロードキャストを有効にする組織コマンドレット。](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. 次Skypeして、組織の会議ブロードキャストを有効にします。
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    設定が有効になっているか確認するには、もう一度を実行  `Get-CsBroadcastMeetingConfiguration` します。
    
     ![Skype会議ブロードキャストを有効にする組織コマンドレット。](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > 変更を行った後、会議ブロードキャスト ポータルで有効Skype 1 時間かかる場合があります。 
  
10. これで、ユーザーは、ビジネス内の他のユーザーとブロードキャスト会議を開催できます。 会議ブロードキャストを開始するには、[会議ブロードキャストとは[] Skypeします。](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>外部出席者との会議をブロードキャストするネットワークを構成する

ファイアウォールを使用している場合に、社外のユーザー (フェデレーションビジネスではないユーザー) とブロードキャストを開催する場合は[、「Skype](set-up-your-network-for-skype-meeting-broadcast.md)会議ブロードキャスト 用にネットワークを設定する」の手順に従ってネットワークを構成する必要があります。 
  
ファイアウォールを構成する経験が十分でない場合は [、Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) パートナーを採用してこの手順を実行することを検討してください。
  
この手順をスキップし、代わりに別のビジネスをフェデレーションに追加するには、「ユーザーが外部ユーザーに連絡することを許可する」を[Skype for Businessしてください](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)。 
  
## <a name="related-topics"></a>関連トピック

[Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
[Skype for Business Online のセットアップ](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
