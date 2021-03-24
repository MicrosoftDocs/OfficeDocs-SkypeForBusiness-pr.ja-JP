---
title: カスタム外部アクセス ポリシーを作成する
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
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
- Setup
description: Skype for Business Online を使用すると、その他の外部アクセス ポリシーを作成できます。 複数な組み合わせを作成できるクライアントポリシーや会議ポリシーとは異なり、シナリオのほとんどをカバーできる 3 つの定義済み外部アクセス ポリシーがあります。
ms.openlocfilehash: 3e5e8cf1c464b1011a49b06b2d1958246d332c91
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100613"
---
# <a name="create-custom-external-access-policies"></a>カスタム外部アクセス ポリシーを作成する

Skype for Business Online を使用すると、その他の外部アクセス ポリシーを作成できます。 複数な組み合わせを作成できるクライアントポリシーや会議ポリシーとは異なり、シナリオのほとんどをカバーできる 3 つの定義済み外部アクセス ポリシーがあります。 これらは：
  
- フェデレーション アクセスまたは Skype 消費者アクセスなし (_タグ: NoFederationAndPIC_ )
    
- フェデレーション アクセスのみ (_タグ: FederationOnly_ )
    
- フェデレーション アクセスと消費者アクセス (_FederationAndPICDefault_)
    
カスタム外部ポリシーを使用すると、上記の設定でカバーされない追加ポリシーを作成できます。 ポリシーを作成した時に、すべての必要なパラメーターを設定する必要があり、設定したパラメーターを後で変更することはできませんでした。 新しいカスタム ポリシーを作成すると、Skype 消費者アクセスなどの機能やパブリック クラウド オーディオ/ビデオを無効にするポリシーなどを管理できます。これは、定義済みの設定でサポートされていなかったものです。 カスタム外部アクセス ポリシーは、クライアントやモビリティ、会議のポリシーと同じ構文に従います。 これらの設定に関する詳細は、 [ここ](/previous-versions//mt228132(v=technet.10))からご覧いただけます。
  
カスタム外部アクセス ポリシーを機能させるには、ユーザーは、そのポリシーに対応している 2016 クイック実行 Skype for Business アプリケーションのサポートされているバージョンを使用していなければなりません。 Skype for Business 2016 クイック実行クライアントの次の最小バージョンが必要です。
  
|**Type**|**リリース日**|**バージョン**|**ビルド**|
|:-----|:-----|:-----|:-----|
|最新機能提供チャネルの最初のリリース  <br/> |2016 年 11 月 17 日  <br/> |16.0.7571.2006  <br/> |バージョン 1611 (ビルド 7571.2006)  <br/> |
|最新機能提供チャネル  <br/> |2016 年 12 月 6 日  <br/> |16.0.7571.2072  <br/> |バージョン 1611 (ビルド 7571.2072)  <br/> |
|段階的提供チャネル  <br/> |2017 年 2 月 22 日  <br/> |16.0.7369.2118  <br/> |バージョン 1609 (ビルド 7369.2118)  <br/> |
   
> [!CAUTION]
> Skype for Business Windows アプリケーションまたは Mac クライアントの以前のバージョンを使用しているユーザーは、ファイルを転送することがあります。 
  
## <a name="start-windows-powershell"></a>スタートWindows PowerShell

> [!NOTE]
> Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。 最新の Teams PowerShell パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。
1. Teams [PowerShell モジュールをインストールします](/microsoftteams/teams-powershell-install)。
    
2. コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。 
 ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   Windows PowerShell の起動の詳細については、「1 つの Windows PowerShell ウィンドウで[すべての Microsoft 365 または Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)サービスに接続する」[](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)または「Windows PowerShell 用にコンピューターをセットアップする」を参照してください。
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a>ユーザー独自の外部アクセス ポリシーを作成します。

これを行う場合は、次を実行します。
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

- Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。 Windows PowerShell を使用すると、単一の管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Microsoft 365 または Office 365 PowerShell を使用する必要がある理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShellは、多くのユーザーに対して同時に設定変更を行う場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性の点で多くの利点があります。 次のトピックでこれらの利点について説明します。
    
  - [Microsoft 365 または Office 365 を他のユーザーとWindows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>関連項目
[ポイント間ファイル転送をブロックする](block-point-to-point-file-transfers.md)

[組織のクライアント ポリシーをセットアップする](set-up-client-policies-for-your-organization.md)

[組織で会議ポリシーを設定する](set-up-conferencing-policies-for-your-organization.md)

  
