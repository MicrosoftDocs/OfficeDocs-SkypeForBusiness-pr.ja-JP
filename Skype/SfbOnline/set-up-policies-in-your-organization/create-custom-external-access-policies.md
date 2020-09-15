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
ms.openlocfilehash: 9ec8fbe2e2d1a0d0882a0115bb201021fbbc1a35
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814196"
---
# <a name="create-custom-external-access-policies"></a>カスタム外部アクセス ポリシーを作成する

Skype for Business Online を使用すると、その他の外部アクセス ポリシーを作成できます。 複数な組み合わせを作成できるクライアントポリシーや会議ポリシーとは異なり、シナリオのほとんどをカバーできる 3 つの定義済み外部アクセス ポリシーがあります。 これらは：
  
- フェデレーション アクセスまたは Skype 消費者アクセスなし (_タグ: NoFederationAndPIC_ )
    
- フェデレーション アクセスのみ (_タグ: FederationOnly_ )
    
- フェデレーション アクセスと消費者アクセス (_FederationAndPICDefault_)
    
カスタム外部ポリシーを使用すると、上記の設定でカバーされない追加ポリシーを作成できます。 ポリシーを作成した時に、すべての必要なパラメーターを設定する必要があり、設定したパラメーターを後で変更することはできませんでした。 新しいカスタム ポリシーを作成すると、Skype 消費者アクセスなどの機能やパブリック クラウド オーディオ/ビデオを無効にするポリシーなどを管理できます。これは、定義済みの設定でサポートされていなかったものです。 カスタム外部アクセス ポリシーは、クライアントやモビリティ、会議のポリシーと同じ構文に従います。 これらの設定に関する詳細は、 [ここ](https://technet.microsoft.com/library/mt228132.aspx)からご覧いただけます。
  
カスタム外部アクセス ポリシーを機能させるには、ユーザーは、そのポリシーに対応している 2016 クイック実行 Skype for Business アプリケーションのサポートされているバージョンを使用していなければなりません。 Skype for Business 2016 クイック実行クライアントの次の最小バージョンが必要です。
  
|**種類**|**リリース日**|**バージョン**|**ビルド**|
|:-----|:-----|:-----|:-----|
|最新機能提供チャネルの最初のリリース  <br/> |2016 年 11 月 17 日  <br/> |16.0.7571.2006  <br/> |バージョン 1611 (ビルド 7571.2006)  <br/> |
|最新機能提供チャネル  <br/> |2016 年 12 月 6 日  <br/> |16.0.7571.2072  <br/> |バージョン 1611 (ビルド 7571.2072)  <br/> |
|段階的提供チャネル  <br/> |2017 年 2 月 22 日  <br/> |16.0.7369.2118  <br/> |バージョン 1609 (ビルド 7369.2118)  <br/> |
   
> [!CAUTION]
> Skype for Business Windows アプリケーションまたは Mac クライアントの以前のバージョンを使用しているユーザーは、ファイルを転送することがあります。 
  
## <a name="verify-and-start-windows-powershell"></a>Windows PowerShell を検証および開始する

- **Windows PowerShell バージョン 3.0 以降を実行していることを確認する**
    
1. 3.0 以降のバージョンが実行されていることを確認する場合: **[スタート] メニュー** > **[Windows PowerShell]**。
    
2. [ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。
    
3. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。 Windows PowerShell をバージョン4.0 にダウンロードして更新するには、「 [Windows Management Framework 4.0](https://www.microsoft.com/download/details.aspx?id=40855) 」を参照してください。 メッセージが表示されたら、コンピューターを再起動します。
    
4. また、Skype for Business Online に接続するリモート Windows PowerShell セッションを作成できるようにする、Teams 用の Windows PowerShell モジュールをインストールする必要があります。
    
    詳細については、「 [単一の Windows PowerShell ウィンドウですべての Microsoft 365 または Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」を参照してください。
    
- **Windows PowerShell セッションを開始する**
    
1. From the **Start Menu** > **Windows PowerShell**.
    
2. **Windows PowerShell**ウィンドウで、次を実行して Microsoft 365 または Office 365 に接続します。
    
  > [!NOTE]
  > Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。
  >
  > 最新の [Teams PowerShell パブリックリリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)を使用している場合は、Skype For Business Online Connector をインストールする必要はありません。

   ```PowerShell      
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   Windows PowerShell の起動の詳細については、「 [1 つの Windows powershell ウィンドウですべての Microsoft 365 または Office 365 サービスに接続](https://technet.microsoft.com/library/dn568015.aspx) する」または「 [windows powershell 用のコンピューターをセットアップ](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)する」を参照してください。
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a>ユーザー独自の外部アクセス ポリシーを作成します。

これを行う場合は、次を実行します。
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

- Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。 Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して、Microsoft 365 または Office 365 と Skype for Business Online を管理することができます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Microsoft 365 または Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、多くのユーザーについて同時に設定を変更する場合など、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を高めることができます。 次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell を使用して Microsoft 365 または Office 365 を管理するのに最適な方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>関連トピック
[ポイントツーポイントファイル転送をブロックする](block-point-to-point-file-transfers.md)

[組織のクライアント ポリシーをセットアップする](set-up-client-policies-for-your-organization.md)

[組織内の会議ポリシーをセットアップする](set-up-conferencing-policies-for-your-organization.md)

  
 
