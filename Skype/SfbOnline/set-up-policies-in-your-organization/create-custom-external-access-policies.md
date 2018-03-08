---
title: "ユーザー設定の外部アクセス ポリシーを作成します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "Skype for Business Online では、その他の外部アクセス ポリシーを作成することができます。ある複数の組み合わせ、クライアントまたは会議のポリシーとは異なり、ほとんどのシナリオを扱うことができる次の 3 つの定義済みの外部アクセス ポリシーがあります。"
ms.openlocfilehash: 7a5e347f3f9629f603544ad9ab06e11d4b649868
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="create-custom-external-access-policies"></a>ユーザー設定の外部アクセス ポリシーを作成します。

Skype for Business Online では、その他の外部アクセス ポリシーを作成することができます。ある複数の組み合わせ、クライアントまたは会議のポリシーとは異なり、ほとんどのシナリオを扱うことができる次の 3 つの定義済みの外部アクセス ポリシーがあります。これらは：
  
- フェデレーションなしまたは Skype のコンシューマー アクセス (_タグ: NoFederationAndPIC_ )
    
- フェデレーションのアクセスのみ (_タグ: FederationOnly_ )
    
- フェデレーションし、コンシューマー (_FederationAndPICDefault_) にアクセス
    
外部のユーザー設定のポリシーを使用するポリシーいないが重なって見えなく上記の設定を作成します。ポリシーを作成すると、必要なすべてのパラメーターを設定する必要があり、後で変更できませんでした。新しいカスタム ポリシーを作成する、Skype のコンシューマー アクセスなどのコントロールの機能を使用するや公開を無効にするポリシーをクラウド音声/ビデオ] のされませんでした定義済みの設定が重なって見えなくなっているものがあります。ユーザー設定の外部アクセス ポリシーでは、クライアント、移動、および会議ポリシー同様の構文に従います。これらの設定の詳細を確認したことが[次のとおり](https://technet.microsoft.com/en-us/library/mt228132.aspx)です。
  
この作業を行うには、ユーザーする必要があります使用サポートされているバージョンの 2016年のクイック実行の Skype for Business アプリをサポートしています。次最小のバージョンの Skype for Business の 2016年クイック実行をクライアントが必要です。
  
|**種類**|**リリース日**|**バージョン**|**作成します。**|
|:-----|:-----|:-----|:-----|
|現在のチャネルの最初のリリース  <br/> |2016/11/17  <br/> |16.0.7571.2006  <br/> |バージョン 1611 (ビルド 7571.2006)  <br/> |
|現在のチャネル  <br/> |2016/12/6  <br/> |16.0.7571.2072  <br/> |バージョン 1611 (ビルド 7571.2072)  <br/> |
|チャンネルの遅延  <br/> |2017/2/22  <br/> |16.0.7369.2118  <br/> |バージョン 1609 (ビルド 7369.2118)  <br/> |
   
> [!CAUTION]
> 以前のバージョンの Skype for Business の Windows アプリまたは Mac クライアントを使用しているユーザーはファイルを転送できます。 
  
## <a name="verify-and-start-windows-powershell"></a>確認し、Windows PowerShell を起動する.

- **3.0 以降のバージョンの Windows PowerShell が実行していることを確認します。**
    
1. 3.0 以降のバージョンが実行していることを確認する: **[スタート] メニュー** > **Windows PowerShell**します。
    
2. **Windows PowerShell**のウィンドウで_ホストの取得_を入力して、バージョンを確認してください。
    
3. バージョン 3.0 以降をお持ちでない場合は、ダウンロードして、Windows PowerShell への更新プログラムをインストールする必要があります。[Windows Management Framework 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855)をダウンロードして 4.0 への Windows PowerShell を更新するを参照してください。表示されたら、お使いのコンピューターを再起動します。
    
4. Skype for Business Online できるようにする Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成するのには、Windows PowerShell モジュールをインストールする必要もします。このモジュールでは、64 ビット版コンピューターにのみサポートされているが、 [Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)では、Microsoft ダウンロード センターからダウンロードできます。求められた場合は、お使いのコンピューターを再起動します。
    
    さらに詳しく調べ必要がある場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスへの接続](https://technet.microsoft.com/EN-US/library/dn568015.aspx)を参照してください。
    
- **Windows PowerShell セッションを開始します。**
    
1. **[スタート] メニュー**から > **Windows PowerShell**します。
    
2. **Windows PowerShell**ウィンドウで、実行して、Office 365 の組織に接続します。
    
    > [!NOTE]
    > Skype for Business Online の Windows PowerShell モジュールに使用する**インポート モジュール**の最初のレコード] コマンドの実行にのみがあります。

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  詳細については、Windows PowerShell を開始する場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」または「 [Skype for Business Online Windows PowerShell を使用してへ接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a>ユーザーのユーザー設定の外部アクセス ポリシーを作成します。

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

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細を知りたいとしていますか。

- Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。
    
  - [Windows PowerShell で Office 365 を管理する最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell を使用して、Skype for Business Online の管理するには](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>関連トピック
[ブロック ポイント間接ファイル転送](block-point-to-point-file-transfers.md)

[組織のクライアントのポリシーを設定します。](set-up-client-policies-for-your-organization.md)

[組織内の会議のポリシーを設定します。](set-up-conferencing-policies-for-your-organization.md)
