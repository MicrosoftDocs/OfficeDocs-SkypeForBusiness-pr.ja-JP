---
title: ポイント ツー ポイントのファイル転送を禁止する
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
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
description: Skype for Business Online では、既存の会議ポリシー設定の一部としてポイントツーポイント (P2P) ファイル転送を制御できます。 ただし、この方法では、ユーザーが同じ組織内のユーザーまたは別の組織のフェデレーションユーザーにファイルを転送しているかどうかに関係なく、ファイルの転送が許可またはブロックされます。 以下の手順に従うと、フェデレーションされた組織またはパートナーとの P2P のファイル転送をブロックできます。
ms.openlocfilehash: 7983ae72cd3b06a21fd4947883a3043d2506b92e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887966"
---
# <a name="block-point-to-point-file-transfers"></a>ポイント ツー ポイントのファイル転送を禁止する

Skype for Business Online では、既存の会議ポリシー設定の一部としてポイントツーポイント (P2P) ファイル転送を制御できます。 ただし、この方法では、ユーザーが同じ組織内のユーザーまたは別の組織のフェデレーションユーザーにファイルを転送しているかどうかに関係なく、ファイルの転送が許可またはブロックされます。 以下の手順に従うと、フェデレーションされた組織またはパートナーとの P2P のファイル転送をブロックできます。
  
 一般的なシナリオとしては、内部ユーザーが P2P ファイル転送を使用できるようにして、フェデレーションパートナーとのファイル送信をブロックすることが必要な場合があります。 このシナリオでは、次の操作を行う必要があります。
  
- P2P のファイル転送が有効になっている会議ポリシー (_EnableP2PFileTransfer_を_True_に設定) を組織のユーザーに割り当てます。
    
- 外部の P2P ファイル転送 (_EnableP2PFileTransfer_が_False_に設定されている) をブロックして組織内のユーザーに割り当てる、グローバルな外部ユーザー通信ポリシーを作成します。 
    
これらの設定に関する詳細は、 [ここ](https://technet.microsoft.com/library/mt228132.aspx)からご覧いただけます。
  
組織外のフェデレーションユーザーが、ポリシーが適用されているユーザーにファイルを送信しようとした場合、**転送失敗**エラーが発生します。 また、ユーザーがファイルを送信しようとすると、**ファイル転送が有効になっ**ていないことを示すエラーが表示されます。
  
この動作を実現するには、サポートされているバージョンの2016のクイック実行 Skype for Business アプリを使用している必要があります。 Skype for Business 2016 クイック実行クライアントの次の最小バージョンが必要です。
  
|**種類**|**リリース日**|**バージョン**|**ビルド**|
|:-----|:-----|:-----|:-----|
|最新機能提供チャネルの最初のリリース  <br/> |2016 年 11 月 17 日  <br/> |16.0.7571.2006  <br/> |バージョン 1611 (ビルド 7571.2006)  <br/> |
|最新機能提供チャネル  <br/> |2016 年 12 月 6 日  <br/> |16.0.7571.2072  <br/> |バージョン 1611 (ビルド 7571.2072)  <br/> |
|段階的提供チャネル  <br/> |2017 年 2 月 22 日  <br/> |16.0.7369.2118  <br/> |バージョン 1609 (ビルド 7369.2118)  <br/> |
   
> [!CAUTION]
> 以前のバージョンの Skype for Business Windows アプリまたは Mac クライアントを使っているユーザーは、引き続きファイルを転送することができます。 
  
## <a name="verify-and-start-windows-powershell"></a>Windows PowerShell を検証および開始する

- **Windows PowerShell バージョン 3.0 以降を実行していることを確認する**
    
    1. 3.0 以降のバージョンが実行されていることを確認する場合: **[スタート] メニュー** > **[Windows PowerShell]**。
        
    2. [ **Windows PowerShell** ] ウィンドウで、「 _Get Host_ 」と入力してバージョンを確認します。
        
    3. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。 Windows PowerShell をバージョン4.0 にダウンロードして更新するには、「 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 」を参照してください。 メッセージが表示されたら、コンピューターを再起動します。
        
    4. Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。
    
    詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」を参照してください。
    
- **Windows PowerShell セッションを開始する**
    
    1. From the **Start Menu** > **Windows PowerShell**.
        
    2. [ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。
    
        > [!NOTE]
        > Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。

       ```PowerShell      
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   Windows PowerShell の起動の詳細については、「[単一の Windows powershell ウィンドウですべての Office 365 サービスに接続](https://technet.microsoft.com/library/dn568015.aspx)する」または「 [windows powershell 用のコンピューターをセットアップ](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)する」を参照してください。
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>組織の P2P ファイル転送を無効にする

既定では、組織のグローバルポリシーで_EnableP2PFileTransfer_が有効になっています。 作成されたユーザーには、 _Bpossallmodality_ポリシーが割り当てられています。
  
組織内の P2P 転送を許可するが、外部ファイル転送を別の組織にブロックするには、それをグローバルレベルで変更する必要があります。 そのためには、次を実行します。
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>ユーザーに対して P2P ファイル転送を無効にする

新しいポリシーを作成し、そのポリシーをそのユーザーに付与することで、ユーザーに適用することができます。 そのためには、次を実行します。 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

- Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。 Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、多くのユーザーについて同時に設定を変更する場合など、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を高めることができます。 次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>関連トピック
[カスタム外部アクセス ポリシーを作成する](create-custom-external-access-policies.md)

[組織のクライアント ポリシーをセットアップする](set-up-client-policies-for-your-organization.md)

[組織内の会議ポリシーをセットアップする](set-up-conferencing-policies-for-your-organization.md)

  
 
