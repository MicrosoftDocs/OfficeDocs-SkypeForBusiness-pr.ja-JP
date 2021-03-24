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
description: 組織内のユーザーが Skype 会議ブロードキャストを使用するには、それを有効にする必要があります。 この操作を行うには、この機能の使い方をWindows PowerShell。 この手順を実行Windows PowerShell、Microsoft パートナーを採用することを検討してください。
ms.openlocfilehash: ab59348d32ef130df6b0de6e1eb65c92d0222e04
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097113"
---
# <a name="enable-skype-meeting-broadcast"></a>Skype 会議ブロードキャストを有効にする

> [!IMPORTANT]
> Skype for Business Online は 2021 年 7 月 31 日に廃止され、サービスへのアクセスが終了します。 Microsoft 365 のコミュニケーションとチームワークのコア クライアントである Microsoft Teams へのアップグレードを開始する方法をお勧めしています。

組織内のユーザーが Skype 会議ブロードキャストを使用するには、それを有効にする必要があります。 この操作を行うには、この機能の使い方をWindows PowerShell。 この手順を実行 [Windows PowerShell、Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) パートナーを採用することを検討してください。



> [!NOTE]
> Microsoft Teams 管理センターは、Skype for Business 管理センター (従来のポータル) に置き換えました。 Skype for Business を管理するためのすべての設定が Teams 管理センターに表示されます。 Teams 管理センターで Skype for Business [AD](/azure/active-directory/roles/permissions-reference) を管理するには、グローバル管理者または Skype for Business 管理者の Azure 管理者の役割が割り当てられている必要があります。 詳細については、「[Microsoft Teams 管理センターで Skype for Business の設定を管理する](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)」を参照してください。

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Skype for Business 管理センターを使用して Skype 会議ブロードキャストを有効にする

![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**

1. グローバル管理者アカウントまたは Skype for Business 管理者アカウントでサインインします [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 。
    
2. 管理センターで、管理センターの Teams **に移動**  >  **します**。
    
3. Teams 管理 **センターで**、従来のポータルのオンライン会議ブロードキャスト会議に移動し、[Skype 会議ブロードキャストを有効にする  >    >  **] を選択します**。
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>PowerShell を使用して Skype 会議ブロードキャストを有効にする

1. Teams [PowerShell モジュールをインストールします](/microsoftteams/teams-powershell-install)。
    
2. コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. 次のコマンドを実行して、現在の Skype 会議ブロードキャストの構成を確認します。
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    _パラメーター EnableBroadcastMeeting_ が設定されています `False` 。
    
     ![Skype 会議ブロードキャストの組織コマンドレットを有効にします。](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. 次のコマンドを実行して、組織の Skype 会議ブロードキャストを有効にします。
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    設定が有効になっているか確認するには、もう一度実行  `Get-CsBroadcastMeetingConfiguration` します。
    
     ![Skype 会議ブロードキャストは組織コマンドレットを有効にします。](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > 変更後、Skype 会議ブロードキャスト ポータルで有効になれるのに最大で 1 時間かかる場合があります。 
  
10. これで、ユーザーは、ビジネスの他のユーザーとブロードキャスト会議を開催できます。 会議を開始するには、Skype 会議ブロードキャストとは [何かを示します。](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>外部出席者との会議をブロードキャストするネットワークを構成する

ファイアウォールを使用している場合に、社外のユーザー (フェデレーション企業ではない) とのブロードキャストを保留にする場合は、次の手順を使用してネットワークを構成する必要があります [。Skype](set-up-your-network-for-skype-meeting-broadcast.md)会議ブロードキャスト用にネットワークをセットアップします。 
  
ファイアウォールの構成を経験していない場合は、この手順を [実行するために Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) パートナーを採用することを検討してください。
  
この手順をスキップし、代わりに別のビジネスをフェデレーションに追加するには、「ユーザーが外部の Skype for Business ユーザーに連絡することを許可する [」を参照してください](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)。 
  
## <a name="related-topics"></a>関連項目

[Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
[Skype for Business Online のセットアップ](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
