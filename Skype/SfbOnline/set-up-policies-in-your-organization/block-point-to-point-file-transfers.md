---
title: ポイント ツー ポイントのファイル転送を禁止する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
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
- Setup
description: ビジネス オンラインの Skype は、既存の会議ポリシー設定の一部として、ポイント ツー ポイント (P2P) ファイルの転送を制御する機能があります。 ただし、これにより、またはファイルかどうかは、ファイルを転送するユーザーは、同じ組織内に、または別の組織からのフェデレーション ユーザーにユーザーの転送をブロックします。 次の手順では、次のまたはパートナーのフェデレーション組織との P2P のファイル転送をブロックできます。
ms.openlocfilehash: 6ca79b45c4e068ae6999db24cf6a0dd54e9e3aa6
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372105"
---
# <a name="block-point-to-point-file-transfers"></a>ポイント ツー ポイントのファイル転送を禁止する

ビジネス オンラインの Skype は、既存の会議ポリシー設定の一部として、ポイント ツー ポイント (P2P) ファイルの転送を制御する機能があります。 ただし、これにより、またはファイルかどうかは、ファイルを転送するユーザーは、同じ組織内に、または別の組織からのフェデレーション ユーザーにユーザーの転送をブロックします。 次の手順では、次のまたはパートナーのフェデレーション組織との P2P のファイル転送をブロックできます。
  
 非常に一般的なシナリオは、内部ユーザーが P2P を使用してファイル転送がフェデレーション パートナーとファイル転送をブロックできるようにする場合です。 このシナリオでは、実行する必要があります。
  
- P2P ファイル転送が有効になっている (_EnableP2PFileTransfer_を_True_に設定) で、組織内のユーザーに会議ポリシーを割り当てます。
    
- 外部の P2P ファイル転送 (_EnableP2PFileTransfer_は_False_に設定) をブロックし、組織内のユーザーに割り当てることに設定した外部ユーザーのグローバル通信ポリシーを作成します。 
    
これらの設定に関する詳細は、 [ここ](https://technet.microsoft.com/en-us/library/mt228132.aspx)からご覧いただけます。
  
組織外のフェデレーション ユーザーは、ポリシーが適用されているユーザーにファイルを送信しようとすると、**転送に失敗しました**エラーが表示されます。 ユーザーがファイルを送信しようとすると場合、エラーが表示されます、**ファイルの転送がオフになっています**。
  
この作業をするためには、ユーザーする必要があります使用している 2016年クイック実行の Skype のサポートされているバージョンでサポートされているビジネス アプリケーションの。 Skype for Business 2016 クイック実行クライアントの次の最小バージョンが必要です。
  
|**種類**|**リリース日**|**Version**|**ビルド**|
|:-----|:-----|:-----|:-----|
|最新機能提供チャネルの最初のリリース  <br/> |2016 年 11 月 17 日  <br/> |16.0.7571.2006  <br/> |バージョン 1611 (ビルド 7571.2006)  <br/> |
|最新機能提供チャネル  <br/> |2016 年 12 月 6 日  <br/> |16.0.7571.2072  <br/> |バージョン 1611 (ビルド 7571.2072)  <br/> |
|段階的提供チャネル  <br/> |2017 年 2 月 22 日  <br/> |16.0.7369.2118  <br/> |バージョン 1609 (ビルド 7369.2118)  <br/> |
   
> [!CAUTION]
> ビジネス Windows アプリケーションまたは Mac クライアントの以前のバージョンの Skype を使用しているユーザーはファイルを転送することがあります。 
  
## <a name="verify-and-start-windows-powershell"></a>Windows PowerShell を検証および開始する

- **Windows PowerShell バージョン 3.0 以降を実行していることを確認する**
    
1. 3.0 以降のバージョンが実行されていることを確認する場合: **[スタート] メニュー** > **[Windows PowerShell]**。
    
2. **Windows PowerShell**ウィンドウで_ホストの取得_を入力してバージョンを確認してください。
    
3. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。
    
4. Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。
    
    詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」を参照してください。
    
- **Windows PowerShell セッションを開始する**
    
1. [**スタート メニュー**]  >  [**Windows PowerShell**] から開きます。
    
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
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>組織の P2P のファイル転送を無効にします。

組織のグローバル ポリシーでは既定では、 _EnableP2PFileTransfer_が有効にします。 それが作成されたとき、 _BposSAllModality_ポリシーがユーザーに割り当てられました。
  
組織はブロック外部ファイルの転送に別の組織内の P2P の転送を許可するには、だけで、グローバル レベルで変更する必要があります。 次のコマンドを実行します。
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>ユーザーの P2P のファイル転送を無効にします。

ユーザーに新しいポリシーを作成して、そのユーザーに付与することによって適用することができます。 次のコマンドを実行します。 
> 
>   ```
>   New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
>   ```
> 
>   ```
>   Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also
[カスタム外部アクセス ポリシーを作成する](create-custom-external-access-policies.md)

[組織のクライアント ポリシーをセットアップする](set-up-client-policies-for-your-organization.md)

[組織内の会議ポリシーを設定します](set-up-conferencing-policies-for-your-organization.md)

  
 