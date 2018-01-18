---
title: "カスタム外部アクセス ポリシーを作成します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "ビジネス オンラインの Skype を使用すると、その他の外部アクセス ポリシーを作成できます。 複数の組み合わせを作成することが、クライアント、または会議のポリシーとは異なり、シナリオのほとんどをカバーできる 3 つの定義済みの外部アクセス ポリシーがあります。"
ms.openlocfilehash: ffb08963d82af77f4d68c679b82bc8b8c44fa75f
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="create-custom-external-access-policies"></a>カスタム外部アクセス ポリシーを作成します。

ビジネス オンラインの Skype を使用すると、その他の外部アクセス ポリシーを作成できます。 複数の組み合わせを作成することが、クライアント、または会議のポリシーとは異なり、シナリオのほとんどをカバーできる 3 つの定義済みの外部アクセス ポリシーがあります。 これらは：
  
- 連合なしまたは Skype の消費者のアクセス (_タグ: NoFederationAndPIC_ )
    
- フェデレーションのアクセスのみ (_タグ: FederationOnly_ )
    
- 連合し、消費者のアクセス (_FederationAndPICDefault_)
    
外部のカスタム ポリシーを使用すると追加を作成するポリシーを上記の設定でカバーされていません。 ポリシーの作成時に必要なすべてのパラメーターを設定する必要があり、それらを後で変更することができませんでした。 新しいカスタム ポリシーを作成する Skype の消費者のアクセスなどのコントロール機能を使用するか、公開を無効にするポリシーではクラウド オーディオ/ビデオ、定義済みの設定の対象でなかったものであります。 カスタム外部アクセス ポリシーは、クライアント、モビリティ、および会議のポリシーと同じ構文に従います。 これらの設定に関する詳細情報を調べることができます[ここ](https://technet.microsoft.com/en-us/library/mt228132.aspx)。
  
この作業をするためには、ユーザーする必要がありますでは、2016 年のサポートされているバージョンでサポートされているビジネス アプリケーションの Skype をクイック実行。 ビジネス 2016年クイック実行クライアントの Skype の次の最小バージョンが必要です。
  
|**タイプ**|**リリース日**|**バージョン**|**ビルド**|
|:-----|:-----|:-----|:-----|
|現在のチャネルの最初のリリース  <br/> |2016/11/17  <br/> |16.0.7571.2006  <br/> |バージョン 1611 (ビルド 7571.2006)  <br/> |
|現在のチャネル  <br/> |2016/12/6  <br/> |16.0.7571.2072  <br/> |バージョン 1611 (ビルド 7571.2072)  <br/> |
|チャネルの遅延  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |バージョン 1609 (ビルド 7369.2118)  <br/> |
   
> [!CAUTION]
> ビジネス Windows アプリケーションまたは Mac クライアントの以前のバージョンの Skype を使用しているユーザーはファイルを転送することがあります。 
  
## <a name="verify-and-start-windows-powershell"></a>Windows PowerShell を検証および開始する

- **Windows PowerShell バージョン 3.0 以降を実行していることを確認する**
    
1. 3.0 以降のバージョンを実行することを確認するのには: **[スタート] メニュー** > **Windows PowerShell**。
    
2. [ **Windows PowerShell**] ウィンドウに「 _Get-Host_」と入力して、バージョンを確認します。
    
3. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://www.microsoft.com/en-us/download/details.aspx?id=40855)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。
    
4. Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。
    
    詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」を参照してください。
    
- **Windows PowerShell セッションを開始する**
    
1. **[スタート] メニュー**の [ > **Windows PowerShell**。
    
2. [ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。
    
    > [!NOTE]
    > Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  Windows PowerShell を開始する方法の詳細を設定する場合は、 [1 つの Windows PowerShell のウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)か、 [Windows PowerShell を使用して、オンライン ビジネスの Skype への接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a>ユーザー独自の外部アクセス ポリシーを作成します。

これを行うには、次のコマンドを実行します。
  
> 
  ```
  New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True 
-EnableOutsideAccess $True
  ```

> 
  ```
  Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 の PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>関連トピック
[ブロック ポイント ツー ポイントのファイルの転送](block-point-to-point-file-transfers.md)

[組織のクライアントのポリシーを設定します](set-up-client-policies-for-your-organization.md)

[組織内の会議ポリシーを設定します](set-up-conferencing-policies-for-your-organization.md)
