---
title: "ブロックのポイントツー ポイント ファイル転送"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
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
description: "Skype for Business Online で、既存の会議のポリシー設定の一部としてポイントツー ポイント (P2P) ファイルの転送を制御する機能があります。ただし、これにより、またはブロック ファイルまたは別の組織のフェデレーションされたユーザーに同じ組織内であるユーザーにファイルを転送がかどうかをユーザーに転送します。次の手順では、次のフェデレーションの組織やパートナーと P2P ファイル転送をブロックすることができます。"
ms.openlocfilehash: 288bec32d55d9784690d84b8daa205dd33568847
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="block-point-to-point-file-transfers"></a>ブロックのポイントツー ポイント ファイル転送

Skype for Business Online で、既存の会議のポリシー設定の一部としてポイントツー ポイント (P2P) ファイルの転送を制御する機能があります。ただし、これにより、またはブロック ファイルまたは別の組織のフェデレーションされたユーザーに同じ組織内であるユーザーにファイルを転送がかどうかをユーザーに転送します。次の手順では、次のフェデレーションの組織やパートナーと P2P ファイル転送をブロックすることができます。
  
 一般的なシナリオは、内部ユーザーが使用 P2P ファイル転送がフェデレーション パートナーとファイル転送のブロックを入力できるようにする場合です。このシナリオでは、操作する必要があります。
  
- 組織のユーザーには、P2P ファイル転送が有効になっている (_EnableP2PFileTransfer_を_True_に設定) を会議ポリシーを設定します。
    
- 外部 P2P ファイル転送 (を_False_に設定されている_EnableP2PFileTransfer_ ) をブロックして、組織内のユーザーに割り当てるに設定グローバルに外部ユーザーの通信ポリシーを作成します。 
    
これらの設定の詳細を確認したことが[次のとおり](https://technet.microsoft.com/en-us/library/mt228132.aspx)です。
  
組織外のフェデレーションされたユーザーは、ポリシーが適用されたユーザーにファイルを送信しようとすると、それら**移行に失敗しました。**エラーが表示されます。**ファイル転送がオフになっている**エラーが表示されますが、ユーザーがファイルを送信しようとすると場合、。
  
この作業をするためには、ユーザーする必要がありますに使用する 2016年クイック実行 Skype のサポートされているバージョンでサポートされているビジネス アプリ。次最小のバージョンの Skype for Business の 2016年クイック実行をクライアントが必要です。
  
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
    
3. バージョン 3.0 以降をお持ちでない場合は、ダウンロードして、Windows PowerShell への更新プログラムをインストールする必要があります。[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)をダウンロードして 4.0 への Windows PowerShell を更新するを参照してください。表示されたら、お使いのコンピューターを再起動します。
    
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
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>組織の P2P ファイル転送を無効にします。

組織のグローバル ポリシーでは既定では、 _EnableP2PFileTransfer_が有効にします。作成したときに、ユーザーは_BposSAllModality_ポリシーに割り当てられたします。
  
組織がブロック外部ファイルの転送に別の組織内の P2P 転送ができるように、だけグローバル レベルで変更する必要があります。そのため、次のコマンドを実行します。
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>ユーザーの P2P ファイル転送を無効にします。

ユーザーに新しいポリシーを作成して、そのユーザーに許可して適用することができます。そのため、次のコマンドを実行します。 
> 
  ```
  New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
  ```
> 
  ```
  Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
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
[ユーザー設定の外部アクセス ポリシーを作成します。](create-custom-external-access-policies.md)

[組織のクライアントのポリシーを設定します。](set-up-client-policies-for-your-organization.md)

[組織内の会議のポリシーを設定します。](set-up-conferencing-policies-for-your-organization.md)

